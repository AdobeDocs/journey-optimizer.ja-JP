---
title: ジャーニー調停ランキング式
description: ルールとコンテキストに基づいてプロファイルごとに最適なジャーニーを選択できるように、調停のジャーニーをランク付けする式を作成する方法を説明します。
feature: Journeys, Decisioning
role: User
level: Intermediate
version: Journey Orchestration
badge: label="限定提供" type="Informative"
exl-id: b172e0e1-b78e-4d96-ab88-254507b55f48
source-git-commit: d7d9c371f4b0d8b4ea51e1f23eb9a2f665711fce
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 20%

---

# 数式を使用したジャーニーのランク付け {#journey-ranking-formulas}

>[!AVAILABILITY]
>
>この機能は現在限定的です。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

[!DNL Adobe Journey Optimizer]を使用すると、プロファイルがシステムで許可されている以上の条件を満たす場合に入力できるジャーニーを制御できます。 これには、[&#x200B; ルールセット &#x200B;](rule-sets.md)を使用して、ジャーニーのエントリまたは同時実行の上限を定義できます。 プロファイルがキャップが許可する以上のジャーニーの対象となる場合、各ジャーニーに割り当てられた優先度によって、選択されるジャーニーが決まります。

優先度を使用する代わりに、**ランキング式**&#x200B;を使用して、ジャーニー属性、プロファイル属性、またはAI モデルスコアに基づいてジャーニーのランキングを動的に調整することもできます。

数式は、静的な優先順位よりも柔軟性があります。 たとえば、ゴールドロイヤルティ会員のジャーニーを強化することができます。

<!--
>[!NOTE]
>
>Journey ranking formulas follow the same guardrails as decisioning ranking formulas (nesting depth, rule string size). [Learn more about Decisioning guardrails & limitations](../experience-decisioning/decisioning-guardrails.md#ranking-formulas).
-->

## ランキング式の作成 {#create-journey-ranking-formula}

ジャーニーのランキング式を作成するには、次の手順に従います。

1. 「**[!UICONTROL オーケストレーションランキング]**」セクションにアクセスし、「**[!UICONTROL ランキング式]**」タブを選択します。 以前に作成した式のリストが表示されます。

1. 「**[!UICONTROL 数式を作成]**」をクリックします。

1. 数式名を指定し、必要に応じて説明を追加します。

   ![名前フィールドと説明フィールドを含む数式の詳細ペイン &#x200B;](assets/journey-formula-details.png){width="80%"}


   >[!NOTE]
   >
   >ランキング オブジェクトは、ランキング式が適用されるエンティティです。 デフォルトでは、ランキングオブジェクトは&#x200B;**[!UICONTROL ジャーニー]**&#x200B;に設定されています。

   <!--
    Selecting a formula entity specifies which type of item—such as journeys or other entities—the ranking formula will apply to. This determines the context in which the formula operates, allowing you to define rules that influence how those items are ranked.
-->

1. オプションで、「**[!UICONTROL AI モデルを選択]**」をクリックして、ランキング式を作成するための参照として使用するモデルを設定します。[詳細情報](journey-ai-models.md)

<!--
    >[!NOTE]
    >
    >[Personalized optimization models](../experience-decisioning/ranking/personalized-optimization-model.md) using continuous metrics are not supported with the AI formula builder.

    Every time you refer to a model score when defining your formula below, the AI model that you selected will be used. [Learn more on AI models](../experience-decisioning/ranking/ai-models.md)
-->

1. **[!UICONTROL 基準1]** セクションで、次の操作を行って、ランキングスコアを適用するジャーニーを指定します。

   * [&#x200B; ジャーニー属性](../building-journeys/journey-properties.md)を選択します（ジャーニー名、タグ、優先順位、その他のジャーニープロパティなど）。
   * 論理演算子を選択します。
   * 一致する条件を追加 – 値を入力または選択するか、プロファイル属性を選択できます。

   ジャーニー属性、演算子、一致する条件を持つ![条件1 セクション &#x200B;](assets/journey-formula-criterion-1.png){width="70%"}

1. オプションで、追加の要素を指定して、条件が true になる一致条件を絞り込むことができます。

   ![一致する条件を絞り込む追加条件](assets/journey-formula-additional-condition.png){width="70%"}

   例えば、*ジャーニータグ*&#x200B;などの&#x200B;*基準1*&#x200B;に&#x200B;*ロイヤルティ*&#x200B;が含まれていることを定義しました。 さらに、*ロイヤルティステータス*&#x200B;が&#x200B;*ゴールド*&#x200B;に等しい場合、*基準1*&#x200B;が真である場合など、別の条件を追加できます。

1. 上記で定義した条件を満たすジャーニーにランキングスコアを割り当てる式を作成します。 次のいずれかを参照できます。
   * 変数：
      * ジャーニーの優先度。ジャーニーの作成時[にジャーニーに割り当てられた手動値です。](../building-journeys/journey-gs.md)
      * 上記でオプションで選択したAI モデルから得られたスコア。
   * 属性：
      * 外部で派生した傾向スコアなど、プロファイルに存在する可能性のある属性。
      * ジャーニー属性；
   * 自由な形式で割り当てることができる静的な値。
   * 上記のすべての組み合わせ。

   ![変数、属性、または静的値を使用してランキングスコアを割り当てる式ビルダー](assets/journey-formula-expression.png){width="70%"}

1. 「**[!UICONTROL 条件を追加]**」をクリックし、必要な回数に応じて 1 つ以上の条件を追加します。ロジックは次のとおりです。
   * 特定の決定項目に対して最初の条件が true である場合、その条件は次の条件よりも優先されます。
   * 最初の条件が true でない場合、決定エンジンは 2 番目の条件に進み、それ以降も同様に処理されます。

1. すべての条件を定義したら、最後のフィールドで、上記の条件を満たさないすべてのジャーニーに割り当てられる式を作成できます。

   条件を満たさないジャーニーの![式フィールド &#x200B;](assets/journey-formula-criteria-not-met.png){width="70%"}

1. 「**[!UICONTROL 作成]**」をクリックして、ランキング式を完了します。

リストからこの数式を選択して詳細を表示し、編集または削除できるようになりました。 このルールは、ルールセットを設定するときに使用できます。 [詳細情報](#assign-formula-to-ruleset)

### ランキング式の例 {#journey-ranking-formula-example}

次の例を考えてみましょう。

+++例1：ジャーニーの優先度またはジャーニータグに基づくAI スコアの使用

![&#x200B; ランキング式：マーケティングタグはジャーニーの優先度を使用します](assets/journey-formula-ex-1.png){width="60%"}

ジャーニーに「マーケティング」タグがある場合、ランキングスコアはジャーニーの優先度です。

![&#x200B; ランキング式：プロモーションタグはAI モデルスコアを使用します](assets/journey-formula-ex-2.png){width="60%"}

ジャーニーに「プロモーション」タグが付いている場合、ランキングスコアはAI モデルスコアです。

+++

+++例2：プロファイルステータス別にロイヤルティジャーニーを向上


![&#x200B; ランキング式：ゴールド ステータスのロイヤルティタグでは、ジャーニーの優先度に5](assets/journey-formula-ex-3.png){width="60%"}が加算されます

ジャーニーに「ロイヤルティ」タグがあり、プロファイルのロイヤルティステータスが「ゴールド」の場合、使用されるランキングスコアは、ジャーニーの優先度に5を加えたものです。

![&#x200B; ランキング式：シルバーのステータスを持つロイヤルティタグでは、ジャーニーの優先度に2](assets/journey-formula-ex-4.png){width="60%"}が加算されます

ジャーニーに「ロイヤルティ」タグがあり、プロファイルのロイヤルティステータスがシルバーの場合、ランキングスコアはジャーニーの優先度に2を加えたものになります。

上記の条件のいずれも満たさない場合は、使用されるランキングスコアがジャーニーの優先度になります。

+++

### コードエディターの使用 {#journey-ranking-formula-code-editor}

ランキング式を **PQL 構文**&#x200B;で表すには、画面の右上にある専用ボタンを使用してコードエディターに切り替えます。PQL 構文の使用方法について詳しくは、[関連するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

>[!CAUTION]
>
>このアクションは、この式のデフォルトのビルダー表示に戻るのを防ぎます。

そして、ジャーニー属性、プロファイル属性、静的値を活用して、ランキング式を構築できます。

<!--The code editor is similar to the one used in Decisioning ranking formulas. [Learn more](../experience-decisioning/ranking/ranking-formulas.md#ranking-code-editor)-->

## ルールセットへの数式の割り当て {#assign-formula-to-ruleset}

数式を使用してジャーニーをランク付けするには、それをルールセットに割り当てる必要があります。

>[!NOTE]
>
>式は、個々のジャーニーではなく、ルールセットレベルで割り当てられます。

1. **[!UICONTROL ビジネスルール]** メニューから、ジャーニーの調停に使用するルールセットを作成します。 [詳細情報](rule-sets.md#Create)

1. **[!UICONTROL ドメイン]** ジャーニーを選択してください。

   ![ジャーニードメインを選択したルールセットプロパティ &#x200B;](assets/journey-formula-rule-set-journey.png){width="60%"}

1. ルールセットプロパティで、**[!UICONTROL ランキング方法]**&#x200B;を&#x200B;**[!UICONTROL 式]**&#x200B;に設定します（デフォルトの&#x200B;**[!UICONTROL 優先度]**&#x200B;の代わりに）。

1. ドロップダウンリストから作成したランキング式を選択します。

   ![&#x200B; ドロップダウンリストから選択されたランキング式を含むルールセット &#x200B;](assets/journey-rule-set-formula.png){width="60%"}

1. ルールセットに追加するジャーニーキャッピングルールを作成します。 [詳細情報](journey-capping.md#create-rule)

1. ルールセットを保存します。

これで、式がルールセットに割り当てられます。 そして、そのルールセットをジャーニーに適用することができます。

## ルールセットをジャーニーに適用する {#assign-rule-set-to-journey}

ジャーニーにルールセットを割り当てるには、次の手順に従います。

1. ルールセットを割り当てるジャーニーを作成するか、開きます。 [詳しくは、ジャーニーの作成方法を参照してください。](../building-journeys/journey-gs.md)

1. ジャーニープロパティで、ドロップダウンリストからルールセットを選択します。  [方法についてはこちらを参照してください](journey-capping.md#apply-capping)。

   >[!NOTE]
   >
   >一度に1つのジャーニーに適用できるルールセットは1つだけです。

1. ジャーニーを保存します。

このルールセットを使用するすべてのジャーニーは、キャップが適用されたときに、選択した数式でランク付けされます。

ルールセットとランキング式のパフォーマンスを監視するには、概要レポートの「[ジャーニーのキャッピングと競合](../reports/channel-report-cja.md#rule-sets)」セクションを参照してください。

<!--
## Reporting {#reporting}

Reporting for journey arbitration helps you understand how rule sets and ranking formulas perform:

* **Exclusions** – Whether journeys were excluded from users and which rule set (and reason) prevented entry.
* **Rule set performance** – For each rule set, metrics such as journey enters, journey exclusions, journey engagement, and other optimization metrics.
* **Cross-journey view** – Time-based view of profiles across journeys (e.g. journey enters, failures, exclusions) to see the impact of capping and ranking.

Use these reports to validate that your formulas and caps are behaving as intended and to tune ranking logic over time.
-->
