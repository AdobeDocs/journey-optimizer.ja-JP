---
title: サブドメインのデリゲート
description: サブドメインのデリゲート方法を説明します
page-status-flag: never-activated
uuid: null
contentOwner: null
products: null
audience: administrators
content-type: reference
topic-tags: null
discoiquuid: null
internal: n
snippet: y
source-git-commit: 2d8b7bbaee7509d4cc33445c64b2382ed14a9678
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 24%

---


# サブドメインへのGoogle TXTレコードの追加

TXT レコードは、ドメインに関するテキスト情報を提供するための一種の DNS レコードで、外部ソースから読み取ることができます。

顧客ジャーニー管理では、Gmailアドレス宛てのEメールの配信品質を確保し、配信を成功させるために、サブドメインにGoogleサイト検証用の特別なTXTレコードを追加して、検証を確実におこなうことができます。

>[!NOTE]
>
> この操作は、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;の場合にのみ実行できます。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

サブドメインにGoogle TXTレコードを追加するには、次の手順に従います。

1. **[!UICONTROL チャネル]** / **[!UICONTROL サブドメイン]**&#x200B;メニューからサブドメインを開きます。

1. 「Google txtレコード」セクションで、[G Suite管理ツール](https://support.google.com/a/answer/183895)で生成された検証コードを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/subdomain-google-txt.png)

1. TXT レコードを追加したら、Google で検証する必要があります。これをおこなうには、G Suite管理ツールに移動し、検証手順を実行します。
