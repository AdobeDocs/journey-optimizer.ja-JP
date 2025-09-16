---
solution: Journey Optimizer
product: Journey Optimizer
title: メールサブドメインのデリゲート
description: メールサブドメインのデリゲート
redpen-status: CREATED_||_2025-08-11_21-07-51
exl-id: 7df9b8e2-136a-4ffc-9243-53c7be026d81
source-git-commit: 2b907a3be8b11ac6308d0b563e122c88478d1d37
workflow-type: ht
source-wordcount: '244'
ht-degree: 100%

---

# メールサブドメインのデリゲート{#section-overview}

Adobe Journey Optimizer でメールのサブドメインをデリゲートすると、管理者はメールの配信品質を向上させ、ドメインの評判を保護し、キャンペーン管理を効率化できます。サブドメインを設定することで、業界標準へのコンプライアンスを確保しながら、マーケティングメッセージやトランザクションメッセージなど、様々なタイプのメールトラフィックを分離できます。この節では、完全なデリゲーションや CNAME 設定などの主要な設定方法と、これらの労力と制御の違いについて説明します。また、DMARC や PTR などの重要な DNS レコードの管理、Google TXT レコードを使用した Gmail の配信品質の向上、IP プールを使用した IP のグループ化についても説明します。セキュリティや評判を最適化する場合でも、このガイドを使用すれとプロセスがわかりやすく、効果的になります。

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
