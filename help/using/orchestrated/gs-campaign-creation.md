---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンを作成するための主な手順
description: Adobe Journey Optimizerを使用したオーケストレートキャンペーン作成の主な原則について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: b04aa15a-71bf-4683-bcbf-f611c189ffe1
source-git-commit: 779c90f0be57749a63da103d18cc642106c5f837
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---


# 調整されたキャンペーンを作成するための主な手順 {#orchestrated-campaign-creation}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/><b>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md)</b> | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [ ](activities/save-audience.md) [ ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

ドキュメントを処理中

>[!ENDSHADEBOX]

このページでは、設定と設計から監視とレポートまで、調整されたキャンペーンを作成して開始するための基本的な手順について説明します。

<!--
<table style="table-layout:fixed"><tr style="border: 0; text-align: center;" >
<td><a href="#create"><img alt="Create & schedule your campaign" src="../../channels/assets/do-not-localize/email.png"></a><br/><a href="#create"><strong>Create & schedule your campaign</strong></a></td>
<td><a href="#orchestrate"><img alt="Orchestrate campaign activities" src="../../channels/assets/do-not-localize/sms.png"></a><br/><a href="#orchestrate"><strong>Orchestrate campaign activities</strong></a></td>
<td><a href="#start"><img alt="Start & monitor your campaign" src="../../channels/assets/do-not-localize/push.png"></a><a href="#start"><strong>Start & monitor your campaign</strong></a></td>
<td><a href="#report"><img alt="Analyze & report on results" src="../../channels/assets/do-not-localize/push.png"></a><a href="#report"><strong>Analyze & report on results</strong></a></td>
</tr></table>-->



## 手順 1：キャンペーンの作成とスケジュール {#create}

何よりも先に、オーケストレーションされたキャンペーンを作成し、キャンペーンを実行する *タイミング* を定義する必要があります。 1 回限りのプッシュか、繰り返しのマルチチャネルキャンペーンかに関わらず、タイミングと頻度を完全に制御できます。

➡️[ キャンペーンの作成およびスケジュール方法を学ぶ ](../orchestrated/create-orchestrated-campaign.md)

## 手順 2：キャンペーンアクティビティの調整 {#orchestrate}

キャンペーンを作成したら、背後にあるロジックをデザインします。 視覚的なキャンバスを使用すると、ターゲティング、配信、フロー制御の各アクティビティを組み合わせて、顧客体験を形成できます。

➡️[ アクティビティの調整方法については、こちらを参照してください ](../orchestrated/orchestrate-activities.md)

## 手順 3：キャンペーンの開始と監視 {#start}

もう少しで着くよ。 最初にテストモードでキャンペーンを実行して、問題を見つけます。 その後、公開してリアルタイムでライブ実行を監視し、進行状況の追跡、エラーのチェック、各ステップでのプロファイルのフローの確認を行います。

➡️[ キャンペーンの開始および監視方法を学ぶ ](../orchestrated/start-monitor-campaigns.md)

## 手順 4：結果の分析とレポート {#report}

ローンチ後、ビルトインレポートを使用して、何がうまくいったか、何を改善できるかを把握します。 リアルタイムダッシュボードと詳細な分析は、今後のキャンペーンを最適化し、戦略を絞り込むのに役立ちます。

➡️ [ レポートの詳細 ](../orchestrated/reporting-campaigns.md)

## 手順：エンゲージメントに基づく再ターゲット {#retarget}

キャンペーンが実行されたら、キャンペーンを開いたかどうかやリンクをクリックしたかどうかなど、メッセージとのやり取りに基づいてプロファイルをリターゲティングすることで、キャンペーンをさらに一歩進めることができます。 これにより、カスタマイズされたメッセージをフォローアップしたり、非アクティブなユーザーを再エンゲージしたり、興味のあるユーザーをダブルクリックしたりできます。

➡️ [ フィードバックイベントに基づいて再ターゲットする方法を学ぶ ](../orchestrated/retarget.md)
