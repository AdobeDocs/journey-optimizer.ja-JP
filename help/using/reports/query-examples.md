---
solution: Journey Optimizer
product: journey optimizer
title: クエリの例
description: クエリの例
feature: Reporting, Journeys
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 26ad12c3-0a2b-4f47-8f04-d25a6f037350
source-git-commit: 81d8d068f1337516adc76c852225fd7850a292e8
workflow-type: tm+mt
source-wordcount: '2749'
ht-degree: 94%

---

# クエリの例{#query-examples}

この節では、データレイクのジャーニーステップイベントに関するクエリを実行する際によく使用される例をいくつか示します。

クエリで使用するフィールドに、対応するスキーマに関連する値があることを確認します。

+++ID、instanceID、profileID の違いとは

* ID：すべてのステップイベントエントリに対して一意です。2 つの異なるステップイベントに同じ ID を割り当てることはできません。
* instanceID：instanceID は、ジャーニー実行内のプロファイルに関連付けられるすべてのステップイベントで同一です。プロファイルがジャーニーに再度入ると、別の instanceID が使用されます。この新しい instanceID は、再入力されたインスタンスのすべてのステップイベント（開始から終了まで）で同じになります。
* profileID：ジャーニー名前空間に対応したプロファイルの ID です。

>[!NOTE]
>
>トラブルシューティングの目的では、ジャーニーのクエリ時に journeyVersionName ではなく journeyVersionID を使用することをお勧めします。ジャーニーのプロパティ属性について詳しくは、[この節](../building-journeys/expression/journey-properties.md#journey-properties-fields)を参照してください。

+++

## 基本的なユースケース／一般的なクエリ {#common-queries}

+++特定の時間枠にジャーニーにエントリしたプロファイルの数

このクエリでは、指定された時間枠に指定されたジャーニーにエントリした個別のプロファイル数が表示されます。

_データレイクのクエリ_

```sql
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>'
AND _experience.journeyOrchestration.stepEvents.nodeType='start'
AND _experience.journeyOrchestration.stepEvents.instanceType = 'unitary'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour);
```

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

+++

+++プロファイルが特定のジャーニーにエントリしなかった原因となったルール

このクエリは、キャップルールまたは実施要件ルールにより、プロファイルがジャーニーにエントリできない場合に、却下されたルールセットとルール情報を返します。

_例_

```sql
SELECT 
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.ID AS RULESET_ID,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.name AS RULESET_NAME,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.rejectedRules.ID AS RULE_ID,
    _experience.journeyOrchestration.serviceEvents.dispatcher.rejectedRuleset.rejectedRules.name AS RULE_NAME
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard'
AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID='3855072d-79c3-438a-a5c3-c77fd6843812'
AND
    timestamp >= to_date('2025-05-16')
```

+++

+++特定のジャーニーの各ノードで一定時間に発生したエラー数

このクエリは、ジャーニーの各ノードでエラーが発生した個別のプロファイルを、ノード名ごとにグループ化してカウントします。これには、すべてのタイプのアクション実行エラーと取得エラーが含まれます。

_データレイクのクエリ_

```sql
SELECT
_experience.journeyOrchestration.stepEvents.nodeName,
count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour)
AND
  (_experience.journeyOrchestration.stepEvents.actionExecutionError is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionOriginCode is not NULL
    OR _experience.journeyOrchestration.stepEvents.actionExecutionOriginError is not NULL
    OR _experience.journeyOrchestration.stepEvents.fetchError is not NULL
    OR _experience.journeyOrchestration.stepEvents.fetchErrorCode is not NULL
  )
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName;
```

+++

+++特定の時間枠に特定のジャーニーから破棄されたイベントの数

このクエリは、ジャーニーから破棄されたイベントの合計数をカウントします。セグメントエクスポートジョブエラー、Dispatcher による破棄、状態マシンによる破棄など、様々な破棄イベントコードに対してフィルタリングします。

_データレイクのクエリ_

```sql
SELECT
count(_id) AS NUMBER_OF_EVENTS_DISCARDED
FROM journey_step_events
WHERE (
   _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'error'
   OR _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard'
   OR _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode = 'discard'
   OR _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode is not null
)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour);
```

+++

+++破棄されたプロファイルのステップイベントの表示

このクエリは、ジャーニーから破棄されたプロファイルのステップイベントの詳細を返します。 ビジネスルールや待ち時間の制約などが原因でプロファイルが破棄された理由を特定するのに役立ちます。 クエリは、特定の破棄イベントタイプに対してフィルタリングし、プロファイル ID、インスタンス ID、ジャーニー詳細、破棄の原因となったエラーなどの主要な情報を表示します。

_データレイクのクエリ_

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.profileID,
    _experience.journeyOrchestration.stepEvents.instanceID,
    _experience.journeyOrchestration.stepEvents.journeyID,
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.actionExecutionError,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    DATE(timestamp),
    timestamp
FROM journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType = '<eventType>' AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journeyVersionID>' AND
    _experience.journeyOrchestration.stepEvents.instanceID = '<instanceID>';
```

_例_

```sql
SELECT 
    _experience.journeyOrchestration.stepEvents.profileID,
    _experience.journeyOrchestration.stepEvents.instanceID,
    _experience.journeyOrchestration.stepEvents.journeyID,
    _experience.journeyOrchestration.stepEvents.journeyVersionID,
    _experience.journeyOrchestration.stepEvents.actionExecutionError,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode,
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType,
    DATE(timestamp),
    timestamp
FROM journey_step_events
WHERE
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
    _experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'quietHours' AND
    _experience.journeyOrchestration.stepEvents.journeyVersionID = '6f21a072-6235-4c39-9f6a-9d9f3f3b2c3a' AND
    _experience.journeyOrchestration.stepEvents.instanceID = 'unitary_089dc93a-1970-4875-9660-22433b18e500';
```

![&#x200B; 破棄されたプロファイルの詳細を示すクエリ結果の例 &#x200B;](assets/query-discarded-profiles.png)

クエリ結果には、プロファイル破棄の理由を特定するのに役立つ次のキーフィールドが表示されます。

* **actionExecutionError** - `businessRuleProfileDiscarded` に設定すると、ビジネスルールが原因でプロファイルが破棄されたことを示します。 「`eventType`」フィールドには、破棄の原因となった特定のビジネス・ルールに関する追加の詳細が表示されます。

* **eventType** – 破棄の原因となったビジネス・ルールのタイプを指定します。
   * `quietHours`：処理が停止している時間設定が原因で、プロファイルが破棄されました
   * `forcedDiscardDueToQuietHours`：処理の少ない時間帯に保持されたプロファイルのガードレール制限に達したので、プロファイルが強制的に破棄されました

+++

+++特定の時間枠での特定ジャーニーにおける特定プロファイルへの影響

このクエリは、指定された時間内の指定されたプロファイルとジャーニーのすべてのステップイベントとサービスイベントを時系列で返します。

_データレイクのクエリ_

```sql
SELECT
timestamp,
_experience.journeyOrchestration.stepEvents.journeyVersionID,
_experience.journeyOrchestration.stepEvents.profileID,
_experience.journeyOrchestration.stepEvents.nodeName,
_experience.journeyOrchestration.stepEvents.journeyNodeProcessed,
_experience.journeyOrchestration.serviceType,
to_json(_experience.journeyOrchestration.profile),
to_json(_experience.journeyOrchestration.serviceEvents)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID='<journeyVersionID>'
AND DATE(timestamp) > (now() - interval '<last x hours>' hour)
AND
  (
    _experience.journeyOrchestration.stepEvents.profileID='<profileID>'
    OR _experience.journeyOrchestration.profile.ID='<profileID>'
  );
ORDER BY timestamp;
```

+++

+++2 つのノード間の経過時間 

これらのクエリは、例えば、待機アクティビティに費やされる時間の見積もりに使用できます。これにより、待機アクティビティを確実に正しく設定できます。

_データレイクのクエリ_

```sql
WITH

START_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_START,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of node before wait activity>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
),

