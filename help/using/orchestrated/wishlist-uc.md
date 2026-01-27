---
solution: Journey Optimizer
product: journey optimizer
title: ウィッシュリスト項目の更新の送信
description: ウィッシュリスト項目の更新の送信
feature: Use Cases
version: Campaign Orchestration
source-git-commit: e486aae3a6635d8eec0c398bfe03b6a63a007ef1
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 4%

---

# ウィッシュリスト項目の更新の送信 {#wishist-uc}

>[!BEGINSHADEBOX]

この例では **ウィッシュリスト** スキーマを使用しますが、同じ方法が、**購入**、**購読**、各受信者が複数の関連レコードを持つカスタムスキーマなど **受信者** に対して 1 対多の関係を持つエンティティに適用されます。

**このユースケースではスキーマが必要です：**

* **受信者**：ターゲティングディメンションとして使用されます
* **WishlistItems**：フィールド `creationDate`、`product`、`Wishlistid` を使用
* **Product**：フィールド `description`、`priceref`、`imageurl` を含む
* **放棄された買い物かご** （任意）：フィールド `lastmodified` を使用

➡️ [&#x200B; リレーショナルスキーマの設定方法を学ぶ &#x200B;](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-reengagement-11.png){zoomable="yes"}

この調整されたキャンペーンは、ウィッシュリストに保存された製品を訪問者に思い出させることで、訪問者のリエンゲージメントに焦点を当てています。 Campaign オーケストレーションを使用して、ウィッシュリストアクティビティに基づく条件でオーディエンスを定義し、訪問者がコンバージョンに戻れるようにします。

1. まず、ウィッシュリストの再エンゲージメントを特別に目的とした新しいキャンペーンを作成します。 これは、アイテムを保存することで、購入意図を示したお客様に対するメッセージの絞り込みに役立ちます。

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. **キャンペーン設定** を入力します。

1. **[!UICONTROL オーディエンスを作成]** アクティビティを追加して、ウィッシュリストの行動に基づいてターゲットにする顧客のグループを特定します。

   ![](assets/uc-reengagement-2.png){zoomable="yes"}

1. このオーディエンスの説明的な **[!UICONTROL ラベル]** を設定し、**[!UICONTROL ターゲティングディメンション]** として **[!UICONTROL 受信者]** を選択します。 次に、「**[!UICONTROL 続行]**」をクリックして、オーディエンスを設定します。

1. 「**[!UICONTROL 条件を追加]**」をクリックし、次の条件を作成してオーディエンスを絞り込みます。

   `WishlistItems Exist such as (creationDate greater than or equal to 36 months ago) AND (product is not empty`
または
   `AbandonedCarts Exist such as lastmodified greater than or equal to 36 months ago`

   このオーディエンスは、ウィッシュリストを持っている受信者、製品画像を含む項目を含んでいる受信者、定義された期間内に放棄された買い物かごを持っている受信者に基づいています。

   ![](assets/uc-reengagement-3.png){zoomable="yes"}

1. **[!UICONTROL 計算]** をクリックしてこれらの条件の影響を受けるプロファイルの数を確認し、**[!UICONTROL 結果を表示]** をクリックして、各条件の詳細を調べ、オーディエンスがターゲットセグメントに一致することを確認します。

   ![](assets/uc-reengagement-4.png){zoomable="yes"}

1. 「**[!UICONTROL 確認]**」をクリックします。

1. **[!UICONTROL エンリッチメント]** アクティビティを追加して、**ウィッシュリスト** および **製品情報** でキャンペーンをパーソナライズします。

   ![](assets/uc-reengagement-5.png){zoomable="yes"}

1. 「**[!UICONTROL エンリッチメントデータを追加]**」をクリックします。

1. `Targeting dimension > Wishlistitems > Wishlistid` にアクセスします。

   ![](assets/uc-reengagement-6.png){zoomable="yes"}

1. データの収集方法を選択します。この場合は「データの収集 **[!UICONTROL を選択して、オーディエンスのウィッシュリストの詳細を収集します]**。

1. 取得する行数を選択します。 デフォルトでは、ウィッシュリストごとに 3 つの項目が取得されますが、これは、キャンペーンで多くの製品をハイライトする必要があるかどうかに応じて調整できます。

1. **[!UICONTROL 属性を追加]** をクリックして、次の 3 つの属性を作成します。

   * `Product > description`
   * `Product > priceref`
   * `Product > imageurl`

   これにより、コンバージョンを促進する詳細な製品情報でメッセージが充実します。

   ![](assets/uc-reengagement-7.png){zoomable="yes"}

1. 電子メールアクティビティを追加して、顧客ごとに個別にパーソナライズされた再エンゲージメントメッセージを作成します。 「**[!UICONTROL コンテンツを編集]**」をクリックして、コンテンツのデザインを開始します。

   ➡️ [&#x200B; 詳しくは、メールのパーソナライゼーションを参照してください &#x200B;](../email/content-from-scratch.md)

   ![](assets/uc-reengagement-8.png){zoomable="yes"}

1. メールの最終処理が完了したら、調整したキャンペーンから「**[!UICONTROL 開始]** をクリックして、キャンペーンを保存し、ドラフトモードで実行します。

1. ドラフトモードを開始した後、ウィッシュリストの詳細を使用してオーディエンスをプレビューします。

   より深いインサイトを得るには、出力結果をクリックし、「**[!UICONTROL 結果をプレビュー]**」を選択します。

   ![](assets/uc-reengagement-10.png){zoomable="yes"}

キャンペーンの実行後、キャンペーンのパフォーマンスに関する堅牢なデータと KPI のセットが表示されるレポートを確認できます。

➡️[&#x200B; レポートの詳細情報 &#x200B;](../reports/campaign-global-report-cja.md)
