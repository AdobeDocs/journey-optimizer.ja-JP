---
title: サブドメインへの Google TXT レコードの追加
description: サブドメインに Google TXT レコードを追加する方法を説明します
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: dcdbf4a0cd6a93e56cbe97535515c1a6143db81b
workflow-type: ht
source-wordcount: '180'
ht-degree: 100%

---

# サブドメインへの Google TXT レコードの追加 {#google-txt-record}

TXT レコードは、ドメインに関するテキスト情報を提供するための一種の DNS レコードで、外部ソースから読み取ることができます。

[!DNL Journey Optimizer] では、Gmail アドレス宛てのメールの配信品質を確保して確実な配信をおこなうために、サブドメインに Google サイト検証用の特別な TXT レコードを追加して、サブドメインを確実に検証できます。

>[!CAUTION]
>
> この操作は、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;の場合にのみ実行できます。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

サブドメインに Google TXT レコードを追加するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL サブドメイン]**&#x200B;メニューからサブドメインを開きます。

1. 「**[!UICONTROL Google txt レコード]**」セクションで、[Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->から生成された確認コードを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/subdomain-google-txt.png)

1. TXT レコードを追加したら、Google で検証する必要があります。これをおこなうには、[Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->に移動し、検証手順を開始します。
