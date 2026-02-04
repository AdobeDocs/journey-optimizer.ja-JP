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
source-git-commit: fd87aeabfae1f07d8f7bea7057f0c6dd0559d024
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 3%

---


# ロイヤルティの課題へのアクセス {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ ロイヤルティの課題の概要 ](get-started.md) – 概要、ワークフロー、前提条件
* **ロイヤルティの課題へのアクセス**◀︎**現在の状況** – 在庫とフィルタリング
* [ 課題の作成 ](create-challenges.md) – 課題の作成と設定
* [ タスクの作成 ](create-tasks.md) – 課題タスクの定義
* [ 課題の管理 ](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

ロイヤルティの課題にアクセスするには、Journey Optimizerに移動し、「**[!UICONTROL ジャーニー管理]**」セクションで **[!UICONTROL 「ロイヤルティの課題（Beta）]** を選択します。

## 課題インベントリ {#challenges-tab}

「**[!UICONTROL 課題]**」タブには、すべての課題が最終変更日順に表示され、最近変更された課題が最初に表示されます。

![](assets/challenges-inventory.png)

次の情報が表示されます。

* **[!UICONTROL チャレンジ]**：チャレンジに割り当てた名前
* **[!UICONTROL 状態]**：チャレンジの現在の状態。 ステータス遷移とチャレンジライフサイクルについて詳しくは、[ チャレンジライフサイクル ](manage-challenges.md#challenge-lifecycle) を参照してください。
* **[!UICONTROL 説明]**：課題の目的の簡単な説明
* **[!UICONTROL タスク]**：チャレンジで設定されたタスクの数
* **[!UICONTROL ジャーニー]**：課題に関連付けられた自動生成ジャーニーへのリンク
* **[!UICONTROL ステータス]**：関連付けられたジャーニーの現在のステータス（ドラフト、ライブ、停止など）
* **[!UICONTROL 開始日（UTC）]**：チャレンジがアクティブになるタイミング
* **[!UICONTROL 終了日（UTC）]**：チャレンジの有効期限がいつ切れるか
* **[!UICONTROL 最終変更]**：最終変更日時
* **[!UICONTROL 作成日]**：チャレンジが作成された日付
* **[!UICONTROL 作成者]**：課題を作成したユーザー

「課題」タブから、課題に対するクイックアクションを実行できます。

* **チャレンジの詳細を表示**：チャレンジ名を選択して詳細ページを開きます
* **チャレンジを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **ドラフトチャレンジの削除**:「![](assets/do-not-localize/Smock_More_18_N.svg)」アイコンを選択し、「**[!UICONTROL 削除]**」を選択します

作成後の課題の管理について詳しくは、[ 課題とタスクの管理 ](manage-challenges.md) を参照してください。

## タスクインベントリ {#tasks-tab}

「タスク」タブには、複数の課題で使用できるすべての再利用可能なタスクが表示されます。 ここで作成したタスクは、チャレンジを作成または編集する際に選択できるようになります。

![](assets/tasks-inventory.png)

タスクインベントリには、次の情報が表示されます。

* **[!UICONTROL タスク名]**：タスクに割り当てた名前
* **[!UICONTROL 説明]**：タスクに必要なものについての簡単な説明
* **[!UICONTROL タスクアクティビティ]**：アクティビティのタイプ（購入、支出）
* **[!UICONTROL SKU]**：適格または除外された項目
* **[!UICONTROL 最終変更]**：最終変更日時
* **[!UICONTROL 最終変更者]**: タスクを最後に変更したユーザー
* **[!UICONTROL 作成日]**: タスクが作成された日付
* **[!UICONTROL 作成者]**: タスクを作成したユーザー

「タスク」タブから、タスクに対してクイックアクションを実行できます。

* **タスクの詳細を表示**：完全な設定を表示するタスク名を選択します
* **タスクを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **タスクを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) アイコンを選択して「**[!UICONTROL 削除]**」を選択します

作成後のタスクの管理について詳しくは、[ 課題とタスクの管理 ](manage-challenges.md) を参照してください。

## 次の手順 {#next-steps}

これで、ロイヤルティ課題インベントリにアクセスしてナビゲートする方法がわかりました。

* [ 課題の作成 ](create-challenges.md) – 最初の課題を作成し、タスクを設定する方法を説明します
* [ タスクの作成 ](create-tasks.md) – 課題に対する再利用可能なタスクを定義する方法を説明します
* [ 課題の管理 ](manage-challenges.md) – 課題を編集、監視、最適化する方法を説明します。
