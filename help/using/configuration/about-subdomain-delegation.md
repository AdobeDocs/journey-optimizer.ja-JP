---
solution: Journey Optimizer
product: journey optimizer
title: ' [!DNL Journey Optimizer] でのサブドメインの委任'
description: サブドメインのデリゲート方法を学ぶ
feature: Subdomains
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン, Optimizer, デリゲーション
exl-id: 1b5ca4db-44d9-49e2-ab39-a1abba223ec7
source-git-commit: 7854de133ebcd3b29ca59b747aa89fae242f2ea5
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 100%

---

# [!DNL Journey Optimizer] でのサブドメインのデリゲーション {#subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_delegated_subdomains"
>title="デリゲートされたサブドメインがこちらに表示されます。"
>abstract="最初のサブドメインをデリゲートします。 デリゲーションが完了すると、PTR レコードが作成され、メールチャネルが有効になります。"

メールキャンペーン用のサブドメインを作成すると、異なるタイプのトラフィック（マーケティングと企業など）を特定の IP プールと特定のドメインに分離できるので、IP ウォーミングプロセスが加速し、全体の配信品質が向上します。

ドメインを共有している場合、そのドメインがブロックされたり、ブロックリストに追加されたりすると、会社のメール配信に影響を与える可能性があります。ただし、メールマーケティングのやりとりに固有のドメインを使用していると、ドメインに関するレピュテーション問題やブロックが与える影響は、そのドメインのメールのフローにとどまります。メインドメインを複数のメールストリームの送信者や「送信元」アドレスとして使用すると、メールの認証が機能せず、メッセージがブロックされたり、スパムフォルダーに仕分けられたりする可能性があります。

>[!CAUTION]
>
>[!DNL Adobe Journey Optimizer] と別の製品（[!DNL Adobe Campaign] または [!DNL Adobe Marketo Engage] など）から同じ送信ドメインを使用してメッセージを送信することはできません。

## サブドメインを設定する理由 {#why-set-up-subdomains}

サブドメインとは、ブランドを分離したり、様々なタイプのトラフィック（トランザクションメッセージ、アドビからのお知らせなど）を分離したりするのに使用できる、ドメインの区分です。

トランザクションコミュニケーションとマーケティングコミュニケーションの両方を送信するために使用される「mybrand.com」ドメインの例を見てみましょう。ここでは、2 つのサブドメインを設定します。

* トランザクションコミュニケーション（購入確認、パスワードリセットなど）用の「info.mybrand.com」サブドメイン
* 見込み客向けのメール送信用の「marketing.mybrand.com」サブドメイン

この設定により、ドメインおよび他のサブドメインの評価を維持するのに役立ちます。例えば、配信品質が悪いために「marketing.mybrand.com」サブドメインがインターネットサービスプロバイダーによってブロックリストに追加された場合、「mybrand.com」ドメイン全体および「info.mybrand.com」サブドメインがブロックリストに追加されるのを防ぎます。

ソリューションを実装する場合、外部から使用するコンポーネント（追跡の対象となるリンクや web ページの設定、ミラーページの表示など）に関する要件があります。

これらの要件は、アドビと顧客の両方がホストするコンポーネントによって管理され、メールの受信者に表示される URL を含みます。基盤となる技術ソリューションやホスティングプロバイダーが URL で示されるのを避けるために、サブドメインを設定し、メールの受信者に対してこの透明性を確保することができます。

**詳細情報**

* インターフェイスから直接[サブドメインをデリゲート](delegate-subdomain.md)する方法については、こちらを参照してください。
* Gmail アドレスへのメールの配信を確実に行うためにサブドメインに [Google TXT レコードを追加](google-txt.md)する方法を説明します
* サブドメイン用に生成された [PTR レコードにアクセス](ptr-records.md)して送信メールサーバーで検証できるようにする方法を説明します

## サブドメインの設定方法 {#subdomain-delegation-methods}

サブドメイン設定を使用すると、Adobe Campaign で使用するドメインのサブセクション（技術的には「DNS ゾーン」）を設定できます。

