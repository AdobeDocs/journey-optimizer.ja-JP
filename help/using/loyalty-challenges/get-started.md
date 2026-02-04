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
source-git-commit: e683461c6adbf45cacb30692e23927175685f9fb
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 4%

---


# ロイヤルティに関する課題の概要 {#get-started-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* **ロイヤルティの課題の概要** ◀︎ **概要** ワークフロー、前提条件
* [ ロイヤルティの課題へのアクセスと管理 ](access-loyalty-challenges.md) – 在庫、課題、タスクの管理
* [ 課題の作成 ](create-challenges.md) – 課題の作成と設定
* [ タスクの作成 ](create-tasks.md) – 課題タスクの定義

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

## 概要 {#overview}

ロイヤルティの課題は、タスクとマイルストーンの定義から、チャネル全体でのコンテンツの配信とパフォーマンスの追跡まで、ロイヤルティプログラムを大規模に作成するための完全なソリューションを提供します。

![](assets/challenges-gs.png)

次の 3 種類のチャレンジエクスペリエンスを作成できます。

* **標準的な課題**：お客様は、任意の順序で任意の数のタスクを完了できます\
  *例：5 つのタスクのうち 3 つを完了する*

* **一連の課題**：お客様が同じタスクを複数回連続して完了する\
  *例：7 日連続で購入する*

* **順次的な課題**：顧客が定義された順序でタスクを完了する\
  *例：購入→レビュー→共有（この順序で完了する必要があります）*

ロイヤルティの課題を抱えると、外部のロイヤルティ管理システムとの統合を維持しながら、報酬の設定、主要なライフサイクル段階でのマルチチャネル通知の送信、自動生成されたジャーニーの使用などをおこなうことができます。

## 仕組み {#how-it-works}

ロイヤルティの課題の作成と開始は、次のワークフローに従います。

1. **データ取り込みの設定** - Experience Platform ソースコネクタ（[ キャピラリコネクタ ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#loyalty) など）を設定して、顧客のアクションと進行状況を追跡するロイヤルティイベントデータを取り込みます。 このデータにより、課題の追跡とタスクの完了が強化されます。

1. **チャレンジの作成** – 名前、タイプ（標準、ストリーク、順次）、日付範囲など、基本的なチャレンジプロパティを定義します。

1. **タスクを追加** - タスクのタイプ（購入、支出）、数量、製品フィルター、報酬など、顧客が完了する必要がある特定のアクションを定義します。

1. **コンテンツカードの設計** – お客様のデバイスに表示されるJourney Optimizer コンテンツカードを使用して、課題を視覚的に表現します。 コンテンツカードには、チャレンジ情報、進行状況および報酬が表示されます。

1. **メッセージの設定** （オプション） – ローンチ、処理中、完了などの主要なライフサイクルステージに対して、マルチチャネルメッセージ（アプリ内、メール、プッシュ）を設定します。

1. **ターゲットオーディエンスを選択** - Adobe Experience Platformからオーディエンスを選択して、どの顧客がチャレンジに参加できるかを定義します。

1. **ジャーニーの公開** - Journey Optimizerは、課題に対応するジャーニーを自動的に生成します。 ジャーニーインベントリに移動し、自動生成されたジャーニーを公開して、お客様が課題を利用できるようにします。

詳細な手順については、[ 課題の作成 ](create-challenges.md) を参照してください。

## 前提条件 {#prerequisites}

ロイヤルティの課題を使用する前に、次の点を確認します。

+++データ取り込み設定

ロイヤルティの課題は、Experience Platform ソースコネクタを通じて取り込まれたデータに依存して、顧客の進捗とタスクの完了を追跡します。

1. **サポートされているソースコネクタの設定**：現在、キャピラリコネクタを使用できます。 今後のリリースで追加のコネクタが予定されています。 [ ロイヤルティソースコネクタについて説明します ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#loyalty)。

1. **データ取り込みの検証**：ロイヤルティイベントと顧客データがExperience Platformに送られ、Journey Optimizerで利用できることを確認します。 データスキーマに、顧客のアクションと進捗を追跡するために必要なフィールドが含まれていることを確認します。

手順について詳しくは、[Experience Platform ソースの概要を参照してください ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)

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

ロイヤルティの課題に参加する資格のある顧客を指定するターゲットオーディエンスを定義します。 チャレンジ作成インターフェイスから既存のオーディエンスを選択することも、新しいオーディエンスを直接作成することもできます。 [ オーディエンスの操作方法を学ぶ ](../audience/about-audiences.md)。

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
    <em> 課題に対して完了すべきアクションの定義 </em>
    </p>
  </td>
</tr>
</table>
