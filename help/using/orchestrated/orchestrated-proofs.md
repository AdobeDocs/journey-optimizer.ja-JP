---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerを使用して調整されたキャンペーンでメッセージをテストし検証します
description: Adobe Journey Optimizerで調整されたキャンペーンで、配達確認を送信し、コンテンツとパーソナライゼーションを検証する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 54d8b2fb-745d-459c-85d6-c224aa5e352e
source-git-commit: 450f83eb53068df10a63d39d1a43483ad3c7e803
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 5%

---

# メッセージのテストと検証 {#orchestrated-proofs}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](create-orchestrated-campaign.md)<br/><br/>[ オーケストレーションされたキャンペーンの設定 ](orchestrated-campaign-settings.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンを使用したメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

ドキュメントを処理中

>[!ENDSHADEBOX]

Campaign マネージャーは、パーソナライズされたメッセージの **配達確認バージョン** を事前に定義された内部レビュー担当者のリストに送信して、本格的にローンチする前にすべてのコンテンツ、パーソナライゼーション、リンクが期待どおりに動作することを確認できます。
