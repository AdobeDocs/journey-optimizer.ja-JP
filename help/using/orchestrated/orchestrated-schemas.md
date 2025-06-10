---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーン用のリレーショナルスキーマの作成
description: 調整されたキャンペーン用のリレーショナルスキーマを作成および管理する方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: b0125a50-d187-49fc-ad12-bbe6650f8f1e
source-git-commit: dd1a9b6e14617014756e5b4449578a1f7bf805b4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 32%

---

# リレーショナルスキーマの作成 {#orchestrated-schemas}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンの作成 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

スキーマは、データの構造と形式を表し、検証します。現実のオブジェクト (人物など) の概念上の定義を提供し、そのオブジェクトの各インスタンスに含める必要があるデータ (名前や誕生日など) の概要を説明します。

![ 「リレーショナル」オプションが選択された「スキーマを作成」ボタン ](assets/create-relational-schema.png)
