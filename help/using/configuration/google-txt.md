---
solution: Journey Optimizer
product: journey optimizer
title: サブドメインへの Google TXT レコードの追加
description: サブドメインに Google TXT レコードを追加する方法を説明します
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン, google, txt, レコード, gmail, 配信品質
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 95%

---

# サブドメインへの Google TXT レコードの追加 {#google-txt-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_google"
>title="Google TXT レコード"
>abstract="Gmail アドレス宛ての電子メールを確実に配信するには、サブドメインに特別な Google サイト検証 TXT レコードを追加して、サブドメインが確実に検証されていることを確認します。"

TXT レコードは、ドメインに関するテキスト情報を提供するために使用される DNS レコードの一種で、外部ソースから読み取ることができます。

[!DNL Journey Optimizer] では、Gmail アドレス宛てのメールの最高の配信品質を確保して確実な配信を行うために、サブドメインに Google サイト検証用の特別な TXT レコードを追加して、確実な検証を行えます。

>[!CAUTION]
>
> この操作は、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;の場合にのみ実行できます。サブドメインのステータスについて詳しくは、[この節](about-subdomain-delegation.md#access-delegated-subdomains)を参照してください。

サブドメインに Google TXT レコードを追加するには、次の手順に従います。

1. **[!UICONTROL チャネル]**/**[!UICONTROL メール設定]**/**[!UICONTROL サブドメイン]** メニューからサブドメインを開きます。

1. 「**[!UICONTROL Google txt レコード]**」セクションで、[Google Workspace](https://support.google.com/a/answer/183895){target="_blank"}<!--G Suite Admin tools--> から生成された確認コードを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/subdomain-google-txt.png)

1. TXT レコードを追加したら、Google で検証する必要があります。これを行うには、[Google Workspace](https://support.google.com/a/answer/183895){target="_blank"}<!--G Suite Admin tools--> に移動し、検証手順を開始します。
