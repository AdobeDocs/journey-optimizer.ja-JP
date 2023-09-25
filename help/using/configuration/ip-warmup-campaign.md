---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアップキャンペーンを作成
description: IP ウォームアップキャンペーンの作成方法を説明します
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
keywords: IP、プール、配信品質
hide: true
hidefromtoc: true
source-git-commit: b3e5a825b881736516b3bcd1d368843c3a601100
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 6%

---

# IP ウォームアップキャンペーンを作成 {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="IP ウォームアッププランオプションを有効にする"
>abstract="このオプションを選択すると、キャンペーンを IP ウォームアッププランで使用できます。 その後、キャンペーンスケジュールは、関連付けられている IP ウォームアッププランによって実行されます。"

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* **[IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)**
* [IP ウォームアッププランを作成する](ip-warmup-plan.md)
* [IP ウォームアッププランを実行します。](ip-warmup-execution.md)

>[!ENDSHADEBOX]

IP ウォームアッププランを作成する前に、 [!DNL Journey Optimizer]を使用する場合、まず、専用のオプションを有効にして 1 つ以上のキャンペーンを作成し、IP ウォームアッププランで使用できるようにする必要があります。

IP ウォームアップキャンペーンを作成するには、次の手順に従います。

1. の作成 [電子メール](../email/email-settings.md) チャネル [表面](channel-surfaces.md) ウォームアッププランで特定したドメインと IP。

   >[!NOTE]
   >
   >で E メールサーフェスで使用するドメインと IP を選択する方法を説明します。 [この節](../email/email-settings.md#subdomains-and-ip-pools).
   >
   >配信品質コンサルタントと協力して、IP ウォームアッププランに使用するドメインと IP を特定します。<!--TBC-->

1. の作成 [campaign](../campaigns/create-campaign.md) をクリックし、 [電子メール](../email/create-email.md#create-email-journey-campaign) アクション。

1. IP ウォームアップ用に作成したサーフェスを選択します。

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 次から： **[!UICONTROL スケジュール]** セクション、選択 **[!UICONTROL IP ウォームアッププランの有効化]**.

   ![](assets/ip-warmup-campaign-plan-activation.png)

   キャンペーン [スケジュール](../campaigns/create-campaign.md#schedule) が、関連付けられる IP ウォームアッププランによって駆動されます。つまり、スケジュールはキャンペーン自体で定義されなくなります。

1. キャンペーンプロパティの定義など、E メールキャンペーンを作成する手順を実行します。 [audience](../audience/about-audiences.md)<!--best practices for IP warmup in terms of audience?-->、および [コンテンツ](../email/get-started-email-design.md#key-steps).

   >[!NOTE]
   >
   >キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

1. [有効化](../campaigns/review-activate-campaign.md) キャンペーン。

   >[!NOTE]
   >
   >IP ウォームアッププランが有効化されたライブキャンペーンの場合、 **[!UICONTROL 削除]** ボタンは、IP ウォームアッププランに関連付けられるまで使用できます。 プランで使用すると、キャンペーンは削除できなくなります。

1. キャンペーンが **[!UICONTROL キャンペーン]** リスト。 現在のサンドボックスで作成されたすべての IP ウォームアップキャンペーンを簡単に取得するには、 **[!UICONTROL IP ウォームアップ]** キャンペーンオプション。

   ![](assets/ip-warmup-campaign-filter.png)

ライブが完了すると、キャンペーンは IP ウォームアッププランで使用できる状態になります。 [詳細情報](ip-warmup-plan.md)

<!--Any recommendations when defining an audience? i.e do you have to include all your database or a limited number or according to your Excel file?-->

