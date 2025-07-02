---
solution: Journey Optimizer
product: journey optimizer
title: 分岐アクティビティの使用
description: 調整されたキャンペーンで「分岐」アクティビティを使用する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
source-git-commit: 7de878c316e966129e7dede37f132938d2abbdf8
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 35%

---

# 分岐 {#fork}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork"
>title="「分岐」アクティビティ"
>abstract="**分岐**&#x200B;アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork_transitions"
>title="分岐アクティビティのトランジション"
>abstract="デフォルトでは、**分岐**&#x200B;アクティビティで 2 つのトランジションが作成されます。 「**トランジションを追加**」ボタンをクリックして追加のアウトバウンドトランジションを定義し、そのラベルを入力します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションの変更 ](change-dimension.md) - [ チャネルアクティビティ ](channels.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) [&#128279;](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

**[!UICONTROL 分岐]** アクティビティは、複数のアウトバウンドトランジションを作成し、複数のアクティビティを並行して実行できる **[!UICONTROL フロー制御]** コンポーネントです。

## 分岐アクティビティの設定{#fork-configuration}

次の手順に従って、**[!UICONTROL 分岐]**&#x200B;アクティビティを設定します。

![](../assets/workflow-fork.png)

1. **[!UICONTROL 分岐]** アクティビティをオーケストレーションされたキャンペーンに追加します。

1. **[!UICONTROL ラベル]** を定義します。

1. 各アウトバウンドトランジションにラベルを割り当てます。 デフォルトでは、2 つのトランジションが用意されています。

1. トランジションを削除するには、トランジシ ![](../assets/do-not-localize/Smock_Delete_18_N.svg) ン アイコンをクリックします。

1. 必要に応じて、「**[!UICONTROL トランジションを追加]**」をクリックして、アウトバウンドトランジションを追加します。
