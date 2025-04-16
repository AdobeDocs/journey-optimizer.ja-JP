---
solution: Journey Optimizer
product: journey optimizer
title: ランディングページプリセットの定義
description: Journey Optimizer でランディングページを作成および使用するための環境を設定する方法を説明します。
feature: Landing Pages, Channel Configuration
role: Admin
level: Experienced
keywords: ランディング, ランディングページ, 設定, 環境, サブドメイン, プリセット
exl-id: 7cf1f083-bef0-40b5-8ddd-920a9d108eca
source-git-commit: 8e5a904f9310385f5a8186159dedde9942624268
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 56%

---

# ランディングページプリセットの定義 {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain_header"
>title="ランディングページプリセットの作成"
>abstract="ランディングページを構築して Journey Optimizer 全体で利用するには、使用するサブドメインを含むランディングページプリセットを作成する必要があります。"

## Get started with landing page presets {#gs-lp-presets}

When [creating a landing page](../landing-pages/create-lp.md#create-a-lp), you must select a landing page preset to be able to build the landing page and leverage it through **[!DNL Journey Optimizer]**. The preset includes the subdomain to use for the landing pages based on this preset.

Before creating a preset, ensure you have previously configured at least one landing page subdomain. [Learn how to create a landing page subdomain](lp-subdomains.md).

## ランディングページプリセットへのアクセス {#access-lp-presets}

To access landing page presets, follow the steps below:

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL ランディングページ設定]**／**[!UICONTROL ランディングページプリセット]**&#x200B;を選択します。

   ![](assets/lp_presets-access.png)

1. 任意のプリセットラベルをクリックして、ランディングページプリセットの詳細にアクセスします。

   ![](assets/lp_preset-details.png)

## ランディングページプリセットの作成 {#lp-create-preset}

To create a landing page preset, follow the steps below:

1. Browse the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** menu, then select **[!UICONTROL Landing page settings]** > **[!UICONTROL Landing page presets]**.

1. 「**[!UICONTROL ランディングページプリセットを作成]**」を選択します。

   ![](assets/lp_create-preset-temp.png)

1. プリセットの名前と説明を入力します。

   Names must begin with a letter (A-Z), and only contain alpha-numeric characters, underscore `_`, dot`.` and hyphen `-` characters.

1. ドロップダウンリストからランディングページのサブドメインを選択します。

   ![](assets/lp_preset-subdomain.png)

   To be able to select a subdomain, ensure you have previously configured at least one landing page subdomain. [方法](#lp-subdomains)

   選択したサブドメインに対応する設定が表示されます。

1. You can select the landing page subdomain for the tracking URL by checking the **[!UICONTROL Same as landing page subdomain]** option. [ トラッキングの詳細情報 ](../email/message-tracking.md)

   ![](assets/lp_preset-subdomain-settings-same.png)

   例えば、ランディングページの URL が「pages.mail.luma.com」で、トラッキング URL が「data.mail.luma.com」の場合、トラッキングサブドメインとして「pages.mail.luma.com」を使用するように選択できます。

1. 「**[!UICONTROL 送信]**」をクリックして、ランディングページプリセットの作成を確定します。<!--You can also save the preset as draft and resume its configuration later on.-->

   <!--![](assets/lp_preset-subdomain-settings-submit.png)-->

1. ランディングページプリセットが作成されると、リストに「**[!UICONTROL アクティブ]**」のステータスで表示されます。これで、ランディングページで使用する準備が整いました。

これで、[!DNL Journey Optimizer] で[ランディングページの作成](../landing-pages/create-lp.md)を行う準備が整いました。
<!--
>[!NOTE]
>
>Learn how to create channel configurations for push notifications and emails in [this section](channel-surfaces.md).-->

**関連トピック**:

* [ランディングページの基本を学ぶ](../landing-pages/get-started-lp.md)
* [ランディングページの作成](../landing-pages/create-lp.md#create-a-lp)
