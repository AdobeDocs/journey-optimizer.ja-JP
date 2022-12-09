---
solution: Journey Optimizer
product: journey optimizer
title: Adobe キャンペーン規格との統合
description: Adobe キャンペーン規格との統合について
feature: Actions
topic: Administration
role: Admin
level: Intermediate
exl-id: 2f0218c9-e1b1-44ba-be51-15824b9fc6d2
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Adobe キャンペーン規格との統合 {#using_adobe_campaign_standard}

Adobe キャンペーン規格のトランザクションメッセ―ジング機能を使用して、電子メール、プッシュ通知、SMS を送信することができます。

Adobe キャンペーン規格に準拠している場合は、Adobe キャンペーン規格への接続が可能なビルトインアクションが用意されています。

このため、旅オプティマイザーで使用するためには、キャンペーン標準のトランザクションメッセージとそれに関連付けられたイベントをパブリッシュする必要があります。 イベントはパブリッシュされても、メッセージが表示されない場合は、旅のオプティマイザーインターフェイスには表示されません。 メッセージがパブリッシュされていても、関連するイベントが公開されていない場合、そのメッセージは、旅のオプティマイザーインターフェイスに表示されますが、使用することはできません。

## 重要な注意事項 {#important-notes}

* 5分間に4000呼び出しの上限規則は、Adobe キャンペーンの標準アクションに自動的に定義されます。 これは、Adobe キャンペーン規格のトランザクションメッセージの正式な拡大率に対応しています。 トランザクションメッセ―ジングについて詳しくは、「Adobe キャンペーン」の「製品概要 ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html) 」を [ 参照してください。

* Adobe キャンペーンの標準統合には、アクションリストに組み込まれた専用のアクションが設定されています。 これは、サンドボックスごとに設定する必要があります。

* セグメント修飾子を使用したキャンペーンや、セグメントの読み取り操作を実行することはできません。

* メッセージとキャンペーンの両方のアクションを使用することはできません。

## アクションの設定 {#configure-action}

これを設定する手順を次に示します。

1. 「管理」メニューの「」を選択 **[!UICONTROL Configurations]** します。 **[!UICONTROL Actions]**&#x200B;セクションのをクリック **[!UICONTROL Manage]** します。アクションのリストが表示されます。

1. 組み込み **[!UICONTROL AdobeCampaignStandard]** アクションを選択します。 画面の右側に、操作設定ウィンドウが表示されます。

   ![](assets/actioncampaign.png)

1. Adobe キャンペーン規格のインスタンス URL をコピーし、フィールドに **[!UICONTROL URL]** ペーストします。

1. **[!UICONTROL Test the instance URL]**&#x200B;をクリックして、インスタンスの妥当性をテストします。

   >[!NOTE]
   >
   >このテストでは次のことが確認されます。
   >
   >ホストは、&quot;campaign.adobe.com&quot;、&quot;campaign-sandbox.adobe.com&quot;、&quot;campaign-demo.adobe.com&quot;、&quot;ats.adobe.com&quot;、&quot;adls.adobe.com&quot; のいずれかです。
   >
   >URL は、https で始まります。
   >
   >この Adobe キャンペーン基準のインスタンスに関連付けられた組織は、旅オプティマイザーの組織と同じです。

旅のデザイン時には、「,,」と **[!UICONTROL Action]** **[!UICONTROL Email]** いう3つのアクションが表示されます。「」を参照 [ ](../building-journeys/using-adobe-campaign-standard.md) してください。 **[!UICONTROL SMS]** **[!UICONTROL Push]**

![](assets/journey58.png)

反力 **イベントを使用** して、同じ旅で送信されたキャンペーン標準メッセージに関連するトラッキングデータに応答することができます。プッシュ通知の場合は、クリックされたメッセージ、送信されたメッセージ、または失敗したメッセージに応答することができます。 SMS メッセージについては、送信されたメッセージまたは失敗したメッセージに応答することができます。 電子メールの場合は、クリック、送信、開封、または失敗メッセージに応答することができます。 反力イベント ](../building-journeys/reaction-events.md) を参照してください [ 。

メッセージを送信するためにサードパーティ製システムを使用している場合は、カスタムアクションを追加して設定する必要があります。 カスタムアクション設定 ](../action/about-custom-action-configuration.md) についてを参照してください [ 。
