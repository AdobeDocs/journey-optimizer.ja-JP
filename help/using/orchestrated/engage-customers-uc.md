---
solution: Journey Optimizer
product: journey optimizer
title: 参照アクティビティによる顧客との関与
description: 参照アクティビティによる顧客との関与
feature: Use Cases
version: Campaign Orchestration
source-git-commit: e486aae3a6635d8eec0c398bfe03b6a63a007ef1
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 98%

---

# 参照アクティビティによる顧客との関与 {#engage-customers-uc}

>[!BEGINSHADEBOX]

このユースケースは、Experience Platform に既に存在するオーディエンス、特に、発生した参照アクティビティを収集するリアルタイムの web 行動オーディエンスから始まります。[Adobe Experience Platform の詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/intro/rtcdp-intro/get-started#audiences)

**このユースケースに必要なスキーマ：**

* **受信者**：ターゲティングディメンションとして使用され、フィールドには `email`、`churnprop` が含まれます
* **ウィッシュリスト**：フィールドには `description`、`priceref`、`imageurl` が含まれます

➡️ [ リレーショナルスキーマの設定方法を学ぶ ](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-interest-14.png){zoomable="yes"}

このキャンペーンは、運動器具カテゴリを参照した顧客をターゲットにしています。オーディエンスは重複排除され、チャーンリスク（エンゲージメントや購入を停止する可能性）ごとにセグメント化されます。

高リスクの顧客は、後で特定の通信に使用される別の新しいオーディエンスに収集され、一方、低リスクと中リスクの顧客は、パーソナライズされたメールとフォローアップによるマルチステップのジャーニーを進めます。

1. まず、**ウィッシュリストの再エンゲージメント**&#x200B;を目的とした新しいキャンペーンを設定します。これにより、製品をウィッシュリストに保存して、既に購入意図を示している顧客に焦点を当てたメッセージが届きます。

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. キャンペーン名、説明、開始日と終了日、関連するタグなど、**[!UICONTROL キャンペーン設定]**&#x200B;を入力します。

1. **[!UICONTROL オーディエンスを読み取り]**&#x200B;アクティビティを追加して、Adobe Experience Platform から事前定義済みのオーディエンス（ここでは、web サイトで運動器具カテゴリを参照した顧客）を選択します。

   受信者は、「**[!UICONTROL エンティティ]**」フィールドから選択されたメールアドレスで特定されます。

   ![](assets/uc-interest-1.png){zoomable="yes"}

1. **[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティを追加して、重複するメールアドレスをオーディエンスから削除し、各顧客がメッセージ 1 件のみを受信するようにします。

1. 「**[!UICONTROL 属性を追加]**」をクリックし、重複排除の属性としてメールを選択します。

   ![](assets/uc-interest-2.png){zoomable="yes"}

1. 次に、**[!UICONTROL 分割]**&#x200B;アクティビティを追加して、顧客をチャーンの可能性別にセグメント化し、各顧客グループに合わせてカスタマイズされたエクスペリエンスを提供できるようにします。

   ![](assets/uc-interest-3.png){zoomable="yes"}

1. 「**[!UICONTROL セグメントを追加]**」をクリックして、次の 3 つのグループを作成します。

   * 低リスク

   * 中リスク

   * 高リスク

   ![](assets/uc-interest-5.png){zoomable="yes"}

1. 「**[!UICONTROL フィルターを作成]**」をクリックして、各グループのチャーンの可能性を定義します。

   **条件エディター**&#x200B;を使用して、各顧客のチャーンリスクを決定する特定の値を設定します。

   ![](assets/uc-interest-6.png){zoomable="yes"}

1. 各セグメントの処理は次のように異なります。

   * [低／中リスク](#low-medium-risk)
   * [高リスク](#high-risk)

1. キャンペーンのテストが完了し、準備が整ったら、「**[!UICONTROL 公開]**」をクリックしてキャンペーンを公開します。

キャンペーンの実行後、レポートダッシュボードを参照して、パフォーマンス指標と主要なインサイトを確認します。

➡️ [レポートの詳細情報](../reports/campaign-global-report-cja.md)

## 高リスクセグメント {#high-risk}

チャーンリスクが高いと特定された顧客に対しては、専用のオーディエンスセグメントを作成します。このオーディエンスは、後で個別のターゲット通信に使用されます。

1. **[!UICONTROL オーディエンスを保存]**&#x200B;を追加します。

   ![](assets/uc-interest-7.png){zoomable="yes"}

1. オーディエンスに&#x200B;**[!UICONTROL ラベル]**&#x200B;を追加し、**[!UICONTROL プロファイルマッピングフィールド]**（ここでは、**受信者のメール**）を選択します。

   ![](assets/uc-interest-8.png){zoomable="yes"}

このオーディエンスは Experience Cloud に保存され、後で特定のターゲットキャンペーンに使用できます。

## 低／中リスクセグメント {#low-medium-risk}

チャーンリスクが低／中の顧客に対しては、エンゲージメント強化を目的としたマルチステップのキャンペーンを設定します。

1. 低リスクと中リスクの両方を&#x200B;**[!UICONTROL 和集合]**&#x200B;アクティビティと組み合わせます。

   ![](assets/uc-interest-9.png){zoomable="yes"}

1. ウィッシュリストや製品情報を使用してキャンペーンをパーソナライズするための&#x200B;**[!UICONTROL エンリッチメント]**&#x200B;アクティビティを追加します。

1. 「**[!UICONTROL 属性を追加]**」をクリックして、次の 3 つの属性を作成します。

   * `Wishlist > description`
   * `Wishlist > priceref`
   * `Wishlist > imageurl`

   これにより、詳細なウィッシュリスト情報を含むメッセージが強化されます。

   ![](assets/uc-interest-10.png){zoomable="yes"}

1. メールとのエンゲージメントに基づいて、リターゲティングの新しいオーディエンスを作成します。

   ここでは、メールのクリックイベントに基づいてオーディエンスを作成し、以前送信されたメールにを操作した、より具体的には、そのメッセージ内のリンクをクリックしたすべての人物をリターゲティングします。

   ![](assets/uc-interest-11.png){zoomable="yes"}

1. エンゲージメントを均等に分割して、SMS またはプッシュ通知を通じてフォローアップを送信し、コンバージョンを促進します。

   ![](assets/uc-interest-12.png){zoomable="yes"}

1. 受信者の名前などのプロファイル属性や、ウィッシュリスト項目などのエンリッチメントデータを含むメッセージコンテンツを各チャネル用に作成して、各メッセージをパーソナライズします。

   ![](assets/uc-interest-13.png){zoomable="yes"}