END_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_END,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of wait activity node>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
)

SELECT 

    T1.INSTANCE_ID AS INSTANCE_ID,
    T1.NODE_NAME AS START_NODE_NAME,
    T2.NODE_NAME AS END_NODE_NAME,
    DATEDIFF(millisecond,T1.TS_START,T2.TS_END) AS ELAPSED_TIME_MS
    
FROM

    START_NODE_INFO AS T1,
    END_NODE_INFO AS T2
    
WHERE

    T1.INSTANCE_ID = T2.INSTANCE_ID
```

_データレイクのクエリ_

```sql
WITH

START_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_START,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of node before wait activity>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
),

END_NODE_INFO AS (

    SELECT 
    
        timestamp AS TS_END,
        _experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        _experience.journeyOrchestration.stepEvents.instanceID AS INSTANCE_ID
        
    FROM 
    
        journey_step_events
    
    WHERE
    
        _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey version id>' AND
        _experience.journeyOrchestration.stepEvents.nodeName = '<name of wait activity node>' AND
        _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = true
        
)

SELECT 

    AVG(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS AVERAGE_ELAPSED_TIME,
    MIN(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS MIN_ELAPSED_TIME,
    MAX(DATEDIFF(millisecond,T1.TS_START,T2.TS_END)) AS MAX_ELAPSED_TIME
    
FROM

    START_NODE_INFO AS T1,
    END_NODE_INFO AS T2
    
WHERE

    T1.INSTANCE_ID = T2.INSTANCE_ID
```

+++

+++serviceEvent の詳細を確認する方法 

ジャーニーステップイベントデータセットには、すべての stepEvents と serviceEvents が含まれています。stepEvents は、ジャーニー内のプロファイルのアクティビティ（イベントやアクションなど）に関連するので、レポーティングに使用されます。serviceEvents は同じデータセットに保存され、デバッグ目的（エクスペリエンスイベント破棄の理由など）での追加情報を示します。

serviceEvent の詳細を確認するクエリの例を次に示します。

_データレイクのクエリ_

```sql
SELECT

     _experience.journeyOrchestration.profile.ID, 
     _experience.journeyOrchestration.journey.versionID, 
     to_json(_experience.journeyOrchestration.serviceEvents) 

FROM journey_step_event 

WHERE _experience.journeyOrchestration.serviceType is not null;
```

## メッセージ／アクションエラー {#message-action-errors}

+++ジャーニーで発生した各エラーのリスト

このクエリを使用すると、メッセージ／アクションの実行中にジャーニーで発生した各エラーをリストできます。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName=<'message-name'>
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

_例_

```sql
SELECT _experience.journeyOrchestration.stepEvents.actionExecutionError, count(distinct _id) FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.nodeName='Message - 100KB Email with Gateway and Kafkav2'
AND _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26'
GROUP BY _experience.journeyOrchestration.stepEvents.actionExecutionError
```

このクエリは、ジャーニーでのアクションの実行中に発生した様々なエラーとその発生回数を返します。

+++

## プロファイルベースのクエリ {#profile-based-queries}

+++プロファイルが特定のジャーニーにエントリしたかどうかの確認

このクエリは、特定のプロファイルとジャーニーの組み合わせに関連付けられたイベントをカウントすることで、特定のプロファイルがジャーニーにエントリしたかどうかを確認します。

_データレイクのクエリ_

```sql
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_例_

```sql
SELECT count(distinct _id) FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = 'ec9efdd0-8a7c-4d7a-a765-b2cad659fa4e' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

結果は 0 より大きい値になります。このクエリは、プロファイルがジャーニーにエントリした正確な回数を返します。

+++

+++プロファイルが特定のメッセージを送信されたかどうかの確認

方法 1：メッセージの名前がジャーニー内で一意でない場合（複数の場所で使用される場合）。

_データレイクのクエリ_

```sql
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='<NodeId in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_例_

```sql
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='17ae65a1-02dd-439d-b54e-b56a78520eba' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

結果は 0 より大きい値になります。このクエリは、メッセージアクションがジャーニー側で正常に実行されたかどうかのみを示します。

方法 2：メッセージの名前がジャーニー内で一意の場合。

_データレイクのクエリ_

```sql
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeName='<NodeName in the UI corresponding to the message>' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>'
```

_例_

```sql
SELECT count(distinct _id) FROM journey_step_events WHERE
_experience.journeyOrchestration.stepEvents.nodeID='Message- 100KB Email' AND
_experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.journeyVersionID = '67b14482-143e-4f83-9cf5-cfec0fca3d26' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com'
```

このクエリは、すべてのメッセージのリストと、選択したプロファイルに対してそれらのメッセージが呼び出された回数を返します。

+++

+++過去 30 日間にプロファイルが受け取ったすべてのメッセージの検索

このクエリは、過去 30 日以内に特定のプロファイルに対して正常に実行されたすべてのメッセージアクションを、メッセージ名ごとにグループ化して取得します。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

_例_

```sql
SELECT _experience.journeyOrchestration.stepEvents.nodeName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
_experience.journeyOrchestration.stepEvents.nodeType = 'action' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName
```

このクエリは、すべてのメッセージのリストと、選択したプロファイルに対してそれらのメッセージが呼び出された回数を返します。

+++

+++過去 30 日間にプロファイルがエントリしたすべてのジャーニーの検索

このクエリは、特定のプロファイルが過去 30 日以内ににエントリしたすべてのジャーニーと、各ジャーニーのエントリ数を返します。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = '<profileID corresponding to the namespace used>' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

_例_

```sql
SELECT _experience.journeyOrchestration.stepEvents.journeyVersionName, count(distinct _id) FROM journey_step_events
WHERE  _experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
_experience.journeyOrchestration.stepEvents.profileID = 'saurgarg@adobe.com' AND
timestamp > (now() - interval '30' day)
GROUP BY _experience.journeyOrchestration.stepEvents.journeyVersionName
```

このクエリは、すべてのジャーニー名のリストと、クエリされたプロファイルがジャーニーにエントリした回数を返します。

+++

+++1 日あたりのジャーニーの対象となったプロファイルの数

このクエリは、指定された期間にジャーニーにエントリした個別のプロファイルの数の日別の分類を提供します。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_例_

```sql
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.profileID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
AND _experience.journeyOrchestration.stepEvents.journeyVersionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1'
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

このクエリは、指定した期間に 1 日ごとにジャーニーにエントリしたプロファイルの数を返します。プロファイルが別の ID を使用してエントリした場合は、2 回カウントされます。再エントリを有効にすると、別の日にジャーニーに再エントリした場合、プロファイル数が複数日にわたって重複する場合があります。

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。


+++

## 「オーディエンスを読み取り」に関連するクエリ {#read-segment-queries}

+++オーディエンスの書き出しジョブの終了に要した時間

このクエリは、ジョブがキューに追加されたタイミングとジョブが完了したタイミングの間の時間差を検出して、オーディエンスエクスポートジョブの期間を計算します。

_データレイクのクエリ_

```sql
select DATEDIFF (minute,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'queued') ,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'finished')) AS export_job_runtime;
```

_例_

```sql
select DATEDIFF (minute,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'queued') ,
              (select timestamp
                where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.status = 'finished')) AS export_job_runtime;
```

クエリは、オーディエンスエクスポートジョブがキューに追加された時刻と最終的に終了した時刻との時間差を分単位で返します。

+++

+++重複が原因でジャーニーによって破棄されたプロファイルの数

このクエリは、オーディエンスを読み取りアクティビティ中にインスタンス重複エラーにより破棄された個別のプロファイルの数をカウントします。

_データレイクのクエリ_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_DUPLICATION'
```

_例_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_DUPLICATION'
```

クエリは、重複していたことが原因でジャーニーによって破棄された、すべてのプロファイル ID を返します。

+++

+++無効な名前空間が原因でジャーニーによって破棄されたプロファイルの数

このクエリは、無効な名前空間があったか、必要な名前空間の ID が欠落していたという理由により破棄されたプロファイルの数を返します。

_データレイクのクエリ_

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_BAD_NAMESPACE'
```

_例_

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_BAD_NAMESPACE'
```

クエリは、プロファイル ID に無効な名前空間が存在する、もしくはその名前空間の ID がないという理由でジャーニーによって破棄された、すべてのプロファイル ID を返します。

+++

+++ID マップがないという理由でジャーニーによって破棄されたプロファイルの数

このクエリは、ジャーニーの実行に必要な ID マップが欠落していたという理由により破棄されたプロファイルをカウントします。

_データレイクのクエリ_

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NO_IDENTITY_MAP'
```

_例_

```sql
SELECT count(*) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NO_IDENTITY_MAP'
```

クエリは、ID マップが見つからないという理由でジャーニーによって破棄された、すべてのプロファイル ID を返します。

+++

+++ジャーニーがテストノードにあり、プロファイルがテストプロファイルでなかったという理由で、ジャーニーによって破棄されたプロファイルの数

このクエリは、ジャーニーがテストモードで実行されていたが、プロファイルの testProfile 属性が true に設定されていなかったという理由により破棄されたプロファイルを特定します。

_データレイクのクエリ_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NOT_A_TEST_PROFILE'
```

_例_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_NOT_A_TEST_PROFILE'
```

クエリは、テストモードで書き出しジョブが実行されたが、プロファイルの testProfile 属性が true に設定されていなかったという理由により、ジャーニーによって破棄されたすべてのプロファイル ID を返します。

+++

+++内部エラーが理由でジャーニーによって破棄されたプロファイルの数

このクエリは、ジャーニーの実行中に内部システムエラーにより破棄されたプロファイルの数を返します。

_データレイクのクエリ_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_INTERNAL'
```

_例_

```sql
SELECT count(distinct _experience.journeyOrchestration.profile.ID) FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '180ad071-d42d-42bb-8724-2a6ff0a109f1' AND
_experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode = 'ERROR_INSTANCE_INTERNAL'
```

クエリは、一部の内部エラーが理由でジャーニーによって破棄されたすべてのプロファイル ID を返します。

+++

+++特定のジャーニーバージョンでの「オーディエンスを読み取り」の概要

このクエリは、オーディエンスエクスポートプロセスのすべてのステージに対するセグメントエクスポートジョブの詳細、イベントコード、ステータス、プロファイル数など、オーディエンスを読み取りアクティビティの包括的な概要を提供します。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator'
```

指定されたジャーニーバージョンに関連するすべてのサービスイベントを返します。次の一連の操作に従うこともできます。

* トピック作成
* エクスポートジョブの作成
* エクスポートジョブの終了（エクスポートされたプロファイルの指標を含む）
* セカンダリ処理の終了

また、次のような問題も検出できます。

* トピックまたはエクスポートジョブ作成時のエラー（オーディエンスのエクスポート API 呼び出しのタイムアウトを含む）
* 停止する可能性があるエクスポートジョブ（特定のジャーニーバージョンで、エクスポートジョブの終了に関するイベントがない場合）
* セカンダリの問題（エクスポートジョブ終了イベントを受け取ったが、セカンダリ処理終了イベントを受け取っていない場合）

重要事項：このクエリでイベントが返されない場合、次のいずれかの理由が原因である可能性があります。

* ジャーニーのバージョンがスケジュールに到達していない
* ジャーニーバージョンでオーケストレーターを呼び出して書き出しジョブをトリガーすると想定されている場合、アップストリームフローで問題（ジャーニーのデプロイメントの問題、ビジネスイベントの問題、スケジューラーに関する問題）が発生します。

+++


+++特定のジャーニーバージョンでの「オーディエンスを読み取り」エラーの取得

このクエリは、トピック作成エラー、API 呼び出しエラー、タイムアウト、失敗したエクスポートジョブなど、オーディエンスを読み取りエラーにに関連する特定のエラーイベントコードをフィルタリングします。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
        'ERROR_TOPIC_CREATION',
        'ERROR_EXPORTJOB_APICALL',
        'ERROR_EXPORTJOB_APICALL_TIMEOUT',
        'ERROR_EXPORTJOB_FAILED'
    )
```

+++

+++エクスポートジョブの処理ステータスを取得

このクエリは、オーディエンスエクスポートジョブの処理ステータスを取得し、プロファイルエクスポート指標と共にジョブが成功したか失敗したかを示します。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode           AS EVENT_CODE,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportSegmentID     AS SEGMENT_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID                  AS EXPORTJOB_ID,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.status              AS EXPORTJOB_STATUS,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal    AS TOTAL_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized AS SUCCESS_EXPORTED_PROFILES_COUNT,
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed   AS FAILED_EXPORTED_PROFILES_COUNT 
FROM
    journey_step_events
WHERE
    _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
    _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
        'INFO_EXPORTJOB_SUCCEEDED',
        'ERROR_EXPORTJOB_FAILED'
    )
```

レコードが返されない場合は、次のいずれかを意味します。

* トピックまたはエクスポートジョブの作成中にエラーが発生しました
* エクスポートジョブがまだ実行中です

+++

+++エクスポートされたプロファイルに関する指標の取得（各エクスポートジョブの破棄およびエクスポートしジョブ指標を含む）

このクエリは、破棄されたプロファイル数と書き出しジョブ指標を組み合わせて、個々のエクスポートジョブのオーディエンス書き出しパフォーマンスの完全なビューを提供します。

_データレイクのクエリ_

```sql
WITH
  
DISCARDED_EXPORTED_PROFILES AS (
  
    SELECT
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID AS EXPORTJOB_ID,
        count(distinct _experience.journeyOrchestration.profile.ID) AS DISCARDED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'ERROR_INSTANCE_DUPLICATION',
            'ERROR_INSTANCE_BAD_NAMESPACE',
            'ERROR_INSTANCE_NO_IDENTITY_MAP',
            'ERROR_INSTANCE_NOT_A_TEST_PROFILE',
            'ERROR_INSTANCE_INTERNAL'
        )
    GROUP BY
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID
 
),
  
