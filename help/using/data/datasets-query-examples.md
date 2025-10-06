---
solution: Journey Optimizer
product: journey optimizer
title: データセットクエリの例
description: データセットクエリの例
feature: Journeys, Reporting, Use Cases, Datasets, Data Management
topic: Content Management
role: Data Engineer, Data Architect, Admin
level: Experienced
keywords: データセット, Optimizer, ユースケース
exl-id: 26ba8093-8b6d-4ba7-becf-b41c9a06e1e8
source-git-commit: 90b8f69f3849418eaec1b65b14e0362980c43e9a
workflow-type: ht
source-wordcount: '958'
ht-degree: 100%

---

# クエリの例 {#query-examples}

このページでは、Adobe Journey Optimizer データセットと関連する使用例のリストを示します。

* [メールトラッキングエクスペリエンスイベントのデータセット](#email-tracking-experience-event-dataset)
* [メッセージフィードバックイベントデータセット](#message-feedback-event-dataset)
* [プッシュトラッキングエクスペリエンスイベントデータセット](#push-tracking-experience-event-dataset)
* [ジャーニーステップイベント](#journey-step-event)
* [意思決定イベントデータセット](#ode-decisionevents)
* [BCC フィードバックイベントデータセット](#bcc-feedback-event-dataset)
* [エンティティデータセット](#entity-dataset)

各スキーマのフィールドと属性の完全なリストを表示するには、[Journey Optimizer スキーマ辞書](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja){target="_blank"}を参照してください。

また、一般的に使用されるいくつかの[ジャーニーステップイベントのクエリを実行する例](../reports/query-examples.md)も参照してください。


## メールトラッキングエクスペリエンスイベントのデータセット{#email-tracking-experience-event-dataset}

_インターフェイスの名前：AJO メールトラッキングエクスペリエンスイベントのデータセット_

Journey Optimizer からメールトラッキングエクスペリエンスイベントを取り込むためのシステムデータセット。

関連するスキーマは、AJO メールトラッキングエクスペリエンスイベントスキーマです。

このクエリは、特定のメッセージに対する様々なメールインタラクション数（開封数、クリック数）を表示します。

```sql
select
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from ajo_email_tracking_experience_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageInteraction.interactionType
```

このクエリは、特定のジャーニーに関してメッセージ別に、様々なメールのインタラクション（開封数、クリック数）のカウントの分類を表示します。

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from ajo_email_tracking_experience_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
group by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType
order by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType
limit 100;
```

## メッセージフィードバックイベントデータセット{#message-feedback-event-dataset}

_インターフェイスの名前：AJO メッセージフィードバックイベントのデータセット_

メールおよびプッシュアプリケーションのフィードバックイベントを Journey Optimizer から取り込むためのデータセット。

関連するスキーマは、AJO メッセージフィードバックイベントスキーマです。

このクエリは、特定のメッセージに対する様々なメールフィードバックステータス（送信済み、バウンスなど）の数を表示します。

```sql
select
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from ajo_message_feedback_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus;
```

このクエリは、特定のジャーニーに関してメッセージ別に、様々なメールのフィードバックステータス（送信済み、バウンスなど）のカウントの分類を表示します。

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from ajo_message_feedback_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
group by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus
order by
    _experience.customerJourneyManagement.messageExecution.messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus
limit 100;
```

集計レベルにおけるドメインレベルのレポート（トップドメイン順）：ドメイン名、送信されたメッセージ、バウンス

```sql
SELECT split_part(_experience.customerJourneyManagement.emailChannelContext.address, '@', 2) AS recipientDomain, SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END)AS sentCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' THEN 1 ELSE 0 END )AS bounceCount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY recipientDomain ORDER BY sentCount DESC;
```

毎日のメール送信：

```sql
SELECT date_trunc('day', TIMESTAMP) AS rolluptimestamp, SUM( CASE WHEN _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent' THEN 1 ELSE 0 END) AS deliveredcount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY date_trunc('day', TIMESTAMP) ORDER BY rolluptimestamp ASC;
```

特定のメール ID がメールを受け取ったかどうか、受け取っていない場合は、エラー、バウンスカテゴリ、コードを調べます。

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.emailchannelcontext.address = 'user@domain.com' AND TIMESTAMP >= now() - INTERVAL '7' DAY ORDER BY status ASC
```

過去 x 時間/日間に、特定のエラー、バウンスカテゴリまたはコードを持つ、または特定のメッセージ配信に関連する、個々のメール ID のリストを見つけます。

```sql
SELECT _experience.customerjourneymanagement.emailchannelcontext.address AS emailid, _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus != 'sent' AND TIMESTAMP >= now() - INTERVAL '10' HOUR AND _experience.customerjourneymanagement.messageexecution.messageexecutionid = 'BMA-45237824' ORDER BY emailid
```

集計レベルでのハードバウンス率：

```sql
select hardBounceCount, case when sentCount > 0 then(hardBounceCount/sentCount)*100.0 else 0 end as hardBounceRate from ( select SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' AND _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.type = 'Hard' THEN 1 ELSE 0 END)AS hardBounceCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END )AS sentCount from ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' )
```

バウンスコード別にグループ化された永続的なエラー：

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, COUNT(*) AS hardbouncecount FROM ajo_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type = 'Hard' AND _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY failurereason
```

>[!NOTE]
>
>一部のジャーニーでは、`messageID` は個々の配信ごとに一意ではない場合があります。ジャーニーで同じアクションを同じプロファイルに再送信する場合は、同じ `messageID` を再利用できます。したがって、個々の送信レベルでイベントを正確に追跡したり属性を設定したりするには、`journeyVersionID`、`journeyActionID`、`batchInstanceID`（バッチジャーニーの場合）または `identityMap` フィールドを組み合わせて、より正確な一意性を実現します。


### ISP のサービス停止後に強制隔離されたアドレスの識別{#isp-outage-query}

インターネットサービスプロバイダー（ISP）のサービス停止が発生した場合は、特定のドメインに対してバウンス（強制隔離）と誤ってマークされたメールアドレスを、一定期間識別する必要があります。これらのアドレスを取得するには、次のクエリを使用します。

```sql
SELECT
    _experience.customerJourneyManagement.emailChannelContext.address AS RecipientAddress,
    timestamp AS EventTime,
    _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.reason AS "Invalid Recipient"
FROM ajo_message_feedback_event_dataset
WHERE
    eventtype = 'message.feedback' AND
    DATE(timestamp) BETWEEN '<start-date-time>' AND '<end-date-time>' AND
    _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND
    _experience.customerJourneyManagement.emailChannelContext.address ILIKE '%domain.com%'
ORDER BY timestamp DESC;
```

日付の形式は、`YYYY-MM-DD HH:MM:SS` です。

識別したら、これらのアドレスを Journey Optimizer 抑制リストから削除します。[詳細情報](../configuration/manage-suppression-list.md#remove-from-suppression-list)




## プッシュトラッキングエクスペリエンスイベントデータセット {#push-tracking-experience-event-dataset}

_インターフェイスの名前：AJO プッシュトラッキングエクスペリエンスイベントのデータセット_

Journey Optimizer からプッシュ用のモバイルトラッキングエクスペリエンスイベントを取り込むためのデータセット。

関連するスキーマは、AJO プッシュトラッキングエクスペリエンスイベントスキーマです。

クエリの例：

```sql
select _experience.customerJourneyManagement.pushChannelContext.platform, sum(pushNotificationTracking.customAction.value)  from ajo_push_tracking_experience_event_dataset
group by _experience.customerJourneyManagement.pushChannelContext.platform

select  _experience.customerJourneyManagement.pushChannelContext.platform, SUM (_experience.customerJourneyManagement.messageInteraction.offers.offerCount) from ajo_email_tracking_experience_event_dataset
  group by _experience.customerJourneyManagement.pushChannelContext.platform
```

## ジャーニーステップイベント{#journey-step-event}

_内部名：ジャーニーステップイベント（システムデータセット）_

ジャーニーでステップイベントを取り込むデータセット。

関連するスキーマは、Journey Orchestration のジャーニーのイベントステップイベントです。

このクエリは、特定のジャーニーのアクションラベル別に、アクション成功数の分類を表示します。

```sql
select
    _experience.journeyOrchestration.stepEvents.actionName AS actionLabel,
    count(1) actionSuccessCount
from journey_step_events
where
     _experience.journeyOrchestration.stepEvents.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
     AND _experience.journeyOrchestration.stepEvents.actionID IS NOT NULL
     AND _experience.journeyOrchestration.stepEvents.actionType IS NOT NULL
     AND _experience.journeyOrchestration.stepEvents.actionExecutionErrorCode IS NULL
group by
    _experience.journeyOrchestration.stepEvents.actionName;   
```

このクエリは、特定のジャーニーの nodeId および nodeLabel ごとに、エントリしたステップ数の分類を表示します。異なるジャーニーノードに対して nodeLabel を同じにできるので、nodeId はここに含まれます。

```sql
select
    _experience.journeyOrchestration.stepEvents.nodeID AS nodeID,
    _experience.journeyOrchestration.stepEvents.nodeName AS nodeLabel,
    count(1) stepEnteredCount
from journey_step_events
where
     _experience.journeyOrchestration.stepEvents.journeyVersionID IN ('0e86ac62-c315-48cc-ab4f-3f8b741ae667')
     AND _experience.journeyOrchestration.stepEvents.journeyNodeProcessed = TRUE
     AND _experience.journeyOrchestration.stepEvents.eventID IS DISTINCT FROM 'createInstance'
group by
    _experience.journeyOrchestration.stepEvents.nodeID,
    _experience.journeyOrchestration.stepEvents.nodeName; 
```




このクエリは、プロファイル ID とメッセージフィードバックイベントデータセットを使用して、プロファイルへのメッセージの配信に関連付けられているジャーニー内のノード（nodeID と nodeName 別）を取得します。

```sql
select
    _experience.journeyorchestration.stepevents.nodeID, JSE._experience.journeyorchestration.stepevents.nodeName
from journey_step_events JSE
where 
    _experience.journeyOrchestration.stepEvents.actionID 
    in

    (
    select
        _experience.customerJourneyManagement.messageExecution.journeyActionID
    from  ajo_message_feedback_event_dataset
    where 
        _experience.customerJourneyManagement.messageProfile.messageProfileID = '<PROFILE ID>'
    group by
        _experience.customerJourneyManagement.messageExecution.journeyActionID
    )

group by
    _experience.journeyorchestration.stepevents.nodeID, JSE._experience.journeyorchestration.stepevents.nodeName  
```


また、一般的に使用されるいくつかの[ジャーニーステップイベントのクエリを実行する例](../reports/query-examples.md)も参照してください。

詳しくは、[journey_step_events で破棄されたイベントタイプのトラブルシューティング](../reports/sharing-field-list.md#discarded-events)を参照してください。

## 意思決定イベントデータセット{#ode-decisionevents}

_インターフェイスの名前：ODE DecisionEvents （システムデータセット）_

オファーの提案をユーザーに取り込むデータセット。

関連するスキーマは、ODE DecisionEvents です。

このクエリでは、前日に返されたすべてのオファーを表示します。

```sql
SELECT date_format(Decision.Timestamp, 'MM/dd/yyyy') as Date
,HOUR(Decision.timestamp) as Hour
,COUNT(*)  as Count
FROM ode_decisionevents_b699fa78_efec_41b1_99fa_78efecc1b1ef_decision AS Decision
WHERE date_format(Decision.timestamp, 'MM/dd/yyyy') = date_format(CURRENT_DATE, 'MM/dd/yyyy') and Decision._experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:13ab41890a335ad6'
GROUP BY date_format(Decision.Timestamp, 'MM/dd/yyyy')
,HOUR(Decision.timestamp)
ORDER BY 1, 2 DESC;
```

このクエリは、特定のアクティビティ／決定において、過去 30 日間にオファーが提案された回数と関連するオファーの優先度を表示します。

```sql
select proposedOffers.id,proposedOffers.name, po._experience.decisioning.ranking.priority, count(proposedOffers.id) as ProposedCount from (
select explode(propositionexplode.selections) AS proposedOffers from
(select explode(_experience.decisioning.propositionDetails) AS propositionexplode,timestamp FROM ode_decisionevents_itca_decisioning_20230925_235340_379  where date_format(timestamp, 'MM/dd/yyyy') >= date_format(DATE_ADD(CURRENT_DATE, -30), 'MM/dd/yyyy') and _experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:12ae6f35a055c6f0')) a, decision_object_repository_personalized_offers po where proposedOffers.id LIKE 'xcore:personalized-offer%' and po._id=proposedOffers.id
group by proposedOffers.id, proposedOffers.name, po._experience.decisioning.ranking.priority;
```

<!--
## Consent Service Dataset{#consent-service-dataset}

_Name in the interface: CJM Consent Service Dataset (system dataset)_

Dataset for Journey Optimizer Consent service.

The related schema is CJM Consent Service Schema.

Query to list email IDs that have consented to receive email:

```sql
select key as email FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
)
where value.marketing.email.val == 'y'
```

Query to return consent value for an email ID where email ID would be the input:

```sql
select value.marketing.email.val FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
```
-->

## BCC フィードバックイベントデータセット{#bcc-feedback-event-dataset}

_インターフェイスの名前：AJO BCC フィードバックイベントデータセット（システムデータセット）_

BCC メッセージの情報を保存するデータセット。

2 日以内のすべての BCC メッセージに対するクエリ（特定のキャンペーンの場合）：

```sql
SELECT bcc.*
FROM ajo_bcc_feedback_event_dataset AS bcc
WHERE 
    bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID = '<message-execution-id>' AND 
    bcc.timestamp >= now() - INTERVAL '2' day; 
```

フィードバックデータセットを含むクエリで、受信しなかったユーザー（すべてのバウンスと抑制）と、特定のメッセージに対して BCC エントリを持つユーザーを表示します。

```sql
SELECT 
    distinct bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS OriginalRecipientAddress 
FROM ajo_bcc_feedback_event_dataset  AS bcc 
WHERE 
    bcc.timestamp > now() - INTERVAL '2' DAY AND     bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND      bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress != '' AND
    ( 
            bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress NOT IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM ajo_message_feedback_event_dataset AS mfe 
        WHERE 
            mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent'
        )  
    OR     bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM ajo_message_feedback_event_dataset AS mfe 
        WHERE 
        mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND 
            mfe._experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category = 'async' AND 
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus
```

## エンティティデータセット{#entity-dataset}

_インターフェイスでの名前：ajo_entity_dataset（システムデータセット）_

エンドユーザーに送信されるメッセージのエンティティメタデータを保存するデータセット。

関連するスキーマは AJO エンティティスキーマです。

このデータセットを使用すると、マーケターが定義したメタデータにアクセスし、外部ツールでレポート視覚化するために Journey Optimizer がデータセットをエクスポートした際に、レポートに関するより優れたインサイトを得ることができます。messageID 属性を使用することで、メッセージフィードバックデータセットやエクスペリエンスイベントトラッキングデータセットなどの様々なデータセットをつなぎ合わせて、プロファイルレベルでの送信からトラッキングまでのメッセージ配信の詳細を取得することができます。

**重要な注意事項**

* メッセージのエントリは、ジャーニーまたはキャンペーンが公開された後にのみ作成されます。

* キャンペーン／ジャーニーが公開されてから 30 分後にエントリが表示される場合があります。

>[!NOTE]
>
>将来の互換性に備え、当面の間、エンティティデータセット内の各メッセージの公開には 2 つのエントリが存在します。このことは、必要に応じてデータセット間で結合クエリを使用して目的の情報を取得する機能には影響しません。

レポートで、特定のジャーニーで送信されたメールを送信元のアクションに従って並べ替える場合は、メッセージフィードバックデータセットをエンティティデータセットと結合できます。使用するフィールドは `_experience.decisioning.propositions.scopeDetails.correlationID` と `_id field in entity dataset` です。

特定のキャンペーンに関連するメッセージテンプレートを取得するのに役立つクエリは次のとおりです。

```sql
SELECT
  AE._experience.customerJourneyManagement.entities.channelDetails.template
from
  ajo_entity_dataset AE
    WHERE AE._experience.customerJourneyManagement.entities.campaign.campaignVersionID = 'd7a01136-b113-4ef2-8f59-b6001f7eef6e'
```

すべてのフィードバックイベントに関連付けられているジャーニー詳細とメール件名を取得するのに役立つクエリは次のとおりです。

```sql
SELECT 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionName, 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionID, 
  AE._experience.customerJourneyManagement.entities.journey.journeyVersionID, 
  AE._experience.customerJourneyManagement.entities.channelDetails.email.subject 
from 
  ajo_entity_dataset AE 
  INNER JOIN ajo_message_feedback_event_dataset MF ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```

ジャーニーステップイベント、メッセージフィードバックおよびトラッキングデータセットをスティッチして、特定のプロファイルの統計を取得できます。

```sql
SELECT 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionName, 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionID, 
  AE._experience.customerJourneyManagement.entities.journey.journeyVersionID, 
  AE._experience.customerJourneyManagement.entities.channelDetails.email.subject,
    JE._EXPERIENCE.JOURNEYORCHESTRATION.STEPEVENTS.PROFILEID,
    JE._EXPERIENCE.JOURNEYORCHESTRATION.STEPEVENTS.NODENAME
from 
  ajo_entity_dataset AE 
  INNER JOIN ajo_message_feedback_event_dataset MF 
    ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
    INNER JOIN journey_step_events JE
    ON AE._experience.customerJourneyManagement.entities.journey.journeyActionID = JE._experience.journeyOrchestration.stepEvents.actionID
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```
