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
source-git-commit: a5ee7c668b51a761266b50216047caf48496f678
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 57%

---

# Adobe Campaign Standard との統合 {#using_adobe_campaign_standard}

Adobe Campaign Standardがある場合は、組み込みのアクションを使用して、Adobe Campaign Standardに接続できます。 Adobe Campaign Standard のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できます。

Journey Optimizer で使用するには、Campaign Standard トランザクションメッセージとそれに関連するイベントを公開する必要があります。イベントが公開されてもメッセージが表示されない場合、Journey Optimizer インターフェイスには表示されません。メッセージが公開されても、関連するイベントが公開されなかった場合、Journey Optimizer インターフェイスには表示されますが、使用はできません。

## 重要な注意事項 {#important-notes}

* Adobe Campaign Standard のアクションに対して、5 分あたり 4,000 回の呼び出しのキャッピングルールが自動的に定義されます。これは、Adobe Campaign Standard トランザクションメッセージの公式な規模に対応しています。トランザクションメッセージ SLA の詳細については、[Adobe Campaign Standard 製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html){target="_blank"}を参照してください。

* Adobe Campaign Standard 統合は、アクションリストの専用組み込みアクションを使用して設定されます。これは、サンドボックスごとに設定する必要があります。

* 「オーディエンスの選定」または「オーディエンスを読み取り」アクティビティでは、Campaign Standard アクションを使用できません。

* ジャーニーは、メッセージアクションと Campaign Standard アクションの両方が使用できません。

## アクションの設定 {#configure-action}

Journey Optimizerでは、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。 次の手順に従います。

1. 管理メニューセクションで **[!UICONTROL 設定]** を選択します。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。アクションのリストが表示されます。

1. 組み込み **[!UICONTROL AdobeCampaignStandard]** アクションを選択します。画面右側にアクション設定ペインが開きます。

   ![](assets/actioncampaign.png)

1. Adobe Campaign Standard インスタンスの URL をコピーし、「**[!UICONTROL URL]**」フィールドにペーストします。

1. 「**[!UICONTROL インスタンス URL をテスト]**」をクリックし、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを検証します。
   >
   >* ホストは、「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です
   >
   >* https で始まる URL
   >
   >* このAdobe Campaign Standardのインスタンスに関連付けられている組織が、Journey Optimizerの OoRg と同じです

この設定が完了すると、ジャーニーを設計する際に、**[!UICONTROL アクション]** カテゴリで **[!UICONTROL メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]** の 3 つのアクションが使用できるようになります。 [ 使用方法を説明します ](../building-journeys/using-adobe-campaign-standard.md)。

![](assets/journey58.png)

**反応** イベントを使用して、同じジャーニー内で送信されるCampaign Standard メッセージに関連するトラッキングデータに反応します。

* プッシュ通知の場合、ジャーニーは、メッセージのクリック、送信、失敗に反応できます。

* SMS メッセージの場合、ジャーニーは、送信されたメッセージや失敗したメッセージに反応できます。

* メールの場合、ジャーニーは、メッセージのクリック、送信、開封、失敗に反応できます。 [ 反応イベントの詳細はこちらを参照 ](../building-journeys/reaction-events.md)。

サードパーティシステムを使用してメッセージを送信する場合は、カスタムアクションを追加して設定する必要があります。 [ カスタムアクション設定の詳細情報 ](../action/about-custom-action-configuration.md)。