SEGMENT_EXPORT_METRICS AS (
  
    SELECT
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID AS EXPORTJOB_ID,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal) AS TOTAL_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized) AS SUCCESS_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed) AS FAILED_EXPORTED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'INFO_EXPORTJOB_SUCCEEDED',
            'ERROR_EXPORTJOB_FAILED'
        )
    GROUP BY
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.ID
  
)
  
SELECT
    sum(T2.TOTAL_EXPORTED_PROFILES_COUNT),
    sum(T2.SUCCESS_EXPORTED_PROFILES_COUNT),
    sum(T2.FAILED_EXPORTED_PROFILES_COUNT),
    sum(T1.DISCARDED_PROFILES_COUNT)
FROM
    DISCARDED_EXPORTED_PROFILES AS T1,
    SEGMENT_EXPORT_METRICS AS T2
WHERE T1.EXPORTJOB_ID = T2.EXPORTJOB_ID
```

+++

+++すべてのエクスポートジョブに関する集計指標の取得（オーディエンスの書き出しジョブと破棄）

このクエリは、特定のジャーニーバージョンのすべての書き出しジョブをまたいだ全体的な指標を集計します。これは、繰り返しジャーニーや、トピックの再利用を含むビジネスイベントによってトリガーされるジャーニーに役立ちます。

_データレイクのクエリ_

```sql
WITH
  
