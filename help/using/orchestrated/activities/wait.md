---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでの待機アクティビティの使用
description: 調整されたキャンペーンで待機アクティビティを使用する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 28284b3d42a0e78add3470ef128dd740f9cc9dfd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 14%

---

# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションの変更 ](change-dimension.md) - [ チャネルアクティビティ ](channels.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) [ ](split.md) [ ](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

**[!UICONTROL 待機]** アクティビティは、調整されたキャンペーンで 2 つのアクティビティ間に遅延を導入するために使用される **[!UICONTROL フロー制御]** コンポーネントです。 これにより、フォローアップアクティビティの時間を短縮し、ユーザーエンゲージメントとの関連性を高めることができます。

例えば、メール配信の数日後に開封数とクリック数のトラックを待機してから、フォローアップメッセージを送信することができます。

## 設定{#wait-configuration}

**[!UICONTROL 待機]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL 待機]** アクティビティを、調整したキャンペーンに追加します。

1. ニーズに最適な待機タイプを選択します。

   * **[!UICONTROL 期間]**：次のアクティビティに進むまでの遅延時間を、秒、分、時間、日で指定します。

   * **[!UICONTROL 固定時間]**：次のアクティビティを開始するまでの特定の日時を設定します。

   ![](../assets/wait_activity.png)

## 例{#wait-example}

以下に、**[!UICONTROL 待機]** アクティビティの一般的なユースケースを示します。  プロモーションコードを含むメールが、誕生日を祝うプロファイルに送信されます。 29 日後、誕生日のプロモーションコードの有効期限が近づいていることを示すリマインダーとして、SMS が同じグループに送信されます。

![](../assets/wait-example.png)
