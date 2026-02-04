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
source-git-commit: f41c1ed8a2d9e74b9d8fe97e0bf9e565d326aec6
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 2%

---


# タスクの作成 {#create-tasks}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [ ロイヤルティの課題の概要 ](get-started.md) – 概要、ワークフロー、前提条件
* [ ロイヤルティの課題へのアクセスと管理 ](access-loyalty-challenges.md) – 在庫、課題、タスクの管理
* [ 課題の作成 ](create-challenges.md) – 課題の作成と設定
* **タスクの作成**◀︎**ここにいる** – 課題タスクの定義

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [ 可用性ラベル ](../rn/releases.md#availability-labels)。

タスクは、ロイヤルティの課題で報酬を獲得するために顧客が完了する必要がある特定のアクションやマイルストーンを定義します。 タスクのタイプ、数量および製品要件を設定して、魅力的でパーソナライズされたロイヤルティエクスペリエンスを作成できます。

各タスクは、チャレンジの完了に貢献する測定可能なアクションを表します。 タスクは、個別に作成して 1 つ以上の課題に追加したり、課題内で直接作成したりできる、再利用可能なコンポーネントです。

## タスクの作成 {#create-task}

タスクは、2 つのエントリポイントから作成できます。 どこから開始しても、設定プロセスは同じです。

>[!BEGINTABS]

>[!TAB  タスクインベントリから ]

「**[!UICONTROL タスク]**」タブを選択し、「**[!UICONTROL タスクを作成]**」を選択します。

![](assets/task-create-inventory.png)

インベントリから作成されたタスクは保存され、複数の課題で再利用できます。

>[!TAB  チャレンジの中から ]

既存の課題を開くか、新しい課題を作成します。 **[!UICONTROL タスクを追加]** を選択し、「**[!UICONTROL 新規]**」ボタンをクリックします。

![](assets/task-create-challenge.png)

この方法で作成されたタスクは、自動的に課題に追加され、他の課題で再利用するためにタスクインベントリにも保存されます。

>[!ENDTABS]

## 顧客アクティビティを選択 {#choose-activity}

このタスクを完了するために顧客が実行する必要があるアクティビティのタイプを選択します。

* **[!UICONTROL 購入]**：このタスクを完了するには、顧客が 1 つ以上のアイテムを購入する必要があります
* **[!UICONTROL 費用]**：顧客はこのタスクを完了するために指定された金額を費やす必要があります

アクティビティタイプを選択するには、「`+`」アイコンをクリックし、結果の目標に最も適した顧客アクティビティを選択します。 各アクティビティタイプには、タスク要件をさらに定義し形成するための、特定の設定可能な属性があります。

![](assets/task-create-activitiy.png)

## 属性の定義 {#define-attributes}

選択したアクティビティタイプに基づいてタスク属性を設定します。

>[!BEGINTABS]

>[!TAB  購入アクティビティ ]

![](assets/task-create-purchase.png)

次の属性を設定します。

* **[!UICONTROL 数量]**：このタスクを完了するために購入する必要がある品目の数を入力します
* **[!UICONTROL 適格な項目と除外]**：タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。詳しくは、[ 適格な項目と除外の定義 ](#eligible-items-exclusions) を参照してください。

**オプションの属性** （「パラメーター」アイコンからアクティブ化）:

* **[!UICONTROL 最小費用金額]**：最小購買金額要件を設定します
* **[!UICONTROL トランザクションの最大数]**：タスクの完了に使用できるトランザクション数を制限します

>[!TAB  支出アクティビティ ]

![](assets/task-create-spend.png)

次の属性を設定します。

* **[!UICONTROL 金額]**：タスクの完了に必要な合計支出金額を入力します。
* **[!UICONTROL トランザクションの最大数]**：費用要件を満たすことができるトランザクションの数を指定します。 トランザクション数を制限しない場合は、パラメーターアイコンからこの属性を非アクティブにします。
* **[!UICONTROL 適格な項目と除外]**:（任意）タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。詳しくは、[ 適格な項目と除外の定義 ](#eligible-items-exclusions) を参照してください。

>[!ENDTABS]

## 実施要件を満たす項目と除外の定義 {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

**購入** アクティビティと **費用** アクティビティの両方について、**[!UICONTROL 適格な項目と除外]** 属性を使用して、適格と除外される項目とグループを定義できます。 これにより、特定の製品、カテゴリまたは場所をターゲットにして、課題の目標に合わせることができます。

ユースケースには、支出作業を特定の製品カテゴリに制限する、またはギフトカードやプロモーション項目を作業の完了に向けてカウントから除外することが含まれます。

![](assets/tasks-create-eligible.png)

* 実施要件を満たす項目を定義するには、「**[!UICONTROL 実施要件を満たすタスクの購入は次の項目に制限されます]** セクションを使用します。 特定の項目 ID、カテゴリまたは宛先 ID をコンマで区切って入力します。

  例：`SKU001, SKU002, CategoryA`

  すべての購入を有効にする `*` を入力します（空のままにした場合のデフォルトの動作）。

* タスクから項目を除外するには、**[!UICONTROL このタスクから除外する項目]** セクションを使用します。 タスクの完了にカウントすべきでない特定の項目 ID、カテゴリまたは宛先 ID を入力します。

  例：`CLEARANCE01, GIFTCARD, SALE_CATEGORY`

  >[!NOTE]
  >
  >除外は、実施要件を満たす項目よりも優先されます。 項目が実施要件を満たす項目と除外の両方に一致する場合、その項目はタスクから除外されます。

## タスクのプロパティの定義 {#define-task-properties}

タスク **[!UICONTROL プロパティ]** ペインで、タスクの基本情報を設定します。

* **[!UICONTROL タスク名]**：タスクのわかりやすい名前を入力します。 この名前は、本人とチームには表示されますが、コンテンツカードのデザインによっては顧客に表示されない場合があります。
* **[!UICONTROL タスクの説明]**：説明は、タスクに設定したアクティビティタイプと属性に基づいて自動的に生成されます。 必要に応じて、自動生成を無効にしたり、カスタム説明を入力したりできます。

![](assets/tasks-create-properties.png)

すべての属性とプロパティを設定したら、「**[!UICONTROL 作成]**」を選択してタスクを保存します。 タスクはタスクインベントリに保存され、チャレンジ内から作成された場合は、そのチャレンジに自動的に追加されます。
