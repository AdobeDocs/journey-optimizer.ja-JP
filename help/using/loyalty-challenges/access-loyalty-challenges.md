---
solution: Journey Optimizer
product: journey optimizer
title: 課題およびタスクへのアクセスと管理
description: Adobe Journey Optimizerでロイヤルティの課題とタスクにアクセス、管理、整理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
source-git-commit: 5ccbddb37c0f45b6dd004cb4b70378b300228c0c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# 課題およびタスクへのアクセスと管理 {#access-loyalty-challenges}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ロイヤルティに関する課題の概要](get-started.md)
* **課題およびタスクへのアクセスと管理** ◀︎ **現在の状況**
* [課題の作成](create-challenges.md)
* [タスクの作成](create-tasks.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **プライベートベータ版** です。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

## 課題およびタスクへのアクセスと管理

ロイヤルティの課題にアクセスするには、Journey Optimizerに移動し、「**[!UICONTROL ジャーニー管理]**」セクションで **[!UICONTROL 「ロイヤルティの課題（Beta）]** を選択します。 ロイヤルティの課題インターフェイスは、すべての課題とタスクを一元的に表示、管理、整理する場所を提供します。

このインターフェイスでは、次の 2 つの主要なインベントリにアクセスできます。

* **課題**：すべてのロイヤルティの課題を表示および管理し、そのステータスを監視し、課題の表示、編集、複製、削除などのクイックアクションを実行する
* **タスク**：複数の課題で再利用可能な再利用可能なタスクを参照し、タスクの定義を個別に管理

## 課題インベントリ {#challenges-tab}

「**[!UICONTROL 課題]**」タブには、すべての課題が最終変更日順に表示され、最近変更された課題が最初に表示されます。

![](assets/challenges-inventory.png)

表示されるキー情報：

* **[!UICONTROL 状態]**：チャレンジの現在の状態（ドラフトまたは公開済み）
* **[!UICONTROL タスク]**：チャレンジで設定されたタスクの数
* **[!UICONTROL ジャーニー]**：課題に関連付けられた自動生成ジャーニーへのリンク
* **[!UICONTROL ステータス]**：課題を提供する自動生成ジャーニーの現在のステータス。
* **[!UICONTROL 開始日/終了日（UTC）]**：チャレンジがアクティブになり、期限切れになる日時

「課題」タブから、課題に対するアクションを実行できます。

* **チャレンジを表示**：チャレンジ名を選択して詳細ページを開きます
* **チャレンジを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します。 コピーは、すべてのタスク、コンテンツおよびメッセージがそのまま作成されます。
* **チャレンジを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 削除]**」を選択します。

  >[!IMPORTANT]
  >
  >チャレンジは、公開されている場合でも削除できます。 削除する前に影響を考慮します。

* **チャレンジの編集**：チャレンジ名を選択して詳細ページを開き、必要な変更を行います。

  公開済みのチャレンジを編集用に開く場合は、まずドラフト状態に戻す必要があります。 自動生成されたジャーニーに直接加えられたカスタマイズは失われます。 変更を加えた後、課題を保存して再度公開し、関連するジャーニーを公開します。 [&#x200B; チャレンジを始める方法を学ぶ &#x200B;](create-challenges.md#launch)

  >[!IMPORTANT]
  >
  >公開済みのチャレンジのドラフトへの復帰は元に戻すことができません。 続行する前に、アクティブなジャーニーへの影響を考慮します。

## タスクインベントリ {#tasks-tab}

「**[!UICONTROL タスク]**」タブには、複数の課題で再利用可能なすべてのタスクが表示されます。 ここで作成したタスクは、チャレンジを作成または編集する際に選択できるようになります。

![](assets/tasks-inventory.png)

表示されるキー情報：

* **[!UICONTROL 説明]**：タスクに必要なものについての簡単な説明
* **[!UICONTROL タスクアクティビティ]**：アクティビティのタイプ（購入、支出）
* **[!UICONTROL SKU]**：適格または除外された項目
* **[!UICONTROL 課題で使用済み]**：現在このタスクを使用している課題の数

「タスク」タブから、タスクに対するアクションを実行できます。

* **タスクの表示/編集**：タスク名を選択して設定をすべて表示し、タスクを編集します
* **タスクを複製**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 複製]**」を選択します
* **タスクを削除**:![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンを選択し、「**[!UICONTROL 削除]**」を選択します。

  >[!IMPORTANT]
  >
  >タスクが 1 つ以上の課題で使用されている場合でも、タスクを削除できます。 削除する前に、タスクを参照する課題への影響を考慮します。
