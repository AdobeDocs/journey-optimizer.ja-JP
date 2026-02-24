---
solution: Journey Optimizer
product: Journey Optimizer
title: メッセージとジャーニーのキャッピングルールの設定
description: メッセージとジャーニーのキャッピングルールの設定
redpen-status: CREATED_||_2025-08-11_20-28-34
exl-id: 630e252a-aab2-4a27-ad46-d4dbfbc3f3a4
source-git-commit: 9e23162373564e7866af115ee2cd706527336e4a
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 38%

---

# メッセージとジャーニーのキャッピングルールの設定{#section-overview}

キャッピングルールは、[ 競合管理と優先順位付け ](../using/conflict-prioritization/gs-conflict-prioritization.md) の一部で、顧客が圧倒されることなく適切な量のコミュニケーションを確実に受け取れるように役立ちます。 ルールを適用する前に、[ 競合検出ツール ](../using/conflict-prioritization/conflicts.md) を使用して、重複するジャーニーとキャンペーンを特定します。 複数の通信が同じプロファイルに適合する場合、[ 優先度スコア ](../using/conflict-prioritization/priority-scores.md) によって最初に配信されるメッセージが決まります。

メッセージの送信頻度（フリークエンシーキャップ）、プロファイルがエントリできるジャーニーの数（ジャーニーキャッピング）、メッセージのブロックタイミング（処理が停止している時間）に制限を設定できます。 ルールは **ルールセット** にグループ化され、キャンペーンやジャーニーに適用されます。 外部システムからのプログラム制御については、[Capping API](../using/configuration/capping.md) を参照してください。

## メッセージとジャーニーのキャッピングルールの設定

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

ルールセットの操作

Adobe Journey Optimizer で、メッセージの頻度とジャーニーエントリルールを制御するルールセットを作成、管理、アクティブ化する方法について説明します。

[ルールセットの探索](../using/conflict-prioritization/rule-sets.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

ジャーニーのキャップと判別

ジャーニーのエントリと同時実行の上限を設定し、ジャーニーに優先順位を付け、除外を監視して通信の過負荷を防ぐ方法について説明します。

[ジャーニーのキャップの詳細情報](../using/conflict-prioritization/journey-capping.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

チャネル別のフリークエンシーキャップ

チャネル固有のフリークエンシーキャップルールを作成および適用し、メッセージの配信を最適化して、過剰なコミュニケーションを回避する方法について説明します。

[フリークエンシーキャップの設定](../using/conflict-prioritization/channel-capping.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg)

クワイエット時間の設定

メール、SMS、プッシュ、WhatsApp に対して時間ベースの除外を定義し、特定の期間中にメッセージが送信されないようにします。これにより、顧客の環境設定とコンプライアンスが考慮されます。

[クワイエットアワーの設定](../using/conflict-prioritization/quiet-hours.md)
:::

::::

## その他のリソース

- **[競合管理と優先順位付けの概要](../using/conflict-prioritization/gs-conflict-prioritization.md)** – 競合検出、優先度スコアおよびルールセットの概要。
- **[潜在的な競合の特定](../using/conflict-prioritization/conflicts.md)** - キャッピングルールを適用する前に、重複するジャーニーとキャンペーンを検出します。
- **[優先度スコアの割り当て](../using/conflict-prioritization/priority-scores.md)** - プロファイルが複数の通信の対象となる際に、どのジャーニーまたはキャンペーンを優先するかを制御します。