DISCARDED_EXPORTED_PROFILES AS (
  
    SELECT
        _experience.journeyOrchestration.journey.versionID AS JOURNEYVERSION_ID,
        count(distinct _experience.journeyOrchestration.profile.ID) AS DISCARDED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'ERROR_INSTANCE_DUPLICATION',
            'ERROR_INSTANCE_BAD_NAMESPACE',
            'ERROR_INSTANCE_NO_IDENTITY_MAP',
            'ERROR_INSTANCE_NOT_A_TEST_PROFILE',
            'ERROR_INSTANCE_INTERNAL'
        )
    GROUP BY
        _experience.journeyOrchestration.journey.versionID
),
  
SEGMENT_EXPORT_METRICS AS (
  
    SELECT
        _experience.journeyOrchestration.journey.versionID AS JOURNEYVERSION_ID,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountTotal) AS TOTAL_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountRealized) AS SUCCESS_EXPORTED_PROFILES_COUNT,
        sum(_experience.journeyOrchestration.serviceEvents.segmentExportJob.exportCountFailed) AS FAILED_EXPORTED_PROFILES_COUNT
    FROM
        journey_step_events
    WHERE
        _experience.journeyOrchestration.journey.versionID = '<journey-version-id>' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventType = 'segmenttrigger-orchestrator' AND
        _experience.journeyOrchestration.serviceEvents.segmentExportJob.eventCode IN (
            'INFO_EXPORTJOB_SUCCEEDED',
            'ERROR_EXPORTJOB_FAILED'
        )
    GROUP BY
          _experience.journeyOrchestration.journey.versionID
 
)
  
