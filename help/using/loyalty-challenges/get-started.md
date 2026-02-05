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
source-git-commit: 7aeb36b88af415d59d9e7275ec3605db1a243b07
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 2%

---


# ロイヤルティに関する課題の概要 {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* **ロイヤルティの課題の概要** ◀︎ **ご利用いただけます**
* [課題およびタスクへのアクセスと管理](access-loyalty-challenges.md)
* [課題の作成](create-challenges.md)
* [タスクの作成](create-tasks.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **プライベートベータ版** です。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

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

1. **データ取り込みの設定** - Experience Platform ソースコネクタ（[&#x200B; キャピラリコネクタ &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#loyalty) など）を設定して、顧客のアクションと進行状況を追跡するロイヤルティイベントデータを取り込みます。 このデータにより、課題の追跡とタスクの完了が強化されます。

1. **チャレンジの作成** – 名前、タイプ（標準、ストリーク、順次）、日付範囲など、基本的なチャレンジプロパティを定義します。

1. **タスクを追加** - タスクのタイプ（購入、支出）、数量、製品フィルター、報酬など、顧客が完了する必要がある特定のアクションを定義します。

1. **コンテンツカードの設計** – お客様のデバイスに表示されるJourney Optimizer コンテンツカードを使用して、課題を視覚的に表現します。 コンテンツカードには、チャレンジ情報、進行状況および報酬が表示されます。

1. **メッセージの設定** （オプション） – ローンチ、処理中、完了などの主要なライフサイクルステージに対して、マルチチャネルメッセージ（アプリ内、メール、プッシュ）を設定します。

1. **ターゲットオーディエンスを選択** - Adobe Experience Platformからオーディエンスを選択して、どの顧客がチャレンジに参加できるかを定義します。

1. **課題の開始** – 課題を公開してから、ジャーニーを生成します。 Journey Optimizerは、課題に対応するジャーニーを自動的に作成します。 自動生成されたジャーニーを公開して、顧客が課題を利用できるようにします。

詳細な手順については、[&#x200B; 課題の作成 &#x200B;](create-challenges.md) を参照してください。

## 前提条件 {#prerequisites}

ロイヤルティの課題を使用する前に、次の点を確認します。

+++データ取り込み設定

ロイヤルティの課題は、Experience Platform ソースコネクタを通じて取り込まれたデータに依存して、顧客の進捗とタスクの完了を追跡します。

開始する前に、サポートされているソースコネクタを設定します。 現在、Capilary コネクタは使用可能です。 今後のリリースで追加のコネクタが予定されています。 [&#x200B; ロイヤルティソースコネクタについて説明します &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#loyalty)。

+++

+++必要な権限

ロイヤルティの課題を使用するには、Journey Optimizerでの適切な権限が必要です。 必要な権限は次のとおりです。

* 未定
* 未定
* 未定

機能にアクセスできない場合や追加の権限が必要な場合は、管理者にお問い合わせください。

+++

+++ターゲットオーディエンス

課題を作成する前に、必要なターゲットオーディエンスがAdobe Experience Platformに存在することを確認します。 チャレンジ設定時に、参加資格のある顧客を定義するオーディエンスを選択します。 [&#x200B; オーディエンスの操作方法を学ぶ &#x200B;](../audience/about-audiences.md)。

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
