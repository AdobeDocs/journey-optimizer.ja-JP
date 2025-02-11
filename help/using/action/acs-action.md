---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign Standard との統合
description: Journey Optimizer を Adobe Campaign Standard と統合する方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate
keywords: キャンペーン, Standard, 統合, キャッピング, アクション
exl-id: 2f0218c9-e1b1-44ba-be51-15824b9fc6d2
source-git-commit: 79bea396ba1ff482aaa4edcab1a31ca3847b3f52
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 97%

---

# Adobe Campaign Standard との統合 {#using_adobe_campaign_standard}

Adobe Campaign Standard のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できます。

Adobe Campaign Standard がある場合は、組み込みのアクションを使用して、Adobe Campaign Standard に接続できます。

Journey Optimizer で使用するには、Campaign Standard トランザクションメッセージとそれに関連するイベントを公開する必要があります。イベントが公開されてもメッセージが表示されない場合、Journey Optimizer インターフェイスには表示されません。メッセージが公開されても、関連するイベントが公開されなかった場合、Journey Optimizer インターフェイスには表示されますが、使用はできません。

## 重要な注意事項 {#important-notes}

* Adobe Campaign Standard のアクションに対して、5 分あたり 4,000 回の呼び出しのキャッピングルールが自動的に定義されます。これは、Adobe Campaign Standard トランザクションメッセージの公式な規模に対応しています。トランザクションメッセージ SLA の詳細については、[Adobe Campaign Standard製品説明 ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html){target="_blank"} を参照してください。

* Adobe Campaign Standard 統合は、アクションリストの専用組み込みアクションを使用して設定されます。これは、サンドボックスごとに設定する必要があります。

* 「オーディエンスの選定」または「オーディエンスを読み取り」アクティビティでは、Campaign Standard アクションを使用できません。

* ジャーニーは、メッセージアクションと Campaign Standard アクションの両方が使用できません。

## アクションの設定 {#configure-action}

次に、設定手順を示します。

1. 「管理メニュー」セクションで「**[!UICONTROL 設定]**」を選択します。「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。アクションのリストが表示されます。

1. 組み込み **[!UICONTROL AdobeCampaignStandard]** アクションを選択します。画面右側にアクション設定ペインが開きます。

   ![](assets/actioncampaign.png)

1. Adobe Campaign Standard インスタンスの URL をコピーし、「**[!UICONTROL URL]**」フィールドにペーストします。

1. 「**[!UICONTROL インスタンス URL をテスト]**」をクリックし、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを検証します。
   >
   >ホストは「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です。
   >
   >https で始まる URL
   >
   >この Adobe Campaign Standard のインスタンスに関連付けられている ORG は、Journey Optimizer の ORG と同じです。

ジャーニーを設計する際、**[!UICONTROL アクション]**&#x200B;カテゴリでは、**[!UICONTROL 電子メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]** の 3 つのアクションが利用可能になります（[Adobe Campaign アクションの使用](../building-journeys/using-adobe-campaign-standard.md)を参照してください)。

![](assets/journey58.png)

**反応**&#x200B;イベントを使用して、同じジャーニー内で送信される Campaign Standard メッセージに関連するトラッキングデータに反応します。プッシュ通知では、メッセージのクリック、送信、失敗に反応できます。SMS メッセージでは、メッセージの送信と失敗に反応できます。メールでは、メッセージのクリック、送信、開封、失敗に反応できます。詳しくは、[反応イベント](../building-journeys/reaction-events.md)を参照してください。

サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを追加および設定する必要があります。[カスタムアクション設定について](../action/about-custom-action-configuration.md)を参照してください。