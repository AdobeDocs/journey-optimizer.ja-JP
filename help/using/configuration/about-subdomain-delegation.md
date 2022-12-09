---
solution: Journey Optimizer
product: journey optimizer
title: でのサブドメインの委任 [!DNL Journey Optimizer]
description: サブドメインを委任する方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 1b5ca4db-44d9-49e2-ab39-a1abba223ec7
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# でのサブドメインの委任 [!DNL Journey Optimizer] {#subdomain-delegation}

電子メールキャンペーン用のサブドメインを作成することで、様々な種類のトラフィック (マーケティングや企業など) を特定の IP プールや特定のドメインに切り分けることができます。これにより、IP 用のプロセスが高速化され、deliverability 全体が改善されます。 ドメインを共有している場合、そのドメインが拒否リストに追加されると、社内メール配信に影響を与える可能性があります。 ただし、電子メールマーケティングの通信に固有のドメインにおける評判の問題やブロックは、この電子メールの流れに影響を及ぼします。 メインドメインを複数のメールストリームに送信する場合や「差出人」アドレスとして使用すると、電子メール認証が中断し、メッセージがブロックされたり、spam フォルダーに置かれたりすることがあります。

>[!NOTE]
>
>同じ送信ドメインを使用して、または [!DNL Adobe Marketo Engage] のような [!DNL Adobe Campaign] 別の製品からメッセージ [!DNL Adobe Journey Optimizer] を送信することはできません。

## サブドメインを設定する理由 {#why-setting-up-subdomains}

サブドメインとは、ドメインの区分であり、これを使用すると、ユーザーのブランドを分離したり、トランザクションメッセージやマーケティング広告などの各種トラフィックを分離したりできます。

ここでは、取引とマーケティングの両方の通信に使用される &quot;mybrand.com&quot; ドメインについて説明します。 このような場合は、2つのサブドメインを設定することができます。

* 取引情報用の &quot;info.mybrand.com&quot; サブドメイン (購入確認、パスワードリセット、その他)
* 「marketing.mybrand.com」サブドメインをご利用ください。

これにより、ドメインおよび他のサブドメインの評判を維持することができます。 例えば、不正な deliverability が原因で、インターネットサービスプロバイダーによって「marketing.mybrand.com」サブドメインが禁止リストに追加された場合は、mybrand.com &quot;ドメイン全体、および&quot; info.mybrand.com &quot;サブドメインが禁止リストに追加されることはありません。

ソリューションの実装については、リンクや web ページの追跡を設定したり、ミラーページを表示したりするなど、外部向けコンポーネントに関する必要条件があります。

このような要件は、アドビとカスタマーの両方でホストされているコンポーネントを使用して管理されますが、電子メールの受信者に表示される Url が含まれています。 基になる技術ソリューションやホストプロバイダーを示す Url を使用しないようにするには、サブドメインを設定して、電子メールの受信者に対して透過的にすることができます。

**詳細情報**

* インターフェイスからサブドメイン ](delegate-subdomain.md) を直接委任する方法に [ ついて説明します。
* Web サブドメインに Google TXT レコード ](google-txt.md) を追加し、Gmail アドレスへの電子メールの配信が成功したかどうかを確認する方法 [ について説明します。
* サブドメイン用に生成された PTR レコード ](ptr-records.md) にアクセスする [ 方法を説明します。これにより、メールサーバーを送信することで、サブドメインを確認できるようになります。

## サブドメインの設定方法 {#subdomain-delegation-methods}

「サブドメイン」を設定すると、Adobe キャンペーンで使用するために、ドメインのサブセクション (技術的には「DNS ゾーン」) を設定することができます。 使用可能なセットアップ方法は次のとおりです。

* **完全なサブドメインから Adobe** への委任 (推奨): サブドメインは adobe に完全に委任されています。 Adobe では、メッセージを配信、描画、追跡するために必要な DNS のすべての側面を制御し、管理することができます。 [完全なサブドメインの委任について詳しく説明しています。](delegate-subdomain.md#full-subdomain-delegation)

* **CNAMEs** の使用: サブドメインを作成し、CNAMEs を使用して Adobe 特有の記録を指定します。 この設定を使用すると、管理者と Adobe の両方が DNS の維持に責務を持っています。 [CNAME サブドメイン委任に関する詳細情報](delegate-subdomain.md#cname-subdomain-delegation)

>[!CAUTION]
>
>* 完全なサブドメインの委任が推奨される方法です。
>
>* 組織のポリシーによって完全なサブドメインの委任方法が制限されている場合は、CNAME メソッドをお勧めします。 この方法では、DNS レコードを独自に管理し、管理する必要があります。 Adobe では、CNAME メソッドを使用して設定されているサブドメインの DNS の変更、メンテナンスまたは管理を支援することはできません。


以下の表に、これらのメソッドの機能と、暗黙の工数を示します。

| 設定方法 | しくみ | 工数のレベル |
|---|---|---|
| **完全な委任** | サブドメインと名前空間のレコードを作成します。 Adobe では、Adobe キャンペーンに必要なすべての DNS レコードを設定します。<br/><br/>この設定では、サブドメインとすべての DNS レコードの管理が完全に実行されます。 | 削減 |
| **CNAME、カスタムメソッド** | サブドメインと名前空間のレコードを作成します。 Adobe では、DNS サーバーに配置するレコードを指定し、その値を Adobe キャンペーン DNS サーバーに設定します。<br/><br/>この設定では、管理者と Adobe の両方が DNS の維持に責務を持っています。 | 高額 |

このドキュメント ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/product-specific-resources/campaign/ac-domain-name-setup.html) では、 [ ドメイン構成についての追加情報が記載されています。

サブドメインの設定方法について質問がある場合は、アドビにお問い合わせいただくか、カスタマーケアにお問い合わせのうえ、Deliverability コンサルティングを依頼してください。

## 委任されたサブドメインへのアクセス {#access-delegated-subdomains}

> **[!UICONTROL Channels]** > **[!UICONTROL Subdomains]** メニューに、すべての委任されたサブドメインが **[!UICONTROL Administration]** 表示されます。リストを調整するには、フィルターを使用します (委任日、ユーザーまたは状態)。

![](assets/subdomain-list.png)

このコラムは、サブドメインの委任処理に関する情報を提供し **[!UICONTROL Status]** ます。

* **[!UICONTROL Draft]**&#x200B;サブドメインの委任は、下書きとして保存されています。 サブドメイン名をクリックして、デリゲーション処理を再開します。
* **[!UICONTROL Processing]**: サブドメインは、使用できるようになる前に複数の設定チェックを行います。
* **[!UICONTROL Success]**&#x200B;サブドメインは正常にチェックを実行し、メッセージの配信に使用することができます。
* **[!UICONTROL Failed]**: サブドメインの委任が送信された後に、1つまたは複数のチェックが失敗しました。

状態が表示されたサブドメインに関する詳細情報にアクセスするには、リストからサブドメイン **[!UICONTROL Success]** を開きます。

![](assets/subdomain-delegated.png)

できます：

* 委任処理の間に設定されたサブドメイン名 (読み取り専用) と、生成された Url (リソース、ミラーページ、追跡 Url) を取得します。

* Google サイト検証の TXT レコードをサブドメインに追加し、検証されたことを確認します (サブドメイン ](google-txt.md) への GOOGLE TXT レコードの追加を参照してください [ )。


>[!CAUTION]
>
>サブドメインの設定はすべての環境で共通です。 そのため、サブドメインに変更を加えると、実働サンドボックスにも影響します。
