---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアップキャンペーンを作成
description: IP ウォームアップキャンペーンの作成方法を学ぶ
feature: Channel Configuration
topic: Administration
role: Admin
level: Intermediate
keywords: IP, プール, 配信品質
hide: true
hidefromtoc: true
exl-id: a9995ca1-d7eb-4f8d-a9d9-fe56198ac325
source-git-commit: 82c189545ab4f37a2e4b1044c0b8cfeb539aed13
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 100%

---

# IP ウォームアップキャンペーンを作成 {#create-ip-warmup-campaign}

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="IP ウォームアッププランオプションを有効にする"
>abstract="このオプションを選択すると、キャンペーンを IP ウォームアッププランで使用できます。その後、キャンペーンスケジュールは、関連付けられている IP ウォームアッププランによって実行されます。"

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* **[IP ウォームアップキャンペーンの作成](ip-warmup-campaign.md)**
* [IP ウォームアッププランを作成](ip-warmup-plan.md)
* [IP ウォームアッププランを実行](ip-warmup-execution.md)

>[!ENDSHADEBOX]

[!DNL Journey Optimizer] で IP ウォームアッププランを作成する前に、まず、専用のオプションを有効にして 1 つ以上のキャンペーンを作成し、IP ウォームアッププランで使用できるようにする必要があります。

IP ウォームアップキャンペーンを作成するには、次の手順に従います。

1. ウォームアッププランで特定したドメインおよび IP の[メール](../email/email-settings.md)チャネル[サーフェス](channel-surfaces.md)を作成します。

   >[!NOTE]
   >
   >[この節](../email/email-settings.md#subdomains-and-ip-pools)では、メールサーフェスで使用するドメインと IP を選択する方法について説明します。
   >
   >配信品質コンサルタントと協力して、IP ウォームアッププランに使用するドメインと IP を特定します。<!--TBC-->

1. [キャンペーン](../campaigns/create-campaign.md)を作成し、[メール](../email/create-email.md#create-email-journey-campaign)アクションを選択します。

1. IP ウォームアップ用に作成したサーフェスを選択します。

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same surface as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 「**[!UICONTROL スケジュール]**」セクションから、「**[!UICONTROL IP ウォームアッププランのアクティブ化]**」を選択します。

   ![](assets/ip-warmup-campaign-plan-activation.png)

   キャンペーン[スケジュール](../campaigns/create-campaign.md#schedule)が、関連付けられる IP ウォームアッププランによって実行されます。つまり、スケジュールはキャンペーン自体で定義されなくなります。

1. キャンペーンプロパティ、[オーディエンス](../audience/about-audiences.md)<!--best practices for IP warmup in terms of audience?-->、[コンテンツ](../email/get-started-email-design.md#key-steps)など、メールキャンペーンを作成する手順を完了します。

   >[!NOTE]
   >
   >キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

1. キャンペーンの[アクティブ化](../campaigns/review-activate-campaign.md)

   >[!NOTE]
   >
   >IP ウォームアッププランが有効化されたライブキャンペーンの場合、**[!UICONTROL 削除]**&#x200B;ボタンは、IP ウォームアッププランに関連付けられるまで使用できます。プランで使用すると、キャンペーンは削除できなくなります。

1. キャンペーンが&#x200B;**[!UICONTROL キャンペーン]**&#x200B;リストに表示されます。現在のサンドボックスで作成されたすべての IP ウォームアップキャンペーンを簡単に取得するには、**[!UICONTROL IP ウォームアップ]**&#x200B;キャンペーンオプションでフィルタリングできます。

   ![](assets/ip-warmup-campaign-filter.png)

ライブになると、キャンペーンは IP ウォームアッププランで使用できる状態になります。[詳細情報](ip-warmup-plan.md)

<!--Any recommendations when defining an audience? i.e do you have to include all your database or a limited number or according to your Excel file?-->
