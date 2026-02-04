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
source-git-commit: dbed4ffeb63ec3c58ff61845bbdb91fd2d51e69b
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 2%

---


# タスクの作成 {#create-tasks}

>[!BEGINSHADEBOX]

**ロイヤルティの課題に関するドキュメント：**

* [&#x200B; ロイヤルティの課題の概要 &#x200B;](get-started.md) – 概要、ワークフロー、前提条件
* [&#x200B; ロイヤルティの課題へのアクセス &#x200B;](access-loyalty-challenges.md) – 在庫とフィルタリング
* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 課題の作成と設定
* **タスクの作成**◀︎**ここにいる** – 課題タスクの定義
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 編集、監視、最適化

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>この機能は現在 **Private Beta** であり、お使いの環境では使用できない場合があります。アクセス権をリクエストするには、Adobe担当者にお問い合わせください。 詳細情報 [&#x200B; 可用性ラベル &#x200B;](../rn/releases.md#availability-labels)。

## 概要 {#overview}

タスクは、ロイヤルティの課題で報酬を獲得するために顧客が完了する必要がある特定のアクションやマイルストーンを定義します。 タスクのタイプ、数量、製品要件および報酬値を設定して、魅力的でパーソナライズされたロイヤルティエクスペリエンスを作成できます。

各タスクは、チャレンジの完了に貢献する測定可能なアクションを表します。 タスクは、個別に作成して 1 つ以上の課題に追加したり、課題内で直接作成したりできる、再利用可能なコンポーネントです。

### 様々な課題タイプでのタスクの仕組み {#task-overview}

<!-- VISUAL: Diagram showing how task completion works differently for Standard, Streak, and Sequential challenges with examples -->

課題のタイプ（標準、順次）に応じて、お客様のタスクの実行方法は異なります。

* **標準的な課題**：お客様は、任意の順序で任意の数のタスクを完了できます
* **一連の課題**：お客様が同じタスクを複数回連続して完了する
* **順次的な課題**：顧客が定義された順序でタスクを完了する

## タスクの作成 {#create-task}

<!-- SCREENSHOT: Two screenshots side by side showing the two entry points: Tasks tab with "Create task" button, and challenge editor with "Add task" button -->

タスクは、2 つのエントリポイントから作成できます。 どこから開始しても、設定プロセスは同じです。

+++タスクインベントリから

1. Journey Optimizerの **[!UICONTROL ロイヤルティの課題]** に移動します。

1. 「**[!UICONTROL タスク]**」タブを選択します。

1. **[!UICONTROL タスクを作成]** を選択します。

インベントリから作成されたタスクは保存され、複数の課題で再利用できます。

+++

+++課題の中から

1. 既存の課題を開くか、新しい課題を作成します。

1. 「**[!UICONTROL タスク]**」セクションに移動します。

1. 「**[!UICONTROL タスクを追加]**」を選択したあと、「**[!UICONTROL 新規タスクを作成]**」を選択します。

この方法で作成されたタスクは、自動的に課題に追加され、他の課題で再利用するためにタスクインベントリにも保存されます。

+++

### タスクのプロパティの定義 {#define-task-properties}

<!-- SCREENSHOT: Task properties form showing Task name and Task description fields -->

タスクの基本情報を設定します。

* **タスク名**：タスクのわかりやすい名前を入力します。 この名前は、本人とチームには表示されますが、コンテンツカードのデザインによっては顧客に表示されない場合があります。
* **タスクの説明**:（任意）タスクの目的または要件に関する詳細を追加します。

### 顧客アクティビティを選択 {#choose-activity}

<!-- SCREENSHOT: Activity type selection showing Purchase and Spend options with radio buttons -->

このタスクを完了するために顧客が実行する必要がある顧客活動のタイプを選択します：

* **[!UICONTROL 購入]**：このタスクを完了するには、顧客が 1 つ以上のアイテムを購入する必要があります
* **[!UICONTROL 費用]**：顧客はこのタスクを完了するために指定された金額を費やす必要があります

結果目標に最も適した顧客アクティビティを選択します。 各アクティビティタイプには、タスク要件をさらに定義し形成するための、特定の設定可能な属性があります。

### 属性の定義 {#define-attributes}

<!-- SCREENSHOT: Attributes form for Purchase activity showing Quantity field, Eligible items & exclusions field, and parameters icon for optional attributes -->

選択したアクティビティタイプに基づいてタスク属性を設定します。

+++購入アクティビティ用

次の属性を設定します。

* **数量**：このタスクを完了するために購入する必要がある品目の数を入力します
* **適格な項目と除外**：タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。詳しくは、[&#x200B; 適格な項目と除外の定義 &#x200B;](#eligible-items-exclusions) を参照してください。

**オプションの属性** （「パラメーター」アイコンからを設定）:

* **最小費用金額**：最小購買金額要件を設定します
* **トランザクションの最大数**：タスクの完了に使用できるトランザクション数を制限します

+++

+++費用アクティビティの

次の属性を設定します。

* **金額**：タスクの完了に必要な合計支出金額を入力します
* **トランザクションの最大数**：費用要件を満たすことができるトランザクションの数を指定します。 トランザクション数を制限しない場合は、パラメーターアイコンからこの属性を非アクティブにします
* **適格な項目と除外**:（任意）タスク完了にカウントされる項目または項目グループとカウントされない項目または項目グループを定義します。詳しくは、[&#x200B; 適格な項目と除外の定義 &#x200B;](#eligible-items-exclusions) を参照してください。

+++

すべての属性を設定したら、「**[!UICONTROL 作成]**」を選択してタスクを保存します。 タスクはタスクインベントリに保存され、チャレンジ内から作成された場合は、そのチャレンジに自動的に追加されます。

## 実施要件を満たす項目と除外の定義 {#eligible-items-exclusions}

<!-- SCREENSHOT: Eligible items & exclusions popup showing the two sections: "Eligible task purchases are limited to the following" and "The following are excluded from this task" with text input fields -->

購入アクティビティと支出アクティビティの両方について、実施要件を満たす項目とグループを定義でき、項目とグループを除外することもできます。 これにより、特定の製品、カテゴリまたは場所をターゲットにして、課題の目標に合わせることができます。

**ユースケース：**

* コーヒー品目の購入に対して顧客に報酬を与え、クリアランス製品は除外するタスクを作成します
* 支出作業を特定の製品カテゴリに制限する
* タスクの完了までのカウントからギフトカードまたはプロモーション項目を除外

### 実施要件を満たす項目を設定 {#configure-eligible-items}

実施要件を満たす項目を定義するには、「**[!UICONTROL 実施要件を満たすタスクの購入は次の項目に制限されます]** セクションを使用します。

* 特定の項目 ID、カテゴリまたは宛先 ID をコンマで区切って入力します
* 例：`SKU001, SKU002, CategoryA, StoreLocation123`
* **ヒント**：すべての購入を有効にする `*` を入力する（空のままにした場合のデフォルト動作）

### 除外の設定 {#configure-exclusions}

タスクから項目を除外するには、**[!UICONTROL このタスクから除外される項目]** セクションを使用します。

* タスクの完了にカウントすべきでない特定の項目 ID、カテゴリまたは宛先 ID を入力します
* 例：`CLEARANCE01, GIFTCARD, SALE_CATEGORY`
* 一般的な除外：販売またはクリアランス項目、ギフトカード、プロモーションアイテム

>[!NOTE]
>
>除外は、実施要件を満たす項目よりも優先されます。 項目が実施要件を満たす項目と除外の両方に一致する場合、その項目はタスクから除外されます。

## 次の手順 {#next-steps}

これで、タスクの作成および設定方法を理解できました。

* [&#x200B; 課題の作成 &#x200B;](create-challenges.md) – 完全な課題を作成し、報酬を設定する方法を説明します
* [&#x200B; 課題の管理 &#x200B;](manage-challenges.md) – 課題を編集、監視、最適化する方法を説明します。
