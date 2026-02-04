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
source-git-commit: dbed4ffeb63ec3c58ff61845bbdb91fd2d51e69b
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 2%

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

## ロイヤルティ課題インベントリへのアクセス {#access-inventory}

<!-- SCREENSHOT: Journey Optimizer main menu showing "Loyalty challenges" under "Customer journeys" section -->

ロイヤルティの課題にアクセスするには、Journey Optimizerに移動し、「**[!UICONTROL カスタマージャーニー]** セクションで **[!UICONTROL ロイヤルティの課題]** を選択します。

<!-- SCREENSHOT: Loyalty Challenges landing page showing the two tabs: Challenges and Tasks -->

ロイヤルティの課題ページには、次の 2 つのタブが表示されます。

* **[!UICONTROL 課題]**：ロイヤルティのすべての課題を表示および管理する

* **[!UICONTROL タスク]**：複数の課題で再利用可能なすべてのタスクを表示および管理

## 課題インベントリ {#challenges-tab}

<!-- SCREENSHOT: Challenges tab showing the inventory table with columns: Challenge name, Status, Type, Start date, End date, Created by, Last modified, Tags -->

「課題」タブには、すべての課題が最終変更日順に表示され、最近変更された課題が最初に表示されます。 次の情報が表示されます。

* **[!UICONTROL チャレンジ名]**：チャレンジに割り当てた名前
* **[!UICONTROL ステータス]**：チャレンジの現在の状態（以下のステータスの説明を参照）
* **[!UICONTROL タイプ]**：チャレンジの種類（スタンダード、ストリーク、シーケンシャル）
* **[!UICONTROL 開始日]**：チャレンジがアクティブになる日時
* **[!UICONTROL 終了日]**：チャレンジの有効期限が切れるタイミング
* **[!UICONTROL 作成者]**：課題を作成したユーザー
* **[!UICONTROL 最終変更]**：最終変更日時
* **[!UICONTROL タグ]**：組織の課題に適用されるタグ

### チャレンジのステータス {#challenge-statuses}

<!-- VISUAL: Status badges showing different challenge statuses with color coding: Draft (gray), Scheduled (blue), Live (green), Completed (gray), Stopped (red), Archived (gray) -->

課題は、ライフサイクルの現在の状態を示す様々なステータスで表示されます。

* **ドラフト**：チャレンジが作成または編集されています
* **スケジュール済み**：チャレンジは公開され、開始日にアクティブになります
* **ライブ**：チャレンジは活発で、お客様も参加できます
* **完了**：課題の終了日を過ぎたか、目標が達成された
* **停止**：チャレンジは完了前に手動で停止されました
* **アーカイブ済み**：課題は、組織目的でアーカイブされています

ステータス遷移とチャレンジライフサイクルについて詳しくは、[ チャレンジライフサイクル ](manage-challenges.md#challenge-lifecycle) を参照してください。

### 課題の検索とフィルタリング {#search-challenges}

<!-- SCREENSHOT: Search bar and filter panel showing available filters (status, type, dates, tags) with an example of active filters applied -->

検索とフィルターを使用して、課題をすばやく見つけることができます。

**検索：**

* 検索バーを使用して、チャレンジ名または説明からキーワードを入力してチャレンジを検索します。 検索の結果は、入力中にリアルタイムで更新されます。

**フィルター：**

* 1 つ以上のフィルターを適用して、結果を絞り込みます。
   * **ステータス**：チャレンジのステータス（ドラフト、スケジュール済み、ライブ、完了、停止、アーカイブ済み）でフィルタリングします
   * **タイプ**：チャレンジタイプ（スタンダード、ストリーク、シーケンシャル）でフィルタリング
   * **日付**：開始日または終了日の範囲でフィルタリングします
   * **タグ**：チャレンジに適用されたタグでフィルタリングします

複数のフィルターを同時に組み合わせることができます。 例えば、「Summer2024」とタグ付けされたライブスタンダードのチャレンジをフィルタリングすると、アクティブな季節のキャンペーンをすばやく見つけることができます。

フィルターをクリアするには、「**[!UICONTROL すべてクリア]**」を選択するか、個々のフィルターを削除します。

### 課題に対する行動 {#inventory-actions}

<!-- SCREENSHOT: More actions menu (three dots) expanded showing options: Edit, Duplicate, Stop, Archive, Delete -->

「課題」タブから、課題に対するクイックアクションを実行できます。

* **チャレンジの詳細を表示**：チャレンジ名を選択して詳細ページを開きます
* **チャレンジの編集**:**[!UICONTROL その他のアクション]** メニュー（3 つのドット）を選択して、**[!UICONTROL 編集]** を選択します
* **チャレンジを複製**: **[!UICONTROL その他のアクション]** メニューを選択して、「**[!UICONTROL 複製]**」を選択します
* **ライブチャレンジを停止**:**[!UICONTROL その他のアクション]** メニューを選択して **[!UICONTROL 停止]** を選択します
* **課題のアーカイブ**:**[!UICONTROL その他のアクション]** メニューを選択し、**[!UICONTROL アーカイブ]** を選択します
* **ドラフトチャレンジの削除**:**[!UICONTROL その他のアクション]** メニューを選択して、**[!UICONTROL 削除]** を選択します（ドラフトでのみ使用できます）

編集制限、複製戦略、パフォーマンス監視、トラブルシューティングなど、作成後の課題の管理について詳しくは、[ 課題の管理 ](manage-challenges.md) を参照してください。

## タスクインベントリ {#tasks-tab}

<!-- SCREENSHOT: Tasks tab showing the inventory table with columns: Task name, Task type, Description, Created by, Last modified, Used in challenges -->

「タスク」タブには、複数の課題で使用できるすべての再利用可能なタスクが表示されます。 ここで作成したタスクは、チャレンジを作成または編集する際に選択できるようになります。

タスクインベントリには、次の情報が表示されます。

* **[!UICONTROL タスク名]**：タスクに割り当てた名前
* **[!UICONTROL タスクタイプ]**：アクションのタイプ（購入、支出額、訪問、エンゲージメント、カスタムイベント）
* **[!UICONTROL 説明]**：タスクに必要なものについての簡単な説明
* **[!UICONTROL 作成者]**: タスクを作成したユーザー
* **[!UICONTROL 最終変更]**：最終変更日時
* **[!UICONTROL 課題で使用済み]**：現在このタスクを使用している課題の数

### タスクに対するアクションの実行 {#tasks-actions}

「タスク」タブから、タスクに対するアクションを実行できます。

* **タスクの詳細を表示**：完全な設定を表示するタスク名を選択します
* **タスクの編集**:**[!UICONTROL その他のアクション]** メニュー（3 つのドット）を選択し、**[!UICONTROL 編集]** を選択します
* **タスクを複製**:「**[!UICONTROL その他のアクション]**」メニューを選択し、「**[!UICONTROL 複製]**」を選択します
* **タスクの削除**:**[!UICONTROL その他のアクション]** メニューを選択し、**[!UICONTROL 削除]** を選択します（アクティブなチャレンジで使用されていない場合のみ）。
* **使用状況を表示**：現在タスクを使用している課題を確認します

## 次の手順 {#next-steps}

これで、ロイヤルティ課題インベントリにアクセスしてナビゲートする方法がわかりました。

* [ 課題の作成 ](create-challenges.md) – 最初の課題を作成し、タスクを設定する方法を説明します
* [ タスクの作成 ](create-tasks.md) – 課題に対する再利用可能なタスクを定義する方法を説明します
* [ 課題の管理 ](manage-challenges.md) – 課題を編集、監視、最適化する方法を説明します。
