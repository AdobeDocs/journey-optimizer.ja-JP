---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティに関する課題の概要
description: Adobe Journey Optimizerでロイヤルティの課題を作成および管理して、魅力的なロイヤルティプログラムを構築する方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
exl-id: 1c84d9d0-cef7-4764-9f72-5428597a7203
source-git-commit: c5d7cbde6e0a9b4b835abac19d33b973f9f364e4
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---

# ロイヤルティに関する課題の概要 {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* **ロイヤルティの課題の概要** ◀︎ **ご利用いただけます**
* [課題およびタスクへのアクセスと管理](access-loyalty-challenges.md)
* [課題の作成](create-challenges.md)
* [タスクの作成](create-tasks.md)
* [ ロイヤルティの課題 API リファレンス ](https://developer.adobe.com/journey-optimizer-apis/references/loyalty-challenges/){target="_blank"}

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **プライベートベータ版** です。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

## 概要 {#overview}

ロイヤルティの課題を使用すると、顧客の行動を促進しブランド関係を深める、魅力的でゲーミフィケーションに富んだロイヤルティプログラムを作成できます。 購入やレビューの作成から、ソーシャルメディアでのエンゲージメントや友人への紹介まで、特定のアクションに対して顧客に報酬を与える課題を作成します。

ロイヤルティの課題に直面すると、次のことが可能です。

* **柔軟な課題タイプの設計**：ビジネス目標に合わせて、標準、連続、または順次の課題を作成します
* **戦略的な報酬の設定**：エンゲージメントを維持するために、タスクのマイルストーンまたは完了時にポイントを提供する
* **エクスペリエンスのパーソナライズ**：コンテンツカードとマルチチャネルメッセージを使用して、没入感のあるブランドエクスペリエンスを作成します
* **シームレスな統合**：既存のロイヤルティプロバイダーとつながり、Experience Platform データを活用します
* **自動的に追跡**：カスタム開発を行わずに、自動生成されたジャーニーを通じて顧客の進行状況を監視します

![](assets/challenges-gs.png)

次の 3 種類のチャレンジエクスペリエンスを作成できます。

* **標準的な課題**：お客様は、任意の順序で任意の数のタスクを完了できます。 このタイプは、柔軟性と複数のパスを補完する場合に使用します。\
  *例：「夏のウェルネスチャレンジ」 - 5 つのタスクのうち 3 つを完了します：健康製品の購入、ソーシャルメディアでの共有、友人への紹介、レビューの書き込み、仮想イベントへの参加*

* **一連の課題**：お客様が同じタスクを複数回連続して完了する。 このタイプを使用すると、時間の経過と共に一貫性のある反復的な動作が促されます。\
  *例：「コーヒーラバーズウィーク」 - 7 日間連続でコーヒー製品を購入すると、無料の飲み物の報酬がロック解除され* す。

* **順次的な課題**：顧客は、定義された順序でタスクを完了します。 このタイプを使用すると、特定のジャーニーやオンボーディングプロセスを通じて顧客をガイドできます。\
  *例：「新規会員ジャーニー」 – メールに新規登録→初めての購入→商品レビューを書く→友達を紹介する（この正確な順序で完了）*

## 仕組み {#how-it-works}

ロイヤルティの課題の作成と開始は、次のワークフローに従います。

1. **チャレンジの作成** – 名前、タイプ（標準、ストリーク、順次）、日付範囲など、基本的なチャレンジプロパティを定義します。

1. **タスクを追加** - タスクのタイプ（購入、支出）、数量、製品フィルター、報酬など、顧客が完了する必要がある特定のアクションを定義します。

1. **コンテンツカードの設計** – お客様のデバイスに表示されるJourney Optimizer コンテンツカードを使用して、課題を視覚的に表現します。 コンテンツカードには、チャレンジ情報、進行状況および報酬が表示されます。

1. **メッセージの設定** （オプション） – ローンチ、処理中、完了などの主要なライフサイクルステージに対して、マルチチャネルメッセージ（アプリ内、メール、プッシュ）を設定します。

1. **ターゲットオーディエンスを選択** - Adobe Experience Platformからオーディエンスを選択して、どの顧客がチャレンジに参加できるかを定義します。

1. **課題の開始** – 課題を公開してから、ジャーニーを生成します。 Journey Optimizerは、課題に対応するジャーニーを自動的に作成します。 自動生成されたジャーニーを公開して、顧客が課題を利用できるようにします。

詳細な手順については、[ 課題の作成 ](create-challenges.md) を参照してください。

## 前提条件 {#prerequisites}

ロイヤルティの課題を使用する前に、次の点を確認します。

+++必要な権限

ロイヤルティの課題を使用するには、Journey OptimizerとAdobe Experience Platformで適切な権限が必要です。

**Journey Optimizer:**

* `journeys.read`
* `journeys.write`
* `journeys.delete`
* `journeys.publish`
* `journeys_events.read`
* `journeys_events.write`
* `journeys_events.delete`
* `journeys_report.read`
* `messages.read`
* `messages_report.read`

**Adobe Experience Platform:**

* `segments.read`
* `profiles.read`
* `identity_namespace.read`

機能にアクセスできない場合や追加の権限が必要な場合は、管理者にお問い合わせください。

+++

+++ターゲットオーディエンス

課題を作成する前に、必要なターゲットオーディエンスがAdobe Experience Platformに存在することを確認します。 チャレンジ設定時に、参加資格のある顧客を定義するオーディエンスを選択します。 [ オーディエンスの操作方法を学ぶ ](../audience/about-audiences.md)。

+++

## さらに深く掘り下げましょう {#lets-dive-deeper}

ロイヤルティの課題とその仕組みを理解したら、詳細に進みます。 以下のトピックを探索して、インターフェイスにアクセスし、最初の課題を作成し、顧客が完了するタスクを定義します。

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="access-loyalty-challenges.md">
      <img alt="アクセス" src="assets/do-not-localize/icon-access.png" width="200"/>
    </a>
    <div>
    <a href="access-loyalty-challenges.md"><strong> 課題およびタスクへのアクセスと管理 </strong></a>
    </div>
    <p>
    <em> インベントリにアクセスし、課題とタスクを管理する方法を説明します </em>
    </p>
  </td>
  <td>
    <a href="create-challenges.md">
      <img alt="作成" src="assets/do-not-localize/icon-challenge.png" width="200"/>
    </a>
    <div>
    <a href="create-challenges.md"><strong> 課題の作成 </strong></a>
    </div>
    <p>
    <em> 最初のロイヤルティの課題を作成および設定する方法を説明します </em>
    </p>
  </td>
  <td>
    <a href="create-tasks.md">
      <img alt="タスク" src="assets/do-not-localize/icon-task.png" width="200"/>
    </a>
    <div>
    <a href="create-tasks.md"><strong> タスクの作成 </strong></a>
    </div>
    <p>
    <em> 課題に関してお客様が完了するタスクを定義する方法を説明します </em>
    </p>
  </td>
</tr>
</table>

## API リファレンス {#api-reference}

ロイヤルティの課題をプログラムで管理するには、[ ロイヤルティの課題 API](https://developer.adobe.com/journey-optimizer-apis/references/loyalty-challenges/){target="_blank"} を使用します。 API を使用すると、REST エンドポイントを介して課題とタスクを作成、更新、管理できます。
