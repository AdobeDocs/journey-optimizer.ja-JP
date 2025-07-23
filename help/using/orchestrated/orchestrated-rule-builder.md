---
solution: Journey Optimizer
product: journey optimizer
title: ルールビルダーの操作
description: 調整されたキャンペーンのルールの作成方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 87%

---


# ルールビルダーの操作 {#orchestrated-rule-builder}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [キャンペーンの作成とスケジュール](create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](start-monitor-campaigns.md)<br/><br/>[レポート](reporting-campaigns.md) | <b>[ルールビルダーの操作](orchestrated-rule-builder.md)</b><br/><br/>[最初のクエリの作成](build-query.md)<br/><br/>[式の編集](edit-expressions.md)<br/><br/>[リターゲティング](retarget.md) | [アクティビティの基本を学ぶ](activities/about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](activities/and-join.md) - [オーディエンスを作成](activities/build-audience.md) - [ディメンションを変更](activities/change-dimension.md) - [チャネルアクティビティ](activities/channels.md) - [結合](activities/combine.md) - [重複排除](activities/deduplication.md) - [エンリッチメント](activities/enrichment.md) - [分岐](activities/fork.md) - [紐付け](activities/reconciliation.md) - [オーディエンスを保存](activities/save-audience.md) - [分割](activities/split.md) - [待機](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

調整されたキャンペーンには、様々な条件に基づいてデータベースをフィルタリングするプロセスを簡素化するルールビルダーが付属しています。ルールビルダーは非常に複雑で長いクエリを効率的に管理し、柔軟性と精度を向上させます。

また、条件内で定義済みフィルターをサポートしているので、包括的なオーディエンスのターゲティングとセグメント化戦略に高度な式と演算子を利用しながら、クエリを簡単に絞り込むことができます。

## ルールビルダーへのアクセス

クエリモデラーは、データをフィルタリングするルールを定義する必要があるすべてのコンテキストで使用できます。

| 用途 | 例 |
|  ---  |  ---  |
| **オーディエンスを作成**：**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを使用して、調整されたキャンペーンでターゲットにする母集団を指定し、ニーズに合わせて新しいオーディエンスを簡単に作成します。[詳しくは、オーディエンスの作成方法を参照してください。](../orchestrated/activities/build-audience.md) | ![オーディエンス作成インターフェイスへのアクセス方法を示す画像](assets/query-access-audience.png){width="200" align="center" zoomable="yes"} |
| **キャンペーンキャンバスで条件を作成**：特定の要件に合わせて、**[!UICONTROL 分割]**&#x200B;アクティビティを使用してキャンペーンキャンバス内でルールを適用します。[分割アクティビティの使用方法の詳細情報](../orchestrated/activities/split.md) | ![ワークフローのカスタマイズオプションへのアクセス方法を示す画像](assets/query-access-split.png){width="200" align="center" zoomable="yes"} |
| **詳細フィルターを作成**：ワークフローログやターゲティングディメンションなどのリストに表示されるデータをフィルタリングするルールを作成します。 | ![リストフィルターのカスタマイズ方法を示す画像](assets/query-access-advanced-filters.png){width="200" align="center" zoomable="yes"} |

## ルールビルダーインターフェイス {#interface}

ルールビルダーは、クエリを作成する中央のキャンバスと、ルールに関する情報を示すプロパティパネルを提供します。

![ルールモデラーインターフェイスを示す画像](assets/rule-builder-interface.png)

* **中央のキャンバス**&#x200B;では、ルールを作成する様々なコンポーネントを追加して組み合わせます。[詳しくは、クエリの作成方法を参照してください。](../orchestrated/build-query.md)

* **[!UICONTROL ルールのプロパティ]**&#x200B;パネルには、ルールに関する情報が表示されます。これにより、様々な操作を実行してルールを確認し、ニーズに合うことを確認できます。

  このパネルは、オーディエンスを作成するクエリを作成する際に表示されます。[クエリを確認および検証する方法を学ぶ](build-query.md#check-and-validate-your-query)
