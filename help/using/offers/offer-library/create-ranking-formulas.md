---
title: ランキング式の作成
description: Adobe Experience Platform でランキング式を作成する方法を説明します。
translation-type: tm+mt
source-git-commit: db7fd318b14d01a0369c934a3e01c6e368d7658d
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 72%

---

# ランキング式の作成 {#create-ranking-formulas}

## ランキング式について {#about-ranking-formulas}

**ランキング式** を使用すると、オファーの優先度スコアを考慮するのではなく、指定されたプレースメントに対して最初に提示するオファーを決定するルールを定義できます。

ランキング式は **PQL 構文**&#x200B;で表され、式中でプロファイル属性、コンテキストデータ、オファー属性を利用できます。 PQL 構文の使用方法について詳しくは、[関連するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja)を参照してください。

ランキング式を作成したら、その数式を決定内のプレースメント(旧オファーアクティビティ)に割り当てることができます。 詳しくは、[オファーの選択を判断時に設定する](../offer-activities/configure-offer-selection.md)を参照してください。

## ランキング式の作成 {#create-ranking-formula}

ランキング式を作成するには、次の手順に従います。

* **[!UICONTROL コンポーネント]**&#x200B;メニューにアクセスし、「**[!UICONTROL ランク]**」タブを選択します。

* 「**[!UICONTROL 数式を作成]**」をクリックして、新しいランキング式を作成します。

   ![](../../assets/ranking-create-formula.png)

* ランキング式の名前、説明、数式を指定します。

   この例では、実際の気温が高い場合に、「hot」属性を持つすべてのオファーの優先度を上げます。そのために、**contextData.weather=hot** を判定の呼び出し時に渡しています。

   ![](../../assets/ranking-syntax.png)

* 「**[!UICONTROL 保存]**」をクリックします。 ランキング式が作成されたら、リストからその式を選択して、詳細を取得したり編集または削除したりできます。

   これで、プレースメントに適格なオファーをランク付けする決定に使用する準備が整いました([決定でのオファーの選択の設定](../offer-activities/configure-offer-selection.md)を参照)。

   ![](../../assets/ranking-formula-created.png)
