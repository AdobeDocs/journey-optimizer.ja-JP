---
solution: Journey Optimizer
product: Journey Optimizer
title: メールサブドメインのデリゲート
description: メールサブドメインのデリゲート
redpen-status: CREATED_||_2025-08-11_21-07-51
exl-id: 7df9b8e2-136a-4ffc-9243-53c7be026d81
source-git-commit: bb50d06e86f9399dfd295b8091aa637abcaea4a8
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---

# メールサブドメインのデリゲート{#section-overview}

メールサブドメインのデリゲートは、[チャネル設定](../using/configuration/get-started-configuration.md)のコア手順で、Journey Optimizer からメールを送信する前に必須です。サブドメインを使用すると、トラフィックタイプ（例：マーケティングとトランザクション）を分離し、メインドメインの評判を保護し、[IP ウォームアップ](../using/configuration/ip-warmup-gs.md)を高速化できます。これらは、[メールチャネル設定](../using/email/get-started-email-config.md)や[配信品質の監視](../using/reports/deliverability.md)と連携して、メッセージがインボックスに確実に届くようにします。

**完全なデリゲーション**（アドビが管理する DNS）、**CNAME 設定**&#x200B;または&#x200B;**カスタムデリゲーション**（証明書とDNSを所有）の複数の設定方法から選択できます。CNAME から開始した場合、より厳格なセキュリティのために[カスタムデリゲーション](../using/configuration/custom-subdomain-migration.md)に後で移行できます。また、この節では、DMARC と PTR レコード、Gmail の Google TXT レコード、IP プールについても説明します。 より広範な配信品質ガイダンスについて詳しくは、[配信品質の基本を学ぶ](../using/reports/deliverability.md)および[メールアドレスの監視](monitor-reputation-landing-page.md)を参照してください。

## メールサブドメインのデリゲート

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=ja)

サブドメインデリゲーションの基本を学ぶ

Adobe Journey Optimizer でサブドメインをデリゲートするメリット、設定方法および考慮事項について説明します。

[サブドメインのデリゲートの開始](../using/configuration/about-subdomain-delegation.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=ja)

サブドメインのデリゲート

完全なデリゲーションと CNAME の設定を含む、サブドメインをアドビに委任する手順について説明します。

[詳しくは、デリゲート方法を参照してください。](../using/configuration/delegate-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/screwdriver-wrench.svg?lang=ja)

カスタムサブドメインの設定

カスタムデリゲーションを使用すると、サブドメインの完全な所有権を取得できます。独自の SSL 証明書をアップロードし、ドメイン設定を完全に制御できます。

[カスタムサブドメインの設定](../using/configuration/delegate-custom-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=ja)

CNAME からカスタムデリゲーションへの移行

既存の CNAME 設定済みサブドメインをカスタムデリゲーションに移行すると、セキュリティポリシーを満たし、証明書を完全に制御できます。

[サブドメインの移行](../using/configuration/custom-subdomain-migration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=ja)

DMARC レコードの設定

DMARC レコードを設定し、デリゲートされたサブドメインのメールのセキュリティと配信品質を強化します。

[今すぐ DMARC を設定](../using/configuration/dmarc-record.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=ja)

Google TXT レコードの追加

Adobe Journey Optimizer に Google TXT レコードを追加して、Gmail の配信品質のサブドメインを検証します。

[Google TXT レコードの追加](../using/configuration/google-txt.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=ja)

PTR レコードへのアクセスと編集

更新ステータスの編集と理解を含む、デリゲートされたサブドメインの PTR レコードを管理します。

[PTR レコードの編集](../using/configuration/ptr-records.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=ja)

IP プールの作成

IP アドレスをグループ化して、メールの配信品質を向上させ、サブドメインの評判を効果的に管理します。

[IP プールの作成](../using/configuration/ip-pools.md)
:::

::::

## その他のリソース

- **[ランディングページのサブドメインの設定](../using/landing-pages/lp-subdomains.md)** - ランディングページと登録フォームのサブドメインを設定します。
- **[Web サブドメインの設定](../using/web/web-delegated-subdomains.md)** - Web エクスペリエンスとトラッキング用のサブドメインをデリゲートします。
- **[チャネル設定の基本を学ぶ](../using/configuration/get-started-configuration.md)** - サブドメインのデリゲーションを含む、すべてのチャネル設定手順の概要。
