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
source-git-commit: f8d62a702824bcfca4221c857acf1d1294427543
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 79%

---

# [!DNL Journey Optimizer] でのサブドメインのデリゲーション {#subdomain-delegation}

>[!CONTEXTUALHELP]
>id="ajo_admin_delegated_subdomains"
>title="デリゲートされたサブドメインがこちらに表示されます。"
>abstract="最初のサブドメインをデリゲートします。デリゲーションが完了すると、PTR レコードが作成され、メールチャネルが有効になります。"

メールキャンペーン用のサブドメインを作成すると、異なるタイプのトラフィック（マーケティングと企業など）を特定の IP プールと特定のドメインに分離できるので、IP ウォーミングプロセスが加速し、全体の配信品質が向上します。

ドメインを共有している場合、そのドメインがブロックされたり、ブロックリストに追加されたりすると、会社のメール配信に影響を与える可能性があります。ただし、メールマーケティングのやりとりに固有のドメインを使用していると、ドメインに関するレピュテーション問題やブロックが与える影響は、そのドメインのメールのフローにとどまります。メインドメインを複数のメールストリームの送信者や「送信元」アドレスとして使用すると、メールの認証が機能せず、メッセージがブロックされたり、スパムフォルダーに仕分けられたりする可能性があります。

>[!NOTE]
>
>[!DNL Adobe Journey Optimizer] と別の製品（[!DNL Adobe Campaign] または [!DNL Adobe Marketo Engage] など）から同じ送信ドメインを使用してメッセージを送信することはできません。

## サブドメインを設定する理由 {#why-set-up-subdomains}

サブドメインとは、ブランドを分離したり、様々なタイプのトラフィック（トランザクションメッセージ、アドビからのお知らせなど）を分離したりするのに使用できる、ドメインの区分です。

例えば、トランザクションコミュニケーションとマーケティングコミュニケーションの両方を送信する「mybrand.com」ドメインを使用する場合を考えてみましょう。 この場合、次の 2 つのサブドメインを設定することができます。

* トランザクション通信（購入の確認、パスワードのリセットなど）の「info.mybrand.com」サブドメイン
* 見込み客向けのメール送信用の「marketing.mybrand.com」サブドメイン

これにより、ドメインおよび他のサブドメインの評価を維持するのに役立ちます。 例えば、「marketing.mybrand.com」サブドメインが、配信品質が低いためにインターネットサービスプロバイダーによってブロックリストに追加された場合は、「mybrand.com」サブドメインと「info.mybrand.com」サブドメイン全体がブロックリストに追加されなくなります。

ソリューションを実装する場合、外部から使用するコンポーネント（追跡の対象となるリンクや web ページの設定、ミラーページの表示など）に関する要件があります。

これらの要件は、アドビと顧客の両方がホストするコンポーネントによって管理され、メールの受信者に表示される URL を含みます。基盤となる技術ソリューションやホスティングプロバイダーが URL で示されるのを避けるために、サブドメインを設定し、メールの受信者に対してこの透明性を確保することができます。

**詳細情報**

* インターフェイスから直接[サブドメインをデリゲート](delegate-subdomain.md)する方法については、こちらを参照してください。
* Gmail アドレスへのメールの配信を確実に行うためにサブドメインに [Google TXT レコードを追加](google-txt.md)する方法を説明します
* サブドメイン用に生成された [PTR レコードにアクセス](ptr-records.md)して送信メールサーバーで検証できるようにする方法を説明します

## サブドメインの設定方法 {#subdomain-delegation-methods}

サブドメイン設定を使用すると、Adobe Campaign 用にドメインのサブセクション（技術的には「DNS ゾーン」）を設定できます。使用可能な設定方法を次に示します。

* **Adobe への完全なサブドメインデリゲーション**（推奨）：サブドメインはアドビに完全にデリゲートされます。アドビは、メッセージの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を制御および管理できます。[完全なサブドメインデリゲーションの詳細情報](delegate-subdomain.md#full-subdomain-delegation)

* **CNAME の使用**：サブドメインを作成し、CNAME を使用してアドビ固有のレコードを指定します。この設定では、お客様とアドビの両方が DNS の維持に対する責任を共有します。[CNAME サブドメインのデリゲーションの詳細情報](delegate-subdomain.md#cname-subdomain-delegation)

>[!CAUTION]
>
>* 推奨される方法は、完全なサブドメインのデリゲーションです。
>
>* 組織のポリシーで完全なサブドメインデリゲーションの方法が制限されている場合は、CNAME の方法をお勧めします。このアプローチでは、DNS レコードを自社で維持および管理する必要があります。アドビは、CNAME メソッドを使用して設定されたサブドメインの DNS の変更、維持または管理をサポートできなくなります。

次の表に、これらの方法の仕組みと、黙示的な作業レベルの概要を示します。

| 設定方法 | 仕組み | 作業レベル |
|---|---|---|
| **完全デリゲーション** | サブドメインと名前空間レコードを作成します。 次に、Adobeは、Adobe Campaignに必要なすべての DNS レコードを設定します。<br/><br/>この設定では、Adobeは、サブドメインとすべての DNS レコードの管理を完全に担当します。 | 低 |
| **CNAME、カスタムメソッド** | サブドメインと名前空間レコードを作成します。 次に、Adobeは DNS サーバーに配置するレコードを提供し、Adobe Campaign DNS サーバーで対応する値を設定します。<br/><br/>この設定では、お客様とAdobeの両方が DNS の管理に対する責任を共有します。 | 高 |

ドメイン設定に関するその他の詳細情報については、を参照してください [このドキュメント](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html?lang=ja).

サブドメインの設定方法について質問がある場合は、アドビにお問い合わせいただくか、最終的にはカスタマーケアに連絡して配信品質のコンサルティングを依頼してください。

## デリゲートされたサブドメインへのアクセス {#access-delegated-subdomains}

デリゲートされたすべてのサブドメインが&#x200B;**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL サブドメイン]**&#x200B;メニューに表示されます。フィルターを使用して、リスト（デリゲーション日、ユーザー、ステータス）を絞り込むことができます。

![](assets/subdomain-list.png)

**[!UICONTROL ステータス]**&#x200B;列には、サブドメインのデリゲーションプロセスに関する情報が表示されます。

* **[!UICONTROL ドラフト]**：サブドメインのデリゲーションがドラフトとして保存されました。サブドメイン名をクリックして、デリゲーションプロセスを再開します。
* **[!UICONTROL 処理中]**：サブドメインを使用する前に、いくつかの設定確認がおこなわれます。
* **[!UICONTROL 成功]**：サブドメインは正常にチェックされ、メッセージの配信に使用できます。
* **[!UICONTROL 失敗]**：サブドメインのデリゲーションが送信された後、1 つ以上の確認が失敗しました。

**[!UICONTROL 成功]**&#x200B;ステータスのサブドメインに関する詳細情報にアクセスするには、リストからサブドメインを開きます。

![](assets/subdomain-delegated.png)

次のことができます。

* デリゲーションプロセス中に設定されたサブドメイン名（読み取り専用）と、生成された URL（リソース、ミラーページ、トラッキング URL）を取得します。

* Google サイト検証 TXT レコードをサブドメインに追加して、検証済みであることを確認します（[サブドメインに Google TXT レコードを追加する](google-txt.md)を参照）。


>[!CAUTION]
>
>サブドメインの設定は、すべての環境で共通です。したがって、サブドメインを変更すると、実稼働用サンドボックスにも影響します。
