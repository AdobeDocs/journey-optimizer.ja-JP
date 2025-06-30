---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform データを意思決定に使用（Beta）
description: Adobe Experience Platform データを意思決定に使用する方法を説明します。
badge: label="ベータ版" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
exl-id: 46d868b3-01d2-49fa-852b-8c2e2f54292f
source-git-commit: 58f4fdf8ec3cdb609efebf5b8713f6b770ef5414
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 4%

---

# Adobe Experience Platform データを意思決定に使用 {#aep-data}

>[!CONTEXTUALHELP]
>id="ajo_exd_rules_dataset_lookup"
>title="データセットルックアップ"
>abstract="決定ルールでAdobe Experience Platform データを使用すると、動的な外部属性に基づいて実施要件条件を定義し、関連する場合にのみ決定項目が表示されるようにすることができます。 マッピングを作成し、Adobe Experience Platform データセットを [!DNL Journey Optimizer] のデータと結合する方法を定義します。 必要な属性を持つデータセットを選択し、決定項目属性とデータセットの両方に存在する結合キーを選択します。"

>[!CONTEXTUALHELP]
>id="ajo_exd_formula_dataset_lookup"
>title="データセットルックアップ"
>abstract="ランキング式は、決定項目の優先度を定義します。 データセット属性 [!DNL Adobe Experience Platform] 使用すると、実際の条件を反映するようにランキングロジックを動的に調整できます。 マッピングを作成し、Adobe Experience Platform データセットを [!DNL Journey Optimizer] のデータと結合する方法を定義します。 必要な属性を持つデータセットを選択し、決定項目属性とデータセットの両方に存在する結合キーを選択します"

>[!AVAILABILITY]
>
>この機能は現在、パブリックベータ版としてすべてのお客様にご使用いただけます。アクセスをご希望の場合は、アカウント担当者にお問い合わせください。

[!DNL Journey Optimizer] を使用すると、[!DNL Adobe Experience Platform] のデータを意思決定に活用できます。 これにより、決定属性の定義をデータセット内の追加データに拡張して、定期的に変更される一括更新を行うことができます。属性を 1 つずつ手動で更新する必要はありません。 例えば、可用性、待機時間など。

## ベータ版の制限事項とガイドライン {#guidelines}

開始する前に、次の制限事項とガイドラインに注意してください。

* 決定ポリシーは、すべての決定ルールとランキング式を組み合わせて、合計で最大 3 つのデータセットを参照できます。 例えば、ルールで 2 つのデータセットを使用する場合、式で使用できるデータセットは 1 つだけです。
* 決定ルールには、3 つのデータセットを使用できます。
* ランキング式には、3 つのデータセットを使用できます。
* 決定ポリシーが評価されると、システムは合計 1000 件までのデータセットクエリ（ルックアップ）を実行します。 決定項目で使用される各データセットマッピングは、1 つのクエリとしてカウントされます。 例：決定項目が 2 つのデータセットを使用する場合、そのオファーを評価すると、2 つのクエリとして 1000 クエリの制限にカウントされます。

## データ参照用データセットの有効化 {#enable}

[!DNL Adobe Experience Platform] データセットのデータを意思決定に使用するには、まず API 呼び出しを介したルックアップを有効にする必要があります。 手順について詳しくは、[Journey OptimizerでのAdobe Experience Platform データセットの活用 ](../data/lookup-aep-data.md) の節を参照してください。

## Adobe Experience Platform データの活用 {#leverage-aep-data}

データセットでルックアップを有効にしたら、その属性を使用して、外部データを使用して決定ロジックを強化できます。 これは、製品の可用性やリアルタイムの価格など、頻繁に変更される属性に特に便利です。

Adobe Experience Platform データセットの属性は、次の 2 つの決定ロジックの部分で使用できます。

* **決定ルール**：決定項目が表示可能かどうかを定義します。
* **ランキング式**：外部データに基づいて決定項目の優先順位を付けます。

次の節では、両方のコンテキストでAdobe Experience Platform データを使用する方法について説明します。

### 決定ルール {#rules}

決定ルールでAdobe Experience Platform データを使用すると、動的な外部属性に基づいて実施要件条件を定義し、関連する場合にのみ決定項目が表示されるようにすることができます。

例えば、オンラインのretailerが、ローカルストアの在庫に基づいて商品レコメンデーションを宣伝するとします。 商品は、最寄りの場所で在庫がある場合にのみ、レコメンデーションの対象となります。 毎日のインベントリ更新を含むデータセットがAdobe Experience Platformにアップロードされます。 ルールロジックは、顧客の優先ストアについて、特定の製品の `inventory_count` が 0 より大きいかどうかを確認します。 その場合は、決定項目が適格となります。

Adobe Experience Platform データを決定ルールに使用するには、次の手順に従います。

1. **[!UICONTROL 戦略設定]**/**[!UICONTROL 決定ルール]** メニューに移動し、「**[!UICONTROL データセットを使用してルールを作成]**」を選択します。

   ![](assets/exd-lookup-rule.png)

1. 「**[!UICONTROL マッピングを作成]**」をクリックして、Adobe Experience Platform データセットと [!DNL Journey Optimizer] のデータの結合方法を定義します。

   * 必要な属性を持つデータセットを選択します。
   * 決定項目属性とデータセットの両方に存在する結合キー（製品 ID、ストア ID など）を選択します。

   ![](assets/exd-lookup-mapping.png)

   >[!NOTE]
   >
   >1 つのルールにつき最大 3 つのマッピングを作成できます。

1. **[!UICONTROL 続行]** をクリックします。 これで、**[!UICONTROL データセットルックアップ]** メニューのデータセット属性にアクセスして、ルール条件で使用できるようになりました。 [決定ルールの作成方法を学ぶ](../experience-decisioning/rules.md#create)

   ![](assets/exd-lookup-menu.png)

### ランキング式 {#ranking-formulas}

ランキング式は、決定項目の優先度を定義します。 データセット属性 [!DNL Adobe Experience Platform] 使用すると、実際の条件を反映するようにランキングロジックを動的に調整できます。

例えば、航空会社がランキング式を使用してアップグレードオファーの優先順位を付けるとします。 顧客のロイヤルティ層が高く、現在の空席数が少ない場合（時間単位で更新されたデータセットに基づく）、その顧客には高い優先度が与えられます。 データセットには、`flight_number`、`available_seats`、`loyalty_score` などのフィールドが含まれます。

Adobe Experience Platform データをランキング式に使用するには、次の手順に従います。

1. ランキング式を作成または編集します。 「**[!UICONTROL データセットルックアップ]**」セクションで、「**[!UICONTROL マッピングを作成]**」をクリックします。

1. データセットマッピングを定義します。

   * 適切なデータセット（フライトでの空席など）を選択します。
   * 決定項目属性とデータセットの両方に存在する結合キー（便名や顧客 ID など）を選択します。

   ![](assets/exd-lookup-formula-mapping.png)

   >[!NOTE]
   >
   >ランキング式ごとに最大 3 つのマッピングを作成できます。

1. データセットフィールドを使用して、通常どおりランキング式を作成します。 [ ランキング式の作成方法を学ぶ ](ranking/ranking-formulas.md#create-ranking-formula)

   ![](assets/exd-lookup-formula-criteria.png)
