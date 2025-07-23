---
solution: Journey Optimizer
product: journey optimizer
title: AND 結合アクティビティの使用
description: 調整されたキャンペーンでの AND 結合アクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 1b99313e-f131-44f7-a129-f85e1977fb05
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 88%

---

# AND 結合 {#join}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join"
>title="「AND 結合」アクティビティ"
>abstract="**AND 結合**&#x200B;アクティビティを使用すると、調整されたキャンペーンの複数の実行分岐を同期させることができます。先行するアクティビティがすべて終了すると、トリガーされます。これにより、調整されたキャンペーンの実行を続ける前に、特定のアクティビティを確実に終了させることができます。"


+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [調整されたキャンペーンを作成する主な手順](../gs-campaign-creation.md)<br/><br/>[キャンペーンの作成とスケジュール](../create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](../orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](../start-monitor-campaigns.md)<br/><br/>[レポート](../reporting-campaigns.md) | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/><b>[AND 結合](and-join.md)</b> - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL AND 結合]**&#x200B;アクティビティは、**[!UICONTROL フロー制御]**&#x200B;アクティビティです。調整されたキャンペーンの複数の実行分岐を同期させることができます。

このアクティビティは、すべてのインバウンドトランジションが有効化された（つまり、前のアクティビティがすべて終了した）ときにのみ、アウトバウンドトランジションをトリガーします。これにより、調整されたキャンペーンの実行を続ける前に、特定のアクティビティを確実に終了させることができます。

## AND 結合アクティビティの設定{#and-join-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_and-join_merging"
>title="結合オプション"
>abstract="結合するアクティビティを選択します。 **プライマリセット**&#x200B;ドロップダウンで、保持するインバウンドトランジションの母集団を選択します。"

**[!UICONTROL AND 結合]**&#x200B;アクティビティを設定するには、次の手順に従います。

![](../assets/workflow-andjoin.png)

1. チャネルアクティビティなど、複数のアクティビティを追加して、2 つ以上の異なる実行分岐を作成します。

1. **[!UICONTROL AND 結合]**&#x200B;アクティビティをいずれかの分岐に挿入します。

1. 「**[!UICONTROL 結合オプション]**」セクションで、結合する前のアクティビティをすべて選択します。

1. **[!UICONTROL プライマリセット]**&#x200B;ドロップダウンから、保持するインバウンドトランジションの母集団を選択します。

## 例{#and-join-example}

この例では、調整された 2 つのキャンペーン分岐における、それぞれのメール配信（1 つはゴールドメンバーをターゲットにし、もう 1 つはシルバーメンバーをターゲットにしている）を示します。**[!UICONTROL AND 結合]**&#x200B;は、両方の受信トランジションがトリガーされるとアクティブ化され、7 日間の遅延の後、両方のメール配信が完了した後にのみ SMS が送信されます。

![](../assets/workflow-andjoin-example.png){zoomable="yes"}
