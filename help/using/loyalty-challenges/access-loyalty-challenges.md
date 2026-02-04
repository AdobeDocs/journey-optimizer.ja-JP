---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティの課題へのアクセスと管理
description: Adobe Journey Optimizerでロイヤルティの課題とタスクにアクセス、管理、整理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
source-git-commit: f41c1ed8a2d9e74b9d8fe97e0bf9e565d326aec6
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 3%

---


# ロイヤルティの課題へのアクセスと管理 {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ ロイヤルティの課題の概要 ](get-started.md) – 概要、ワークフロー、前提条件
* **ロイヤルティの課題へのアクセス** ◀︎ **現在の状況** – 在庫、課題、タスクの管理
* [ 課題の作成 ](create-challenges.md) – 課題の作成と設定
* [ タスクの作成 ](create-tasks.md) – 課題タスクの定義

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

## 常連の課題にアクセス

ロイヤルティの課題にアクセスするには、Journey Optimizerに移動し、「**[!UICONTROL ジャーニー管理]**」セクションで **[!UICONTROL 「ロイヤルティの課題（Beta）]** を選択します。

ロイヤルティの課題インターフェイスは、すべての課題とタスクを一元的に表示、管理、整理する場所を提供します。 次の 2 つの主要なインベントリにアクセスできます。

* **課題インベントリ**：すべてのロイヤルティの課題を表示および管理し、そのステータスを監視して、クイックアクションを実行します
* **タスクインベントリ**：複数の課題で再利用可能なタスクを参照する

## 課題インベントリ {#challenges-tab}

「**[!UICONTROL 課題]**」タブには、すべての課題が最終変更日順に表示され、最近変更された課題が最初に表示されます。

![](assets/challenges-inventory.png)

表示されるキー情報：

* **[!UICONTROL チャレンジ]**：チャレンジ名
* **[!UICONTROL 状態]**：チャレンジの現在の状態（ドラフトまたは公開済み）
* **[!UICONTROL タスク]**：チャレンジで設定されたタスクの数
* **[!UICONTROL ジャーニー]**：課題に関連付けられた自動生成ジャーニーへのリンク
* **[!UICONTROL ステータス]**：関連付けられたジャーニーの現在のステータス（ドラフト、ライブ、停止など）
* **[!UICONTROL 開始日/終了日（UTC）]**：チャレンジがアクティブになり、期限切れになる日時

「課題」タブから、課題に対するアクションを実行できます。

* **チャレンジを表示**：チャレンジ名を選択して詳細ページを開きます
* **チャレンジを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します。 コピーは、すべてのタスク、コンテンツおよびメッセージがそのまま作成されます。
* **チャレンジを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 削除]**」を選択します
* **チャレンジの編集**：チャレンジ名を選択して詳細ページを開き、編集します。

  公開済みのチャレンジを編集用に開く場合は、まずドラフトステータスに戻す必要があります。

   * 自動生成されたジャーニーに直接加えられたカスタマイズは失われます
   * チャレンジがドラフトステータスに戻ります
   * 変更を加えた後、課題を保存して再度公開する必要があります
   * 更新された課題を顧客に提供するには、関連するジャーニーを再公開する必要があります

  >[!IMPORTANT]
  >
  >公開済みのチャレンジのドラフトへの復帰は元に戻すことができません。 続行する前に、アクティブなジャーニーへの影響を考慮します。

## タスクインベントリ {#tasks-tab}

「**[!UICONTROL タスク]**」タブには、複数の課題で再利用可能なすべてのタスクが表示されます。 ここで作成したタスクは、チャレンジを作成または編集する際に選択できるようになります。

![](assets/tasks-inventory.png)

表示されるキー情報：

* **[!UICONTROL タスク名]**：タスクに割り当てた名前
* **[!UICONTROL 説明]**：タスクに必要なものについての簡単な説明
* **[!UICONTROL タスクアクティビティ]**：アクティビティのタイプ（購入、支出）
* **[!UICONTROL SKU]**：適格または除外された項目
* **[!UICONTROL 課題で使用済み]**：現在このタスクを使用している課題の数

「タスク」タブから、タスクに対するアクションを実行できます。

* **タスクの表示/編集**：完全な設定を表示してタスクを編集するには、タスク名を選択します
* **タスクを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **タスクを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) アイコンを選択して「**[!UICONTROL 削除]**」を選択します
