---
solution: Journey Optimizer
product: journey optimizer
title: ブラウジングアクティビティで顧客を引き付ける
description: ブラウジングアクティビティで顧客を引き付ける
version: Campaign Orchestration
source-git-commit: 51c8c9282cb6eb9cdbd310d8f263d7973f28bbf0
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 2%

---

# ブラウジングアクティビティで顧客を引き付ける {#engage-customers-uc}

>[!BEGINSHADEBOX]

このユースケースは、Experience Platformに既に存在するオーディエンス、特に、発生したブラウジングアクティビティを収集するリアルタイムの web 行動オーディエンスから始まります。 [&#x200B; 詳しくは、Adobe Experience Platformを参照してください &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/intro/rtcdp-intro/get-started#audiences)

**このユースケースではスキーマが必要です：**

* **受信者**：ターゲティングディメンションとして使用され、フィールド `email`、`churnprop` を持つ
* **ウィッシュリスト**：フィールド `description`、`priceref`、`imageurl` を使用

➡️ [&#x200B; モデルベースのスキーマを設定する方法を学ぶ &#x200B;](gs-schemas.md)

>[!ENDSHADEBOX]

![](assets/uc-interest-14.png){zoomable="yes"}

このキャンペーンは、運動器具カテゴリを参照した顧客をターゲットにします。 オーディエンスは重複排除され、チャーンリスク（エンゲージメントや購入を停止する可能性の高さ）によってセグメント化されます。

高リスクの顧客は、別の新しいオーディエンスに収集され、後で特定のコミュニケーションに使用されます。一方、低リスクおよび中程度のリスクの顧客は、パーソナライズされたメールとフォローアップで複数のステップから成るジャーニーを進めます。

1. まず、**ウィッシュリストの再エンゲージメント** を目的とした新しいキャンペーンを設定します。 これにより、製品をウィッシュリストに保存することで、既に購入意図を示している顧客に焦点を当てたメッセージが届きます。

   ![](assets/uc-reengagement-1.png){zoomable="yes"}

1. キャンペーン名、説明、開始日と終了日 **[!UICONTROL 関連するタグなど、「]** キャンペーン設定」を入力します。

1. **[!UICONTROL オーディエンスを読み取り]** アクティビティを追加して、Adobe Experience Platform（ここでは、web サイトで演習機器カテゴリを参照したお客様）から事前定義済みのオーディエンスを選択します。

   受信者は、「**[!UICONTROL エンティティ]** フィールドから選択したメールアドレスで識別されます。

   ![](assets/uc-interest-1.png){zoomable="yes"}

1. **[!UICONTROL 重複排除]** アクティビティを追加して、オーディエンスから重複したメールアドレスを削除し、各顧客が 1 つのメッセージのみを受け取るようにします。

1. **[!UICONTROL 属性を追加]** をクリックし、重複排除の属性として「メール」を選択します。

   ![](assets/uc-interest-2.png){zoomable="yes"}

1. 次に、**[!UICONTROL 分割]** アクティビティを追加して、チャーンの可能性に基づいて顧客をセグメント化し、顧客グループごとにカスタマイズされたパーソナライズされたエクスペリエンスを提供できるようにします。

   ![](assets/uc-interest-3.png){zoomable="yes"}

1. 「**[!UICONTROL セグメントを追加]**」をクリックして、次の 3 つのグループを作成します。

   * 低リスク

   * Mediumの危険

   * 高リスク

   ![](assets/uc-interest-5.png){zoomable="yes"}

1. 「**[!UICONTROL フィルターを作成]**」をクリックして、各グループのチャーンの可能性を定義します。

   **条件エディター** を使用して、各顧客のチャーンリスクを決定する特定の値を設定します。

   ![](assets/uc-interest-6.png){zoomable="yes"}

1. 各セグメントの処理は次のように異なります。

   * [低/中程度のリスク](#low-medium-risk)
   * [高リスク](#high-risk)

1. キャンペーンのテストが完了し、準備が整ったら、「**[!UICONTROL 公開]**」をクリックしてキャンペーンを公開します。

キャンペーンの実行後、レポートダッシュボードでパフォーマンス指標と主要インサイトを確認できます。

➡️[&#x200B; レポートの詳細情報 &#x200B;](../reports/campaign-global-report-cja.md)

## 高リスクセグメント {#high-risk}

チャーンのリスクが高いと識別された顧客に対して、専用のオーディエンスセグメントを作成します。 このオーディエンスは、後で個別のターゲット設定された通信に使用されます。

1. **[!UICONTROL オーディエンスを保存]** を追加します。

   ![](assets/uc-interest-7.png){zoomable="yes"}

1. オーディエンスに **[!UICONTROL ラベル]** を追加し、**[!UICONTROL プロファイルマッピングフィールド]**、ここでは **recipients-email** を選択します。

   ![](assets/uc-interest-8.png){zoomable="yes"}

このオーディエンスはExperience Cloudに保存され、後で特定のターゲットキャンペーンに使用できます。

## 低/中リスクセグメント {#low-medium-risk}

チャーンのリスクが低い顧客と中程度の顧客は、エンゲージメントを強化することを目的として、複数の手順から成るキャンペーンを設定します。

1. 低リスクとMediumリスクの両方を **[!UICONTROL 結合]** アクティビティと組み合わせます。

   ![](assets/uc-interest-9.png){zoomable="yes"}

1. **[!UICONTROL エンリッチメント]** アクティビティを追加して、ウィッシュリストと製品情報でキャンペーンをパーソナライズします。

1. **[!UICONTROL 属性を追加]** をクリックして、次の 3 つの属性を作成します。

   * `Wishlist > description`
   * `Wishlist > priceref`
   * `Wishlist > imageurl`

   これにより、詳細なウィッシュリスト情報でメッセージが強化されます。

   ![](assets/uc-interest-10.png){zoomable="yes"}

1. メールとのエンゲージメントに基づいて、リターゲティングの新しいオーディエンスを作成します。

   ここでは、メールのクリックイベントに基づいてオーディエンスを作成します。これにより、以前に送信されたメールを操作したすべての人物、より具体的には、そのメッセージ内のリンクをクリックしたすべての人物をリターゲティングします。

   ![](assets/uc-interest-11.png){zoomable="yes"}

1. エンゲージメントを均等に分割し、SMS またはプッシュ通知を通じてフォローアップを送信し、コンバージョンを促します。

   ![](assets/uc-interest-12.png){zoomable="yes"}

1. 受信者の名前などのプロファイル属性や、ウィッシュリスト項目などのエンリッチメントデータを含むメッセージコンテンツを各チャネル用に作成して、各メッセージをパーソナライズします。

   ![](assets/uc-interest-13.png){zoomable="yes"}
