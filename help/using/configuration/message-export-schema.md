---
solution: Journey Optimizer
product: journey optimizer
title: AJO メッセージ書き出しスキーマ
description: AJO メッセージ書き出しデータセットで使用できるフィールドについて説明します
feature: Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: 書き出し、メッセージ、データセット、スキーマ、メール、SMS
feature_v2: []
subfeature_v2:
  - id: cf64c7f6-7428-4ae5-b158-8df9771f38f4
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 37%

---

# AJO メッセージ書き出しスキーマ {#ajo-message-export-schema}

**メッセージ書き出し**&#x200B;が電子メールまたはSMS チャネル設定で有効になっている場合、送信されたメッセージの内容は[!DNL Adobe Experience Platform]の&#x200B;**AJO メッセージ書き出しデータセット**&#x200B;に書き込まれます。

この節では、書き出されたデータセットで使用可能なフィールドの一覧を示します。

## データセットフィールド

+++ _experience

**フィールド：** `_experience`\
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > customerJourneyManagement

**フィールド：** `customerJourneyManagement`\
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > customerJourneyManagement > messageDeliveryMetadata

**フィールド：** `messageDeliveryMetadata`\
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > customerJourneyManagement > messageDeliveryMetadata > emailMetadata

**フィールド：** `emailMetadata`\
**タイプ：**&#x200B;オブジェクト

* 受信者

  **フィールド：** `recipient`\
  **タイプ：**&#x200B;オブジェクト

   * bcc

     **フィールド：** `bcc`\
     **型：**&#x200B;文字列の配列

   * cc

     **フィールド：** `cc`\
     **型：**&#x200B;文字列の配列

   * メール

     **フィールド：** `email`\
     **タイプ：**&#x200B;文字列

   * name

     **フィールド：** `name`\
     **タイプ：**&#x200B;文字列

* 送信者

  **フィールド：** `sender`\
  **タイプ：**&#x200B;オブジェクト

   * メール

     **フィールド：** `email`\
     **タイプ：**&#x200B;文字列

   * errorEmail

     **フィールド：** `errorEmail`\
     **タイプ：**&#x200B;文字列

   * name

     **フィールド：** `name`\
     **タイプ：**&#x200B;文字列

   * replyToEmail

     **フィールド：** `replyToEmail`\
     **タイプ：**&#x200B;文字列

   * replyToName

     **フィールド：** `replyToName`\
     **タイプ：**&#x200B;文字列

+++

+++ _experience > customerJourneyManagement > messageDeliveryMetadata > smsMetadata

**フィールド：** `smsMetadata`\
**タイプ：**&#x200B;オブジェクト

* 受信者

  **フィールド：** `recipient`\
  **タイプ：**&#x200B;オブジェクト

   * 数値

     **フィールド：** `number`\
     **タイプ：**&#x200B;文字列

* 送信者

  **フィールド：** `sender`\
  **タイプ：**&#x200B;オブジェクト

   * 数値

     **フィールド：** `numbers`\
     **型：**&#x200B;文字列の配列

+++

+++ _experience > customerJourneyManagement > messageExecution

**フィールド：** `messageExecution`\
**タイプ：**&#x200B;オブジェクト

* オーディエンス

  **フィールド：** `audience`\
  **タイプ：**&#x200B;オブジェクト

   * ID

     **フィールド：** `id`\
     **タイプ：**&#x200B;文字列

   * タイプ

     **フィールド：** `type`\
     **タイプ：**&#x200B;文字列

* fragmentPublicationID

  **フィールド：** `fragmentPublicationIDs`\
  **型：**&#x200B;文字列の配列

* メタデータ

  **フィールド：** `metadata`\
  **種類：** マップ

   * [ マップ キー]

     **タイプ：**&#x200B;文字列

* parentSourceMeta

  **フィールド：** `parentSourceMeta`\
  **タイプ：**&#x200B;オブジェクト

   * sourceActionID

     **フィールド：** `sourceActionID`\
     **タイプ：**&#x200B;文字列

   * sourceID

     **フィールド：** `sourceID`\
     **タイプ：**&#x200B;文字列

   * sourceType

     **フィールド：** `sourceType`\
     **タイプ：**&#x200B;文字列

   * sourceVersionID

     **フィールド：** `sourceVersionID`\
     **タイプ：**&#x200B;文字列

* batchInstanceID

  **フィールド：** `batchInstanceID`\
  **タイプ：**&#x200B;文字列

* campaignActionID

  **フィールド：** `campaignActionID`\
  **タイプ：**&#x200B;文字列

* campaignID

  **フィールド：** `campaignID`\
  **タイプ：**&#x200B;文字列

* campaignVersionID

  **フィールド：** `campaignVersionID`\
  **タイプ：**&#x200B;文字列

* journeyActionID

  **フィールド：** `journeyActionID`\
  **タイプ：**&#x200B;文字列

