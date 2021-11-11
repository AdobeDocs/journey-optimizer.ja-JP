---
title: サブドメインのデリゲート
description: サブドメインのデリゲート方法を学ぶ
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
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: 7138e1f031bd26caf9379c3ff19d79ac29442bc6
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---

# サブドメインへの Google TXT レコードの追加

TXT レコードは、ドメインに関するテキスト情報を提供するための一種の DNS レコードで、外部ソースから読み取ることができます。

カスタマージャーニー管理では、Gmail アドレス宛てのメールの配信品質を確保して確実な配信を行うために、サブドメインに Google サイト検証用の特別な TXT レコードを追加して、サブドメインが確実に検証されるようにすることが可能です。

>[!NOTE]
>
> この操作は、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;の場合にのみ実行できます。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

サブドメインに Google TXT レコードを追加するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL サブドメイン]**&#x200B;メニューからサブドメインを開きます。

1. 「Google txt レコード」セクションで、[G Suite 管理ツール](https://support.google.com/a/answer/183895)で生成された検証コードを入力し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/subdomain-google-txt.png)

1. TXT レコードを追加したら、Google で検証する必要があります。これをおこなうには、G Suite 管理ツールに移動し、検証手順を実行します。
