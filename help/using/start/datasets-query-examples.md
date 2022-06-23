---
title: データセットクエリの例
description: データセットクエリの例
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 5a6e18e6ff236d25bd5f81b42430be2998208321
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# データセットの使用例 {#tracking-datasets}

このページでは、Adobe Journey Optimizerデータセットと関連する使用例のリストを示します。

[メールトラッキングエクスペリエンスイベントデータセット](../start/datasets-query-examples.md#email-tracking-experience-event-dataset)
[メッセージフィードバックイベントデータセット](../start/datasets-query-examples.md#message-feedback-event-dataset)
[プッシュ追跡エクスペリエンスイベントデータセット](../start/datasets-query-examples.md#push-tracking-experience-event-dataset)
[ジャーニーステップイベント](../start/datasets-query-examples.md#journey-step-event)
[offer decisioningイベントデータセット](../start/datasets-query-examples.md#ode-decisionevents)
[同意サービスデータセット](../start/datasets-query-examples.md#consent-service-dataset)
[BCC フィードバックイベントデータセット](../start/datasets-query-examples.md#bcc-feedback-event-dataset)

## メールトラッキングエクスペリエンスイベントデータセット{#email-tracking-experience-event-dataset}

_インターフェイスの名前：CJM E メールトラッキングエクスペリエンスイベントデータセット_

Journey Optimizerから電子メールトラッキングエクスペリエンスイベントを取り込むためのシステムデータセット。

関連するスキーマは、CJM 電子メールトラッキングエクスペリエンスイベントスキーマです。

このクエリは、特定のメッセージに対する様々な E メールインタラクション数（開封数、クリック数）を表示します。

```sql
select
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from cjm_email_tracking_experience_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageInteraction.interactionType
```

このクエリは、特定のジャーニーに関するメッセージ別に、様々な E メールインタラクション（開封数、クリック数）のカウントの分類を表示します。

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageInteraction.interactionType AS interactionType,
    count(1) eventCount
from cjm_email_tracking_experience_event_dataset
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

_インターフェイスの名前：CJM メッセージフィードバックイベントデータセット_

電子メールおよびプッシュアプリケーションのフィードバックイベントをJourney Optimizerから取り込むデータセット。

関連するスキーマは、 CJM Message Feedback Event Schema です。

このクエリは、特定のメッセージに対する様々な E メールフィードバックステータス（送信済み、バウンスなど）の数を表示します。

```sql
select
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from cjm_message_feedback_event_dataset
where
     _experience.customerJourneyManagement.messageExecution.messageExecutionID IN ('UMA-30647505')
group by
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus;
```

このクエリは、特定のジャーニーに関するメッセージ別に、様々な E メールのフィードバックステータス（送信済み、バウンスなど）のカウントの分類を表示します。

```sql
select
    _experience.customerJourneyManagement.messageExecution.messageExecutionID AS messageExecutionID,
    _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus AS feedbackStatus,
    count(1) eventCount
from cjm_message_feedback_event_dataset
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

集計レベルで、ドメインレベルのレポート（上位ドメイン順）:ドメイン名、送信されたメッセージ、バウンス

```sql
SELECT split_part(_experience.customerJourneyManagement.emailChannelContext.address, '@', 2) AS recipientDomain, SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END)AS sentCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' THEN 1 ELSE 0 END )AS bounceCount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY recipientDomain ORDER BY sentCount DESC;
```

毎日の電子メール送信：

```sql
SELECT date_trunc('day', TIMESTAMP) AS rolluptimestamp, SUM( CASE WHEN _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent' THEN 1 ELSE 0 END) AS deliveredcount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY date_trunc('day', TIMESTAMP) ORDER BY rolluptimestamp ASC;
```

特定の電子メール ID が電子メールを受け取ったかどうか、受け取っていない場合は、エラー、バウンスカテゴリ、コードは何でしたかを調べます。

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.emailchannelcontext.address = 'user@domain.com' AND TIMESTAMP >= now() - INTERVAL '7' DAY ORDER BY status ASC
```

過去 x 時間/日間に特定のエラー、バウンスカテゴリまたはコードが発生したか、特定のメッセージ配信に関連付けられた個々の電子メール ID のリストを見つけます。

```sql
SELECT _experience.customerjourneymanagement.emailchannelcontext.address AS emailid, _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus != 'sent' AND TIMESTAMP >= now() - INTERVAL '10' HOUR AND _experience.customerjourneymanagement.messageexecution.messageexecutionid = 'BMA-45237824' ORDER BY emailid
```

集計レベルでのハードバウンス率：

```sql
select hardBounceCount, case when sentCount > 0 then(hardBounceCount/sentCount)*100.0 else 0 end as hardBounceRate from ( select SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' AND _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.type = 'Hard' THEN 1 ELSE 0 END)AS hardBounceCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END )AS sentCount from cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' )
```

バウンスコード別にグループ化された永続的なエラー：

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, COUNT(*) AS hardbouncecount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type = 'Hard' AND _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY failurereason
```

## プッシュ追跡エクスペリエンスイベントデータセット {#push-tracking-experience-event-dataset}

_インターフェイスの名前：CJM プッシュトラッキングエクスペリエンスイベントデータセット_

Journey Optimizerからプッシュ用のモバイルトラッキングエクスペリエンスイベントを取り込むデータセット。

関連するスキーマは、CJM プッシュトラッキングエクスペリエンスイベントスキーマです。

クエリの例：

```sql
select _experience.customerJourneyManagement.pushChannelContext.platform, sum(pushNotificationTracking.customAction.value)  from cjm_push_tracking_experience_event_dataset
group by _experience.customerJourneyManagement.pushChannelContext.platform

select  _experience.customerJourneyManagement.pushChannelContext.platform, SUM (_experience.customerJourneyManagement.messageInteraction.offers.offerCount) from cjm_email_tracking_experience_event_dataset
  group by _experience.customerJourneyManagement.pushChannelContext.platform
```
## ジャーニーステップイベント{#journey-step-event}

_内部名：ジャーニーステップイベント（システムデータセット）_

ジャーニーでステップイベントを取り込むデータセット。

関連するスキーマは、ジャーニーのイベントステップイベントJourney Orchestrationです。

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

このクエリは、特定のジャーニーの nodeId および nodeLabel ごとに、入力されたステップの分類を表示します。 nodeId は異なるジャーニーノードで同じにすることができるので、ここに含まれます。

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

## offer decisioningイベントデータセット{#ode-decisionevents}

_インターフェイスの名前：ODE DecisionEvents （システムデータセット）_

オファーの提案をユーザーに取り込むデータセット。

関連するスキーマは ODE DecisionEvents です。

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

このクエリは、特定のアクティビティ/決定の過去 30 日間にオファーが提案された回数と、関連するオファーの優先度を表示します。

```sql
select proposedOffers.id,proposedOffers.name, po._experience.decisioning.ranking.priority, count(proposedOffers.id) as ProposedCount from (
select explode(propositionexplode.selections) AS proposedOffers from
(select explode(_experience.decisioning.propositionDetails) AS propositionexplode,timestamp FROM ode_decisionevents_itca_decisioning_20200925_235340_379  where date_format(timestamp, 'MM/dd/yyyy') >= date_format(DATE_ADD(CURRENT_DATE, -30), 'MM/dd/yyyy') and _experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:12ae6f35a055c6f0')) a, decision_object_repository_personalized_offers po where proposedOffers.id LIKE 'xcore:personalized-offer%' and po._id=proposedOffers.id
group by proposedOffers.id, proposedOffers.name, po._experience.decisioning.ranking.priority;
```

## 同意サービスデータセット{#consent-service-dataset}

_インターフェイスの名前：CJM 同意サービスデータセット（システムデータセット）_

Journey Optimizer Consent サービスのデータセット。

関連するスキーマは、CJM Consent Service スキーマです。

電子メールの受信に同意した電子メール ID をリストするクエリ：

```sql
select key as email FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
)
where value.marketing.email.val == 'y'
```

電子メール ID が入力となる電子メール ID の同意値を返すクエリ：

```sql
select value.marketing.email.val FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
```

## BCC フィードバックイベントデータセット{#bcc-feedback-event-dataset}

_インターフェイスの名前：AJO BCC フィードバックイベントデータセット（システムデータセット）_

BCC メッセージの情報を保存するデータセット。

2 日以内のすべての BCC メッセージに対するクエリ（特定のキャンペーンの場合）:

```sql
SELECT bcc.*
FROM ajo_bcc_feedback_event_dataset AS bcc
WHERE 
    bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID = '<message-execution-id>' AND 
    bcc.timestamp >= now() - INTERVAL '2' day; 
```

フィードバックデータセットを含むクエリで、受信しなかった（すべてのバウンスと抑制）ユーザーと、特定のメッセージに対して BCC エントリを持つユーザーを表示します。

```sql
SELECT 
    distinct bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress AS OriginalRecipientAddress 
FROM ajo_bcc_feedback_event_dataset  AS bcc 
WHERE 
    bcc.timestamp > now() - INTERVAL '2' DAY AND     bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND      bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress != '' AND
    ( 
            bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress NOT IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM cjm_message_feedback_event_dataset AS mfe 
        WHERE 
            mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent'
        )  
    OR     bcc._experience.customerJourneyManagement.secondaryRecipientDetail.originalRecipientAddress IN ( 
        SELECT distinct mfe._experience.customerJourneyManagement.emailChannelContext.address
        FROM cjm_message_feedback_event_dataset AS mfe 
        WHERE 
        mfe.timestamp > now() - INTERVAL '2' DAY AND 
            mfe._experience.customerJourneyManagement.messageExecution.messageExecutionID  = '<message-execution-id>' AND 
            mfe._experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category = 'async' AND 
            mfe._experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus
```
