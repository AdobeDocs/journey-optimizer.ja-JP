---
title: PTRレコード
description: xxxxの方法を説明します
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
source-git-commit: 6988a6ab9412e5d27f1ba9d1145cc11c7c06e7b7
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# PTRレコード

## PTRレコードについて

ポインタレコード(PTR)は、IPアドレスにリンクされたドメイン名を提供するDNS(Domain Name System)レコードの一種です。

PTRレコードを使用すると、受信側のメールサーバーは、IPアドレスがサーバーの接続名に対応しているかどうかを識別して、送信側のメールサーバーの信頼性を確認できます。

## サブドメインのPTRレコードへのアクセス

Customer Journey Managementでサブドメインがデリゲートされると、PTRレコードが自動的に作成され、このサブドメインに関連付けられます。 **[!UICONTROL チャネル]** / **[!UICONTROL PTRレコード]**&#x200B;メニューからアクセスできます。

![](../assets/ptr-records.png)

このリストには、次の構文を使用して、各デリゲートされたサブドメインに対して生成されたPTRレコードが表示されます。

* 「r」（レコード）
* IPアドレスの2つの最後の数字の場合は「xx」
* サブドメイン名。

リストからPTRレコードを開くと、関連するサブドメイン名とIPアドレスを表示できます。

>[!NOTE]
>
>PTRレコードは読み取り専用で、IPアドレスに関連付けられたサブドメインを変更することはできません。
