---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerで調整されたキャンペーンのレポート
description: Adobe Journey Optimizerを使用してオーケストレートキャンペーンに関するレポートにアクセスする方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 8cb569a2-a4a0-45a5-b7f9-f5a591e44335
source-git-commit: 8a6fc9fca96bfab90a72be329e2ab99c6942a4a7
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 15%

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


## レポートのタイプ {#reporting-types}

<table style="table-layout:auto; width: 100%; border-collapse: collapse;">
  <tbody>
    <tr>
      <td><a href="../reports/live-report.md"><img alt="ライブレポート" src="assets/last-24hours.png"></a></td>
      <td>
        <b> ライブレポート </b> を使用し、オーケストレーションしたキャンペーンの影響とパフォーマンスを組み込みダッシュボードでリアルタイムに測定および視覚化します。 調整したキャンペーンが <b> 過去 24 時間のレポートを表示 </b> メニューから実行されるとすぐに、<b> ライブレポート </b> でデータを入手できます。 ライブレポートについて詳しくは、<a href="../reports/live-report.md">この節</a>を参照してください。
      </td>
        </br>
    </tr>
    <tr style="background-color: #FFFFFF;">
      <td><a href="../reports/report-gs-cja.md"><img alt="全期間のレポート" src="assets/all-time-report.png"></a></td>
      <td>
        調整されたキャンペーンレポートは、Customer Journey Analytics機能と完全に統合され、両方のプラットフォーム間でレポートを標準化し、データの一貫性と信頼性を向上させます。 <a href="../reports/report-gs-cja.md"> すべての時間レポート </a> の詳細情報。
      </td>
    </tr>
  </tbody>
</table>

## チャネルレポートの詳細

<table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="メール" src="../channels/assets/do-not-localize/email.png">
<div align="center"><p><a href="../reports/campaign-global-report-cja-email.md"><strong>メールチャネル</strong></a></p></div></td>
<td><a href="../reports/campaign-global-report-cja-sms.md"><img alt="SMS" src="../channels/assets/do-not-localize/sms.png"></a>
<div align="center"><p><a href="../reports/campaign-global-report-cja-sms.md"><strong>SMS チャネル</strong></a></p></div></td>
<td><a href="../reports/campaign-global-report-cja-push.md"><img alt="プッシュ" src="../channels/assets/do-not-localize/push.png"></a>
<div align="center"><p><a href="../reports/campaign-global-report-cja-push.md"><strong>プッシュチャネル</strong></p></a></div></td>
</table>
