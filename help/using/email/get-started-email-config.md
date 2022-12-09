---
solution: Journey Optimizer
product: journey optimizer
title: 電子メール設定を使用した作業の開始
description: での電子メール設定について詳しくは、 [!DNL Journey Optimizer]
role: Admin
level: Intermediate
feature: Application Settings
topic: Administration
exl-id: 1fc9a4f6-6c34-4414-b400-aac6bda9ee25
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# 電子メール設定を使用した作業の開始 {#get-starte-email-config}

で [!DNL Journey Optimizer] journeys およびキャンペーンを使用して電子メールを送信するには、いくつかの設定手順を実行する必要があります。

1. 最適な [!DNL Journey Optimizer] deliverability と評判を確保するには、電子メールを送信するのに使用するサブドメインを Adobe に委任します。 これらのサブドメインは、トラックされる web ページやミラーページの Url などの要素を識別します。 [詳細情報](../configuration/about-subdomain-delegation.md)

   ![](../configuration/assets/subdomain-list.png)

1. インスタンスにプロビジョニングされた IP アドレスをグループ化することによって、電子メールの deliverability と評判を向上させることができます。 [詳細情報](../configuration/ip-pools.md)

   ![](../configuration/assets/ip-pool-create.png)

1. チャンネルのサーフェスを作成し、 **[!UICONTROL Email]** チャンネルを選択します。 [詳細情報](../configuration/channel-surfaces.md)


   ![](../configuration/assets/preset-general.png)

1. 電子メールチャンネルの各面に、電子メールを配信するために必要なすべての技術的なパラメーターを設定します。 [詳細情報](email-settings.md)

   * ここでは、電子メールを送信するサブドメインと、そのサーフェスに関連付ける IP プールを選択します。 [詳細情報](email-settings.md#subdomains-and-ip-pools)

   ![](assets/preset-subdomain-ip-pool.png)

   * And **[!UICONTROL Error email]** アドレスには **[!UICONTROL Sender email]** 、現在選択されている委任サブドメインを使用する必要があります。[詳細情報](email-settings.md#email-header)

   ![](assets/preset-header.png)

1. Adobe エクスペリエンスプラットフォームで複数のアドレスを利用できるようになった場合に、宛先にどの電子メールアドレスを使用するかを指定します。 [詳細情報](../configuration/primary-email-addresses.md)

   ![](../configuration/assets/primary-address-execution-fields.png)

1. 電子メールアドレスを抑制リストに送信する前にリトライが実行される日数を管理します。 [詳細情報](../configuration/manage-suppression-list.md)

   ![](../configuration/assets/suppression-list-edit-retries.png)
