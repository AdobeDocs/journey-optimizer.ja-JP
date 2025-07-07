---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンの基本を学ぶ
description: 調整されたキャンペーンを開始する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 611dd06d-aa18-4fa3-a477-8a910cec21d8
source-git-commit: a19fe429d34a88c6159ab3b2b4dfa3768bcd24ad
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 17%

---

# 調整されたキャンペーンの基本を学ぶ {#orchestrated-camp}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| <b>[ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)</b><br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [ ](activities/save-audience.md) [ ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

## オーケストレートキャンペーンとは

キャンペーンのオーケストレーションは、ブランド主導の堅牢なバッチキャンペーン機能を導入することでAdobe Journey Optimizerを強化し、高度なセグメント化戦略を使用してクロスチャネルキャンペーンの計画と調整を行えるようにします。

クロスチャネルマーケティングは、顧客に効果的にリーチすることを目指すあらゆるビジネスにとって不可欠です。Adobe Journey Optimizerは、マーケティングキャンペーンを簡単に管理するのに役立つ複雑なプロセスを設定できる包括的なグラフィカル環境を提供します。 調整されたキャンペーンを使用すると、あらゆるプロセスとタスクを調整し、セグメントの作成やメッセージの準備から配信に至るまでの、マーケティングキャンペーンのあらゆる側面でスピードと規模を改善できます。 さらに、キャンペーンオーケストレーション用の使いやすい単一のインターフェイスでチャネルを同期させることができます。

調整されたキャンペーンの最も大きな利点の 1 つは、あらゆるチャネルにわたってパーソナライズされたコンテンツを簡単に顧客に配信できる点です。 顧客がメールやモバイルでのメッセージの受信を好む場合でも、Adobe Journey Optimizerでは、あらゆるチャネルで一貫したコンテキストに沿ったエクスペリエンスを提供し、すべての顧客のジャーニーを独自のエクスペリエンスに変換できます。

オーケストレートキャンペーンは非常に汎用性が高く、オーディエンスの管理やメッセージの送信のターゲティング、データを操作するためのデータ管理（ETL）、データのインポートなど、様々なコンテキストで使用できます。

包括的なグラフィカル環境を使用すると、セグメント化、キャンペーン実行、ファイル処理などのプロセスを設計できます。 また、調整されたキャンペーンには、タスクを割り当てたり、実行されたタスクを承認したりすることで、ユーザーを参加させることもできます。これにより、チームの作業を容易に管理し、すべてが正しく実行されるようになります。

## ジャーニーオーケストレーションとキャンペーンオーケストレーション

Campaign オーケストレーションは、ブランドコミュニケーションを大規模に設計、送信、追跡するための主要なモジュールです。 プロファイルエンティティとプロファイル以外のエンティティを組み合わせることで、既存のデータセグメントを活用して効果的なパーソナライゼーションを行い、ターゲットオーディエンスに対するマーケティングメッセージの自動配信を可能にします。 キャンペーン主導のアウトリーチに最適な Campaign オーケストレーションは、多くの場合、事前にスケジュールされた、一貫性のある効率的なメッセージ配信を確保して、顧客エンゲージメントを促進し、主要なマーケティング目標をサポートします。

Campaign Orchestration は、Adobe Journey Optimizerにマルチエンティティを有効化することでオーディエンスのセグメント化を再定義し、特定のステータス、イベント、契約、予約などに基づいてターゲットメッセージングを容易にします。 プロファイル以外のエンティティにコミュニケーションを送信したり、任意のエンティティに対してクエリを作成したりできるので、全体像を把握し、幅広いインサイトを取得してオーディエンスを構築できます。

データに基づく意思決定を可能にする Campaign オーケストレーションでは、動的にエンリッチメントされたデータセットに対して複数のソースを活用します。

## 前提条件

>[!BEGINSHADEBOX]

ドキュメントを処理中

>[!ENDSHADEBOX]

<!--prerequisites & permissions-->

## さらに深く掘り下げましょう

これで、Adobe Campaign でワークフローの概要と使用できる操作を理解できたので、ドキュメントの節で詳しく説明し、この機能の使用を開始します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="gs-campaign-creation.md">
<img alt="ワークフローへのアクセスと管理" src="assets/do-not-localize/workflow-access.jpeg">
</a>
<div>
<a href="gs-campaign-creation.md"><strong>設定の手順</strong></a>
</div>
<p>
</td>
<td>
<a href="create-orchestrated-campaign.md">
<img alt="リード" src="assets/do-not-localize/workflow-create.jpeg">
</a>
<div><a href="create-orchestrated-campaign.md"><strong> オーケストレーションされたキャンペーンの作成 </strong>
</div>
<p>
</td>
<td>
<a href="activities/about-activities.md">
<img alt="低頻度" src="assets/do-not-localize/workflow-activities.jpeg">
</a>
<div>
<a href="activities/about-activities.md"><strong> アクティビティの操作 </strong></a>
</div>
<p></td>
</tr></table>
