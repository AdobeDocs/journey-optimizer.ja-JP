---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーの公開
description: 選択したジャーニー指標を報告する方法について説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
keywords: 公開, ジャーニー, ライブ, 有効性, 確認
exl-id: 95d0267e-fab4-4057-8ab5-6f7c9c866b0f
source-git-commit: d28341dd39ec3ab838a5fbb3ae49539b8776c60b
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 96%

---

# ジャーニー指標の設定とトラッキング {#success-metrics}

ジャーニー指標を使用すると、定義済みの指標に対してアクティビティのパフォーマンスを追跡することで、アクティビティの影響を効果的に測定できます。
これらの指標を追跡することで、ジャーニーのパフォーマンスを確認し、改善すべき領域を特定し、情報に基づいた決定を行って顧客エンゲージメントを強化できます。

## 前提条件 {#prerequisites}

ジャーニー指標を使用する前に、`Commerce Details`、`Web` および `Mobile` の[フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#field-group){target="_blank"}を含むデータセットを追加する必要があります。

## 使用可能な指標 {#metrics}

指標のリストは、データセットに含まれる[フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#field-group){target="_blank"}によって異なります。

データセットが設定されていない場合は、**[!UICONTROL クリック]**、**[!UICONTROL ユニーククリック]**、**[!UICONTROL クリックスルー率]**&#x200B;および&#x200B;**[!UICONTROL 開封率]**&#x200B;の指標のみが使用可能になります。

Customer Journey Analytics ライセンスを使用すると、カスタム成功指標を作成できます。[詳細情報](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/participation-metric)


| 指標 | 関連フィールドグループ |
|-|-|
| クリック数 | フィールドグループは不要です |
| ユニーククリック数 | フィールドグループは不要です |
| クリックスルー率（CTR） | フィールドグループは不要です |
| クリックスルー開封率（CTOR） | フィールドグループは不要です |
| ページビュー数 | Web フィールドグループ |
| アプリの起動数 | モバイルフィールドグループ |
| アプリの初回起動数 | モバイルフィールドグループ |
| アプリインストール数 | モバイルフィールドグループ |
| アプリのアップグレード回数 | モバイルフィールドグループ |
| 購入 | コマースの詳細フィールドグループ |
| チェックアウト | コマースの詳細フィールドグループ |
| 買い物かごへの追加数 | コマースの詳細フィールドグループ |
| 買い物かごの開封数 | コマースの詳細フィールドグループ |
| 買い物かごの閲覧数 | コマースの詳細フィールドグループ |
| 買い物かごの削除数 | コマースの詳細フィールドグループ |
| 製品表示 | コマースの詳細フィールドグループ |
| 後で使用するために保存 | コマースの詳細フィールドグループ |

## アトリビューション {#attribution}

各指標には、特定の結果に貢献したタッチポイントまたはインタラクションを決定するアトリビューションが設定されます。

* **Journey Optimizer ライセンスを使用した指標アトリビューション**：

  Journey Optimizer ライセンスのみを使用した場合、選択した指標に対して使用可能な最大ルックバックウィンドウは 7 日間に設定されます。これらの指標の場合、アトリビューションモデルは、デフォルトで&#x200B;**ラストタッチ**、つまりコンバージョン前の最新のインタラクションに設定されます。

  例えば、過去 7 日以内に顧客がジャーニーにインタラクションを行った後に購入が行われたかどうかを追跡できます。

* **Customer Journey Analytics ライセンスを使用した指標アトリビューション**：

  Journey Optimizer ライセンスと Customer Journey Analytics ライセンスの両方を使用すると、特定のアトリビューション設定を使用してカスタム指標を作成したり、組み込み指標のアトリビューションを変更したりできます。

  詳細情報 [ アトリビューションモデル ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/component-settings/attribution#attribution-models)

## ジャーニー指標の割り当て {#assign}

ジャーニー指標のトラッキングを開始するには、次の手順に従います。

1. **[!UICONTROL ジャーニー]**&#x200B;メニューから、「**[!UICONTROL ジャーニーを作成]**」をクリックします。

1. ジャーニーの設定パネルを編集して、ジャーニーの名前を定義し、そのプロパティを設定します。ジャーニーのプロパティを設定する方法については、[ このページ ](../building-journeys/journey-properties.md) を参照してください。

1. ジャーニーの効果を測定するために使用する&#x200B;**[!UICONTROL ジャーニー指標]**&#x200B;を選択します。

   指標はジャーニー自体に適用され、ジャーニーのすべての要素に適用されます。

   ![](assets/success_metric.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

1. 必要な&#x200B;**[!UICONTROL アクティビティ]**&#x200B;を使用してジャーニーを設計します。

1. ジャーニーをテストして公開します。

1. ジャーニーレポートを開いて、割り当てられた成功指標のパフォーマンスを追跡します。

   選択した指標が、レポートの KPI とジャーニー統計テーブルに表示されます。

   ![](assets/success_metric_2.png)
