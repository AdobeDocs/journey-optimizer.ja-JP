---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアップキャンペーンを作成
description: IP ウォームアップキャンペーンの作成方法を説明します
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP、プール、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
source-git-commit: 53be033ff0474cbafff71ed36194c18627234fd4
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 8%

---

# IP ウォームアップキャンペーンを作成 {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="IP ウォームアッププランオプションを有効にする"
>abstract="IP ウォームアッププランの有効化オプションを選択します。 キャンペーンがライブになると、IP ウォームアッププランに関連付けることができます。"

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* **[IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)**
* [IP ウォームアッププランを作成する](ip-warmup-plan.md)
* [IP ウォームアッププランを実行する](ip-warmup-running.md)

>[!ENDSHADEBOX]

IP ウォームアッププランで使用できるよう、特定のオプションを有効にした 1 つ以上のキャンペーンを作成する必要があります。

IP ウォームアップキャンペーンを作成するには、次の手順に従います。

1. E メールの作成 [表面](channel-surfaces.md) ウォームアッププランで特定したドメインと IP。<!--how do you identify these or who does it at the customer level?-->

   >[!NOTE]
   >
   >で E メールサーフェスで使用するドメインと IP を選択する方法を説明します。 [この節](using/email/email-settings.md#subdomains-and-ip-pools).

1. の作成 [campaign](../campaigns/create-campaign.md) をクリックし、 [電子メール](../email/create-email.md#create-email-journey-campaign) アクション。

1. IP ウォームアップ用に作成したサーフェスを選択します。

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 次から： **[!UICONTROL スケジュール]** セクション、選択 **[!UICONTROL IP ウォームアッププランの有効化]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   キャンペーン [スケジュール](../campaigns/create-campaign.md#schedule) それは [IP ウォームアッププラン](ip-warmup-plan.md) これはに関連付けられます。つまり、スケジュールはキャンペーン自体で定義されなくなります。

1. [有効化](../campaigns/review-activate-campaign.md) キャンペーン。 ライブが完了すると、IP ウォームアッププランで使用できる状態になります。

>[!NOTE]
>
>IP ウォームアッププランが有効化されたライブキャンペーンの場合、 **[!UICONTROL 削除]** ボタンは、IP ウォームアッププランに関連付けられるまで使用できます。

キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

