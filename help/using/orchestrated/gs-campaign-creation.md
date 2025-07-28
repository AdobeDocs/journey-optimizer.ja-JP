---
solution: Journey Optimizer
product: journey optimizer
title: オーケストレートキャンペーンを作成するための主な手順
description: Adobe Journey Optimizerを使用したオーケストレートキャンペーン作成の主な原則について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: b04aa15a-71bf-4683-bcbf-f611c189ffe1
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 60%

---


# オーケストレートキャンペーンを作成するための主な手順 {#orchestrated-campaign-creation}

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレートキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/><b>[ オーケストレートキャンペーンを作成するための主な手順 ](gs-campaign-creation.md)</b> | [キャンペーンの作成とスケジュール](create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](start-monitor-campaigns.md)<br/><br/>[レポート](reporting-campaigns.md) | [ルールビルダーの操作](orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](build-query.md)<br/><br/>[式の編集](edit-expressions.md)<br/><br/>[リターゲティング](retarget.md) | [アクティビティの基本を学ぶ](activities/about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](activities/and-join.md) - [オーディエンスを作成](activities/build-audience.md) - [ディメンションを変更](activities/change-dimension.md) - [チャネルアクティビティ](activities/channels.md) - [結合](activities/combine.md) - [重複排除](activities/deduplication.md) - [エンリッチメント](activities/enrichment.md) - [分岐](activities/fork.md) - [紐付け](activities/reconciliation.md) - [オーディエンスを保存](activities/save-audience.md) - [分割](activities/split.md) - [待機](activities/wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

このページでは、設定と設計から監視とレポートに至るまで、オーケストレートキャンペーンを作成して開始するための基本的な手順について説明します。

<!--
<table style="table-layout:fixed"><tr style="border: 0; text-align: center;" >
<td><a href="#create"><img alt="Create & schedule your campaign" src="../../channels/assets/do-not-localize/email.png"></a><br/><a href="#create"><strong>Create & schedule your campaign</strong></a></td>
<td><a href="#orchestrate"><img alt="Orchestrate campaign activities" src="../../channels/assets/do-not-localize/sms.png"></a><br/><a href="#orchestrate"><strong>Orchestrate campaign activities</strong></a></td>
<td><a href="#start"><img alt="Start & monitor your campaign" src="../../channels/assets/do-not-localize/push.png"></a><a href="#start"><strong>Start & monitor your campaign</strong></a></td>
<td><a href="#report"><img alt="Analyze & report on results" src="../../channels/assets/do-not-localize/push.png"></a><a href="#report"><strong>Analyze & report on results</strong></a></td>
</tr></table>-->



## 手順 1：キャンペーンの作成とスケジュール {#create}

何よりも先に、オーケストレートキャンペーンを作成し、実行する *タイミング* を定義する必要があります。 1 回限りのプッシュか、繰り返しのマルチチャネルキャンペーンかに関わらず、タイミングと頻度を完全に制御できます。

➡️ [キャンペーンの作成とスケジュール方法の詳細情報](../orchestrated/create-orchestrated-campaign.md)

## 手順 2：キャンペーンアクティビティの調整{#orchestrate}

キャンペーンを作成したら、背後にあるロジックをデザインします。 視覚的なキャンバスを使用すると、ターゲティング、配信、フロー制御の各アクティビティを組み合わせて、顧客体験を形成できます。

➡️ [詳しくは、アクティビティの調整方法を参照してください。](../orchestrated/orchestrate-activities.md)

## 手順 3：キャンペーンの開始と監視 {#start}

もう少しで着くよ。 最初にテストモードでキャンペーンを実行し、問題がないか確認します。次に、キャンペーンを公開し、ライブ実行をリアルタイムで監視します。進行状況を追跡し、エラーを確認し、各手順でプロファイルのフローの確認を行います。

➡️ [詳しくは、キャンペーンの開始と監視方法を参照してください。](../orchestrated/start-monitor-campaigns.md)

## 手順 4：結果の分析とレポート {#report}

ローンチ後は、ビルトインレポートを使用して、何がうまくいったか、何を改善できるかを把握します。リアルタイムのダッシュボードと詳細な分析により、今後のキャンペーンを最適化し、戦略を改善できます。

➡️ [詳しくは、レポートを参照してください。](../orchestrated/reporting-campaigns.md)

## さらなる改善を行うには：エンゲージメントに基づくリターゲティング {#retarget}

キャンペーンを実行したら、メッセージを開いたか、リンクをクリックしたかなど、メッセージとのやり取りに基づいてプロファイルをリターゲティングすることで、キャンペーンをさらに向上させることができます。これにより、カスタマイズされたメッセージをフォローアップしたり、非アクティブなユーザーに再度惹きつけたり、興味を倍増させたりすることができます。

➡️ [詳しくは、フィードバックイベントに基づいてリターゲティングする方法を参照してください。](../orchestrated/retarget.md)
