---
title: ランキング式の作成
description: Adobe Experience Platform でランキング式を作成する方法を説明します。
source-git-commit: ea8a3644ecef911a14ea087b03d367976f0c898d
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 93%

---

# ランキング式の作成 {#create-ranking-formulas}

## ランキング式について {#about-ranking-formulas}

**ランキング式** を使用すると、オファーの優先度スコアを考慮するのではなく、指定されたプレースメントに対して最初に提示するオファーを決定するルールを定義できます。

ランキング式は **PQL 構文**&#x200B;で表され、式中でプロファイル属性、コンテキストデータ、オファー属性を利用できます。 PQL 構文の使用方法について詳しくは、[関連するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

ランキング式を作成したら、決定（旧称：オファー アクティビティ）内のプレースメントに割り当てることができます。詳しくは、[決定でのオファー選択の設定](../offer-activities/configure-offer-selection.md)を参照してください。

## ランキング式の作成 {#create-ranking-formula}

ランキング式を作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**&#x200B;メニューにアクセスし、「**[!UICONTROL ランキング]** 」タブを選択します。作成済みのランク付けのリストが表示されます。

   ![](../../assets/rankings-list.png)

1. 「**[!UICONTROL ランキングを作成]**」をクリックして、新しいランキング式を作成します。

   ![](../../assets/ranking-create-formula.png)

1. ランキング式の名前、説明、数式を指定します。

   この例では、実際の気温が高い場合に、「hot」属性を持つすべてのオファーの優先度を上げます。そのために、**contextData.weather=hot** を判定の呼び出し時に渡しています。

   ![](../../assets/ranking-syntax.png)

1. 「**[!UICONTROL 保存]**」をクリックします。 ランキング式が作成されたら、リストからその式を選択し、詳細を取得、編集、または削除できます。

   これで、この式を決定で使用し、プレースメントの対象となるオファーをランク付けできるようになりました。 「( [決定でのオファー選択の設定](../offer-activities/configure-offer-selection.md))」を参照）。

   ![](../../assets/ranking-formula-created.png)
