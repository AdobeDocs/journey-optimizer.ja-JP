---
solution: Journey Optimizer
product: journey optimizer
title: ルールビルダーの操作
description: オーケストレートキャンペーン用のルールを作成する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
source-git-commit: 5ebc82f566d416a177a3278816c60d896a10eff6
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 16%

---


# ルールビルダーの操作 {#orchestrated-rule-builder}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ キャンペーンの作成を調整するための主な手順 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成およびスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティの調整 ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | <b>[ ルールビルダーの操作 ](orchestrated-rule-builder.md)</b><br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [&#128279;](activities/save-audience.md) [&#128279;](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

オーケストレートキャンペーンには、様々な条件に基づいてデータベースをフィルタリングするプロセスを簡素化するルールビルダーが付属しています。 ルールビルダーは、非常に複雑で長いクエリを効率的に管理し、柔軟性と精度を向上させます。

また、条件内で定義済みフィルターもサポートされているので、高度な式や演算子を利用して包括的なオーディエンスのターゲティングやセグメント化戦略を行いながら、簡単にクエリを絞り込むことができます。

## ルールビルダーへのアクセス

クエリモデラーは、データをフィルタリングするルールを定義する必要があるすべてのコンテキストで使用できます。

| 用途 | 例 |
|  ---  |  ---  |
| **オーディエンスの作成**:**[!UICONTROL オーディエンスの作成]** アクティビティを使用して、オーケストレーションされたキャンペーンでターゲットにする母集団を指定し、ニーズに合わせて新しいオーディエンスを簡単に作成します。 [詳しくは、オーディエンスの作成方法を参照してください。](../orchestrated/activities/build-audience.md) | ![ オーディエンス作成インターフェイスへのアクセス方法を示す画像 ](assets/query-access-audience.png){width="200" align="center" zoomable="yes"} |
| **キャンペーンキャンバスでの条件の作成**:**[!UICONTROL 分割]** アクティビティを使用して、キャンペーンキャンバス内でルールを適用し、特定の要件に合わせます。 [ 分割アクティビティの使用方法を学ぶ ](../orchestrated/activities/split.md) | ![ ワークフローのカスタマイズオプションへのアクセス方法を示す画像 ](assets/query-access-split.png){width="200" align="center" zoomable="yes"} |
| **詳細フィルターの作成**：ワークフローログやターゲティングディメンションなどのリストに表示されるデータをフィルタリングするルールを作成します。 | ![ リストフィルターのカスタマイズ方法を示す画像 ](assets/query-access-advanced-filters.png){width="200" align="center" zoomable="yes"} |

## ルールビルダーインターフェイス {#interface}

ルールビルダーは、クエリを構築するための中央キャンバスと、ルールに関する情報を提供するプロパティペインを提供します。

![ ルールビルダーインターフェイスを示す画像 ](assets/rule-builder-interface.png)

* **中央キャンバス** では、様々なコンポーネントを追加および組み合わせてルールを作成します。 [ ルールの作成方法を学ぶ ](../orchestrated/build-query.md)

* **[!UICONTROL ルールのプロパティ]** ペインには、ルールに関する情報が表示されます。 様々な操作を実行してルールを確認し、ニーズに合っていることを確認できます。

  このパネルは、オーディエンスを作成するクエリを作成する際に表示されます。[クエリを確認および検証する方法を学ぶ](build-query.md#check-and-validate-your-query)
