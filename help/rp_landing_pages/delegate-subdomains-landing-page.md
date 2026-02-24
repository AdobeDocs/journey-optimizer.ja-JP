---
solution: Journey Optimizer
product: Journey Optimizer
title: メールサブドメインのデリゲート
description: メールサブドメインのデリゲート
redpen-status: CREATED_||_2025-08-11_21-07-51
exl-id: 7df9b8e2-136a-4ffc-9243-53c7be026d81
source-git-commit: bb50d06e86f9399dfd295b8091aa637abcaea4a8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 41%

---

# メールサブドメインのデリゲート{#section-overview}

メールサブドメインのデリゲートは、[&#x200B; チャネル設定 &#x200B;](../using/configuration/get-started-configuration.md) の中核となる手順で、Journey Optimizerからメールを送信する前に必要です。 サブドメインを使用すると、トラフィックタイプ（マーケティングとトランザクションなど）を分離し、メインドメインのレピュテーションを保護し、[IP ウォームアップ &#x200B;](../using/configuration/ip-warmup-gs.md) を高速化できます。 [&#x200B; メールチャネル設定 &#x200B;](../using/email/get-started-email-config.md) および [&#x200B; 配信品質の監視 &#x200B;](../using/reports/deliverability.md) と連携して、メッセージがインボックスに確実に届くようにします。

**完全デリゲーション** （Adobeが DNS を管理）、**CNAME 設定**、**カスタムデリゲーション** （ユーザーが証明書と DNS を所有）のいずれかの設定方法を選択できます。 CNAME から開始する場合は、後で [&#x200B; カスタムの委任に移行 &#x200B;](../using/configuration/custom-subdomain-migration.md) して、セキュリティを強化できます。 この節では、DMARCと PTR レコード、Gmail 用のGoogle TXT レコードおよび IP プールについても説明します。 より広範な配信品質ガイダンスについては、[&#x200B; 配信品質の基本を学ぶ &#x200B;](../using/reports/deliverability.md) および [&#x200B; メールアドレスの監視 &#x200B;](monitor-reputation-landing-page.md) を参照してください。

## メールサブドメインのデリゲート

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

サブドメインデリゲーションの基本を学ぶ

Adobe Journey Optimizer でサブドメインをデリゲートするメリット、設定方法および考慮事項について説明します。

[サブドメインのデリゲートの開始](../using/configuration/about-subdomain-delegation.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

サブドメインのデリゲート

完全なデリゲーションと CNAME の設定を含む、サブドメインをアドビに委任する手順について説明します。

[詳しくは、デリゲート方法を参照してください。](../using/configuration/delegate-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/screwdriver-wrench.svg)

カスタムサブドメインの設定

カスタムデリゲーションでサブドメインの完全な所有権を取得 – 独自の SSL 証明書をアップロードし、ドメイン設定を完全に制御できます。

[カスタムサブドメインの設定](../using/configuration/delegate-custom-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

CNAME からカスタム委任への移行

セキュリティポリシーを満たし、証明書を完全に制御するには、CNAME で設定された既存のサブドメインをカスタムデリゲーションに移行します。

[サブドメインの移行](../using/configuration/custom-subdomain-migration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

DMARC レコードの設定

DMARC レコードを設定し、デリゲートされたサブドメインのメールのセキュリティと配信品質を強化します。

[今すぐ DMARC を設定](../using/configuration/dmarc-record.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

Google TXT レコードの追加

Adobe Journey Optimizer に Google TXT レコードを追加して、Gmail の配信品質のサブドメインを検証します。

[Google TXT レコードの追加](../using/configuration/google-txt.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

PTR レコードへのアクセスと編集

更新ステータスの編集と理解を含む、デリゲートされたサブドメインの PTR レコードを管理します。

[PTR レコードの編集](../using/configuration/ptr-records.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

IP プールの作成

IP アドレスをグループ化して、メールの配信品質を向上させ、サブドメインの評判を効果的に管理します。

[IP プールの作成](../using/configuration/ip-pools.md)
:::

::::

## その他のリソース

- **[ランディングページのサブドメインの設定](../using/landing-pages/lp-subdomains.md)** - ランディングページと購読フォームのサブドメインを設定します。
- **[web サブドメインの設定](../using/web/web-delegated-subdomains.md)** - web エクスペリエンスおよびトラッキング用のサブドメインをデリゲートします。
- **[チャネル設定の概要](../using/configuration/get-started-configuration.md)** - サブドメインデリゲーションを含む、すべてのチャネル設定手順の概要。
