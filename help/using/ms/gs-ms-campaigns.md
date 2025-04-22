---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンの基本を学ぶ
description: 調整されたキャンペーンを開始する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 611dd06d-aa18-4fa3-a477-8a910cec21d8
source-git-commit: 408e2264056c52c1d73bcd412e7a73f25812c224
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 18%

---

# 調整されたキャンペーンの基本を学ぶ {#ms-camp}

>[!BEGINSHADEBOX]

**目次**

* 調整されたキャンペーンの基本を学ぶ
* 設定
   * [ オーケストレートキャンペーンの設定 ](gs-campaign-config.md)
   * [リレーショナルスキーマの作成](ms-schemas.md)
* 最初のオーケストレーション済みキャンペーンを作成
   * [主要な原則](gs-campaign-creation.md)
   * [調整されたキャンペーンの作成](create-ms-campaign.md)
   * [キャンペーン設定の指定](ms-campaign-settings.md)
   * [アクティビティの概要](activities/about-activities.md)
   * [アクティビティの調整](orchestrate-activities.md)
* [メッセージのパーソナライズ](ms-personalization.md)
* [クエリの作成](ms-query-modeler.md)
* [メッセージのテストと検証](ms-proofs.md)
* [キャンペーンのスケジュール設定と開始](start-monitor-campaigns.md)
* アクティビティのリスト : [And 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ チャネルアクション ](activities/channels.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ オーディエンスを保存 ](activities/save-audience.md) - [ オーディエンスを変更 ](activities/split.md) [ ](activities/test.md) [ ](activities/wait.md) -
* [レポート](reporting-campaigns.md)

>[!ENDSHADEBOX]

キャンペーンのオーケストレーションは、ブランド主導の堅牢なバッチキャンペーン機能を導入することでAdobe Journey Optimizerを強化し、高度なセグメント化戦略を使用してクロスチャネルキャンペーンの計画と調整を行えるようにします。

## オーケストレートキャンペーンとは

クロスチャネルマーケティングは、顧客に効果的にリーチすることを目指すあらゆるビジネスにとって不可欠です。Adobe Journey Optimizerは、マーケティングキャンペーンを簡単に管理するのに役立つ複雑なプロセスを設定できる包括的なグラフィカル環境を提供します。 調整されたキャンペーンを使用すると、あらゆるプロセスとタスクを調整し、セグメントの作成やメッセージの準備から配信に至るまでの、マーケティングキャンペーンのあらゆる側面でスピードと規模を改善できます。 さらに、キャンペーンオーケストレーション用の使いやすい単一のインターフェイスでチャネルを同期させることができます。

調整されたキャンペーンの最も大きな利点の 1 つは、あらゆるチャネルにわたってパーソナライズされたコンテンツを簡単に顧客に配信できる点です。 顧客がメールやモバイルでのメッセージの受信を好む場合でも、Adobe Journey Optimizerでは、あらゆるチャネルで一貫したコンテキストに沿ったエクスペリエンスを提供し、すべての顧客のジャーニーを独自のエクスペリエンスに変換できます。

オーケストレートキャンペーンは非常に汎用性が高く、オーディエンスの管理やメッセージの送信のターゲティング、データを操作するためのデータ管理（ETL）、データのインポートなど、様々なコンテキストで使用できます。

包括的なグラフィカル環境を使用すると、セグメント化、キャンペーン実行、ファイル処理などのプロセスを設計できます。 また、調整されたキャンペーンには、タスクを割り当てたり、実行されたタスクを承認したりすることで、ユーザーを参加させることもできます。これにより、チームの作業を容易に管理し、すべてが正しく実行されるようになります。


## ジャーニーオーケストレーションとキャンペーンオーケストレーション

Campaign オーケストレーションは、ブランドコミュニケーションを大規模に設計、送信、追跡するための主要なモジュールです。 プロファイルエンティティとプロファイル以外のエンティティを組み合わせることで、既存のデータセグメントを活用して効果的なパーソナライゼーションを行い、ターゲットオーディエンスに対するマーケティングメッセージの自動配信を可能にします。 キャンペーン主導のアウトリーチに最適な Campaign オーケストレーションは、多くの場合、事前にスケジュールされた、一貫性のある効率的なメッセージ配信を確保して、顧客エンゲージメントを促進し、主要なマーケティング目標をサポートします。

Campaign Orchestration は、Adobe Journey Optimizerにマルチエンティティを有効化することでオーディエンスのセグメント化を再定義し、特定のステータス、イベント、契約、予約などに基づいてターゲットメッセージングを容易にします。 プロファイル以外のエンティティにコミュニケーションを送信したり、任意のエンティティに対してクエリを作成したりできるので、全体像を把握し、幅広いインサイトを取得してオーディエンスを構築できます。

データに基づく意思決定を可能にする Campaign オーケストレーションでは、動的にエンリッチメントされたデータセットに対して複数のソースを活用します。


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
<a href="create-ms-campaign.md">
<img alt="リード" src="assets/do-not-localize/workflow-create.jpeg">
</a>
<div><a href="create-ms-campaign.md"><strong> オーケストレーションされたキャンペーンの作成 </strong>
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
