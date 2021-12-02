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
source-git-commit: 1d7f661dc0a89e4754a76ecf2cdce1e43a5275ec
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 60%

---

# サブドメインへの Google TXT レコードの追加

TXT レコードは、ドメインに関するテキスト情報を提供するための一種の DNS レコードで、外部ソースから読み取ることができます。

Gmail アドレス宛ての E メールの配信品質を確保し、配信を成功させるには、次の手順を実行します。 [!DNL Journey Optimizer] では、サブドメインに特別なGoogleサイト検証 TXT レコードを追加して、検証されていることを確認できます。

>[!CAUTION]
>
> この操作は、サブドメインのステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;の場合にのみ実行できます。 サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。

サブドメインに Google TXT レコードを追加するには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL サブドメイン]**&#x200B;メニューからサブドメインを開きます。

1. 内 **[!UICONTROL Google txt レコード]** セクションで、 [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->を選択し、「 **[!UICONTROL 保存]**.

   ![](../assets/subdomain-google-txt.png)

1. TXT レコードを追加したら、Google で検証する必要があります。これをおこなうには、に移動します。 [Google Workspace](https://support.google.com/a/answer/183895){target=&quot;_blank&quot;}<!--G Suite Admin tools-->をクリックし、検証ステップを起動します。
