---
title: PTR レコード
description: '"ptr レコードの管理方法について説明します"'
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
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---


# PTR レコード

## PTR レコードについて

ポインタレコード（PTR）は、IP アドレスと関連付けたドメイン名を提供する DNS（Domain Name System）レコードの一種です。

PTR レコードを使用すると、受信メールサーバーは、送信メールサーバーの IP アドレスが接続先の名前に対応しているかどうかを識別することにより、送信メールサーバーの信頼性を確認できます。

## サブドメインの PTR レコードへのアクセス

Customer Journey Management でサブドメインをデリゲートすると、PTR レコードが自動的に作成され、サブドメインに関連付けられます。 **[!UICONTROL チャネル]** `>` **[!UICONTROL PTR レコード]**&#x200B;メニューからアクセスできます。

![](../assets/ptr-records.png)

このリストには、以下の構文を使用して、デリゲートされたサブドメインごとに生成された PTR レコードが表示されます。

* レコードの場合は「r」。
* IP アドレスの最後の 2 桁には「xx」。
* サブドメイン名。

リストから PTR レコードを開くと、関連するサブドメイン名と IP アドレスを表示できます。

>[!NOTE]
>
>PTR レコードは読み取り専用であり、IP アドレスに関連付けられたサブドメインを変更することはできません。