SELECT
    sum(T2.TOTAL_EXPORTED_PROFILES_COUNT),
    sum(T2.SUCCESS_EXPORTED_PROFILES_COUNT),
    sum(T2.FAILED_EXPORTED_PROFILES_COUNT),
    sum(T1.DISCARDED_PROFILES_COUNT)
FROM
    DISCARDED_EXPORTED_PROFILES AS T1,
    SEGMENT_EXPORT_METRICS AS T2
WHERE T1.JOURNEYVERSION_ID = T2.JOURNEYVERSION_ID
```

このクエリは前のクエリとは異なります。

実行可能なジョブに関係なく（繰り返しジャーニーの場合、トピックの再利用をトリガーしたビジネスイベントなど）、特定のジャーニーバージョンの全体的な指標を返します。

+++

## オーディエンスの選定に関連するクエリ {#segment-qualification-queries}

+++設定されたオーディエンスとは異なるオーディエンス適合が原因で破棄されたプロファイル

このクエリは、オーディエンス適合ステータスがジャーニーのオーディエンスの選定の設定と一致しなかった理由により破棄されたプロファイルを特定します（例: 「エントリ」に設定されているが、プロファイルは「退出済み」）。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID
FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = '<journey-version id>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SEGMENT_REALISATION_CONDITION_MISMATCH'
```

_例_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID
FROM journey_step_events
where
_experience.journeyOrchestration.journey.versionID = 'a868f3c9-4888-46ac-a274-94cdf1c4159d' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SEGMENT_REALISATION_CONDITION_MISMATCH'
```

このクエリは、間違ったオーディエンス適合が原因でジャーニーバージョンによって破棄されたすべてのプロファイル ID を返します。

+++

+++特定のプロファイルについて他の理由で破棄されたオーディエンスの選定イベント

このクエリは、内部サービスエラーにより、特定のプロファイルに対して破棄されたすべてのオーディエンスの選定イベントまたは外部イベントを取得します。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID, _experience.journeyOrchestration.serviceEvents.dispatcher.projectionID
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID = '<profile-id>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

_例_

```sql
SELECT DATE(timestamp),  _experience.journeyOrchestration.profile.ID, _experience.journeyOrchestration.serviceEvents.dispatcher.projectionID
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID = 'mandee@adobe.com' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

