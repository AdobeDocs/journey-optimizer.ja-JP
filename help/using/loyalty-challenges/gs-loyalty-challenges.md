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
source-git-commit: 419c7b3913ca4da50c69ed36ffc1a8c8520607b4
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 8%

---


# ロイヤルティに関する課題の概要 {#get-started-loyalty-challenges}

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権を取得するには、アドビ担当者にお問い合わせください。

ロイヤルティの課題を使用すると、顧客に対してパーソナライズされたエンゲージメントオファーを作成し、ロイヤルティプログラムを大規模に調整できます。 特定のタスクやマイルストーンを使用して課題を設計し、それらを完了したお客様に報酬を与え、Adobe Journey Optimizer チャネルを通じてエクスペリエンスを提供できます。

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* **ロイヤルティの課題の概要** ◀︎ **現在の状況** – 概要と次の手順
* [&#x200B; ロイヤルティの課題について &#x200B;](get-started.md) – 機能、ワークフロー、前提条件
* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 課題の作成と設定
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

## クイック概要 {#quick-overview}

ロイヤルティの課題を使用して次のことを行います。

* **標準（任意のタスク）、連続（繰り返しタスク）または順次（順序付きタスク）の 3 種類の課題の作成**
* **課題コンテンツの設計**：コンテンツカードを使用して、顧客デバイスに課題を表示します
* **タスク要件の設定**：報酬を含む購入、訪問、カスタムイベントなどのアクションを定義する
* **マルチチャネル通知の送信**：主要なステージでアプリ内、メールおよびプッシュを介してメッセージを配信します
* **パフォーマンスの追跡**：自動生成されたジャーニーとビルトインレポートを使用した監視

## 仕組み {#how-it-works-overview}

ロイヤルティの課題の作成は、次のワークフローに従います。

1. **データ取得の設定** – 顧客のアクションを追跡するソースコネクタを設定します
2. **課題の作成** - タイプ、オーディエンスおよび日付の定義
3. **タスクを追加** - アクションと報酬を設定します
4. **コンテンツのデザイン** - コンテンツカードとオプションのメッセージの作成
5. **公開** - Journey Optimizerがジャーニーを自動生成し、アクティブ化します
6. **監視** - パーティシペーションとパフォーマンスの追跡

>[!NOTE]
>
>自動生成されたジャーニーはジャーニーインベントリに表示され、必要に応じてカスタマイズできます。 ただし、ジャーニーに直接加えられた変更は、チャレンジ設定には同期されません。

## 前提条件 {#prerequisites-overview}

ロイヤルティの課題を使用する前に：

* Experience Platform ソースコネクタ（キャピラリーなど）を設定して、ロイヤルティイベントデータを取り込みます
* Journey Optimizerでの適切な権限があることを確認します。
* Experience Platformでのターゲットオーディエンスの作成

前提条件について詳しくは、[&#x200B; ロイヤルティの課題について &#x200B;](get-started.md#prerequisites) を参照してください。

## 重要な制限事項 {#limitations-overview}

* **元帳システムなし**：ロイヤルティの課題は、金額またはポイント残高を追跡しません。 Journey Optimizerは、外部のロイヤルティマネジメントシステムを呼び出してポイント配分を処理します。
* **オーディエンスの選択のみ**：既存のオーディエンスを選択できますが、ロイヤルティの課題 UI から新しいオーディエンスを作成することはできません。

## 次の手順 {#next-steps}

<table style="table-layout:fixed">
<tr style="border: 0;">
  <td>
    <a href="get-started.md">
    <img alt="について" src="../assets/do-not-localize/learn-more-button.svg">
    </a>
    <div>
    <a href="get-started.md"><strong> ロイヤルティの課題について </strong></a>
    </div>
    <p>
    <em> 機能、ワークフロー、機能について </em>
    <p>
  </td>
  <td>
    <a href="create-challenges.md">
      <img alt="作成" src="../assets/do-not-localize/start-button.svg">
    </a>
    <div>
    <a href="create-challenges.md"><strong> 課題の作成 </strong></a>
    </div>
    <p>
    <em> ロイヤルティに関する最初の課題を作成および設定 </em>
    <p>
  </td>
  <td>
    <a href="manage-challenges.md">
    <img alt="管理" src="../assets/do-not-localize/monitor-button.svg">
    </a>
    <div>
    <a href="manage-challenges.md"><strong> 課題の管理 </strong></a>
    </div>
    <p>
    <em> 課題を編集、監視、最適化 </em>
    <p>
  </td>
</tr>
</table>
