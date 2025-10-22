---
solution: Journey Optimizer
product: journey optimizer
title: メール設定の基本を学ぶ
description: 詳しくは、 [!DNL Journey Optimizer] でのメール設定を参照してください
role: Admin
level: Experienced
feature: Channel Configuration, Email
topic: Administration
keywords: メール, 設定, サーフェス, サブドメイン
exl-id: 1fc9a4f6-6c34-4414-b400-aac6bda9ee25
source-git-commit: ea8f77c2821bfae7b853b3ac39ea22f0d19ae43d
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 62%

---

# メール設定の基本を学ぶ {#get-starte-email-config}

[!DNL Journey Optimizer] でジャーニーとキャンペーンを通じてメールを送信できるようにするには、いくつかの設定手順を完了する必要があります。

1. 最適な配信品質を確保しレピュテーションを保護するには、まず **サブドメインをAdobeにデリゲート** して、を使用して [!DNL Journey Optimizer] でメールを送信します。 これらのサブドメインによって、追跡する web ページやミラーページの URL などの要素が決まります。[詳細情報](../configuration/about-subdomain-delegation.md)

   ![](../configuration/assets/subdomain-list.png)

1. インスタンスでプロビジョニングされた IP プールを作成 **IP アドレスをグループ化** します。 [詳細情報](../configuration/ip-pools.md)

   ![](../configuration/assets/ip-pool-create.png)

1. **チャネル設定** を作成し、**[!UICONTROL メール]** チャネルを選択します。 [詳細情報](../configuration/channel-surfaces.md)


   ![](../configuration/assets/preset-general.png)

1. 各メールチャネル設定で、メールの配信に必要なすべての **技術的パラメーター** を設定します。 [詳細情報](email-settings.md)

   * ここで、メールの送信に使用するサブドメインと、設定に関連付ける IP プールを選択します。[詳細情報](email-settings.md#subdomains-and-ip-pools)

   ![](assets/surface-subdomain-ip-pool.png)

   * **[!UICONTROL 送信者メール]**&#x200B;および&#x200B;**[!UICONTROL エラーメール]**&#x200B;アドレスでは、現在選択されているデリゲートされたサブドメインを使用する必要があります。[詳細情報](email-settings.md#email-header)

   ![](assets/preset-header.png)

1. Adobe Experience Platformで使用可能なアドレスが複数ある場合、受信者に優先して使用する **実行フィールド** を決定します。 [詳細情報](../configuration/primary-email-addresses.md)

   ![](../configuration/assets/primary-address-execution-fields.png)

1. 抑制リストにメールアドレスを送信するまでに&#x200B;**再試行**&#x200B;を実行する日数を管理します。[詳細情報](../configuration/manage-suppression-list.md)

   ![](../configuration/assets/suppression-list-edit-retries.png)
