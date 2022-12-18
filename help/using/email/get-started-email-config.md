---
solution: Journey Optimizer
product: journey optimizer
title: メール設定の基本を学ぶ
description: 電子メール設定について詳しくは、 [!DNL Journey Optimizer]
role: Admin
level: Intermediate
feature: Application Settings
topic: Administration
exl-id: 1fc9a4f6-6c34-4414-b400-aac6bda9ee25
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 37%

---

# メール設定の基本を学ぶ {#get-starte-email-config}

でジャーニーやキャンペーンを通じて E メールを送信できるようにする [!DNL Journey Optimizer]を使用する場合は、いくつかの設定手順を実行する必要があります。

1. 最適な配信品質を確保し、レピュテーションを保護するには、まず、E メールの送信に使用するサブドメインをAdobeにデリゲートします [!DNL Journey Optimizer]. これらのサブドメインによって、追跡する Web ページやミラーページの URL などの要素が決まります。 [詳細情報](../configuration/about-subdomain-delegation.md)

   ![](../configuration/assets/subdomain-list.png)

1. インスタンスでプロビジョニングされた IP アドレスをグループ化することで、E メールの配信品質とレピュテーションを向上させます。 [詳細情報](../configuration/ip-pools.md)

   ![](../configuration/assets/ip-pool-create.png)

1. チャネルサーフェスを作成し、 **[!UICONTROL 電子メール]** チャネル。 [詳細情報](../configuration/channel-surfaces.md)


   ![](../configuration/assets/preset-general.png)

1. 各 E メールチャネルの表面で、E メールの配信に必要なすべての技術的パラメーターを設定します。 [詳細情報](email-settings.md)

   * ここで、E メールの送信に使用するサブドメインと、サーフェスに関連付ける IP プールを選択します。 [詳細情報](email-settings.md#subdomains-and-ip-pools)

   ![](assets/preset-subdomain-ip-pool.png)

   * **[!UICONTROL 送信者メール]**&#x200B;および&#x200B;**[!UICONTROL エラーメール]**&#x200B;アドレスでは、現在選択されているデリゲートされたサブドメインを使用する必要があります。[詳細](email-settings.md#email-header)

   ![](assets/preset-header.png)

1. Adobe Experience Platform で使用可能なアドレスが複数ある場合、受信者に優先して使用するメールアドレスを決定します。[詳細](../configuration/primary-email-addresses.md)

   ![](../configuration/assets/primary-address-execution-fields.png)

1. 抑制リストにメールアドレスを送信する前に再試行が実行される日数を管理します。[詳細](../configuration/manage-suppression-list.md)

   ![](../configuration/assets/suppression-list-edit-retries.png)