このクエリは、あるプロファイルについてその他の理由で破棄されたすべてのイベント（外部イベント／オーディエンスの選定イベント）を返します。

+++

## イベントベースのクエリ {#event-based-queries}

+++ジャーニーがビジネスイベントを受け取ったかどうかを確認する

このクエリは、指定された時間枠内に、日付別にグループ化されたビジネスイベントがジャーニーで受信された回数をカウントします。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp), count(distinct _id)
FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-version-id>' AND
_experience.journeyOrchestration.stepEvents.nodeName = '<node-name-corresponding-to-business-event>' AND
_experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
WHERE DATE(timestamp) > (now() - interval '<last x hours>' hour)
```

_例_

```sql
SELECT DATE(timestamp), count(distinct _id)
FROM journey_step_events
where
_experience.journeyOrchestration.stepEvents.journeyVersionID = 'b1093bd4-11f3-44cc-961e-33925cc58e18' AND
_experience.journeyOrchestration.stepEvents.nodeName = 'TEST_MLTrainingSession' AND
_experience.journeyOrchestration.stepEvents.nodeType = 'start' AND
WHERE DATE(timestamp) > (now() - interval '6' hour)
```

+++

+++関連するジャーニーが見つからなかったことが理由でプロファイルの外部イベントが破棄されたかどうかの確認

このクエリは、特定のプロファイルの外部イベントを受信するように設定されたアクティブなジャーニーまたは一致するジャーニーがなかったという理由により、そのイベントが破棄されたタイミングを特定します。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp) FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID = '<eventId>' AND
_experience.journeyOrchestration.profile.ID = '<profileId>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'EVENT_WITH_NO_JOURNEY'
```

_例_

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp) FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID = '515bff852185e434ca5c83bcfc4f24626b1545ca615659fc4cfff91626ce61a6' AND
_experience.journeyOrchestration.profile.ID = 'mandee@adobe.com' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'EVENT_WITH_NO_JOURNEY'
```

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

+++

+++その他の理由でプロファイルの外部イベントが破棄されたかどうかの確認

このクエリは、イベント ID とエラーコードと共に、内部サービスエラーにより、特定のプロファイルに対して破棄された外部イベントを取得します。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp), _experience.journeyOrchestration.serviceEvents.dispatcher.eventID, _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID='<profileID>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID='<eventID>' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

_例_

```sql
SELECT _experience.journeyOrchestration.profile.ID, DATE(timestamp), _experience.journeyOrchestration.serviceEvents.dispatcher.eventID, _experience.journeyOrchestration.serviceEvents.dispatcher.eventCode
FROM journey_step_events
where
_experience.journeyOrchestration.profile.ID='mandee@adobe.com' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventID='81c51be978d8bdf9ef497076b3e12b14533615522ecea9f5080a81c736491656' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventCode = 'discard' AND
_experience.journeyOrchestration.serviceEvents.dispatcher.eventType = 'ERROR_SERVICE_INTERNAL';
```

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

+++

+++errorCode で stateMachine によって破棄されたすべてのイベント数の確認

このクエリは、ジャーニーの状態マシンにより破棄されたすべてのイベントをエラーコード別に集計し、破棄の最も一般的な理由を特定するのに役立ちます。

_データレイクのクエリ_

```sql
SELECT _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode, COUNT() FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' GROUP BY _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode
```

_例_

```sql
SELECT _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode, COUNT() FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' GROUP BY _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode
```

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

+++

+++再エントリが許可されなかったことが理由で破棄されたすべてのイベントの確認

このクエリは、ジャーニー設定で再エントリが許可されていない際に、プロファイルがジャーニーに再エントリしようとしたという理由により破棄されたすべてのイベントを特定します。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp), _experience.journeyOrchestration.profile.ID,
_experience.journeyOrchestration.journey.versionID,
_experience.journeyOrchestration.serviceEvents.stateMachine.eventCode 
FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' AND _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode='reentranceNotAllowed'
```

_例_

```sql
SELECT DATE(timestamp), _experience.journeyOrchestration.profile.ID,
_experience.journeyOrchestration.journey.versionID,
_experience.journeyOrchestration.serviceEvents.stateMachine.eventCode 
FROM journey_step_events
where
_experience.journeyOrchestration.serviceEvents.stateMachine.eventType = 'discard' AND _experience.journeyOrchestration.serviceEvents.stateMachine.eventCode='reentranceNotAllowed'
```

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

+++

## 一般的なジャーニーベースのクエリ {#journey-based-queries}

+++日別のアクティブなジャーニーの数

このクエリは、アクティビティがあった一意のジャーニーバージョンの日別の数を返すので、ジャーニー実行パターンの推移を理解するのに役立ちます。

_データレイクのクエリ_

