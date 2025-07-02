---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerで調整されたキャンペーンのレポート
description: Adobe Journey Optimizerを使用してオーケストレートキャンペーンに関するレポートにアクセスする方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 8cb569a2-a4a0-45a5-b7f9-f5a591e44335
source-git-commit: 1a76d5349de807fe106535424940a8eca3922797
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 14%

---

# 調整されたキャンペーンレポート {#report-campaigns}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ キャンペーンの作成を調整するための主な手順 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成およびスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティの調整 ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)<br/><br/><b>[ レポート ](reporting-campaigns.md)</b> | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [&#128279;](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

調整されたキャンペーンは、その堅牢なレポート機能を通じて、実用的なインサイトを提供します。 これらのインサイトは、オーディエンスの行動をより深く理解し、カスタマージャーニーの各ステップのパフォーマンスを測定し、今後のキャンペーンを最適化するためのデータ駆動型の決定を行うのに役立ちます。 詳細な指標とビジュアライゼーションを使用すると、エンゲージメントを追跡し、ターゲティング戦略を微調整して、最大の効果を得ることができます。

<table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="メール" src="../channels/assets/do-not-localize/email.png">
<div align="center"><p><a href="../reports/campaign-global-report-cja-email.md"><strong>メールチャネル</strong></a></p></div></td>
<td><a href="../reports/campaign-global-report-cja-sms.md"><img alt="SMS" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><p><a href="../reports/campaign-global-report-cja-sms.md"><strong>SMS チャネル</strong></a></p></div></td>
<td><a href="../reports/campaign-global-report-cja-push.md"><img alt="プッシュ" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><p><a href="../reports/campaign-global-report-cja-push.md"><strong>プッシュチャネル</strong></p></a></div></td>
</table>


## レポートのタイプ {#reporting-types}


| レポートタイプ | 説明 |
|-----|------------|
| ![](assets/last-24hours.png){zoomable="yes"}{width="50%"} | **[!UICONTROL ライブレポート]** を使用し、オーケストレーションしたキャンペーンの影響とパフォーマンスを組み込みダッシュボードでリアルタイムに測定および視覚化します。 調整したキャンペーンが **[!UICONTROL 過去 24 時間のレポートを表示]** メニューから実行されるとすぐに、**[!UICONTROL ライブレポート]** でデータを入手できます。 ライブレポートについて詳しくは、[この節](../reports/live-report.md)を参照してください。 |
| ![](assets/all-time-report.png){zoomable="yes"}{width="50%"} | 調整されたキャンペーンレポートは、Customer Journey Analytics機能と完全に統合され、両方のプラットフォーム間でレポートを標準化し、データの一貫性と信頼性を向上させます。  すべての時間レポートについて詳しくは [ この節 ](../reports/report-gs-cja.md) を参照してください。 |
