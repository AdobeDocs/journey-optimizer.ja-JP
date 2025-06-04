---
solution: Journey Optimizer
product: journey optimizer
title: クエリModelerの操作
description: 調整されたキャンペーン用のクエリを作成する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
source-git-commit: 2935e611bb9682256a324485b28e7dd2552e1dd2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 19%

---


# クエリModelerの操作 {#orchestrated-query-modeler}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ クエリの操作Modeler](orchestrated-query-modeler.md)<br/><br/>[ 最初のクエリ ](build-query.md)<br/><br/>[ 編集式を作成 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/><br/>

>[!BEGINSHADEBOX]

ドキュメントを処理中

>[!ENDSHADEBOX]

オーケストレートキャンペーンには、様々な条件に基づいてデータベースをフィルタリングするプロセスを簡素化するクエリモデラーが付属しています。 クエリモデラーは、非常に複雑で長いクエリを効率的に管理し、柔軟性と精度を向上させます。 また、条件内で定義済みフィルターをサポートしているので、ユーザーは包括的なオーディエンスのターゲティングとセグメント化戦略に高度な式と演算子を利用しながら、クエリを簡単に絞り込むことができます。

<!--rapatrier docs utiles de la doc Web UI -->