利用できる設定メソッドを次に示します。

### サブドメインのアドビへの完全なデリゲート（推奨） {#full-subdomain-delegation}

[!DNL Journey Optimizer] では、サブドメインを製品インターフェイスから直接アドビに、完全にデリゲートできます。アドビは、メールキャンペーンの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を制御および管理することで、メッセージをマネージドサービスとして提供できます。

<!--The subdomain is fully delegated to Adobe. Adobe is able to control and maintain all aspects of DNS that are required for delivering, rendering and tracking messages.-->

メールマーケティング送信ドメインに関する業界標準の配信品質要件を満たすために必要な DNS インフラストラクチャの管理はアドビに任せ、引き続き社内メール用ドメインの DNS を管理し、制御できます。

>[!IMPORTANT]
>
>推奨される方法は、完全なサブドメインのデリゲーションです。

サブドメインをアドビに完全にデリゲートする方法について詳しくは、[この節](delegate-subdomain.md#set-up-subdomain)を参照してください。

### CNAME を使用したサブドメインの設定 {#cname-subdomain-setup}

ドメイン固有の制限ポリシーがあり、アドビが DNS の一部を制御する必要がある場合は、自社で DNS 関連のすべてのアクティビティを実行するように選択できます。

CNAME サブドメイン設定では、サブドメインを作成し、CNAME を使用してアドビ固有のレコードを示すことができます。この設定を使用すると、メールの送信、レンダリング、トラッキングの環境を設定するために、DNS の管理に対する責任を、お客様とアドビで共有します。

>[!CAUTION]
>
>組織のポリシーで完全なサブドメインデリゲーションの方法が制限されている場合は、CNAME の方法をお勧めします。このアプローチでは、DNS レコードを自社で維持および管理する必要があります。
>
>アドビは、CNAME メソッドを使用して設定されたサブドメインの DNS の変更、維持または管理をサポートできなくなります。

CNAME を使用してサブドメインを作成しアドビ固有のレコードを指すようにする方法について詳しくは、[この節](delegate-subdomain.md#cname-subdomain-setup)を参照してください。

## 設定方法の比較

次の表に、これらの方法の仕組みと、黙示的な作業レベルの概要を示します。

| 設定方法 | 仕組み | 労力のレベル |
|---|---|---|
| **完全なデリゲーション** | サブドメインと名前空間レコードを作成します。次に、アドビは Adobe Campaign に必要なすべての DNS レコードを設定します。<br/><br/>この設定では、アドビは、サブドメインとすべての DNS レコードを管理するすべての責任を負います。 | 低 |
| **CNAME メソッド** | サブドメインと名前空間レコードを作成します。次に、アドビは、DNS サーバーに配置されるレコードを提供し、対応する値を Adobe Campaign DNS サーバーに設定します。<br/><br/>この設定では、お客様とアドビの両方が DNS の維持に対する責任を共有します。 | 高 |

<!--
| Configuration method | How it works | Level of effort |
|---|---|---|
| **Full delegation** | Create the subdomain and namespace record. Adobe will then configure all DNS records required for Adobe Campaign.<br/><br/>In this setup, Adobe is fully responsible for managing the subdomain and all the DNS records. | Low |
| **CNAME method** |  Create the subdomain and namespace record. Adobe will then provide the records to be placed in your DNS servers and will configure the corresponding values in Adobe Campaign DNS servers.<br/><br/>In this setup, both you and Adobe share responsibility for maintaining DNS. | High |
| **Custom delegation method** |  Create the subdomain and namespace record - Adobe will then provide the records to be placed in your DNS servers. Upload the SSL Certificate obtained from the Certificate Authority and complete the Feedback Loop steps by verifying domain ownership and reporting email address.<br/><br/>In this setup, you have full responsibility for maintaining DNS. | Very high |-->

ドメイン設定に関するその他の詳細情報については、[このドキュメント](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html?lang=ja){target="_blank"}を参照してください。

サブドメインの設定方法について質問がある場合は、アドビにお問い合わせいただくか、カスタマーケアに連絡して配信品質のコンサルティングを依頼してください。


