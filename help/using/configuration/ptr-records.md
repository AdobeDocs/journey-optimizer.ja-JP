---
title: PTRレコード
description: 「ptr-recordsの管理方法の詳細」
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
feature: アプリケーション設定
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---


# PTRレコード

## PTRレコードについて

ポインタレコード(PTR)は、IPアドレスにリンクされたドメイン名を提供するDNS(Domain Name System)レコードの一種です。

PTRレコードを使用すると、受信側のメールサーバーは、IPアドレスがサーバーの接続名に対応しているかどうかを識別して、送信側のメールサーバーの信頼性を確認できます。

## サブドメインのPTRレコードへのアクセス

Customer Journey Managementでサブドメインがデリゲートされると、PTRレコードが自動的に作成され、このサブドメインに関連付けられます。 **[!UICONTROL チャネル]** `>` **[!UICONTROL PTRレコード]**&#x200B;メニューからアクセスできます。

![](../assets/ptr-records.png)

このリストには、次の構文を使用して、各デリゲートされたサブドメインに対して生成されたPTRレコードが表示されます。

* 「r」（レコード）
* IPアドレスの2つの最後の数字の場合は「xx」
* サブドメイン名。

リストからPTRレコードを開くと、関連するサブドメイン名とIPアドレスを表示できます。

>[!NOTE]
>
>PTRレコードは読み取り専用で、IPアドレスに関連付けられたサブドメインを変更することはできません。
