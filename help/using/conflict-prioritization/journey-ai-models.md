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
source-git-commit: fe6e8221201ee813251a46c6603d85f0803873c0
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 18%

---

# AI モデルを使用したジャーニーのランク付け {#journey-ai-models}

>[!AVAILABILITY]
>
>この機能は現在、限定提供（LA）になっています。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

[!DNL Adobe Journey Optimizer] れは、プロファイルがシステムで許可されている量以上の対象として認定されたときに、そのプロファイルが入力できるジャーニーを制御するのに役立ちます。 これを行うには、[&#x200B; ルールセット &#x200B;](rule-sets.md) を使用して、ジャーニーのエントリまたは同時実行に対するキャップを定義します。 プロファイルが上限を超えるジャーニーに対して適格な場合、各ジャーニーに割り当てられる優先度によって、選択されるジャーニーが決まります。

優先度やランキングの式を使用する代わりに、**AI モデル** を使用して、トレーニング済みモデルスコアに基づいてジャーニーを動的にランク付けできます。 UI の **[!UICONTROL オーケストレーションランキング]** セクションから AI モデルを作成し、ルールセットで使用してジャーニーに適用できます。

[!DNL Journey Optimizer] で使用可能な AI モデルタイプの概要については、意思決定の節の [AI モデルの基本を学ぶ &#x200B;](../experience-decisioning/ranking/ai-models.md#ai-model-types) を参照してください。

## AI モデルの作成 {#create-ai-model}

>[!CAUTION]
>
>AI モデルを作成、編集または削除するには、**ランキング戦略を管理**&#x200B;する権限が必要です。[詳細情報](../administration/high-low-permissions.md#manage-ranking-strategies)

ジャーニーランキングの AI モデルを作成するには、次の手順に従います。

1. コンバージョンイベントが収集されるデータセットを作成します。[方法についてはこちらを参照](../experience-decisioning/data-collection/create-dataset.md)

1. **[!UICONTROL オーケストレーションランキング]** セクションにアクセスし、「**[!UICONTROL AI モデル]**」タブを選択します。 以前に作成した AI モデルのリストが表示されます。

1. **[!UICONTROL AI モデルを作成]** をクリックします。

1. AI モデルの一意の名前と、必要に応じて説明を指定します。

   ![&#x200B; 名前と説明フィールドを含んだ AI モデルの詳細ペイン &#x200B;](assets/journey-model-details.png){width="80%"}

   >[!NOTE]
   >
   >ランキングオブジェクトは、ランキング式が適用されるエンティティです。 デフォルトでは、ランキングオブジェクトは **[!UICONTROL ジャーニー]** に設定されています。

<!--
1. Select the type of AI model you want to create:

    * **[!UICONTROL Auto-optimization]** optimizes based on past performance. [Learn more](../experience-decisioning/ranking/auto-optimization-model.md)
    * **[!UICONTROL Personalized optimization]** optimizes and personalizes based on audiences and performance. [Learn more](../experience-decisioning/ranking/personalized-optimization-model.md)-->

1. 「**[!UICONTROL 最適化指標]**」セクションでは、AI モデルが使用するコンバージョンイベントに関する情報が提供されます。 [!DNL Journey Optimizer] は **コンバージョン率** に基づいてランク付けされます（コンバージョン率= コンバージョンイベントの合計数/インプレッションイベントの合計数）。 コンバージョン率は次を使用して計算されます。

   * **インプレッションイベント** （表示される項目）
   * **コンバージョンイベント** （クリックやコンバージョンが発生する項目）

   これらのイベントは、Web SDKまたはモバイル SDKを使用して自動的にキャプチャされます。 詳しくは、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja) 概要を参照してください。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを選択します。このようなデータセットを作成する方法について詳しくは、[この節](../experience-decisioning/data-collection/create-dataset.md)を参照してください。

   ![&#x200B; コンバージョンイベントとインプレッションイベントのデータセット選択 &#x200B;](../experience-decisioning/assets/ai-model-datasets.png){width="85%"}

   >[!CAUTION]
   >
   >「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループ（以前の mixin）に関連付けられたスキーマから作成されたデータセットのみがドロップダウンリストに表示されます。

1. &#x200B;<!--If you are creating a **[!UICONTROL Personalized optimization]** AI model, -->AI モデルのトレーニングに使用するセグメントを選択します。

   >[!NOTE]
   >
   >最大 5 個のオーディエンスを選択できます。

1. AI モデルを保存して有効化します。

AI モデルは、ルールセットを設定する際に使用できるようになりました。

## AI モデルをルールセットに割り当てる {#assign-ai-model-to-ruleset}

AI モデルを使用してジャーニーをランク付けするには、式で使用し、この式をルールセットに割り当てる必要があります。

1. 作成した AI モデルを使用してランキング式を作成します。 [詳細情報](journey-ranking-formulas.md#create-journey-ranking-formula)

1. **[!UICONTROL ビジネスルール]** メニューから、ジャーニーの判別に使用するルールセットを作成します。 [詳細情報](rule-sets.md#Create)

1. 必ず **[!UICONTROL ジャーニー]** ドメインを選択してください。

1. ルールセットのプロパティで、**[!UICONTROL ランキング方法]** を **[!UICONTROL 優先度]** ではなく **[!UICONTROL 式]** に設定します。

1. 作成した AI モデルを使用する式をドロップダウンリストから選択します。

1. ルールセットに追加するジャーニーキャッピングルールを作成します。 [詳細情報](journey-capping.md#create-rule)

1. ルールセットを保存します。

これで、AI モデルを使用した数式がルールセットに割り当てられます。 その後、そのルールセットをジャーニーに適用できます。

## ジャーニーへのルールセットの適用 {#assign-rule-set-to-journey}

ジャーニーにルールセットを割り当てるには、次の手順に従います。

1. ルールセットを割り当てるジャーニーを作成するか、開きます。 [詳しくは、ジャーニーの作成方法を参照してください。](../building-journeys/journey-gs.md)

1. ジャーニーのプロパティで、ドロップダウンリストからルールセットを選択します。 [方法についてはこちらを参照してください](journey-capping.md#apply-capping)。

   >[!NOTE]
   >
   >ジャーニーに一度に適用できるルールセットは 1 つだけです。

1. ジャーニーを保存します。

このルールセットを使用するすべてのジャーニーは、キャップが適用される際に、AI モデルを使用して、選択された式でランク付けされます。
