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
ht-degree: 98%

---

# ウィッシュリスト項目の更新の送信 {#wishist-uc}

>[!BEGINSHADEBOX]

この例では&#x200B;**ウィッシュリスト**&#x200B;スキーマを使用していますが、**購入**、**購読**&#x200B;など、**受信者**&#x200B;と一対多の関係を持つ任意のエンティティや、各受信者が複数の関連レコードを持つ場合がある任意のカスタムスキーマにも同じ方法が適用されます。

**このユースケースに必要なスキーマ：**

* **受信者**：ターゲティングディメンションとして使用されます
* **ウィッシュリスト項目**：フィールドには `creationDate`、`product`、`Wishlistid` が含まれます
* **製品**：フィールドには `description`、`priceref`、`imageurl` が含まれます
* **放棄された買い物かご**（任意）：フィールドには `lastmodified` が含まれます

➡️ [ リレーショナルスキーマの設定方法を学ぶ ](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-reengagement-11.png){zoomable="yes"}

このオーケストレーションキャンペーンは、ウィッシュリストに保存された製品を思い出させることで、訪問者を再度関与することに焦点を当てています。キャンペーンオーケストレーションを使用すると、ウィッシュリストのアクティビティに基づいて条件付きでオーディエンスを定義し、訪問者を再びコンバージョンに戻すことができます。

1. まず、ウィッシュリストの再エンゲージメントを目的とした新しいキャンペーンを作成します。これにより、項目を保存して、購入意図を示している顧客に対してメッセージに焦点を当てることができます。

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. **キャンペーン設定**&#x200B;を入力します。

1. **[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを追加して、ウィッシュリストの行動に基づいてターゲットにする顧客グループを特定します。

   ![](assets/uc-reengagement-2.png){zoomable="yes"}

1. このオーディエンスに説明的な&#x200B;**[!UICONTROL ラベル]**&#x200B;を設定し、**[!UICONTROL ターゲティングディメンション]**&#x200B;として&#x200B;**[!UICONTROL 受信者]**&#x200B;を選択します。次に、「**[!UICONTROL 続行]**」をクリックして、オーディエンスを設定します。

1. 「**[!UICONTROL 条件を追加]**」をクリックし、次の条件を作成してオーディエンスを絞り込みます。

   `WishlistItems Exist such as (creationDate greater than or equal to 36 months ago) AND (product is not empty`
または
   `AbandonedCarts Exist such as lastmodified greater than or equal to 36 months ago`

   このオーディエンスは、ウィッシュリストを持っている受信者、製品画像を含む項目が含まれている受信者、定義された期間内に放棄された買い物かごを持っている受信者に基づいています。

   ![](assets/uc-reengagement-3.png){zoomable="yes"}

1. 「**[!UICONTROL 計算]**」をクリックすると、これらの条件の影響を受けるプロファイルの数が表示され、「**[!UICONTROL 結果を表示]**」をクリックすると、各条件の詳細を調べて、オーディエンスがターゲットセグメントと一致しているかどうかを確認できます。

   ![](assets/uc-reengagement-4.png){zoomable="yes"}

1. 「**[!UICONTROL 確認]**」をクリックします。

1. **ウィッシュリスト**&#x200B;や&#x200B;**製品情報**&#x200B;を使用してキャンペーンをパーソナライズする&#x200B;**[!UICONTROL エンリッチメント]**&#x200B;アクティビティを追加します。

   ![](assets/uc-reengagement-5.png){zoomable="yes"}

1. 「**[!UICONTROL エンリッチメントデータを追加]**」をクリックします。

1. `Targeting dimension > Wishlistitems > Wishlistid` にアクセスします。

   ![](assets/uc-reengagement-6.png){zoomable="yes"}

1. データの収集方法を選択します。この場合は、「**[!UICONTROL データを収集]**」を選択して、オーディエンスのウィッシュリストの詳細を収集します。

1. 取得する行の数を選択します。デフォルトでは、ウィッシュリストごとに 3 つの項目が取得されますが、キャンペーンのニーズに応じて調整して、ハイライト表示する製品を増減できます。

1. 「**[!UICONTROL 属性を追加]**」をクリックして、次の 3 つの属性を作成します。

   * `Product > description`
   * `Product > priceref`
   * `Product > imageurl`

   これにより、コンバージョンを推進する詳細な製品情報を含むメッセージが強化されます。

   ![](assets/uc-reengagement-7.png){zoomable="yes"}

1. メールアクティビティを追加して、顧客ごとに個別にパーソナライズされた再エンゲージメントメッセージを作成します。「**[!UICONTROL コンテンツを編集]**」をクリックして、コンテンツのデザインを開始します。

   ➡️ [メールのパーソナライゼーションの詳細情報](../email/content-from-scratch.md)

   ![](assets/uc-reengagement-8.png){zoomable="yes"}

1. メールの最終処理が完了したら、オーケストレーションキャンペーンから「**[!UICONTROL 開始]**」をクリックして、キャンペーンを保存し、ドラフトモードで実行します。

1. ドラフトモードを開始したら、ウィッシュリストの詳細を含むオーディエンスをプレビューします。

   より深いインサイトを得るには、出力結果をクリックし、「**[!UICONTROL 結果をプレビュー]**」を選択します。

   ![](assets/uc-reengagement-10.png){zoomable="yes"}

キャンペーンの実行後はレポートを確認して、キャンペーンのパフォーマンスに関する堅牢なデータと KPI のセットを取得できます。

➡️ [レポートの詳細情報](../reports/campaign-global-report-cja.md)
