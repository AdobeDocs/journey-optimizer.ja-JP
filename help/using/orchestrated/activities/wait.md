---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでの待機アクティビティの使用
description: 調整されたキャンペーンで待機アクティビティを使用する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 6439be00315dfde7ab385d7f848b7031d95060f4
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 13%

---

# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ キャンペーンの作成を調整するための主な手順 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成およびスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティの調整 ](orchestrate-activities.md)<br/><br/><b>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)</b><br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [ ](save-audience.md) [ ](activities/split.md) [ ](activities/wait.md) - |

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