* journeyVersionID

  **フィールド：** `journeyVersionID`\
  **タイプ：**&#x200B;文字列

* journeyVersionInstanceID

  **フィールド：** `journeyVersionInstanceID`\
  **タイプ：**&#x200B;文字列

* journeyVersionNodeID

  **フィールド：** `journeyVersionNodeID`\
  **タイプ：**&#x200B;文字列

* messageExecutionID

  **フィールド：** `messageExecutionID`\
  **タイプ：**&#x200B;文字列

* messageID

  **フィールド：** `messageID`\
  **タイプ：**&#x200B;文字列

* messagePublicationID

  **フィールド：** `messagePublicationID`\
  **タイプ：**&#x200B;文字列

* messageType

  **フィールド：** `messageType`\
  **タイプ：**&#x200B;文字列

* waveID

  **フィールド：** `waveID`\
  **タイプ：**&#x200B;文字列

+++

+++ _experience > customerJourneyManagement > messageProfile

**フィールド：** `messageProfile`\
**タイプ：**&#x200B;オブジェクト

* チャネル

  **フィールド：** `channel`\
  **タイプ：**&#x200B;オブジェクト

   * contentTypes

     **フィールド：** `contentTypes`\
     **型：**&#x200B;文字列の配列

   * locationTypes

     **フィールド：** `locationTypes`\
     **型：**&#x200B;文字列の配列

   * metricTypes

     **フィールド：** `metricTypes`\
     **型：**&#x200B;文字列の配列

   * _id

     **フィールド：** `_id`\
     **タイプ：**&#x200B;文字列

   * _type

     **フィールド：** `_type`\
     **タイプ：**&#x200B;文字列

   * mediaAction

     **フィールド：** `mediaAction`\
     **タイプ：**&#x200B;文字列

   * mediaType

     **フィールド：** `mediaType`\
     **タイプ：**&#x200B;文字列

   * mode

     **フィールド：** `mode`\
     **タイプ：**&#x200B;文字列

   * referringSource

     **フィールド：** `referringSource`\
     **タイプ：**&#x200B;文字列

   * typeAtSource

     **フィールド：** `typeAtSource`\
     **タイプ：**&#x200B;文字列

* isSendTimeOptimized

  **フィールド：** `isSendTimeOptimized`\
  **型：** ブール値

* isTestExecution

  **フィールド：** `isTestExecution`\
  **型：** ブール値

* messageProfileID

  **フィールド：** `messageProfileID`\
  **タイプ：**&#x200B;文字列

* messageProfileTrackingID

  **フィールド：** `messageProfileTrackingID`\
  **タイプ：**&#x200B;文字列

* requestID

  **フィールド：** `requestID`\
  **タイプ：**&#x200B;文字列

* secondaryDimensionID

  **フィールド：** `secondaryDimensionID`\
  **タイプ：**&#x200B;文字列

* secondaryDimensionName

  **フィールド：** `secondaryDimensionName`\
  **タイプ：**&#x200B;文字列

* バリアント

  **フィールド：** `variant`\
  **タイプ：**&#x200B;文字列

+++

+++ _experience > customerJourneyManagement > messageRenderedContent

**フィールド：** `messageRenderedContent`\
**タイプ：**&#x200B;オブジェクト

* emailContent

  **フィールド：** `emailContent`\
  **タイプ：**&#x200B;オブジェクト

   * html

     **フィールド：** `html`\
     **タイプ：**&#x200B;文字列

   * 件名

     **フィールド：** `subject`\
     **タイプ：**&#x200B;文字列

   * テキスト

     **フィールド：** `text`\
     **タイプ：**&#x200B;文字列

* smsContent

  **フィールド：** `smsContent`\
  **タイプ：**&#x200B;オブジェクト

   * メディア

     **フィールド：** `media`\
     **タイプ：**&#x200B;文字列

   * message

     **フィールド：** `message`\
     **タイプ：**&#x200B;文字列

   * タイトル

     **フィールド：** `title`\
     **タイプ：**&#x200B;文字列

+++

+++ identityMap

**フィールド：** `identityMap`\
**種類：** マップ

* [ マップ キー]

  **タイプ：** オブジェクトの配列

   * authenticatedState

     **フィールド：** `authenticatedState`\
     **タイプ：**&#x200B;文字列

   * ID

     **フィールド：** `id`\
     **タイプ：**&#x200B;文字列

   * プライマリ

     **フィールド：** `primary`\
     **型：** ブール値

+++

+++ eventType

**フィールド：** `eventType`\
**タイプ：**&#x200B;文字列

+++

+++ producedBy

**フィールド：** `producedBy`\
**タイプ：**&#x200B;文字列

+++

+++ タイムスタンプ

**フィールド：** `timestamp`\
**種類：**&#x200B;日時

+++

