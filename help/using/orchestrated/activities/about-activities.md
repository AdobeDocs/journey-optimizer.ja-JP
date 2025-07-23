---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンアクティビティの操作
description: 調整されたキャンペーンアクティビティの操作方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 02f986b2-8200-4e0e-8918-44e528a6a3ec
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 91%

---

# 調整されたキャンペーンアクティビティについて {#orchestrated-campaign-activities}


+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [調整されたキャンペーンを作成する主な手順](../gs-campaign-creation.md)<br/><br/>[キャンペーンの作成とスケジュール](../create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](../orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](../start-monitor-campaigns.md)<br/><br/>[レポート](../reporting-campaigns.md) | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | <b>[アクティビティの基本を学ぶ](about-activities.md)</b><br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

調整されたキャンペーンアクティビティは、3 つのカテゴリにグループ化されます。使用可能なアクティビティは、コンテキストに応じて異なる場合があります。

すべてのアクティビティについて、以下の節で詳しく説明します。

* [ターゲティングアクティビティ](#targeting)
* [チャネルアクティビティ](#channel)
* [フロー制御アクティビティ](#flow-control)

![キャンバスで使用できるアクティビティのリスト](../assets/orchestrated-activities.png){width="80%" align="left"}

## ターゲティングアクティビティ {#targeting}

これらのアクティビティは、ターゲティングに固有です。オーディエンスを定義するか、積集合、和集合、除外の各操作を使用して分割または結合することで、1 つまたは複数のターゲットを作成できます。

![ターゲティングアクティビティのリスト](../assets/targeting-activities.png){width="40%" align="left"}

* [オーディエンスを作成](build-audience.md)：ターゲット母集団を定義します。既存のオーディエンスを選択するか、クエリモデラーを使用して独自のクエリを定義できます。
* [ディメンションを変更](change-dimension.md)：調整されたキャンペーンの作成時にターゲティングディメンションを変更します。
* [結合](combine.md)：インバウンド母集団に対してセグメント化を実行します。和集合、積集合または除外を使用できます。
* [重複排除 - 重複](deduplication.md)：インバウンドアクティビティの結果から重複を削除します。
* [エンリッチメント](enrichment.md)：調整されたキャンペーンで処理する追加のデータを定義します。このアクティビティでは、インバウンドトランジションを利用し、追加データを活用して出力トランジションを補完するようにアクティビティを設定できます。
* [紐付け](reconciliation.md)：Journey Optimizer データ内のデータと作業用テーブル内のデータ（外部ファイルから読み込まれたデータなど）を結ぶリンクを定義します。
* [分割](split.md)：入力母集団を複数のサブセットにセグメント化します。

## チャネルアクティビティ {#channel}

Adobe Journey Optimizer を使用すると、複数のチャネル間でマーケティングキャンペーンを自動化および実行できます。チャネルアクティビティをキャンバスに組み合わせて、顧客の行動に基づいてアクションをトリガーできるクロスチャネルの調整されたキャンペーンを作成できます。使用できる&#x200B;**チャネル**&#x200B;アクティビティは、メールと SMS です。[詳しくは、調整されたキャンペーンのコンテキストでのチャネルアクションの作成方法を参照してください](channels.md)。

## フロー制御アクティビティ {#flow-control}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_end"
>title="終了アクティビティ"
>abstract="**終了**&#x200B;アクティビティを使用すると、調整されたキャンペーンの終了をグラフィカルに示すことができます。このアクティビティは、機能上の影響はないので、省略可能です。"

![フロー制御アクティビティのリスト](../assets/flow-control-activities.png){width="30%" align="left"}

次のアクティビティは、調整されたキャンペーンの整理と実行に固有です。主なタスクは、他のアクティビティの調整です。

* [AND 結合](and-join.md)：調整されたキャンペーンの複数の実行分岐を同期します。
* [分岐](fork.md)：アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始します。
* [待機](wait.md)：調整されたキャンペーンの一部の実行を一時的に中断します。
  <!--* [Test](test.md): Enable transitions based on specified conditions.-->

>[!NOTE]
>**終了**&#x200B;アクティビティは、調整されたキャンペーンの終了をグラフィカルに示します。このアクティビティは、機能上の影響はないので、省略可能です。
