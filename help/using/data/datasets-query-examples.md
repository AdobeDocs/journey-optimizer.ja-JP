---
solution: Journey Optimizer
product: journey optimizer
title: データセットクエリーの例
description: データセットクエリーの例
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 26ba8093-8b6d-4ba7-becf-b41c9a06e1e8
source-git-commit: 0b19af568b33d29f4b35deeab6def17919cfe824
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 0%

---

# データセットユースケース {#tracking-datasets}

このページには、次の Adobe Aioptimizer データセットおよび関連するユースケースのリストが表示されます。

[電子メール追跡体験イベントデータセット ](#email-tracking-experience-event-dataset) メッセージフィードバックイベントデータセット [ ](#message-feedback-event-dataset) プッシュトラッキングエクスペリエンスイベントデータセット [ ](#push-tracking-experience-event-dataset) 道ステップイベント [ ](#journey-step-event) Decisioning イベント ](#ode-decisionevents) [ データセット同意サービスデータセット同意サービスデータ ](#bcc-feedback-event-dataset) ](#consent-service-dataset) [ [ セットお持ちのイベントデータセット [






](#entity-dataset)

## 電子メール追跡エクスペリエンスイベントデータセット{#email-tracking-experience-event-dataset}

_インターフェイス内の名前: CJM 電子メール追跡体験イベントデータセット_

Ingesting の電子メール追跡エクスペリエンスイベントのシステムデータセット。このようなイベントを、旅オプティマイザーによって発生します。

関連するスキーマは、CJM 電子メール追跡エクスペリエンスイベントスキーマです。

次のクエリーは、指定されたメッセージについて、様々な電子メール操作 (開く、クリック) の数を示します。

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

このクエリーは、次のようなメッセージによって、電子メールのやり取り (開く、クリック) の回数の内訳を示します。

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

_インターフェイス内の名前: CJM メッセージフィードバックイベントデータセット_

Ingesting の電子メールのデータセットと、旅のオプティマイザーによるアプリケーションのフィードバックイベントの通知を使用できます。

関連するスキーマは CJM メッセージフィードバックイベントスキーマです。

次のクエリーは、特定のメッセージについて、電子メールのフィードバック状態 (送信、バウンス、その他) の数を示します。

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

このクエリーは、1回のメッセージによって送信された、バウンスされた、またはメッセージによって送信された電子メールの数と、次のような件数の内訳を示します。

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

アグリゲートレベル (トップドメインによってソートされる): ドメイン名、送信されたメッセージ、バウンス

```sql
SELECT split_part(_experience.customerJourneyManagement.emailChannelContext.address, '@', 2) AS recipientDomain, SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END)AS sentCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' THEN 1 ELSE 0 END )AS bounceCount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY recipientDomain ORDER BY sentCount DESC;
```

電子メールが日常的に送信する場合:

```sql
SELECT date_trunc('day', TIMESTAMP) AS rolluptimestamp, SUM( CASE WHEN _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'sent' THEN 1 ELSE 0 END) AS deliveredcount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY date_trunc('day', TIMESTAMP) ORDER BY rolluptimestamp ASC;
```

電子メールが届いたかどうかを確認します。そうでない場合は、エラー、バウンスのカテゴリー、コードが次のようになります。

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.emailchannelcontext.address = 'user@domain.com' AND TIMESTAMP >= now() - INTERVAL '7' DAY ORDER BY status ASC
```

特定のエラー、バウンスカテゴリーまたは過去1時間またはコードのバウンス、または特定のメッセージ配信に関連付けられていない個別の電子メール id のリストを検索します。

```sql
SELECT _experience.customerjourneymanagement.emailchannelcontext.address AS emailid, _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus AS status, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type AS bouncetype FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' AND _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus != 'sent' AND TIMESTAMP >= now() - INTERVAL '10' HOUR AND _experience.customerjourneymanagement.messageexecution.messageexecutionid = 'BMA-45237824' ORDER BY emailid
```

「アグリゲート」レベルのハードバウンスレート:

```sql
select hardBounceCount, case when sentCount > 0 then(hardBounceCount/sentCount)*100.0 else 0 end as hardBounceRate from ( select SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'bounce' AND _experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.type = 'Hard' THEN 1 ELSE 0 END)AS hardBounceCount , SUM( CASE WHEN _experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' THEN 1 ELSE 0 END )AS sentCount from cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' )
```

バウンスコードでグループ化されている永続的なエラーは以下のとおりです。

```sql
SELECT _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.reason AS failurereason, COUNT(*) AS hardbouncecount FROM cjm_message_feedback_event_dataset WHERE _experience.customerjourneymanagement.messagedeliveryfeedback.feedbackstatus = 'bounce' AND _experience.customerjourneymanagement.messagedeliveryfeedback.messagefailure.type = 'Hard' AND _experience.customerjourneymanagement.messageprofile.channel._id = 'https://ns.adobe.com/xdm/channels/email' GROUP BY failurereason
```

## プッシュトラッキングエクスペリエンスイベントデータセット {#push-tracking-experience-event-dataset}

_インターフェイス内の名前: CJM プッシュトラッキングエクスペリエンスイベントデータセット_

Ingesting mobile 追跡エクスペリエンスイベント用のデータセット。これにより、旅オプティマイザーからプッシュされます。

関連するスキーマは、CJM プッシュトラッキングエクスペリエンスイベントスキーマです。

クエリーの例:

```sql
select _experience.customerJourneyManagement.pushChannelContext.platform, sum(pushNotificationTracking.customAction.value)  from cjm_push_tracking_experience_event_dataset
group by _experience.customerJourneyManagement.pushChannelContext.platform

select  _experience.customerJourneyManagement.pushChannelContext.platform, SUM (_experience.customerJourneyManagement.messageInteraction.offers.offerCount) from cjm_email_tracking_experience_event_dataset
  group by _experience.customerJourneyManagement.pushChannelContext.platform
```

## 旅のステップイベント{#journey-step-event}

_内部名: 旅のステップイベント (システムデータセット)_

Ingesting step イベントのデータセット。

関連するスキーマは、旅オーケストレーション用の段階的なステップイベントスキーマです。

このクエリーは、指定された旅のアクションラベルによるアクションの成功数の内訳を表示します。

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

このクエリーは、指定された旅の nodeId &amp; nodeLabel によって、入力されたステップの内訳を示します。 このような nodeId は、ノードの種類によって異なる場合があります。

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

## Decisioning イベントデータセット{#ode-decisionevents}

_インターフェイスの名前: DecisionEvents (システムデータセット)_

Ingesting 用のデータセットは、ユーザーに提示されます。

関連するスキーマは、「DecisionEvents」になります。

このクエリーは、前日に返されたすべてのサービスを表示します。

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

このクエリーには、ある特定のアクティビティ/決定、およびそれに関連付けられた特典について、過去30日間にわたって提供された特典が表示されます。

```sql
select proposedOffers.id,proposedOffers.name, po._experience.decisioning.ranking.priority, count(proposedOffers.id) as ProposedCount from (
select explode(propositionexplode.selections) AS proposedOffers from
(select explode(_experience.decisioning.propositionDetails) AS propositionexplode,timestamp FROM ode_decisionevents_itca_decisioning_20200925_235340_379  where date_format(timestamp, 'MM/dd/yyyy') >= date_format(DATE_ADD(CURRENT_DATE, -30), 'MM/dd/yyyy') and _experience.decisioning.propositionDetails.activity[0].id = 'xcore:offer-activity:12ae6f35a055c6f0')) a, decision_object_repository_personalized_offers po where proposedOffers.id LIKE 'xcore:personalized-offer%' and po._id=proposedOffers.id
group by proposedOffers.id, proposedOffers.name, po._experience.decisioning.ranking.priority;
```

## 同意サービスデータセット{#consent-service-dataset}

_インターフェイス内の名前: CJM 同意サービスデータセット (システムデータセット)_

「データセット」を使用して、旅オプティマイザーの同意サービスを行います。

関連するスキーマは、CJM の同意サービススキーマです。

電子メールの受信に consented が付いている電子メール Id を表示するためのクエリー:

```sql
select key as email FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
)
where value.marketing.email.val == 'y'
```

電子メール id が入力された電子メール ID に対する同意値を返すクエリー:

```sql
select value.marketing.email.val FROM (
  select explode(value) FROM (
  select explode(consents.idSpecific)
  from cjm_consent_service_dataset
 )
```

## BCC フィードバックイベントデータセット{#bcc-feedback-event-dataset}

_インターフェイスの名前: AJO BCC フィードバックイベントデータセット (システムデータセット)_

BCC メッセージの情報を格納するためのデータセット。

次のいずれかの方法で、すべての BCC メッセージについてクエリーを実行します (特定のキャンペーン)。

```sql
SELECT bcc.*
FROM ajo_bcc_feedback_event_dataset AS bcc
WHERE 
    bcc._experience.customerJourneyManagement.messageExecution.messageExecutionID = '<message-execution-id>' AND 
    bcc.timestamp >= now() - INTERVAL '2' day; 
```

フィードバックデータセットでクエリーを実行すると、受信されていないユーザー (すべてのバウンスと非表示)、および特定のメッセージに対して BCC エントリを取得したユーザーが表示されます。

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

## エンティティデータセット{#entity-dataset}

_インターフェイスの名前: ajo_entity_dataset (システムデータセット)_

データセットは、エンドユーザーに送信されるメッセージのエンティティメタデータを格納します。

関連するスキーマは AJO Entity Schema です。

このデータセットには marketer 定義されたメタデータへのアクセスが許可されています。これにより、外部ツールを使用して、オプティマイザーのオプティマイザーデータセットを書き出したときに、より優れたレポート情報を取得できます。 これは、messageID 属性を使用して、メッセージフィードバックデータセットやエクスペリエンスイベント追跡データセットなどの各種データセットを作成し、プロファイルレベルで送信されたメッセージの配信に関する詳細情報を取得するのに役立ちます。

**重要な注意事項**

* メッセージのエントリは、「旅」または「キャンペーン」が公開された後に作成されます。

* キャンペーンまたは旅が公開されてから30分後にエントリが表示されることがあります。

>[!NOTE]
>
>今後、互換性のために、エンティティデータセットの各メッセージ公開について2つのエントリが表示されます。 これにより、必要に応じて結合クエリーを使用して目的の情報を取得することができます。

レポートには、送信したアクションに応じて、特定の旅によって送信された電子メールが並べ替えられます。 メッセージフィードバックデータセットは、エンティティデータセットに参加できます。 使用するフィールドは以下のとおりです。 `_experience.decisioning.propositions.scopeDetails.correlationID` `_id field in entity dataset`

次のクエリーは、指定されたキャンペーンに関連付けられたメッセージテンプレートを取得するのに役立ちます。

```sql
SELECT
  AE._experience.customerJourneyManagement.entities.channelDetails.template
from
  ajo_entity_dataset AE
    WHERE AE._experience.customerJourneyManagement.entities.campaign.campaignVersionID = 'd7a01136-b113-4ef2-8f59-b6001f7eef6e'
```

次のクエリーを使用すると、すべてのフィードバックイベントに関連付けられた移動の詳細情報と電子メールの件名を取得することができます。

```sql
SELECT 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionName, 
  AE._experience.customerJourneyManagement.entities.journey.journeyActionID, 
  AE._experience.customerJourneyManagement.entities.journey.journeyVersionID, 
  AE._experience.customerJourneyManagement.entities.channelDetails.email.subject 
from 
  ajo_entity_dataset AE 
  INNER JOIN cjm_message_feedback_event_dataset MF ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```

特定のプロファイルの統計情報を取得するには、次のような旅のステップイベント、メッセージフィードバック、追跡データセットを作成することができます。

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
  INNER JOIN cjm_message_feedback_event_dataset MF 
    ON AE._experience.customerJourneyManagement.entities.channelDetails.messageID = MF._experience.customerJourneyManagement.messageExecution.messageID 
    INNER JOIN journey_step_events JE
    ON AE._experience.customerJourneyManagement.entities.journey.journeyActionID = JE._experience.journeyOrchestration.stepEvents.actionID
WHERE 
  AE._experience.customerJourneyManagement.entities.channelDetails.channel._id = 'https://ns.adobe.com/xdm/channels/email' 
  AND MF._experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'sent' 
  AND AE._experience.customerJourneyManagement.entities.journey.journeyVersionID IS NOT NULL
```
