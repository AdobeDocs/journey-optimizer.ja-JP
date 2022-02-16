---
title: クエリの例
description: クエリの例
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 26ad12c3-0a2b-4f47-8f04-d25a6f037350
source-git-commit: 6d744c0289e81ab2229f02c44ead43943b945b89
workflow-type: ht
source-wordcount: '373'
ht-degree: 100%

---

# クエリの例{#query-examples}

この節では、データレイクのジャーニーステップイベントに関するクエリを実行する際によく使用される例をいくつか示します。

## メッセージ／アクションエラー {#message-action-errors}

### ジャーニーで発生した各エラーのリスト {#error-list-journey}

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

## プロファイルベースのクエリ {#profile-based-queries}

### プロファイルが特定のジャーニーにエントリしたかどうかの確認 {#profile-entered-journey}

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

結果は 0 より大きい値になります。 このクエリは、プロファイルがジャーニーにエントリした正確な回数を返します。

### プロファイルが特定のメッセージを送信されたかどうかの確認 {#profile-specific-message}

**方法 1：**&#x200B;メッセージの名前がジャーニー内で一意でない場合（複数の場所で使用される場合）。

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

結果は 0 より大きい値になります。 このクエリは、メッセージアクションがジャーニー側で正常に実行されたかどうかのみを示します。

**方法 2：**&#x200B;メッセージの名前がジャーニー内で一意の場合。

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

## 過去 30 日間にプロファイルが受け取ったすべてのメッセージの検索 {#message-received-30-days}

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

### 過去 30 日間にプロファイルがエントリしたすべてのジャーニーの検索 {#profile-entered-30-days}

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

### 1 日あたりのジャーニーの対象となったプロファイルの数 {#profile-qualified}

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

このクエリは、指定した期間に 1 日ごとにジャーニーにエントリしたプロファイルの数を返します。 プロファイルが別の ID を使用してエントリした場合は、2 回カウントされます。 再エントリを有効にすると、別の日にジャーニーに再エントリした場合、プロファイル数が複数日にわたって重複する場合があります。

## ジャーニーベースのクエリ {#journey-based-queries}

### 日別のアクティブなジャーニーの数 {#daily-active-journeys}

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

このクエリは、指定した期間に 1 日にトリガーされた一意のジャーニーの数を返します。 1 つのジャーニーが複数日でトリガーされる場合は、1 日につき 1 回とカウントされます。
