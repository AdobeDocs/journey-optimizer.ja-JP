---
title: ランキング式
description: オファーをランク付けする数式を作成する方法を学ぶ
feature: Ranking, Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: 35d7488b-e7d8-402f-b337-28a0c869bff0
version: Journey Orchestration
source-git-commit: 0b94bfeaf694e8eaf0dd85e3c67ee97bd9b56294
workflow-type: tm+mt
source-wordcount: '1457'
ht-degree: 92%

---

# AI 式ビルダーの使用 {#create-ranking-formulas}

**ランキング式**&#x200B;を使用すると、優先度スコアを考慮するのではなく、最初に提示するオファーを決定するルールを定義できます。

これらのルールを作成するために、**[!UICONTROL Adobe Journey Optimizer]** の AI 式ビルダーを使用すると、オファーのランク付け方法をより柔軟に制御できます。静的なオファーの優先度のみに依存するのではなく、ガイド付きインターフェイスを通じて、AI モデルスコア、オファーの優先度、プロファイル属性、オファー属性、コンテキストシグナルを組み合わせたカスタムランキング式を定義できるようになりました。

このアプローチにより、AI 駆動型の傾向、ビジネス価値、リアルタイムのコンテキストの任意の組み合わせに基づいてオファーのランキングを動的に調整できるので、マーケティング目標と顧客ニーズの両方に合わせた決定が容易になります。AI 式ビルダーは、適用するコントロールのレベルに応じて、シンプルな式または高度な式をサポートします。

ランキング式を作成したら、[選択戦略](../selection-strategies.md)に割り当てることができます。この選択戦略の使用時に実施要件を満たすオファーが複数ある場合、決定エンジンは選択した式を使用して、最初に配信するオファーを計算します。

## ランキング式の作成 {#create-ranking-formula}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_formulas"
>title="ランキング式の作成"
>abstract="式を使用すると、項目の優先度スコアを考慮するのではなく、最初に提示する決定項目を決定するルールを定義できます。ランキング式を作成したら、選択戦略に割り当てることができます。"

ランキング式を作成するには、次の手順に従います。

1. **[!UICONTROL 戦略設定]**&#x200B;メニューにアクセスし、「**[!UICONTROL ランキング式]**」タブを選択します。以前に作成した式のリストが表示されます。

   ![](../assets/ranking-formulas-list.png)

1. 「**[!UICONTROL 数式を作成]**」をクリックします。

1. 式の名前を指定し、必要に応じて説明を追加します。

   ![](../assets/create-formula.png){width="80%"}

