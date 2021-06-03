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
source-git-commit: da995c56b59fb191934788c7aea9048123a2fe6d
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 72%

---


# サブドメインデリゲーションの概要

## レピュテーションを保護するためにブランドを分離

サブドメインとは、ブランドや様々なタイプのトラフィック（トランザクションメッセージ、マーケティング情報など）を分離するために使用できるドメインの区分です。トランザクションコミュニケーションとマーケティングコミュニケーションの両方を送信するために使用される「mybrand.com」ドメインの例を見てみましょう。この場合、2 つのサブドメインを設定することに決めることができます。

* トランザクションコミュニケーション（購入確認、パスワードリセットなど）用の「info.mybrand.com」サブドメイン
* 見込み客向けの E メール送信用の「marketing.mybrand.com」サブドメイン

そうすることで、ドメインおよび他のサブドメインの評価を守るのに役立ちます。例えば、配信品質が悪いために「marketing.mybrand.com」サブドメインがインターネットサービスプロバイダーによってブロックリストに追加された場合、「mybrand.com」ドメイン全体および「info.mybrand.com」サブドメインがブロックリストに追加されるのを防ぎます。

## リソースURLを顧客に対して透過的に保つ

ソリューションを実装する場合、外部から使用するコンポーネントに関する要件があります。例えば、追跡するリンクや web ページの設定、ミラーページの表示などがあります。

これらの要件は、アドビと顧客の両方がホストするコンポーネントによって管理され、E メールの受信者が参照できる URL が含まれています。基盤となる技術ソリューションやホスティングプロバイダーを示す URL の表示を避けるために、E メールの受信者に対してこの情報を明らかにするようにサブドメインを設定できます。[ドメインのデリゲーションについて説明します](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html?lang=ja)。

## Journey Optimizerでのサブドメインのデリゲーション

Journey Optimizerには、サブドメインの管理に役立つ機能がいくつか用意されています。

* [サブドメイン](delegate-subdomain.md) をインターフェイスから直接委任する
* [Google TXTレコードをサ](google-txt.md) ブドメインに追加して、Gmailアドレスへの電子メールの配信を確実におこなえるようにします。
* [サブドメイン用に生](ptr-records.md) 成されたPTRレコードにアクセスし、メールサーバーを送信してレコードを検証できます。
