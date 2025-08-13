---
solution: Journey Optimizer
product: Journey Optimizer
title: メールサブドメインのデリゲート
description: メールサブドメインのデリゲート
redpen-status: CREATED_||_2025-08-11_21-07-51
source-git-commit: 5a8ef88cba254241933607ca59156d35e0e92926
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 3%

---


# メールサブドメインのデリゲート{#section-overview}

Adobe Journey Optimizerでメールサブドメインをデリゲートすると、管理者はメールの配信品質を向上させ、ドメインのレピュテーションを保護し、キャンペーン管理を効率化できます。 サブドメインを設定すると、業界標準への準拠を確保しながら、マーケティングメッセージやトランザクションメッセージなど、様々なタイプのメールトラフィックを分離できます。 この節では、完全なデリゲーションや CNAME 設定などの主要な設定方法を紹介したあと、それらの作業量や制御の違いについて説明します。 また、DMARCや PTR などの重要な DNS レコードの管理、Google TXT レコードを使用した Gmail の配信品質の向上、IP プールを使用した IP のグループ化についても説明します。 セキュリティやレピュテーションを最適化しているかどうかにかかわらず、このガイドにより、プロセスが親しみやすく効果的になります。

## メールサブドメインのデリゲート

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

サブドメインデリゲーションの概要

Adobe Journey Optimizerでサブドメインをデリゲートするメリット、設定方法および考慮事項について説明します。

[サブドメインのデリゲートの開始](../using/configuration/about-subdomain-delegation.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

サブドメインのデリゲート

完全なデリゲーションと CNAME 設定を含む、サブドメインをAdobeにデリゲートするためのステップバイステップのガイダンス。

[デリゲート方法を学ぶ](../using/configuration/delegate-subdomain.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

DMARC レコードの設定

DMARC レコードを設定して、デリゲートされたサブドメインのメールのセキュリティと配信品質を強化します。

[DMARCを今すぐセットアップ](../using/configuration/dmarc-record.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

Google TXT レコードを追加

Adobe Journey OptimizerにGoogle TXT レコードを追加して、Gmail の配信品質をサブドメインで検証します。

[Google TXT レコードの追加](../using/configuration/google-txt.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

PTR レコードへのアクセスと編集

更新ステータスの編集と理解を含め、デリゲートされたサブドメインの PTR レコードを管理します。

[PTR レコードの編集](../using/configuration/ptr-records.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

IP プールの作成

IP アドレスをグループ化して、メールの配信品質を向上させ、サブドメインのレピュテーションを効果的に管理します。

[IP プールの作成](../using/configuration/ip-pools.md)
:::

::::
