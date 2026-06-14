---
title: 決定のユースケース
description: コードベースのエクスペリエンスチャネルを使用して、決定を作成し、コンテンツ実験で使用する方法について説明します。
feature: Decisioning, Use Cases
topic: Integrations
role: User
level: Intermediate, Experienced
exl-id: 09770df2-c514-4217-a71b-e31c248df543
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/aDWJPWR3IA1EOvCxgqg9vf7KGgw3w4bzsJIZdaUphu4
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee394c77b226dd35a9c27f4a02e3b8d7a997ccbd
workflow-type: tm+mt
source-wordcount: 931
ht-degree: 87%

---

# コードベースのエクスペリエンスでコンテンツ実験に意思決定を活用する {#experience-decisioning-uc}

>[!BEGINSHADEBOX]

**このページでは、** 2つの選択戦略を構築し、コードベースのエクスペリエンス コンテンツ実験でランキング方法を比較するユースケースに従います。これにより、オーディエンスにとって最も効果的な決定アプローチを判断できます。

>[!ENDSHADEBOX]

このユースケースでは、[!DNL Journey Optimizer] コードベースチャネルで決定の使用に必要なすべての手順を示します。

➡️ [動画でユースケースを見つける](#video)

>[!NOTE]
>
>従来の意思決定管理機能は、コードベースのエクスペリエンスチャネルではサポートされていません。

この例では、特定のランキング式が、事前に割り当てられたオファーの優先度よりも優れたパフォーマンスを発揮するかどうか確信が持てません。 ターゲットオーディエンスに最適なパフォーマンスを測定するには、[コンテンツ実験](../content-management/content-experiment.md)を使用してキャンペーンを作成し、次の 2 つの配信処理を定義します。

* 最初の処理では、ランキング方法として&#x200B;**優先度**&#x200B;を使用します。
* 2 番目の処理では、ランキング方法として&#x200B;**式**&#x200B;を使用します。

>[!NOTE]
>
>コードベースのエクスペリエンスで決定を使用する際のテストと重複排除の実装について詳しくは、[このページ](../code-based/code-based-decisioning-implementations.md)を参照してください。

## 選択戦略の作成

まず、ランキング方法として優先度を使用する選択戦略と、ランキング方法として式を使用する選択戦略の 2 つを作成する必要があります。

>[!NOTE]
>
>また、選択戦略を介さずに 1 つの決定項目を作成することもできます。 各項目に設定されている優先度が適用されます。

### 優先度を使用した戦略の作成

ランキング方法として優先度を使用する最初の選択戦略を作成するには、次の手順に従います。

1. 決定項目を作成します。 [方法について詳しくは、こちらを参照してください](items.md)

1. 他の決定項目と比較した決定項目の&#x200B;**[!UICONTROL 優先度]**&#x200B;を設定します。 プロファイルが複数の項目に該当する場合、優先度の高い項目が他の項目よりも優先されます。

   ![](assets/exd-uc-item-priority.png){width="90%"}

   >[!NOTE]
   >
   >優先度は、整数データタイプです。 整数データタイプであるすべての属性には、整数値（小数は含まない）を含める必要があります。

1. 決定項目の実施要件を設定します。

   * オーディエンスまたはルールを定義して、項目を特定のプロファイルのみに制限します。 [詳細情報](items.md#eligibility)

   * キャップルールを設定し、オファーを提示できる最大回数を定義します。 [詳細情報](items.md#capping)

1. 必要に応じて、上記の手順を繰り返して、追加の決定項目を作成します。

1. 決定項目が含まれる&#x200B;**コレクション**&#x200B;を作成します。 [詳細情報](collections.md)

1. [選択戦略](selection-strategies.md#create-selection-strategy)を作成し、検討するオファーを含む[コレクション](collections.md)を選択します。

1. [ランキング方法を選択](#select-ranking-method)し、プロファイルごとに最適なオファーを選択するのに使用します。 この場合、「**[!UICONTROL オファーの優先度]**」を選択します。複数のオファーがこの戦略の実施要件を満たす場合、決定エンジンはオファーの&#x200B;**[!UICONTROL 優先度]**&#x200B;として設定された値を使用します。 [詳細情報](selection-strategies.md#offer-priority)

   ![](assets/exd-uc-strategy-priority.png){width="90%"}

### 式を使用した別の戦略の作成

ランキング方法として式を使用する 2 番目の選択戦略を作成するには、次の手順に従います。

1. 決定項目を作成します。 [方法について詳しくは、こちらを参照してください](items.md)

   <!--Do you need to set the same **[!UICONTROL Priority]** as for the first decision item, or it won't be considered at all?-->

1. 決定項目の実施要件を設定します。

   * オーディエンスまたはルールを定義して、項目を特定のプロファイルのみに制限します。 [詳細情報](items.md#eligibility)

   * キャップルールを設定し、オファーを提示できる最大回数を定義します。 [詳細情報](items.md#capping)

1. 必要に応じて、上記の手順を繰り返して、追加の決定項目を作成します。

1. 決定項目が含まれる&#x200B;**コレクション**&#x200B;を作成します。 [詳細情報](collections.md)

1. [選択戦略](selection-strategies.md#create-selection-strategy)を作成し、検討するオファーを含む[コレクション](collections.md)を選択します。

1. プロファイルごとに最適なオファーを選択するのに使用する[ランキング方法を選択](#select-ranking-method)します。 この場合、「**[!UICONTROL 式]**」を選択し、特定の計算済みスコアを使用して、配信する実施要件を満たすオファーを決定します。 [詳細情報](selection-strategies.md#ranking-formula)

   ![](assets/exd-uc-strategy-formula.png){width="90%"}

## コードベースのエクスペリエンスキャンペーンの作成

2つの選択戦略を設定したら、コードベースのエクスペリエンスキャンペーンを作成し、各戦略に対して異なる処理を定義して、最もパフォーマンスが高いものを比較します。

1. キャンペーンを作成し、**[!UICONTROL コードベースのエクスペリエンス]**&#x200B;アクションを選択します。 [詳細情報](../code-based/create-code-based.md)

1. キャンペーンの概要ページで「**[!UICONTROL 実験を作成]**」をクリックして、コンテンツ実験を設定します。 [方法について詳しくは、こちらを参照してください](../content-management/content-experiment.md)

   ![](assets/exd-uc-create-experiment.png){width="90%"}

1. キャンペーンの概要ページで、コードベースの設定を選択し、「**[!UICONTROL コンテンツを編集]**」をクリックします。

   ![](assets/exd-uc-edit-cbe-content.png){width="90%"}

1. コンテンツ編集ウィンドウから、**処理 A** のパーソナライズを開始するには、「**[!UICONTROL コードを編集]**」をクリックします。

   ![](assets/exd-uc-experiment-treatment-a.png){width="90%"}

1. [コードエディター](../code-based/create-code-based.md#edit-code)から「**[!UICONTROL 決定ポリシー]**」を選択し、「**[!UICONTROL 決定ポリシーを追加]**」をクリックして、決定の詳細を入力します。 [詳細情報](create-decision.md#add)

   ![](assets/decision-code-based-create.png){width="90%"}

1. 「**[!UICONTROL 戦略シーケンス]**」セクションで、「**[!UICONTROL 追加]**」ボタンをクリックし、「**[!UICONTROL 選択戦略]**」を選択します。 [詳細情報](create-decision.md#select)

   ![](assets/decision-code-based-strategy-sequence.png){width="80%"}

   >[!NOTE]
   >
   >また、「**[!UICONTROL 決定項目]**」を選択して、選択戦略を介さずに 1 つの項目を追加することもできます。 各項目に設定されている優先度が適用されます。

1. 作成した最初の戦略（ランキング方法として優先度を使用する戦略）を選択します。

   ![](assets/exd-uc-experiment-strategy-priority.png){width="90%"}

1. 変更を保存し、「**[!UICONTROL 作成]**」をクリックします。 **[!UICONTROL 決定ポリシー]**&#x200B;の下に新しい決定が追加されます。

1. 「**[!UICONTROL ポリシーを挿入]**」ボタンをクリックします。 決定ポリシーに対応するコードが追加されます。 次に、必要なすべての属性（プロファイル属性を含む）をコードに追加します。 [詳細情報](create-decision.md#create-decision)

   ![](assets/exd-uc-experiment-insert-policy.png){width="90%"}

1. 変更を保存します。

1. コンテンツ編集ウィンドウに戻り、「+」ボタンを選択して&#x200B;**処理 B** を追加し、これを選択して「**[!UICONTROL コードを編集]**」をクリックします。

   ![](assets/exd-uc-experiment-treatment-b.png){width="90%"}

1. 上記の手順 5 と 6 を繰り返して別の決定ポリシーを作成し、作成した 2 番目の選択戦略（ランキング方法として式を使用する戦略）を選択します。<!--Do you need to create exactly the same content to compare only the ranking method?-->

   ![](assets/exd-uc-experiment-strategy-formula.png){width="90%"}

1. 必要に応じて決定ポリシーを編集します（上記の手順 8 および 9 を参照）。

1. 変更を保存し、[コードベースのエクスペリエンスキャンペーンを公開](../code-based/publish-code-based.md)します。

実験を実行した後、[実験キャンペーンレポート ](../reports/campaign-global-report-cja-experimentation.md)でキャンペーン処理のパフォーマンスを追跡します。<!-- and [report on decisioning](cja-reporting.md).--> その後、実験の結果を解釈できます。 [方法についてはこちらを参照](../content-management/get-started-experiment.md#interpret-results)

結果が最終的な場合：

* 最もパフォーマンスの高いランキングで処理をすべてのお客様にプッシュできます。
* または、最もパフォーマンスの高いランキング方法を複製する選択戦略を使用して、新しいキャンペーンを作成することもできます。

## チュートリアルビデオ {#video}

コードベースのエクスペリエンスでDecisioningを使用する方法を示すエンドツーエンドのチュートリアルをご覧ください。

>[!VIDEO](https://video.tv.adobe.com/v/3451100/?learn=on&enablevpops)