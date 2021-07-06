---
title: 決定の作成
description: 決定の作成方法を説明します
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: a25264cb43f77671c29f18522110fd85d0155697
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 87%

---

# 決定の作成 {#create-offer-activities}

決定（旧称：オファーアクティビティ）は、オファーのコンテナです。配信のターゲットに応じて、提供する最適なオファーを選ぶために Offer Decisioning エンジンを使用します。

![](../../assets/do-not-localize/how-to-video.png) [この機能をビデオで見る](#video)

決定のリストは、**[!UICONTROL オファー]**&#x200B;メニュー／「**[!UICONTROL 決定]**」タブでアクセスできます。フィルターは、ステータスや開始日、終了日に応じて決定を取得するのに役立ちます。

![](../../assets/activities-list.png)

決定を作成する前に、以下のコンポーネントがオファーライブラリに作成されていることを確認してください。

* [プレースメント](../offer-library/creating-placements.md)
* [コレクション](../offer-library/creating-collections.md)
* [パーソナライズされたオファー](../offer-library/creating-personalized-offers.md)
* [フォールバックオファー](../offer-library/creating-fallback-offers.md)

## 決定の作成 {#create-activity}

1. 決定リストにアクセスし、「**[!UICONTROL アクティビティを作成]**」をクリックします。

1. 決定の名前、開始日時、終了日時を指定して、「**[!UICONTROL 次へ]**」をクリックします。

   ![](../../assets/activities-name.png)

## 判定範囲の追加 {#add-decision-scopes}

1. リストからプレースメントをドラッグ＆ドロップして決定に追加し、「 **[!UICONTROL コレクションを追加]**」をクリックします。

   ![](../../assets/activities-placement.png)

   >[!NOTE]
   >
   >同じ配置を、判定で複数回選択できます。

1. 考慮するオファーを含んだコレクションを選択し、「**[!UICONTROL 追加]**」をクリックします。

   ![](../../assets/activities-collection.png)

1. 選択したオファーがプレースメントに追加されます。この例では、コールセンターソリューションにオファーを提示することを目的とした JSON タイプのプレースメントに表示される 2 つのオファーを選択しました。

   ![](../../assets/offers-added.png)

1. このプレースメントに対して、実施要件を満たすオファーが複数ある場合、デフォルトでは、優先度スコアが最も高いオファーが顧客に配信されます。

   実施要件を満たす配信対象オファーを特定の数式を使用して選択する場合は、**[!UICONTROL Rank offers by]** ドロップダウンリストからランキング式を選択します。詳しくは、[この節](../offer-activities/configure-offer-selection.md)を参照してください。

1. 「**[!UICONTROL 制約]**」フィールドにより、このプレースメントのオファーの選択が制限されます。この制約は、決定ルールまたは 1 つ以上の Adobe Experience Platform セグメントを使用して適用できます。

   オファーの選択を Adobe Experience Platform セグメントのメンバーに限定するには、「**[!UICONTROL セグメント]**」を選択し、「**[!UICONTROL セグメントを追加]**」をクリックします。

   ![](../../assets/activity_constraint_segment.png)

   左側のペインから 1 つまたは複数のセグメントを追加し、**[!UICONTROL かつ]**／**[!UICONTROL または]**&#x200B;論理演算子を使用してそれらを結合したあと、「**[!UICONTROL 選択]**」をクリックして確認します。

   セグメントの評価方法について詳しくは、[Segmentation Service　ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=ja)を参照してください。

   ![](../../assets/activity_constraint_segment2.png)

   決定ルールを使用してこのプレースメントに選択制約を追加する場合は、「**[!UICONTROL 決定ルール]**」オプションを選択し、目的のルールを左ペインから「**[!UICONTROL 決定ルール]**」領域にドラッグします。決定ルールの作成方法について詳しくは、[この節](../offer-library/creating-decision-rules.md)を参照してください。

   ![](../../assets/activity_constraint_rule.png)

## フォールバックオファーの追加 {#add-fallback}

オファーの実施要件ルールと制約に一致しない顧客に最後の手段として提示するフォールバックオファーを選択し、「**[!UICONTROL 次へ]**」をクリックします。

![](../../assets/add-fallback-offer.png)

## 決定のレビューと保存 {#review}

すべてが適切に設定され、決定が顧客にオファーを提供できる状態になっている場合は、「**[!UICONTROL 完了]**」をクリックし、「**[!UICONTROL 保存してアクティベート]**」を選択します。

決定はドラフトとして保存し、後で編集してアクティベートできるようにします。

![](../../assets/save-activities.png)

判定は、前の手順で有効化したかどうかに応じて、「**[!UICONTROL ライブ]**」ステータスまたは「**[!UICONTROL ドラフト]**」ステータスでリストに表示されます。

これで、顧客にオファーを提供するために使用する準備が整いました。選択してプロパティを表示し、編集または抑制できます。

オファーの配信の詳細については、次の節を参照してください。

* [パーソナライズされたオファーをメッセージに追加](../../deliver-personalized-offers.md)
* [API を使用したオファーの配信](../api-reference/decisions-api/deliver-offers.md)

![](../../assets/activities-created.png)

>[!NOTE]
>
>決定が作成されたら、リスト内の名前をクリックして詳細情報にアクセスし、**[!UICONTROL 変更ログ]**&#x200B;タブを使用して、それに加えられたすべての変更を視覚化できます（[オファーと決定の変更ログ](../get-started/user-interface.md#changes-log)を参照）。

## チュートリアルビデオ {#video}

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
