---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティに関する課題の概要
description: Adobe Journey Optimizerでロイヤルティの課題を作成および管理して、魅力的なロイヤルティプログラムを作成する方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
source-git-commit: e978d075efbbcb42e7500d921bd8cc3ed1eee890
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 4%

---


# ロイヤルティに関する課題の概要 {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* **ロイヤルティの課題の概要** ◀︎ **概要** ワークフロー、前提条件
* [&#x200B; ロイヤルティの課題へのアクセス &#x200B;](access-loyalty-challenges.md) – 在庫とフィルタリング
* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 課題の作成と設定
* [&#x200B; タスクの作成 &#x200B;](create-tasks.md) – 課題タスクの定義
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

## 概要 {#overview}

ロイヤルティの課題は、タスクとマイルストーンの定義から、チャネル全体でのコンテンツの配信とパフォーマンスの追跡まで、ロイヤルティプログラムを大規模に作成するための完全なソリューションを提供します。

次の 3 種類のチャレンジエクスペリエンスを作成できます。

* **標準的な課題**：お客様は、任意の順序で任意の数のタスクを完了できます
* **一連の課題**：お客様が同じタスクを複数回連続して完了する
* **順次的な課題**：顧客が定義された順序でタスクを完了する

ロイヤルティの課題を使用すると、外部のロイヤルティ管理システムとの統合を維持しながら、報酬を設定し、主要なライフサイクル段階でマルチチャネル通知を送信し、自動生成されたジャーニーを通じてパフォーマンスを監視できます。

<!-- SCREENSHOT: High-level diagram showing Loyalty Challenges architecture with: Data ingestion from source connectors -> Challenge creation in JO -> Content cards & messaging -> Customer device -> Journey tracking -->

## 仕組み {#how-it-works}

<!-- SCHEMA: Visual workflow diagram showing the 8 steps in the loyalty challenge creation process with icons for each step -->

ロイヤルティの課題の作成と開始は、次のワークフローに従います。

1. **データ取り込みの設定** - Experience Platform ソースコネクタ（キャピラリーコネクタなど）を設定して、顧客のアクションと進行状況を追跡するロイヤルティイベントデータを取り込みます。 このデータにより、課題の追跡とタスクの完了が強化されます。

1. **チャレンジの作成** – 名前、タイプ（標準、ストリーク、順次）、オーディエンス、日付範囲など、基本的なチャレンジのプロパティを定義します。 手順について詳しくは、[&#x200B; 課題の作成 &#x200B;](create-challenges.md) を参照してください。

1. **タスクを追加** - タスクのタイプ（購入、支出、訪問、エンゲージメント、カスタムイベント）、数量、製品フィルター、報酬など、顧客が完了する必要がある特定のアクションを定義します。 手順について詳しくは、[&#x200B; タスクの作成 &#x200B;](create-tasks.md) を参照してください。

1. **コンテンツカードの設計** – お客様のデバイスに表示されるJourney Optimizer[&#x200B; コンテンツカード &#x200B;](../content-card/create-content-card.md) を使用して、課題を視覚的に表現します。 コンテンツカードには、チャレンジ情報、進行状況および報酬が表示されます。

1. **メッセージの設定** （オプション） – ローンチ、処理中、完了などの主要なライフサイクルステージに対して、マルチチャネルメッセージ [&#128279;](../in-app/get-started-in-app.md) アプリ内 [、メール &#x200B;](../email/get-started-email.md)、[&#x200B; プッシュ &#x200B;](../push/get-started-push.md)）を設定します。

1. **レビューして公開** - [&#x200B; テストプロファイル &#x200B;](../content-management/test-profiles.md) を使用して課題をテストし、公開して、ターゲットオーディエンスで利用できるようにします。

1. **ジャーニーのアクティブ化** – 課題を公開すると、Journey Optimizerは、コンテンツカードの配信とメッセージングを調整する [&#x200B; ジャーニー &#x200B;](../building-journeys/journey-gs.md) をドラフトステータスで自動的に作成します。 ジャーニーインベントリに移動し、自動生成されたジャーニー（「チャレンジ：[ チャレンジ名 ]」という名前）を見つけて [&#x200B; アクティブ化 &#x200B;](../building-journeys/publish-journey.md) し、お客様がチャレンジを使用できるようにします。

1. **パフォーマンスの監視** – 組み込みレポートとジャーニーキャンバスを通じて、パーティシペーション、完了率、報酬分布およびメッセージエンゲージメントを追跡します。 監視について詳しくは、[&#x200B; 課題の管理 &#x200B;](manage-challenges.md) を参照してください。

## 前提条件 {#prerequisites}

ロイヤルティの課題を使用する前に、次の点を確認します。

+++データ取り込み設定

ロイヤルティの課題は、Experience Platform ソースコネクタを通じて取り込まれたデータに依存して、顧客の進捗とタスクの完了を追跡します。

1. **サポートされているソースコネクタの設定**：現在、キャピラリコネクタは一般入手可能です。 今後のリリースで追加のコネクタが予定されています。

1. **データ取り込みの検証**：ロイヤルティイベントと顧客データがExperience Platformに送られ、Journey Optimizerで利用できることを確認します。 データスキーマに、顧客のアクションと進捗を追跡するために必要なフィールドが含まれていることを確認します。

手順について詳しくは、以下を参照してください。

* [Experience Platform ソースのドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/home)
* [Journey Optimizerでのソースコネクタの設定](../start/get-started-sources.md)

+++

+++必要な権限

ロイヤルティの課題を使用するには、Journey Optimizerでの適切な権限が必要です。 必要な権限は次のとおりです。

* **[!UICONTROL ロイヤルティの課題（Beta）]** 機能へのアクセス
* ジャーニーを作成および管理する権限
* コンテンツカードを作成および管理する権限
* オーディエンスを作成および管理する権限

機能にアクセスできない場合や追加の権限が必要な場合は、管理者にお問い合わせください。

+++

+++ターゲットオーディエンス

ロイヤルティの課題に参加する資格のある顧客を指定するターゲットオーディエンスを定義します。 チャレンジ作成インターフェイスから既存のオーディエンスを選択することも、新しいオーディエンスを直接作成することもできます。 [&#x200B; オーディエンスの操作方法を学ぶ &#x200B;](../audience/about-audiences.md)。

+++

## 次の手順 {#next-steps}

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="access-loyalty-challenges.md">
    <!--<img alt="Access" src="../assets/do-not-localize/learn-more-button.svg">-->
    </a>
    <div>
    <a href="access-loyalty-challenges.md"><strong> アクセスに関するロイヤルティの課題 </strong></a>
    </div>
    <p>
    <em> 在庫へのアクセスと課題のフィルタリング方法を学ぶ </em>
    </p>
  </td>
  <td>
    <a href="create-challenges.md">
      <!--<img alt="Create" src="../assets/do-not-localize/start-button.svg">-->
    </a>
    <div>
    <a href="create-challenges.md"><strong> 課題の作成 </strong></a>
    </div>
    <p>
    <em> ロイヤルティに関する最初の課題を作成および設定 </em>
    </p>
  </td>
  <td>
    <a href="create-tasks.md">
    <!--<img alt="Tasks" src="../assets/do-not-localize/start-button.svg">-->
    </a>
    <div>
    <a href="create-tasks.md"><strong> タスクの作成 </strong></a>
    </div>
    <p>
    <em> 課題に対する行動と報酬の定義 </em>
    </p>
  </td>
  <td>
    <a href="manage-challenges.md">
    <!--<img alt="Manage" src="../assets/do-not-localize/monitor-button.svg">-->
    </a>
    <div>
    <a href="manage-challenges.md"><strong> 課題の管理 </strong></a>
    </div>
    <p>
    <em> 課題を編集、監視、最適化 </em>
    </p>
  </td>
</tr>
</table>