1. オプションで、「**[!UICONTROL AI モデルを選択]**」をクリックして、ランキング式を作成するための参照として使用するモデルを設定します。

   >[!NOTE]
   >
   >連続的な指標を使用した、[パーソナライズされた最適化モデル](personalized-optimization-model.md)は、AI 式ビルダーではサポートされていません。

   以下の式を定義する際にモデルスコアを参照するたびに、選択した AI モデルが使用されます。

   >[!CAUTION]
   >
   >ランキング式に組み込まれた AI モデルを使用する場合、[ホールドアウトトラフィックとモデル駆動型トラフィックのコンバージョン率](../../reports/campaign-global-report-cja-code.md#conversion-rate)レポートにデータが反映されません。

1. 一致する決定項目のランキングスコアを決定する条件を定義します。以下のいずれかを実行できます。

   * [ユーザーインターフェイス](#ranking-select-criteria)から「**[!UICONTROL 条件]**」セクションに入力する。
   * [コードエディター](#ranking-code-editor)に切り替える。

   >[!NOTE]
   >
   >ランキング式のネスト深度は 30 レベルに制限されています。これは、PQL 文字列内の `)` の閉じ丸括弧をカウントすることによって測定されます。UTF-8 でエンコードされた文字の場合、ルール文字列のサイズは最大 8 KB になります。これは、8,000 個の ASCII 文字（各 1 バイト）、または 2,000～4,000 個の非 ASCII 文字（各 2～4 バイト）に相当します。[詳しくは、決定ガードレールと制限を参照してください](../decisioning-guardrails.md#ranking-formulas)

1. また、Adobe Experience Platform のデータを使用して、実際の条件を反映するようにランキングロジックを動的に調整することもできます。これは、製品の在庫状況やリアルタイムの価格設定など、頻繁に変更される属性の場合に特に役立ちます。

   この機能は現在、パブリックベータ版としてすべてのお客様にご使用いただけます。アクセス権をご希望の場合は、アカウント担当者にお問い合わせください。[詳しくは、決定の Adobe Experience Platform データの使用方法を参照してください。](../aep-data-exd.md)

<!--## Select an ELS dataset {#els-dataset}

Journey Optimizer allows you to leverage data from Adobe Experience Platform. [Learn more](../data/aep-data-perso.md)

To leverage data from an AEP dataset, follow the steps below.

1. From the **[!UICONTROL ELS settings]** section, select an ELS dataset from the list.

1. Select a decision attribute.

    >[!NOTE]
    >
    >This action is mandatory.

![](../assets/formula-els-settings.png){width="80%"-->

## 式ビルダーを使用した条件の定義 {#ranking-select-criteria}

直感的なインターフェイスにより、AI スコア（傾向）、オファーの値（優先度）、コンテキストレバー、外部プロファイルの傾向を個別または組み合わせて調整することで、決定を微調整し、すべてのインタラクションを最適化できます。<!--Whether you are maximizing revenue, promoting strategic offers, or balancing business goals with real-time context, the formula builder gives you total control in defining ranking strategies.-->

インターフェイスから直接条件を定義するには、次の手順に従います。

<!--![](../assets/ranking-formula-criteria.png){width="80%"}-->

1. 「**[!UICONTROL 条件 1]**」セクションで、次の手順を実行して、ランキングスコアを適用する決定項目を指定します。
   * [決定項目属性](../items.md#attributes)を選択します。
   * 論理演算子を選択します。
   * 一致条件を追加します（値を入力するか、プロファイル属性または[コンテキストデータ](../context-data.md)を選択できます）。

   ![](../assets/ranking-formula-criterion-1.png){width="70%"}

1. オプションで、追加の要素を指定して、条件が true になる一致条件を絞り込むことができます。

   ![](../assets/ranking-formula-addtional-conditions.png){width="80%"}

   例えば、条件 1 として、*天気*&#x200B;カスタム属性が&#x200B;*暖かい*&#x200B;に&#x200B;*等しい*&#x200B;という条件を定義したとします。さらに、最初の条件が満たされ、リクエスト時に温度が 75℃を超える場合は条件 1 が true になるなどの別の条件を追加できます。<!--Add a screenshot with the example-->

1. 上記で定義した条件を満たす決定項目にランキングスコアを割り当てる式を作成します。次のいずれかを参照できます。

   * [上記](#create-ranking-formula)の「**[!UICONTROL 詳細]**」セクションでオプションで選択した AI モデルから出力されたスコア。
   * 決定項目の優先度（[決定項目を作成](../items.md#attributes)する際に手動で割り当てられる値）。<!--If a profile qualifies for multiple decision items, a higher priority grants the item precedence over others.-->
   * 外部で派生した傾向スコアなど、プロファイルに存在する可能性のある属性。
   * 自由な形式で割り当てることができる静的な値。
   * 上記のすべての組み合わせ。

   ![](../assets/ranking-formula-expression.png){width="70%"}

   >[!NOTE]
   >
   >フィールドの横にあるアイコンをクリックして、定義済みの変数を追加します。

1. 「**[!UICONTROL 条件を追加]**」をクリックし、必要な回数に応じて 1 つ以上の条件を追加します。ロジックは次のとおりです。
   * 特定の決定項目に対して最初の条件が true である場合、その条件は次の条件よりも優先されます。
   * 最初の条件が true でない場合、決定エンジンは 2 番目の条件に進み、それ以降も同様に処理されます。

1. 最後のフィールドでは、上記の条件を満たさないすべての決定項目に割り当てられる式を作成できます。

   ![](../assets/ranking-formula-criteria-not-met.png){width="70%"}

1. 「**[!UICONTROL 作成]**」をクリックして、ランキング式を完成させます。リストから選択して詳細を表示し、編集または削除できるようになりました。実施要件を満たす決定項目をランク付けするための[選択戦略](../selection-strategies.md)で使用する準備が整いました。

### ランキング式の例

次の例をご覧ください。

![](../assets/ranking-formula-example.png){width="80%"}

決定項目の地域（カスタム属性）がプロファイルの地理ラベル（プロファイル属性）と等しい場合、ここで表されるランキングスコア（決定項目の優先度、AI モデルスコア、静的な値の組み合わせ）が、その条件を満たすすべての決定項目に適用されます。

## コードエディターの使用 {#ranking-code-editor}

ランキング式を **PQL 構文**&#x200B;で表すには、画面の右上にある専用ボタンを使用してコードエディターに切り替えます。PQL 構文の使用方法について詳しくは、[関連するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

>[!CAUTION]
>
>このアクションは、この式のデフォルトのビルダー表示に戻るのを防ぎます。

その後、プロファイル属性、[コンテキストデータ](../context-data.md)、[決定項目属性](../items.md#attributes)を活用できます。

例えば、実際の気温が高い場合に、「hot」属性を持つすべてのオファーの優先度を上げるとします。これを行うには、決定の呼び出し時に **contextData.weather=hot** を渡します。<!--[Learn how to work with context data](context-data.md)-->

![](../assets/ranking-formula-code-editor.png){width="80%"}

>[!IMPORTANT]
>
>ランキング式を作成する際、過去 1 か月以内に発生したエクスペリエンスイベントを式のコンポーネントとして追加するなど、以前の期間を振り返ることはサポートされていません。数式の作成中にルックバック期間を含めようとすると、保存時にエラーがトリガーされます。

数式で決定項目に関連する属性を活用するには、ランキング式のコードで正しい構文に従っていることを確認してください。詳しくは、各節を展開してください。

+++決定項目の標準属性の活用

![](../assets/formula-attribute.png)

+++

+++決定項目のカスタム属性の活用

![](../assets/formula-attribute-custom.png)

+++

### ランキング式 PQL の例 {#ranking-formula-examples}

必要に応じて、様々なランキング式を作成できます。以下に例を示します。

+++プロファイル属性に基づいた特定のオファー属性を持つオファーのブースト

オファーに対応する市区町村にプロファイルが住んでいる場合は、その市区町村内のすべてのオファーの優先度を 2 倍にします。

**ランキング式：**

```
if( offer.characteristics.get("city") = homeAddress.city, offer.rank.priority * 2, offer.rank.priority)
```

+++

+++終了日が今から 24 時間以内のオファーのブースト

**ランキング式：**

```
if( offer.selectionConstraint.endDate occurs <= 24 hours after now, offer.rank.priority * 3, offer.rank.priority)
```

+++

+++オファーされる製品を顧客が購入する傾向に基づいたオファーのブースト

顧客の傾向スコアに基づいて、オファーのスコアを上げることができます。

この例では、インスタンステナントは *_salesvelocity* です。また、プロファイルスキーマには、一連のスコアが配列に格納されます。

![](../assets/ranking-example-schema.png)

これを前提として、例えば、次のようなプロファイルの場合、

```
{"_salesvelocity": {"individualScoring": [
                    {"core": {
                            "category":"insurance",
                            "propensityScore": 96.9
                        }},
                    {"core": {
                            "category":"personalLoan",
                            "propensityScore": 45.3
                        }},
                    {"core": {
                            "category":"creditCard",
                            "propensityScore": 78.1
                        }}
                    ]}
}
```

+++

+++プロファイルの郵便番号と年収に基づいてオファーをブースト

この例では、システムは常に最初に ZIP 一致のオファーを表示しようとし、一致が見つからない場合は一般的なオファーにフォールバックし、他の ZIP コード向けのオファーを表示しないようにします。

```pql
if( offer._luma.offerDetails.zipCode = _luma.zipCode,luma.annualIncome / 1000 + 10000, if( not offer.luma.offerDetails.zipCode,_luma.annualIncome / 1000, -9999) )
```

数式の機能：

* オファーの郵便番号がユーザーと同じ場合は、非常に高いスコアを付けて、最初に選択されるようにします。
* オファーに郵便番号がまったく含まれていない場合（一般的なオファーの場合）、ユーザーの収入に基づいて通常のスコアを付けます。
* オファーの郵便番号がユーザーと異なる場合は、スコアを非常に低く設定し、選択されないようにします。

+++

+++コンテキストデータに基づいてオファーの優先度を上げる

[!DNL Journey Optimizer] を使用すると、呼び出しで渡されるコンテキストデータに基づいて、特定のオファーの優先度を上げることができます。例えば、`contextData.weather=hot` が渡される場合は、`attribute=hot` を含んだすべてのオファーの優先度を上げる必要があります。

>[!NOTE]
>
>コンテキストデータを渡す方法について詳しくは<!-- using the **Edge Decisioning** and **Decisioning** APIs-->、[この節](../context-data.md)を参照してください。

**Decisioning** API を使用する場合は、次の例のように、コンテキストデータをリクエスト本文のプロファイル要素に追加します。

```
"xdm:profiles": [
{
    "xdm:identityMap": {
        "crmid": [
            {
            "xdm:id": "CRMID1"
            }
        ]
    },
    "xdm:contextData": [
        {
            "@type":"_xdm.context.additionalParameters;version=1",
            "xdm:data":{
                "xdm:weather":"hot"
            }
        }
    ]
    
}],
```

+++
