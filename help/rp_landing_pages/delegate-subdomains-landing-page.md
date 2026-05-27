---
solution: Journey Optimizer
product: Journey Optimizer
title: メールサブドメインのデリゲート
description: メールサブドメインのデリゲート
redpen-status: CREATED_||_2025-08-11_21-07-51
exl-id: 7df9b8e2-136a-4ffc-9243-53c7be026d81
source-git-commit: bb50d06e86f9399dfd295b8091aa637abcaea4a8
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 46%

---

# メールサブドメインのデリゲート{#section-overview}

メールサブドメインのデリゲートは、[&#x200B; チャネル設定](../using/configuration/get-started-configuration.md)の中核的な手順です。Journey Optimizerからメールを送信する前に必要です。 サブドメインを使用すると、トラフィックタイプ（マーケティングとトランザクションなど）を分離し、メインドメインのレピュテーションを保護し、[IP ウォームアップ &#x200B;](../using/configuration/ip-warmup-gs.md)を高速化できます。 [&#x200B; メールチャネル設定](../using/email/get-started-email-config.md)および[配信品質モニタリング &#x200B;](../using/reports/deliverability.md)と連携して、メッセージが受信トレイに確実に届くようにします。

複数のセットアップ方法から選択できます：**完全委任** （AdobeはDNSを管理）、**CNAME setup**、または&#x200B;**カスタム委任** （自分が証明書とDNSを所有）。 CNAMEから始める場合は、後で[&#x200B; カスタム委任](../using/configuration/custom-subdomain-migration.md)に移行してセキュリティを強化できます。 この節では、DMARCとPTR レコード、GmailのGoogle TXT レコード、およびIP プールについても説明します。 より広範な配信品質ガイダンスについては、[配信品質の基本を学ぶ](../using/reports/deliverability.md)および[電子メールアドレスを監視](monitor-reputation-landing-page.md)を参照してください。

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

カスタムデリゲーションを使用してサブドメインの完全な所有権を取得し、独自のSSL証明書をアップロードして、ドメイン設定の完全な制御を維持します。

[カスタムサブドメインの設定](../using/configuration/delegate-custom-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=ja)

CNAMEからカスタム委任への移行

既存のCNAME設定済みサブドメインをカスタム委任に移行して、セキュリティポリシーに対応し、証明書を完全に制御します。

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

- **[ランディングページサブドメインの設定](../using/landing-pages/lp-subdomains.md)** - ランディングページとサブスクリプションフォームのサブドメインを設定します。
- **[Web サブドメインの設定](../using/web/web-delegated-subdomains.md)** - Web エクスペリエンスとトラッキング用のサブドメインをデリゲートします。
- **[チャネル設定の概要](../using/configuration/get-started-configuration.md)** - サブドメインのデリゲーションを含むすべてのチャネル設定手順の概要。
