---
title: 決定のユースケース
description: コードベースチャネルでの実験を使用した決定の作成方法について説明します。
feature: Decisioning
topic: Integrations
role: User
level: Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: 09770df2-c514-4217-a71b-e31c248df543
source-git-commit: 98b7a5493a4e325328ab349c405af423b3836807
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 54%

---

# 決定のユースケース {#experience-decisioning-uc}

このユースケースでは、[!DNL Journey Optimizer] コードベースチャネルで決定の使用に必要なすべての手順を示します。

この例では、特定のランキング式が、事前に割り当てられたオファーの優先度よりも優れたパフォーマンスを発揮するかどうかは不明です。 ターゲットオーディエンスに最適なパフォーマンスを測定するには、[ コンテンツ実験 ](../content-management/content-experiment.md) を使用してキャンペーンを作成し、次の 2 つの配信処理を定義します。

* 最初の処理では、ランキング方法として優先度を使用します。
* 2 番目の処理では、ランキング方法として式を使用します。

## 選択戦略の作成

まず、ランキング方法として優先度を使用する選択戦略と、ランキング方法として式を使用する選択戦略の 2 つを作成する必要があります。

>[!NOTE]
>
>選択戦略を実行しなくても、1 つの決定項目を作成できます。 各項目に設定された優先度が適用されます。

### 優先度を使用した戦略の作成

ランキング方法として優先度を使用する最初の選択戦略を作成するには、次の手順に従います。

1. 決定項目を作成します。[方法について詳しくは、こちらを参照してください](items.md)

1. 他の決定項目と比較した決定項目の&#x200B;**[!UICONTROL 優先度]**&#x200B;を設定します。プロファイルが複数の項目に該当する場合、優先度の高い項目が他の項目よりも優先されます。

   ![](assets/exd-uc-item-priority.png){width="90%"}

   >[!NOTE]
   >
   >優先度は、整数データタイプです。整数データタイプであるすべての属性には、整数値（小数は含まない）を含める必要があります。

