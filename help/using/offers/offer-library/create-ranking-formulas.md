---
title: ランキング式の作成
description: Adobe Experience Platform でランキング式を作成する方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 8bc808da-4796-4767-9433-71f1f2f0a432
source-git-commit: 58dffe64b1ca8a81728ae7043ec276917d3b9616
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 41%

---

# ランキング式の作成 {#create-ranking-formulas}

## ランキング式について {#about-ranking-formulas}

**ランキング式** を使用すると、オファーの優先度スコアを考慮するのではなく、指定されたプレースメントに対して最初に提示するオファーを決定するルールを定義できます。

ランキング式は **PQL 構文**&#x200B;で表され、式中でプロファイル属性、コンテキストデータ、オファー属性を利用できます。PQL 構文の使用方法について詳しくは、[関連するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

ランキング式を作成したら、決定（旧称：オファーアクティビティ）内のプレースメントに割り当てることができます。詳しくは、[決定でのオファーの選択設定](../offer-activities/configure-offer-selection.md)を参照してください。

## ランキング式の作成 {#create-ranking-formula}

ランキング式を作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**&#x200B;メニューにアクセスし、「**[!UICONTROL ランキング]**」タブを選択します。作成済みのランキングのリストが表示されます。

   ![](../../assets/rankings-list.png)

1. 「**[!UICONTROL ランキングを作成]**」をクリックして、新しいランキング式を作成します。

   ![](../../assets/ranking-create-formula.png)

1. ランキング式の名前、説明、数式を指定します。

   この例では、実際の気温が高い場合に、「hot」属性を持つすべてのオファーの優先度を上げます。そのために、**contextData.weather=hot** を判定の呼び出し時に渡しています。

   ![](../../assets/ranking-syntax.png)

1. 「**[!UICONTROL 保存]**」をクリックします。ランキング式が作成されたら、リストからその式を選択して詳細を取得し、式を編集または削除したりできます。

   これで、ランキング式を決定で使用して、プレースメントに対する実施要件を満たすオファーをランク付けする準備が整いました（「 [決定でのオファー選択の設定](../offer-activities/configure-offer-selection.md)」を参照してください）。

   ![](../../assets/ranking-formula-created.png)

## ランキング式の例 {#ranking-formula-examples}

必要に応じて、様々なランキング式を作成できます。 以下に例を示します。

<!--
Boost by offer ID

Boost the priority of an offer with the offer ID *xcore:personalized-offer:13d213cd4cb328ec* by 5.

**Ranking formula:**

```
if( offer._id = "xcore:personalized-offer:13d213cd4cb328ec", offer.rank.priority + 5, offer.rank.priority)
```

Change the offer priority based on a certain profile attribute

Set the offer priority to 30 for offer *xcore:personalized-offer:13d213cd4cb328ec* if the user lives in the city of Bondi.

**Ranking formula:**

```
if( offer._id = "xcore:personalized-offer:13d213cd4cb328ec" and homeAddress.city.equals("Bondi", false), 30, offer.rank.priority)
```

Boost multiple offers by offer ID based on the presence of a profile's segment membership

Boost the priority of offers based on whether the user is a member of a priority segment, which is configured as an attribute in the offer.

**Ranking formula:**

```
if( segmentMembership.get("ups").get(offer.characteristics.prioritySegmentId).status in (["realized","existing"]), offer.rank.priority + 10, offer.rank.priority)
```
-->

### プロファイル属性に基づいて特定のオファー属性を持つオファーを増やす

プロファイルがオファーに対応する市に住んでいる場合、その市内のすべてのオファーの優先度を2倍にします。

**ランキング式:**

```
if( offer.characteristics.city = homeAddress.city, offer.rank.priority * 2, offer.rank.priority)
```

### 終了日が24時間未満のオファーを今すぐブースト

**ランキング式:**

```
if( offer.selectionConstraint.endDate occurs <= 24 hours after now, offer.rank.priority * 3, offer.rank.priority)
```

### コンテキストデータに基づいて、特定のオファー属性を持つオファーをブーストする

判定呼び出しで渡されるコンテキストデータに基づいて、特定のオファーをブーストします。 例えば、判定呼び出しで`contextData.weather=hot`が渡される場合は、`attribute=hot`を含むすべてのオファーの優先度を上げる必要があります。

**ランキング式:**

```
if (@{_xdm.context.additionalParameters;version=1}.weather.isNotNull()
and offer.characteristics.weather=@{_xdm.context.additionalParameters;version=1}.weather, offer.rank.priority + 5, offer.rank.priority)
```

判定APIを使用する場合、コンテキストデータはリクエスト本文のプロファイル要素に追加されます（下図の例を参照）。

**リクエスト本文のスニペット：**

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

### 提供される製品を購入する顧客の傾向に基づいてオファーを押し上げる

航空会社の&#x200B;*travelInsurance*&#x200B;と&#x200B;*extraBagge*&#x200B;を購入する傾向を計算する&#x200B;*CustomerAI*&#x200B;の2つのインスタンスがある場合、次のランキング式は、保険に固有のオファーの優先順位（50ポイント）を上げます。0.

ただし、*CustomerAI*&#x200B;インスタンスごとに、統合プロファイルスキーマ内に独自のオブジェクトが作成されるので、オファーの傾向タイプに基づいてスコアを動的に選択することはできません。 したがって、`if`ステートメントを連結して、最初にオファーの傾向タイプを確認し、次に適切なプロファイルフィールドからスコアを抽出する必要があります。

**ランキング式:**

```
if ( offer.characteristics.propensityType = "extraBaggagePropensity" and _salesvelocity.CustomerAI.extraBaggagePropensity.score > 90, offer.rank.priority + 50,
    (
        if ( offer.characteristics.propensityType = "travelInsurancePropensity" and _salesvelocity.CustomerAI.insurancePropensity.score > 90, offer.rank.priority + 50, offer.rank.priority )
    )
)
```

より良い解決策は、スコアをプロファイルの配列に格納することです。 次の例は、単純なランキング式を使用して、様々な傾向スコアに対して機能します。 スコアの配列を持つプロファイルスキーマがあることが予想されます。 この例では、インスタンステナントは&#x200B;*_salesvelocity*&#x200B;で、プロファイルスキーマには次の値が含まれます。

![](../../assets/ranking-example-schema.png)

この場合、次のようなプロファイルに対して：

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

オファーには、スコアのカテゴリに一致する&#x200B;*propensityType*&#x200B;の属性が含まれます。

![](../../assets/ranking-example-propensityType.png)

次に、各オファーの優先度を、その&#x200B;*propensityType*&#x200B;の顧客&#x200B;*propensityScore*&#x200B;と等しく設定できます。 スコアが見つからない場合は、オファーに設定された静的優先度を使用します。

```
let score = (select _Individual_Scoring1 from _salesvelocity.individualScoring
             where _Individual_Scoring1.core.category.equals(offer.characteristics.propensityType, false)).head().core.propensityScore
in if(score.isNotNull(), score, offer.rank.priority)
```
