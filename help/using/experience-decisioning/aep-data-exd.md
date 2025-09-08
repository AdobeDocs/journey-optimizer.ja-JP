---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform データを決定に使用
description: 決定の Adobe Experience Platform データの使用方法について説明します。
badge: label="限定提供" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
exl-id: 46d868b3-01d2-49fa-852b-8c2e2f54292f
source-git-commit: 58389860e5e0b07f32dd62b95a508e80579aaa73
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 36%

---

# Adobe Experience Platform データを決定に使用 {#aep-data}

>[!CONTEXTUALHELP]
>id="ajo_exd_catalogs_dataset"
>title="データセット参照"
>abstract=In order to use attributes from Adobe Experience Platform for decisioning, you need to create a mapping to define how the Adobe Experience Platform dataset joins with data in [!DNL Journey Optimizer].”

>[!CONTEXTUALHELP]
>id="ajo_exd_catalogs_dataset_create"
>title="データセット参照"
>abstract="参照に対して有効になっているすべてのAdobe Experience Platform データセットの中から、必要な属性を持つデータセットを選択し、決定項目属性とデータセットの両方に存在するマッピングキー（便名、顧客 ID など）を選択します。"

>[!CONTEXTUALHELP]
>id="ajo_exd_rules_dataset_lookup"
>title="データセットルックアップ"
>abstract="必要な属性を持つAdobe Experience Platform データセットを選択します。 データセットがリストに表示されない場合は、検索に対してデータセットが有効になっていて、データセットの検索マッピングが作成されていることを確認します。"

>[!CONTEXTUALHELP]
>id="ajo_exd_formula_dataset_lookup"
>title="データセットルックアップ"
>abstract="データセット属性 [!DNL Adobe Experience Platform] 使用して、実際の条件を反映するようにランキングロジックを動的に調整します。 「**[!UICONTROL データセットを追加]**」をクリックして、必要な属性を持つAdobe Experience Platform データセットを選択します。 データセットがリストに表示されない場合は、検索に対してデータセットが有効になっていて、データセットの検索マッピングが作成されていることを確認します。"

>[!CONTEXTUALHELP]
>id="ajo_exd_item_capping_dataset"
>title="データセットを追加」"
>abstract="データセット属性 [!DNL Adobe Experience Platform] 使用して、動的な外部属性に基づいてキャッピング条件を定義します。 「**[!UICONTROL データセットを追加]**」をクリックして、必要な属性を持つAdobe Experience Platform データセットを選択します。 データセットがリストに表示されない場合は、検索に対してデータセットが有効になっていて、データセットルックアップマッピングが作成されていることを確認します。」"

>[!AVAILABILITY]
>
>この機能は、現在、限定提供リリースとしてすべてのお客様が利用できます。

[!DNL Journey Optimizer] を使用すると、決定に [!DNL Adobe Experience Platform] のデータを活用できます。これにより、決定属性の定義をデータセットの追加データに拡張し、属性を 1 つずつ手動で更新する必要がなく、定期的に変更される一括更新を行うことができます。例えば、可用性、待機時間などです。

>[!IMPORTANT]
>
>[!DNL Journey Optimizer] 単一の決定ポリシーに対して最大 1,000 個の検索をサポートします。

## 前提条件

### 参照用にデータセットを有効にする

開始する前に、決定に必要なデータセットを最初に参照に対して有効にする必要があります。 [Adobe Experience Platform データを使用 ](../data/lookup-aep-data.md) の節で説明している手順に従います。

### マッピングの作成

Adobe Experience Platformの属性を意思決定に使用するには、マッピングを作成して、Adobe Experience Platform データセットが [!DNL Journey Optimizer] のデータにどのように結合するかを定義する必要があります。 それには、次の手順に従います。

