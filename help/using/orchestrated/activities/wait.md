---
solution: Journey Optimizer
product: journey optimizer
title: オーケストレートキャンペーンでの待機アクティビティの使用
description: オーケストレートキャンペーンでの待機アクティビティの使用方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 11ef095b-77ec-4e2e-ab4d-49a248354f08
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 62%

---

# 待機 {#wait}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_wait"
>title="待機アクティビティ"
>abstract="**待機**&#x200B;アクティビティは、アクティビティ間のトランジションを遅延させるために使用します。"


+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - <b>[待機](wait.md)</b> |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL 待機]** アクティビティは、オーケストレーションされたキャンペーンで 2 つのアクティビティ間に遅延を導入するために使用される **[!UICONTROL フロー制御]** コンポーネントです。 これにより、フォローアップアクティビティの時間を短縮し、ユーザーエンゲージメントとの関連性を高めることができます。

例えば、メール配信後に数日待機して、開封数とクリック数を追跡してから、フォローアップメッセージを送信できます。

## 設定{#wait-configuration}

**[!UICONTROL 待機]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL 待機]** アクティビティをオーケストレーションされたキャンペーンに追加します。

1. ニーズに最適な待機タイプを選択します。

   * **[!UICONTROL 期間]**：次のアクティビティに進む前に、秒、分、時間、日で遅延を指定します。

   * **[!UICONTROL 固定時間]**：次のアクティビティが開始される特定の日時を設定します。

   ![](../assets/wait_activity.png)

## 例{#wait-example}

次に、**[!UICONTROL 待機]**&#x200B;アクティビティの一般的なユースケースを示します。誕生日を祝うプロファイルには、プロモーションコードが記載されたメールが送信されます。29 日後、誕生日のプロモーションコードの有効期限が近づいていることを示すリマインダーとして、SMS が同じグループに送信されます。

![](../assets/wait-example.png)