```sql
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '<last x days>' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

_例_

```sql
SELECT DATE(timestamp), count(distinct _experience.journeyOrchestration.stepEvents.journeyVersionID) FROM journey_step_events
WHERE DATE(timestamp) > (now() - interval '100' day)
GROUP BY DATE(timestamp)
ORDER BY DATE(timestamp) desc
```

このクエリは、指定した期間に 1 日にトリガーされた一意のジャーニーの数を返します。1 つのジャーニーが複数日でトリガーされる場合は、1 日につき 1 回とカウントされます。


+++

## ジャーニーインスタンスに対するクエリ {#journey-instances-queries}

+++特定の時間に特定の状態となっているプロファイルの数

このクエリは、共通テーブル式（CTE）を使用して、ノードを通過したがまだ次のノードに進んでいないプロファイルを見つけることで、ジャーニーの特定のノードで現在待機しているプロファイルを特定します。

_データレイクのクエリ_

```sql
WITH
 
INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS (
 
    SELECT
        STEP_EVENTS.timestamp AS TS,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID AS ID
    FROM
        journey_step_events AS STEP_EVENTS
    WHERE
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>'
 
),
 
INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS (
 
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME = '<specific node name>' AND
        <filter on time for profile in specific node>
 
),
 
INSTANCES_PASSED_IN_NEXT_NODES AS (
     
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME in (<list of next node names from the specific node>)
 
),
 
INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS (
 
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1
 
    EXCEPT
     
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NEXT_NODES AS T1
 
)
 
SELECT
    DATE_FORMAT(T1.TS,'<date pattern>') AS DATETIME,
    count(T1.ID) AS INSTANCES_COUNT
FROM
    INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1,
    INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS T2
WHERE
    T1.ID = T2.ID
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

_例_

```sql
WITH
 
INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS (
 
    SELECT
        STEP_EVENTS.timestamp AS TS,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID AS ID
    FROM
        journey_step_events AS STEP_EVENTS
    WHERE
        STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009'
 
),
 
INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS (
 
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME = 'slack_bso_tests - test1' AND
        T1.TS > (now() - interval '18 hour')
 
),
 
INSTANCES_PASSED_IN_NEXT_NODES AS (
     
    SELECT
        T1.TS AS TS,
        T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_ALL_NODES_WITH_DETAILS AS T1
    WHERE
        T1.NODE_NAME in ('slack_bso_tests - test2')
 
),
 
INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS (
 
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1
 
    EXCEPT
     
    SELECT
        distinct T1.ID AS ID
    FROM
        INSTANCES_PASSED_IN_NEXT_NODES AS T1
 
)
 
SELECT
    DATE_FORMAT(T1.TS,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(T1.ID) AS INSTANCES_COUNT
FROM
    INSTANCES_PASSED_IN_NODE_WITH_DETAILS AS T1,
    INSTANCES_PASSED_IN_NODE_NOT_PASSED_IN_NODES AS T2
WHERE
    T1.ID = T2.ID
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

+++

+++特定の期間にジャーニーから離脱したプロファイルの数

このクエリは、完了、エラー、タイムアウト、キャップエラーによる終了を含む、指定された期間中に退出したジャーニーインスタンスをカウントします。

_データレイクのクエリ_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    <timestamp filter>
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

_例_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    STEP_EVENTS.timestamp > (now() - interval '22 hour')
GROUP BY
    DATETIME
ORDER BY
    DATETIME DESC
```

+++

+++特定の期間にジャーニーから離脱したプロファイルの数（ノード／ステータスも指定）

このクエリは、ジャーニーの退出の詳細な分類を提供し、退出したインスタンスごとにノード名と退出ステータスを表示して、プロファイルがジャーニーを退出した場所と理由を特定するのに役立ちます。

_データレイクのクエリ_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus AS EXIT_STATUS,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = '<journey version name>' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    <timestamp filter>
GROUP BY
    DATETIME, NODE_NAME, EXIT_STATUS
ORDER BY
    DATETIME DESC
```

_例_

```sql
SELECT
    DATE_FORMAT(STEP_EVENTS.timestamp,'yyyy/MM/dd HH:mm') AS DATETIME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.nodeName AS NODE_NAME,
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus AS EXIT_STATUS,
    count(STEP_EVENTS._experience.journeyOrchestration.stepEvents.instanceID) AS EXITED_INSTANCES_COUNT
FROM
    journey_step_events AS STEP_EVENTS
WHERE
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.journeyVersionName = 'Journey20009' AND
    STEP_EVENTS._experience.journeyOrchestration.stepEvents.stepStatus in ('endStep', 'error', 'timedOut', 'cappingError') AND
    STEP_EVENTS.timestamp > (now() - interval '22 hour')
GROUP BY
    DATETIME, NODE_NAME, EXIT_STATUS
ORDER BY
    DATETIME DESC