1. **[!UICONTROL カタログ]**/**[!UICONTROL データセット参照]** 移動し、「**[!UICONTROL 作成]**」をクリックします。

   ![](assets/exd-lookup-mapping.png)

1. マッピングを設定します。

   1. **[!UICONTROL データセットを選択]** をクリックして、参照が有効になっているすべてのAdobe Experience Platform データセットを表示します。 必要な属性を持つデータセットを選択します。

   1. 「**[!UICONTROL キーを選択]**」をクリックして、決定項目属性とデータセットの両方に存在する結合キー（便名や顧客 ID など）を選択します。

   ![](assets/exd-lookup-mapping-create.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## Adobe Experience Platform データの活用 {#leverage-aep-data}

データセットがルックアップに対して有効になり、マッピングが作成されたら、そのデータを使用して、外部データで決定ロジックを強化できます。 これは、製品の在庫状況やリアルタイムの価格設定など、頻繁に変更される属性の場合に特に役立ちます。

Adobe Experience Platform データセットの属性は、次の 2 つの決定ロジックの部分で使用できます。

* **決定ルール**：決定項目が表示可能かどうかを定義します。
* **ランキング式**：外部データに基づいて決定項目に優先順位を付けます。
* **キャッピングルール**：外部データを使用して、キャッピングルールのスレホールドを計算します。

次の節では、これらのコンテキストでAdobe Experience Platform データを使用する方法について説明します。

### 決定ルール {#rules}

決定ルールで Adobe Experience Platform データを使用すると、動的な外部属性に基づいて実施要件の条件を定義し、関連する場合にのみ決定項目を表示できます。

例えば、オンライン小売業者がローカルストアの在庫に基づいて製品のレコメンデーションを宣伝するとします。製品は、最寄りの場所に在庫がある場合にのみレコメンデーションの対象となります。毎日の在庫更新を含むデータセットが Adobe Experience Platform にアップロードされます。ルールロジックは、顧客の優先ストアでの特定の製品の `inventory_count` が 0 より大きいかどうかを確認します。その場合は、決定項目の実施要件が満たされます。

Adobe Experience Platform データを決定ルールに使用するには、次の手順に従います。

1. **[!UICONTROL 戦略設定]**／**[!UICONTROL 決定ルール]**&#x200B;メニューに移動し、「**[!UICONTROL データセットを使用してルールを作成]**」を選択します。

   ![](assets/exd-lookup-rule.png)

1. 「**[!UICONTROL データセットを追加]**」をクリックして、必要な属性を持つデータセットを選択します。

   ![](assets/exd-lookup-select-dataset.png)

1. 「**[!UICONTROL 続行]**」をクリックします。これで、**[!UICONTROL データセット参照]**&#x200B;メニューでデータセット属性にアクセスし、ルール条件で使用できるようにになりました。[詳しくは、決定ルールの作成方法を参照してください。](../experience-decisioning/rules.md#create)

   ![](assets/exd-lookup-menu.png)

### ランキング式 {#ranking-formulas}

ランキング式は、決定項目の優先度を定義します。[!DNL Adobe Experience Platform] データセット属性を使用すると、実際の条件を反映するようにランキングロジックを動的に調整できます。

例えば、航空会社がアップグレードオファーの優先順位付けにランキング式を使用しているとします。 顧客のロイヤルティ層が高く、現在の座席の空き状況が少ない場合（時間単位で更新されるデータセットに基づく）、その顧客にはより高い優先度が与えられます。データセットには、`flight_number`、`available_seats`、`loyalty_score` などのフィールドが含まれます。

Adobe Experience Platform データをランキング式に使用するには、次の手順に従います。

1. ランキング式を作成または編集します。

1. 「**[!UICONTROL データセットルックアップ]**」セクションで、「**[!UICONTROL データセットを追加]**」をクリックします。

1. 適切なデータセットを選択します。

   ![](assets/exd-lookup-formula-dataset.png)

   >[!NOTE]
   >
   >探しているデータセットがリストに表示されない場合は、そのデータセットで検索を有効にしており、データセットの検索マッピングを作成していることを確認します。 詳しくは、[ 前提条件 ](#prerequisites) の節を参照してください。

1. データセットフィールドを使用して、通常どおりランキング式を作成します。[ランキング式の作成方法の詳細情報](ranking/ranking-formulas.md#create-ranking-formula)

   ![](assets/exd-lookup-formula-criteria.png)

### キャッピングルール {#capping-rules}

キャッピングルールは、決定項目を提示できる最大回数を定義する制約として使用されます。 キャッピングルールでAdobe Experience Platform データを使用すると、動的な外部属性に基づいてキャッピング条件を定義できます。 これを行うには、キャッピングルールで式を使用して、目的のキャッピングしきい値を計算します。

例えば、retailerでは、リアルタイムの商品インベントリに基づいてオファーの上限を設定することができます。 固定しきい値を 500 に設定する代わりに、Adobe Experience Platform データセットから `inventory_count` フィールドを参照する式を使用します。 データセットで 275 個の項目が在庫として示されている場合、オファーはその数まで配信されます。

>[!NOTE]
>
>キャッピングルール **式** は現在、すべてのユーザーが限定提供（LA）機能として使用でき、**[!UICONTROL 合計]** キャッピングタイプでのみサポートされています。

Adobe Experience Platform データをキャッピングルール式に使用するには、次の手順に従います。

1. 決定項目を作成または編集します。

1. 項目の実施要件を定義する際に、「**[!UICONTROL データセットを追加]**」をクリックし、適切なデータセットを選択します。

   ![](assets/exd-lookup-capping.png)

   >[!NOTE]
   >
   >探しているデータセットがリストに表示されない場合は、そのデータセットで検索を有効にしており、データセットの検索マッピングを作成していることを確認します。 詳しくは、[ 前提条件 ](#prerequisites) の節を参照してください。

1. キャッピングタイプ **[!UICONTROL 合計]** を選択し、「**[!UICONTROL 式]**」オプションを有効にします。

   ![](assets/exd-lookup-capping-expression.png)

   >[!NOTE]
   >
   >探しているデータセットがリストに表示されない場合は、そのデータセットで検索を有効にしており、データセットの検索マッピングを作成していることを確認します。 詳しくは、[ 前提条件 ](#prerequisites) の節を参照してください。

1. 式を編集し、データセットフィールドを使用して式を作成します。

   ![](assets/exd-lookup-capping-attribute.png)

1. キャッピングとルールの決定項目の設定を通常どおり完了します。 [ キャッピングルールの設定方法を学ぶ ](../experience-decisioning/items.md#capping)
