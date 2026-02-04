---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティの課題へのアクセス
description: Adobe Journey Optimizerでロイヤルティの課題にアクセス、検索、フィルタリングする方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
source-git-commit: e978d075efbbcb42e7500d921bd8cc3ed1eee890
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 4%

---


# ロイヤルティの課題へのアクセス {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [&#x200B; ロイヤルティの課題の概要 &#x200B;](get-started.md) – 概要、ワークフロー、前提条件
* **ロイヤルティの課題へのアクセス**◀︎**現在の状況** – 在庫とフィルタリング
* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 課題の作成と設定
* [&#x200B; タスクの作成 &#x200B;](create-tasks.md) – 課題タスクの定義
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

ロイヤルティの課題にアクセスするには、Journey Optimizerに移動し、「**[!UICONTROL ジャーニー管理]**」セクションで **[!UICONTROL 「ロイヤルティの課題（Beta）]** を選択します。

## 概要 {#overview}

ロイヤルティの課題インターフェイスは、すべての課題とタスクを一元的に表示、管理、整理する場所を提供します。 次の 2 つの主要なインベントリにアクセスできます。

* **課題インベントリ**：すべてのロイヤルティの課題を表示および管理し、そのステータスを監視して、クイックアクションを実行します
* **タスクインベントリ**：複数の課題で再利用可能なタスクを参照する

## 課題インベントリ {#challenges-tab}

「**[!UICONTROL 課題]**」タブには、すべての課題が最終変更日順に表示され、最近変更された課題が最初に表示されます。

![](assets/challenges-inventory.png)

表示されるキー情報：

* **[!UICONTROL チャレンジ]**：チャレンジ名
* **[!UICONTROL 状態]**：チャレンジの現在の状態（ドラフトまたは公開済み）。 [&#x200B; ステータス遷移の詳細情報 &#x200B;](manage-challenges.md#challenge-lifecycle)
* **[!UICONTROL タスク]**：チャレンジで設定されたタスクの数
* **[!UICONTROL ジャーニー]**：課題に関連付けられた自動生成ジャーニーへのリンク
* **[!UICONTROL ステータス]**：関連付けられたジャーニーの現在のステータス（ドラフト、ライブ、停止など）
* **[!UICONTROL 開始日/終了日（UTC）]**：チャレンジがアクティブになる日時と有効期限が切れる日時

「課題」タブから、課題に対するクイックアクションを実行できます。

* **チャレンジの詳細を表示**：チャレンジ名を選択して詳細ページを開いたり、チャレンジを編集したりします
* **チャレンジを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **ドラフトチャレンジの削除**:「![](assets/do-not-localize/Smock_More_18_N.svg)」アイコンを選択し、「**[!UICONTROL 削除]**」を選択します

[&#x200B; 作成後に課題を管理する方法を説明します &#x200B;](manage-challenges.md)。

## タスクインベントリ {#tasks-tab}

「タスク」タブには、複数の課題で使用できるすべての再利用可能なタスクが表示されます。 ここで作成したタスクは、チャレンジを作成または編集する際に選択できるようになります。

![](assets/tasks-inventory.png)

表示されるキー情報：

* **[!UICONTROL タスク名]**：タスクに割り当てた名前
* **[!UICONTROL 説明]**：タスクに必要なものについての簡単な説明
* **[!UICONTROL タスクアクティビティ]**：アクティビティのタイプ（購入、支出）
* **[!UICONTROL SKU]**：適格または除外された項目

「タスク」タブから、タスクに対してクイックアクションを実行できます。

* **タスクの詳細を表示**：完全な設定を表示したり、タスクを編集したりするには、タスク名を選択します
* **タスクを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **タスクを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) アイコンを選択して「**[!UICONTROL 削除]**」を選択します

[&#x200B; 作成後にタスクを管理する方法を説明します &#x200B;](manage-challenges.md)。

## 次の手順 {#next-steps}

これで、ロイヤルティ課題インベントリにアクセスしてナビゲートする方法がわかりました。

* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 最初の課題を作成し、タスクを設定する方法を説明します
* [&#x200B; タスクの作成 &#x200B;](create-tasks.md) – 課題に対する再利用可能なタスクを定義する方法を説明します
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 課題を編集、監視、最適化する方法を説明します。