1. 決定項目の実施要件を設定します。

   * オーディエンスまたはルールを定義して、項目を特定のプロファイルのみに制限します。[詳細情報](items.md#eligibility)

   * キャッピングルールを設定し、オファーを提示できる最大回数を定義します。[詳細情報](items.md#capping)

1. 必要に応じて、上記の手順を繰り返して、追加の決定項目を作成します。

1. 決定項目が含まれる&#x200B;**コレクション**&#x200B;を作成します。[詳細情報](collections.md)

1. [選択戦略](selection-strategies.md#create-selection-strategy)を作成し、検討するオファーを含む[コレクション](collections.md)を選択します。

1. [ランキング方法を選択](#select-ranking-method)し、プロファイルごとに最適なオファーを選択するのに使用します。この場合、「**[!UICONTROL オファーの優先度]**」を選択します。複数のオファーがこの戦略の実施要件を満たす場合、決定エンジンはオファーの&#x200B;**[!UICONTROL 優先度]**&#x200B;として設定された値を使用します。[詳細情報](selection-strategies.md#offer-priority)

   ![](assets/exd-uc-strategy-priority.png){width="90%"}

### 式を使用して別の戦略を作成する

ランキング方法として式を使用する 2 番目の選択戦略を作成するには、次の手順に従います。

1. 決定項目を作成します。[方法について詳しくは、こちらを参照してください](items.md)

   <!--Do you need to set the same **[!UICONTROL Priority]** as for the first decision item, or it won't be considered at all?-->

1. 決定項目の実施要件を設定します。

   * オーディエンスまたはルールを定義して、項目を特定のプロファイルのみに制限します。[詳細情報](items.md#eligibility)

   * キャッピングルールを設定し、オファーを提示できる最大回数を定義します。[詳細情報](items.md#capping)

1. 必要に応じて、上記の手順を繰り返して、追加の決定項目を作成します。

1. 決定項目が含まれる&#x200B;**コレクション**&#x200B;を作成します。[詳細情報](collections.md)

1. [選択戦略](selection-strategies.md#create-selection-strategy)を作成し、検討するオファーを含む[コレクション](collections.md)を選択します。

1. プロファイルごとに最適なオファーを選択するのに使用する[ランキング方法を選択](#select-ranking-method)します。この場合、「**[!UICONTROL 式]**」を選択し、特定の計算済みスコアを使用して、配信する実施要件を満たすオファーを決定します。[詳細情報](selection-strategies.md#ranking-formula)

   ![](assets/exd-uc-strategy-formula.png){width="90%"}

## コードベースのエクスペリエンスキャンペーンの作成

<!--To present the best dynamic offer and experience to your visitors on your website or mobile app, add a decision policy to a code-based campaign.

Define two delivery treatments each containing a different decision policy.-->

2 つの選択戦略を設定したら、コードベースのエクスペリエンスキャンペーンを作成します。このキャンペーンでは、パフォーマンスが最も高い戦略を比較するために、戦略ごとに異なる処理を定義します。

1. キャンペーンを作成し、**[!UICONTROL コードベースのエクスペリエンス]**&#x200B;アクションを選択します。[詳細情報](../code-based/create-code-based.md)

1. キャンペーンの概要ページで、「**[!UICONTROL 実験を作成]**」をクリックしてコンテンツ実験を設定します。 [方法について詳しくは、こちらを参照してください](../content-management/content-experiment.md)

   ![](assets/exd-uc-create-experiment.png){width="90%"}

1. キャンペーンの概要ページで、コードベースの設定を選択し、「**[!UICONTROL コンテンツを編集]**」をクリックします。

   ![](assets/exd-uc-edit-cbe-content.png){width="90%"}

1. コンテンツ編集ウィンドウで、**処理 A** のパーソナライズを開始するには、「**[!UICONTROL コードを編集]**」をクリックします。

   ![](assets/exd-uc-experiment-treatment-a.png){width="90%"}

1. [ コードエディター ](../code-based/create-code-based.md#edit-code) から「**[!UICONTROL 決定ポリシー]**」を選択し、「**[!UICONTROL 決定ポリシーを追加]**」をクリックして、決定の詳細を入力します。 [詳細情報](create-decision.md#add)

   ![](assets/decision-code-based-create.png){width="90%"}

1. 「**[!UICONTROL 戦略シーケンス]**」セクションで、「**[!UICONTROL 追加]**」ボタンをクリックし、「**[!UICONTROL 選択戦略]**」を選択します。 [詳細情報](create-decision.md#select)

   ![](assets/decision-code-based-strategy-sequence.png){width="80%"}

   >[!NOTE]
   >
   >**[!UICONTROL 決定項目]** を選択して、選択戦略を実行せずに 1 つの項目を追加することもできます。 各項目に設定された優先度が適用されます。

1. 最初に作成した戦略を選択します。

   ![](assets/exd-uc-experiment-strategy-priority.png){width="90%"}

1. 変更を保存し、「**[!UICONTROL 作成]**」をクリックします。 新しい決定が **[!UICONTROL 決定ポリシー]** の下に追加されます。

1. 「**[!UICONTROL ポリシーを挿入]**」ボタンをクリックします。決定ポリシーに対応するコードが追加されます。次に、プロファイル属性を含む、コードに必要なすべての属性を追加します。 [詳細情報](create-decision.md#use-decision-policy)

   ![](assets/exd-uc-experiment-insert-policy.png){width="90%"}

1. 変更を保存します。

1. コンテンツ編集ウィンドウに戻り、「+」ボタンを選択して **処理 B** を追加して選択し、「**[!UICONTROL コードを編集]**」をクリックします。

   ![](assets/exd-uc-experiment-treatment-b.png){width="90%"}

1. 上記の手順を繰り返して、別の決定ポリシーを作成し、作成した 2 番目の選択戦略を選択します。<!--Do you need to create exactly the same content to compare only the ranking method?-->

1. 変更を保存し [ コードベースのエクスペリエンスキャンペーンを公開 ](../code-based/publish-code-based.md) します。

エクスペリエンスを実行した後、[ 実験キャンペーンレポート ](../reports/campaign-global-report-cja-experimentation.md) を使用してキャンペーン処理のパフォーマンスを追跡します。<!-- and [report on decisioning](cja-reporting.md).--> その後、実験の結果を解釈できます。 [方法について詳しくは、こちらを参照してください](../content-management/get-started-experiment.md#interpret-results)

実験の結果が決定的な場合は、すべての顧客に最もパフォーマンスの高いランキングで処理をプッシュできます。 または、最もパフォーマンスの高いランキング方法がレプリケートされる選択戦略を使用して、新しいキャンペーンを作成できます。