---
title: ジャーニー判別 AI モデル
description: 判別のためにジャーニーをランク付けする AI モデルを作成および使用して、AI 駆動のスコアに基づいてプロファイルごとに最適なジャーニーを選択する方法を説明します。
feature: Journeys, Decisioning
role: User
level: Intermediate
version: Journey Orchestration
badge: label="限定提供" type="Informative"
hide: true
hidefromtoc: true
exl-id: 3e7c3069-b022-4709-936d-acaad56b5882
source-git-commit: a1b9d589773c168cc8ad0cfac0cd1ba178ae4bb6
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 14%

---

# AI モデルを使用したジャーニーのランク付け {#journey-ai-models}

>[!AVAILABILITY]
>
>この機能は現在、限定提供（LA）になっています。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

[!DNL Adobe Journey Optimizer] れは、プロファイルがシステムで許可されている量以上の対象として認定されたときに、そのプロファイルが入力できるジャーニーを制御するのに役立ちます。 これを行うには、[ ルールセット ](rule-sets.md) を使用して、ジャーニーのエントリまたは同時実行に対するキャップを定義します。 プロファイルが上限を超えるジャーニーに対して適格な場合、各ジャーニーに割り当てられる優先度によって、選択されるジャーニーが決まります。

優先度を使用する代わりに、ランキング式で **AI モデル** を使用して、トレーニング済みモデルスコアに基づいてジャーニーを動的にランク付けすることもできます。

## AI モデルの作成 {#create-ai-model}

<!--Do you need specific permissions to create AI models?
>[!CAUTION]
>
>To create, edit, or delete AI models, you must have the **Manage Ranking Strategies** permission. [Learn more](../administration/high-low-permissions.md#manage-ranking-strategies)-->

ジャーニーランキングの AI モデルを作成するには、次の手順に従います。

1. コンバージョンイベントが収集されるデータセットを作成します。[方法についてはこちらを参照](../experience-decisioning/data-collection/create-dataset.md)

1. **[!UICONTROL オーケストレーションランキング]** セクションにアクセスし、「**[!UICONTROL AI モデル]**」タブを選択します。 以前に作成した AI モデルのリストが表示されます。

1. **[!UICONTROL AI モデルを作成]** をクリックします。

1. AI モデルの一意の名前と、必要に応じて説明を指定します。

   ![ 名前および説明フィールドを示す AI モデルの詳細 ](assets/journey-model-details.png){width="85%"}

   >[!NOTE]
   >
   >ランキングオブジェクトは、ランキング式が適用されるエンティティです。 デフォルトでは、ランキングオブジェクトは **[!UICONTROL ジャーニー]** に設定されています。

<!--
1. Select the type of AI model you want to create:

    * **[!UICONTROL Auto-optimization]** optimizes based on past performance. [Learn more](../experience-decisioning/ranking/auto-optimization-model.md)
    * **[!UICONTROL Personalized optimization]** optimizes and personalizes based on audiences and performance. [Learn more](../experience-decisioning/ranking/personalized-optimization-model.md)-->

1. 「**[!UICONTROL 最適化指標]**」セクションでは、デフォルトの指標 [!DNL Customer Journey Analytics] データビュー [ のすべて ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/data-views){target="_blank"} 指標がリストに表示されます。 モデルを最適化する指標を選択します。

   ![AI モデルのCustomer Journey Analytics指標を一覧表示する最適化指標ドロップダウン ](assets/journey-model-metrics.png){width="70%"}

   [!DNL Journey Optimizer] は **コンバージョン率** に基づいてランク付けされます（コンバージョン率= コンバージョンイベントの合計数/インプレッションイベントの合計数）。 コンバージョン率は次を使用して計算されます。

   * **インプレッションイベント** （表示される項目）
   * **コンバージョンイベント** （クリックやコンバージョンが発生する項目）

   これらのイベントは、Web SDKまたはモバイル SDKを使用して自動的にキャプチャされます。 詳しくは、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 概要を参照してください。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを選択します。このようなデータセットを作成する方法について詳しくは、[この節](../experience-decisioning/data-collection/create-dataset.md)を参照してください。

   ![ コンバージョンイベントとインプレッションイベントのデータセット選択 ](../experience-decisioning/assets/ai-model-datasets.png){width="85%"}

   >[!CAUTION]
   >
   >**[!UICONTROL エクスペリエンスイベント – 提案インタラクション]** フィールドグループに関連付けられたスキーマから作成されたデータセットのみがドロップダウンリストに表示されます。 最大 5 つのデータセットを選択できます。

1. <!--If you are creating a **[!UICONTROL Personalized optimization]** AI model, -->AI モデルのトレーニングに使用するセグメントを選択します。

   >[!NOTE]
   >
   >最大 50 個のオーディエンスを選択できます。

1. AI モデルを保存して有効化します。

ランキング式を作成する際に、AI モデルを選択できるようになりました。

## ジャーニーをランク付けする式で AI モデルを参照します {#reference-ai-model}

これで、ランキング式を作成するための参照として AI モデルを設定し、その式をルールセットに割り当てて、ルールセットをジャーニーに適用できます。 これを行うには、以下の手順に従います。

1. ランキング式を作成します。 [詳細情報](journey-ranking-formulas.md#create-journey-ranking-formula)

1. **[!UICONTROL AI モデルを選択]** ボタンを使用して、式に使用する AI モデルを選択します。

   ![ 「AI モデルを選択」ボタンを使用したジャーニーランキング式の詳細 ](assets/journey-formula-ai-model.png){width="80%"}

1. 「**[!UICONTROL 条件]**」セクションの少なくとも 1 つで条件を定義し、ランキングメソッドとして **[!UICONTROL AI モデルスコア]** を選択します。 例えば、ジャーニーに「プロモ」タグがある場合、ランキングスコアは AI モデルスコアです。

   ![ プロモタグ条件で AI モデルスコアをランキングメソッドとして使用するランキング式の例 ](assets/journey-formula-ex-2.png){width="60%"}

1. 「**[!UICONTROL 作成]**」をクリックして、ランキング式を完成させます。

1. 次に、ルールセットを作成し、ランキング方法として作成した式を選択します。 [詳細情報](journey-ranking-formulas.md#assign-formula-to-ruleset)

1. ジャーニーキャッピングルールを作成し、ルールセットを保存します。

1. 目的のジャーニーにルールセットを適用して保存します。 [詳細情報](journey-ranking-formulas.md#assign-rule-set-to-journey)

   >[!NOTE]
   >
   >ジャーニーに一度に適用できるルールセットは 1 つだけです。

このルールセットを使用するすべてのジャーニーは、キャップが適用されると、選択した AI モデルを参照する式でランク付けされます。