```

+++

## カスタムアクションのパフォーマンス指標に関連するクエリ {#query-custom-action}

+++ 特定の期間での各エンドポイントの 1 秒あたりの成功した呼び出し、エラー、リクエストの合計数

このクエリは、カスタム HTTP アクションのパフォーマンス指標を提供します。これには、合計呼び出し数、成功した呼び出し数、タイプ別のエラー数（4xx、5xx、タイムアウト、キャッピング）、各エンドポイントの 1 秒あたりのリクエストのスループットが含まれます。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (<actionExecutionOriginStartTime filter> OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND <timestamp filter>))
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND timestamp > (now() - interval '1' day)))
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++ 特定の期間での各エンドポイントの成功した呼び出し、エラー、スループットの時系列

このクエリは、前のクエリと同じパフォーマンス指標を提供しますが、時系列として整理され、エンドポイントのパフォーマンスが分単位の精度で時間の経過と共にどのように変化するかを示します。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(COALESCE(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, timestamp), 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (<actionExecutionOriginStartTime filter> OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND
           <timestamp filter>))
GROUP BY 
    ENDPOINT, SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(COALESCE(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, timestamp), 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS TOTAL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL THEN 1 END) AS SUCCESSFUL_CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '4%' THEN 1 END) AS "4xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'http' AND
                    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode LIKE '5%' THEN 1 END) AS "5xx_ERRORS",
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'timedout' THEN 1 END) AS TIMEOUTS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' THEN 1 END) AS CAPPED_CALLS,
    ROUND(COUNT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime) / 
        COUNT(DISTINCT DATE_TRUNC('second', _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime)), 0) AS THROUGHPUT_RPS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND
           timestamp > (now() - interval '1' day)))
GROUP BY 
    ENDPOINT, SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++特定の期間での各エンドポイントの 50 パーセンタイル、95 パーセンタイル、99 パーセンタイル、99.9 パーセンタイルでの応答待ち時間

このクエリは、カスタムアクションエンドポイントの応答時間のパーセンタイルを計算し、待ち時間の配分を理解し、様々なパーセンタイルしきい値でのパフォーマンスの異常値を特定するのに役立ちます。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS SUCCESSFUL_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS SUCCESSFUL_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++特定の期間での各エンドポイントの応答待ち時間パーセンタイルの時系列

このクエリは、時系列として整理された待ち時間パーセンタイルを提供するので、エンドポイントの応答時間が様々なパーセンタイルレベルで時間の経過と共にどのように変化するかを追跡できます。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,    
    COUNT(1) AS SUCCESSFUL_CALLS,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,    
    COUNT(1) AS SUCCESSFUL_CALLS,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P50_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P95_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.99) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P99_LATENCY_MS,
    ROUND(PERCENTILE_CONT(0.999) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime),0) AS P999_LATENCY_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++ 特定の期間でのスロットルされたエンドポイントの 50 パーセンタイルおよび 95 パーセンタイルでのキュー内の待ち時間

このクエリは、スロットルされたエンドポイントのキューの待ち時間を分析し、50 パーセンタイルと 95 パーセンタイルの待ち時間を表示して、スロットルがカスタムアクションに与える影響を理解するのに役立ちます。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT
ORDER BY
    ENDPOINT;
```

+++

+++ スロットルされた各エンドポイントのキュー待ち時間パーセンタイルの時系列

このクエリは、キューの待ち時間パーセンタイルを時系列で提供し、スロットルが各エンドポイントの待ち時間に時間の経過と共にどのように影響するかを監視できます。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    <actionExecutionOriginStartTime filter>
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint AS ENDPOINT,
    DATE_FORMAT(_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime, 'yyyy/MM/dd HH:mm') AS SPAN,
    COUNT(1) AS THROTTLED_CALLS,
    ROUND(PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P50_QUEUE_TIME_MS,
    ROUND(PERCENTILE_CONT(0.95) WITHIN GROUP (ORDER BY _experience.journeyOrchestration.stepEvents.actionWaitTime),0) AS P95_QUEUE_TIME_MS
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionIsThrottled = 'true' AND
    _experience.journeyOrchestration.stepEvents.actionWaitTime IS NOT NULL AND
    _experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day)
GROUP BY 
    ENDPOINT,
    SPAN
ORDER BY
    ENDPOINT,
    SPAN;
```

+++

+++ 特定の期間での特定のエンドポイントのタイプおよびコード別のエラー数

このクエリは、再試行に関する情報を含む、エラータイプとエラーコード別にグループ化された、特定のエンドポイントのエラーの詳細な分類を提供します。

_データレイクのクエリ_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionExecutionError AS ERROR_TYPE,
    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode AS ERROR_CODE,
    COUNT(1) AS CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionOriginError IS NOT NULL THEN 1 END) AS CALLS_WITH_RETRY
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint = '<endpoint URI>' AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL AND
    (<actionExecutionOriginStartTime filter>) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND <timestamp filter>))
GROUP BY 
    ERROR_TYPE, ERROR_CODE
ORDER BY
    ERROR_TYPE, ERROR_CODE;
```

_例_

```sql
SELECT
    _experience.journeyOrchestration.stepEvents.actionExecutionError AS ERROR_TYPE,
    _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode AS ERROR_CODE,
    COUNT(1) AS CALLS,
    COUNT(CASE WHEN _experience.journeyOrchestration.stepEvents.actionExecutionOriginError IS NOT NULL THEN 1 END) AS CALLS_WITH_RETRY
FROM 
    journey_step_events
WHERE 
    _experience.journeyOrchestration.stepEvents.actionType = 'customHttpAction' AND
    _experience.journeyOrchestration.stepEvents.actionOriginEndpoint = 'https://example.com/my/endpoint' AND
    _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL AND
    (_experience.journeyOrchestration.stepEvents.actionExecutionOriginStartTime > (now() - interval '1' day) OR
        (_experience.journeyOrchestration.stepEvents.actionExecutionError = 'capped' AND timestamp > (now() - interval '1' day)))
GROUP BY 
    ERROR_TYPE, ERROR_CODE
ORDER BY
    ERROR_TYPE, ERROR_CODE;
```

+++

