---
solution: Journey Optimizer
product: journey optimizer
title: オーケストレーションされたキャンペーンへのパーソナライゼーションの追加
description: プロファイル属性、ワークテーブルのターゲット属性、エンリッチメント収集配列を使用して、オーケストレーションされたキャンペーンメッセージをパーソナライズする方法を説明します。
exl-id: c4a91e2b-6f08-4d1a-9e3b-2f8f5a0d1c62
version: Campaign Orchestration
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: e0a12bd7971c778378f9905cf93653792f38509d
workflow-type: tm+mt
source-wordcount: 477
ht-degree: 0%

---

# オーケストレーションされたキャンペーンへのパーソナライゼーションの追加 {#add-personalization}

キャンバス上で[&#x200B; アクティビティ &#x200B;](orchestrate-activities.md)を調整し、チャネルアクティビティを追加した後、メール、SMS、またはその他のチャネルエディターでメッセージコンテンツをパーソナライズします。

オーケストレーションキャンペーンのPersonalizationは、他の[!DNL Journey Optimizer] キャンペーンまたはジャーニーと同様に機能しますが、**ワークテーブル**&#x200B;に関連する違いがあります。プロファイルストアのデータだけでなく、キャンバス上のターゲティングおよびエンリッチメントアクティビティによって計算される属性です。

## パーソナライゼーションエディターへのアクセス {#access}

1. オーケストレーションされたキャンペーンを開き、チャネルアクティビティを追加します。 [&#x200B; チャネルアクティビティを追加する方法を学ぶ](activities/channels.md#add)

1. チャネルアクティビティを設定し、「**[!UICONTROL コンテンツ]**」タブを開いてメッセージを編集します。

1. メッセージエディターで、パーソナライゼーションエディターを使用してコンテンツに属性を挿入します。

チャネルアクティビティからパーソナライズされたコンテンツをプレビューおよびテストするには、[&#x200B; コンテンツの確認とテスト &#x200B;](activities/channels.md#simulate-content-test-profiles)を参照してください。

## プロファイル属性とターゲット属性 {#attributes}

パーソナライゼーションエディターを開くと、パーソナライゼーションに使用できる属性が2つのメインフォルダーに含まれます。

* **[!UICONTROL プロファイル属性]**

  [!DNL Adobe Experience Platform]のプロファイル関連データ：名前、電子メールアドレス、場所、ユーザープロファイルに取り込まれたその他の特性。

* **[!UICONTROL ターゲット属性]** （オーケストレーションされたキャンペーンのみ）

  ワークテーブルからキャンペーンキャンバスで計算された属性。 このフォルダーには、次の2つのサブフォルダーがあります。

   * **`<Targeting dimension>`** （例：受信者または購入者） – キャンペーンでターゲットにするディメンションに関連する属性。

   * **`Enrichment`** — **[!UICONTROL エンリッチメント]** アクティビティを通じて追加されたデータ （リレーショナルリンク、収集された行、集計）。 1:N **[!UICONTROL データ収集]**&#x200B;のエンリッチメントを実行すると、番号付き行とコレクション配列の両方が取得されます。 [&#x200B; エンリッチメント収集データの使用方法を説明](#enrichment-collections)

[!DNL Journey Optimizer]全体のパーソナライゼーションエディターの詳細な概要については、[&#x200B; パーソナライゼーションの基本を学ぶ](../personalization/personalize.md)を参照してください。

## エンリッチメント収集データの操作 {#enrichment-collections}

1:N リンクと&#x200B;**[!UICONTROL データを収集]**&#x200B;で&#x200B;**[!UICONTROL エンリッチメント]** アクティビティを設定すると、エンリッチメント属性は&#x200B;**[!UICONTROL ターゲット属性] > [!UICONTROL &#x200B; エンリッチメント]**&#x200B;の2つの形式で利用できます。

* **行の統合** – 取得した行ごとに1つのフィールド （例：**購入1**、**購入2**、**購入3**）で、各フィールドにはリンクで選択した属性（価格や商品など）が含まれます。 個別の固定スロット（例：`target.enrichment.purchase1.price`）が必要な場合は、これらのスロットを使用します。

* **コレクション配列** – 収集されたすべての行の1つの配列。リンクラベルから名前が付けられます（例：**purchases**）。 この機能は、[配列関数](#array-functions)を使用してレコードの完全なセットに取り組む必要がある場合に使用します。

![](assets/enrichment-target-attributes-picker.png)

コレクション配列からフラット化された行を識別するには、式エディターに属性を挿入し、生成されるパスを読み取ります。 コレクション配列は、パスが&#x200B;**plural** （例：`purchases`）で、**行番号** （`purchase1`、`purchase2`など）のないエントリです。

| 必要なもの | 式エディターのパス |
| --- | --- |
| **1件の収集された行** | **番号付き** – 例：`target.enrichment.purchase1.price` |
| **完全なコレクション** | **複数形および番号なし** – 例：`target.enrichment.purchases.price` |

`target.enrichment.<label>`を参照して、[!DNL Journey Optimizer]の別の場所で使用されている同じ[配列およびリスト関数](../personalization/functions/arrays-list.md)をエンリッチメントコレクションに適用できます。

たとえば、件名には、収集した購入数と最初の商品の価格を表示することができます。

```sql
Hello number of Items: {%= count(target.enrichment.purchases.price) %} , Name of first item: {%= head(target.enrichment.purchases.product) %}
```

➡️ [&#x200B; キャンバスでコレクションのエンリッチメントを設定する方法を学ぶ](activities/enrichment.md#collection-personalization)
