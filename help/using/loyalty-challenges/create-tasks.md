---
solution: Journey Optimizer
product: journey optimizer
title: ロイヤルティの課題に対するタスクの作成
description: Adobe Journey Optimizerでロイヤルティの課題に対応するタスクを作成および設定する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Private Beta" type="Informative"
mini-toc-levels: 1
source-git-commit: 342df0950622de1c4c246bf624d05843671e199f
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---


# タスクの作成 {#create-tasks}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ロイヤルティに関する課題の概要](get-started.md)
* [課題およびタスクへのアクセスと管理](access-loyalty-challenges.md)
* [課題の作成](create-challenges.md)
* **タスクの作成** ◀︎ **You are here**

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **プライベートベータ版** です。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

タスクは、ロイヤルティの課題で報酬を獲得するために顧客が完了する必要がある特定のアクションやマイルストーンを定義します。 タスクのタイプ、数量および製品要件を設定して、魅力的でパーソナライズされたロイヤルティエクスペリエンスを作成できます。

各タスクは、チャレンジの完了に貢献する測定可能なアクションを表します。 タスクは、個別に作成して 1 つ以上の課題に追加したり、課題内で直接作成したりできる、再利用可能なコンポーネントです。

## タスクの作成 {#create-task}

タスクは、2 つのエントリポイントから作成できます。 どこから開始しても、設定プロセスは同じです。

>[!BEGINTABS]

>[!TAB  タスクインベントリから ]

「**[!UICONTROL タスク]**」タブを選択し、「**[!UICONTROL タスクを作成]**」を選択します。 インベントリから作成されたタスクは保存され、複数の課題で再利用できます。

![](assets/task-create-inventory.png)

>[!TAB  チャレンジの中から ]

既存の課題を開くか、新しい課題を作成します。 **[!UICONTROL タスクを追加]** を選択し、「**[!UICONTROL 新規]**」ボタンをクリックします。 この方法で作成されたタスクは、自動的に課題に追加され、他の課題で再利用するためにタスクインベントリにも保存されます。

![](assets/task-create-challenge.png)

>[!ENDTABS]

## 顧客アクティビティを選択 {#choose-activity}

このタスクを完了するために顧客が実行する必要があるアクティビティのタイプを選択します。

* **[!UICONTROL 購入]**：このタスクを完了するには、顧客が 1 つ以上のアイテムを購入する必要があります
* **[!UICONTROL 費用]**：顧客はこのタスクを完了するために指定された金額を費やす必要があります

アクティビティを選択するには、「**+**」アイコンをクリックし、結果目標に最も適した顧客アクティビティを選択します。 各アクティビティタイプには、タスク要件をさらに定義し形成するための、特定の設定可能な属性があります。
![](assets/task-create-activity.png)

## タスク属性の定義 {#define-attributes}

選択したアクティビティタイプに基づいてタスク属性を設定します。 各アクティビティタイプで使用可能な属性を確認するには、以下のタブを参照してください。

>[!BEGINTABS]

>[!TAB  購入アクティビティ ]

**購入** アクティビティで使用可能な属性：

* **[!UICONTROL 数量]**：このタスクを完了するために購入する必要がある品目の数を入力します。
* **[!UICONTROL 適格な項目と除外]**：タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。[ 実施要件を満たす項目と除外について詳しくはこちらを参照 ](#eligible-items-exclusions)
* **[!UICONTROL 最小費用金額]**：最小購買金額要件を設定します。
* **[!UICONTROL トランザクションの最大数]**：タスクの完了に使用できるトランザクション数を制限します。

![](assets/task-create-purchase.png)

>[!TAB  支出アクティビティ ]

**費用** アクティビティで使用可能な属性：

* **[!UICONTROL 金額]**：タスクの完了に必要な合計支出金額を入力します。
* **[!UICONTROL 適格な項目と除外]**：タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。[ 実施要件を満たす項目と除外について詳しくはこちらを参照 ](#eligible-items-exclusions)
* **[!UICONTROL トランザクションの最大数]**：費用要件を満たすことができるトランザクションの数を指定します。 この属性は、「パラメーター」アイコンからアクティブ化できます。

![](assets/task-create-spend.png)

>[!ENDTABS]

## 実施要件を満たす項目と除外の定義 {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

**購入** アクティビティと **費用** アクティビティの両方について、**[!UICONTROL 適格な項目と除外]** 属性を使用して、適格と除外される項目とグループを定義できます。 これにより、特定の製品、カテゴリまたは場所をターゲットにして、課題の目標に合わせることができます。

例えば、費用タスクを特定の製品カテゴリに制限したり、ギフトカードやプロモーション項目をタスクの完了へのカウントから除外したりできます。

![](assets/tasks-create-eligible.png)

* 実施要件を満たす項目を定義するには、「**[!UICONTROL 実施要件を満たすタスクの購入は次の項目に制限されます]**」フィールドで、特定の項目 ID、カテゴリ、宛先 ID をコンマで区切って入力します。 このフィールドを空のままにすると、すべての購入がデフォルトで適格となります。 `*` を入力して、明示的にすべての購入を対象にすることもできます。

  例：`SKU001, SKU002, CategoryA`

* タスクから項目を除外するには、特定の項目 ID、カテゴリまたは宛先 ID を「**[!UICONTROL このタスクから以下を除外]**」フィールドに入力します。

  例：`CLEARANCE01, GIFTCARD, SALE_CATEGORY`

## タスクのプロパティの定義 {#define-task-properties}

タスク **[!UICONTROL プロパティ]** ペインで、タスクの基本情報を設定します。

* **[!UICONTROL タスク名]**：タスクのわかりやすい名前を入力します。
* **[!UICONTROL タスクの説明]**：説明は、設定されたアクティビティと属性に基づいて自動的に生成されます。 カスタムの説明を入力するには、「自動生成」オプションをオフに切り替え、テキストフィールドに説明を入力します。

![](assets/tasks-create-properties.png)

すべての属性とプロパティを設定したら、「**[!UICONTROL 作成]**」を選択してタスクを保存します。 タスクはタスクインベントリに保存され、チャレンジ内から作成された場合は、そのチャレンジに自動的に追加されます。
