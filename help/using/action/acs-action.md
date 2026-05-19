---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign Standard との統合
description: Journey Optimizer を Adobe Campaign Standard と統合する方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Developer, Admin
level: Intermediate
keywords: キャンペーン, Standard, 統合, キャップ, アクション
exl-id: 2f0218c9-e1b1-44ba-be51-15824b9fc6d2
TQID: https://experienceleague.adobe.com/1JQFfviWGc3OXYN0YdAh0Koaboro2wJU8HpEf75PoKQ
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 450
ht-degree: 100%

---

# Adobe Campaign Standard との統合 {#using_adobe_campaign_standard}

Adobe Campaign Standard がある場合は、ビルトインのアクションを使用して、Adobe Campaign Standard に接続できます。 Adobe Campaign Standard のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS を送信できます。

Journey Optimizer で使用するには、Campaign Standard トランザクションメッセージとそれに関連するイベントを公開する必要があります。 イベントが公開されてもメッセージが表示されない場合、Journey Optimizer インターフェイスには表示されません。 メッセージが公開されても、関連するイベントが公開されなかった場合、Journey Optimizer インターフェイスには表示されますが、使用はできません。

## ガードレールと制限 {#important-notes}

* Adobe Campaign Standard のアクションに対して、5 分あたり 4,000 回の呼び出しのキャップルールが自動的に定義されます。 トランザクションメッセージ SLA の詳細については、[Adobe Campaign Standard 製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html){target="_blank"}を参照してください。

* Adobe Campaign Standard 統合は、アクションリストの専用ビルトインのアクションを使用して設定されます。 これは、サンドボックスごとに設定する必要があります。

* 「オーディエンスの選定」または「オーディエンスを読み取り」アクティビティでは、Campaign Standard アクションを使用できません。

* 1 つのジャーニーで、[ビルトインのチャネルアクション](../building-journeys/journey-action.md)と [Campaign Standard アクション](../building-journeys/using-adobe-campaign-standard.md)の両方を使用することはできません。

## アクションの設定 {#configure-action}

Journey Optimizer では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。

Campaign Standard アクションを設定するには、次の手順に従います。

1. 「管理」メニューセクションで「**[!UICONTROL 設定]**」を選択します。

1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。 アクションのリストが表示されます。

1. ビルトインの **[!UICONTROL AdobeCampaignStandard]** アクションを選択します。 画面右側にアクション設定ペインが開きます。

   ![](assets/actioncampaign.png)

1. Adobe Campaign Standard インスタンスの URL をコピーし、「**[!UICONTROL URL]**」フィールドにペーストします。

1. 「**[!UICONTROL インスタンス URL をテスト]**」をクリックし、インスタンスの有効性をテストします。

   >[!NOTE]
   >
   >このテストでは、次のことを検証します。
   >
   >* ホストは「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」または「.adls.adobe.com」です。
   >
   >* https で始まる URL
   >
   >* この Adobe Campaign Standard インスタンスに関連付けられている組織は、Journey Optimizer 組織と同じです。

この設定が完了すると、ジャーニーを設計する際に、**[!UICONTROL アクション]**&#x200B;カテゴリで&#x200B;**[!UICONTROL メール]**、**[!UICONTROL プッシュ]**、**[!UICONTROL SMS]** の 3 つのアクションが使用できます。 [使用方法の詳細情報](../building-journeys/using-adobe-campaign-standard.md)

![](assets/journey58.png)

**反応**&#x200B;イベントを使用して、同じジャーニー内で送信される Campaign Standard メッセージに関連するトラッキングデータに反応します。

* プッシュ通知では、ジャーニーはメッセージのクリック、送信、失敗に反応できます。

* SMS メッセージでは、ジャーニーはメッセージの送信と失敗に反応できます。

* メールでは、ジャーニーはメッセージのクリック、送信、開封、失敗に反応できます。 [反応イベントの詳細情報](../building-journeys/reaction-events.md)

サードパーティのシステムを使用してメッセージを送信する場合は、カスタムアクションを追加および設定する必要があります。 [カスタムアクション設定の詳細情報](../action/about-custom-action-configuration.md)