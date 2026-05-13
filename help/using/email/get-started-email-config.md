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
TQID: https://experienceleague.adobe.com/mVdk2WGb0rL06j1cmNEh4fj0JC-hwuro8ku-0Yv02N8
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: cf64c7f6-7428-4ae5-b158-8df9771f38f4id: e30b0a1a-b594-47b8-af94-1e3a2be6df11id: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: fae48155-b23f-40d2-a252-a25bce350b4d
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 84%

---

# メール設定の基本を学ぶ {#get-starte-email-config}

[!DNL Journey Optimizer] でジャーニーとキャンペーンを通じてメールを送信できるようにするには、いくつかの設定手順を完了する必要があります。

1. 最適な配信品質を確保しレピュテーションを保護するには、まず [!DNL Journey Optimizer] でメールを送信するのに使用する&#x200B;**サブドメインをアドビにデリゲート**&#x200B;します。 これらのサブドメインによって、追跡する web ページやミラーページの URL などの要素が決まります。 [詳細情報](../configuration/about-subdomain-delegation.md)

   ![](../configuration/assets/subdomain-list.png)

1. IP プールを作成して、インスタンスでプロビジョニングされた **IP アドレスをグループ化**&#x200B;します。 [詳細情報](../configuration/ip-pools.md)

   ![](../configuration/assets/ip-pool-create.png)

1. **チャネル設定**&#x200B;を作成し、**[!UICONTROL メール]**&#x200B;チャネルを選択します。 [詳細情報](../configuration/channel-surfaces.md)


   ![](../configuration/assets/preset-general.png)

1. 各メールチャネル設定で、メールの配信に必要なすべての&#x200B;**技術的パラメーター**&#x200B;を設定します。 [詳細情報](email-settings.md)

   * ここで、メールの送信に使用するサブドメインと、設定に関連付ける IP プールを選択します。 [詳細情報](email-settings.md#ip-pools)

   ![](assets/surface-subdomain-ip-pool.png)

   * **[!UICONTROL 送信元メールプレフィックス]**&#x200B;および&#x200B;**[!UICONTROL エラーメールプレフィックス]**&#x200B;は、現在選択されている[ デリゲートされたサブドメイン ](../configuration/about-subdomain-delegation.md)を使用しています。 オプションとして、**[!UICONTROL 送信者の名前]**&#x200B;と&#x200B;**[!UICONTROL 送信者の電子メール]**&#x200B;は、異なる送信者を識別できます（完全な&#x200B;**送信者** アドレス、そのサブドメインサフィックスに関連付けられていません）。 [詳細情報](header-parameters.md#sender-header)

   ![](assets/preset-header.png)

1. Adobe Experience Platform で使用可能なアドレスが複数ある場合、受信者に優先して使用する&#x200B;**実行フィールド**&#x200B;を決定します。 [詳細情報](../configuration/primary-email-addresses.md)

   ![](../configuration/assets/primary-address-execution-fields.png)

1. 抑制リストにメールアドレスを送信するまでに&#x200B;**再試行**&#x200B;を実行する日数を管理します。 [詳細情報](../configuration/manage-suppression-list.md)

   ![](../configuration/assets/suppression-list-edit-retries.png)
