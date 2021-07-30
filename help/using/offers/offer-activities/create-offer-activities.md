---
title: 決定の作成
description: 決定の作成方法を説明します
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: 80451fcd012257c8648e751076ed668aa05c44c7
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 58%

---

# 決定の作成 {#create-offer-activities}

決定（旧称：オファーアクティビティ）はオファーのコンテナで、配信のターゲットに応じて、配信する最適なオファーを選ぶために Offer Decisioning エンジンを利用します。

➡️ [この機能をビデオで確認](#video)

決定のリストは、**[!UICONTROL オファー]**&#x200B;メニュー／「**[!UICONTROL 決定]**」タブでアクセスできます。フィルターは、ステータスや開始日、終了日に応じて決定を取得するのに役立ちます。

![](../../assets/activities-list.png)

決定を作成する前に、以下のコンポーネントがオファーライブラリに作成されていることを確認してください。

* [プレースメント](../offer-library/creating-placements.md)
* [コレクション](../offer-library/creating-collections.md)
* [パーソナライズされたオファー](../offer-library/creating-personalized-offers.md)
* [フォールバックオファー](../offer-library/creating-fallback-offers.md)

## 決定の作成 {#create-activity}

1. 決定リストにアクセスし、「**[!UICONTROL 決定を作成]**」をクリックします。

1. 決定の名前、開始日時、終了日時を指定して、「**[!UICONTROL 次へ]**」をクリックします。

   ![](../../assets/activities-name.png)

## 決定範囲の追加 {#add-decision-scopes}

1. リストからプレースメントをドラッグ＆ドロップして決定に追加したあと、「**[!UICONTROL コレクションを追加]**」をクリックします。

   ![](../../assets/activities-placement.png)

   >[!NOTE]
   >
   >同じプレースメントを、決定で複数回選択できます。

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

   セグメントの操作方法について詳しくは、[このページ](../../segment/about-segments.md)を参照してください。

   ![](../../assets/activity_constraint_segment2.png)

   決定ルールを使用してこのプレースメントに選択制約を追加する場合は、「**[!UICONTROL 決定ルール]**」オプションを選択し、目的のルールを左ペインから「**[!UICONTROL 決定ルール]**」領域にドラッグします。決定ルールの作成方法について詳しくは、[この節](../offer-library/creating-decision-rules.md)を参照してください。

   ![](../../assets/activity_constraint_rule.png)

## フォールバックオファーの追加 {#add-fallback}

オファーの実施要件ルールと制約に一致しない顧客に、最後の手段として提示するフォールバックオファーを選択し「**[!UICONTROL 次へ]**」をクリックします。

![](../../assets/add-fallback-offer.png)

## 決定のレビューと保存 {#review}

すべてが正しく設定されている場合は、判定プロパティの概要が表示されます。

1. お客様にオファーを提示するために、決定を使用する準備が整っていることを確認します。
1. **[!UICONTROL Finish]**&#x200B;をクリックします。
1. 次に、「**[!UICONTROL 保存して有効化]**」を選択します。

   ![](../../assets/save-activities.png)

   決定はドラフトとして保存し、後で編集してアクティベートできるようにします。

決定は、前のステップで有効にしたかどうかに応じて、**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL ドラフト]**&#x200B;のステータスでリストに表示されます。

これで、顧客にオファーを提供するために使用する準備が整いました。

## 判定リスト {#decision-list}

決定リストから、プロパティを表示する決定を選択できます。 ここから編集し、ステータス（**ドラフト**、**ライブ**、**完了**、**アーカイブ**）を変更したり、決定を複製したり、削除したりできます。

![](../../assets/decision_created.png)

「**[!UICONTROL 編集]**」ボタンを選択して、判定編集モードに戻ります。このモードで、判定の[詳細](#create-activity)、[判定範囲](#add-decision-scopes)および[フォールバックオファー](#add-fallback)を変更できます。

ライブ判定を選択し、「**[!UICONTROL 非アクティブ化]**」をクリックして、判定ステータスを「**[!UICONTROL ドラフト]**」に戻します。

ステータスを再度「**[!UICONTROL ライブ]**」に設定するには、表示された「**[!UICONTROL アクティブ化]**」ボタンを選択します。

![](../../assets/decision_activate.png)

「**[!UICONTROL その他のアクション]**」ボタンをクリックすると、以下に示すアクションが有効になります。

![](../../assets/decision_more-actions.png)

* **[!UICONTROL 完了]**:は、判定のステータスを「完 **[!UICONTROL 了]**」に設定します。つまり、判定を呼び出すことはできません。このアクションは、アクティブ化された決定に対してのみ使用できます。 判定はリストから引き続き利用できますが、ステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;または&#x200B;**[!UICONTROL 承認済み]**&#x200B;に戻すことはできません。 複製、削除またはアーカイブのみが可能です。

* **[!UICONTROL 複製]**:は、同じプロパティ、判定範囲およびフォールバックオファーを使用して判定を作成します。デフォルトでは、新しい判定のステータスは&#x200B;**[!UICONTROL ドラフト]**&#x200B;です。

* **[!UICONTROL 削除]**:判定をリストから削除します。

   >[!CAUTION]
   >
   >判定とその内容は、もはやアクセスできなくなります。 この操作は元に戻せません。
   >
   >判定が別のオブジェクトで使用されている場合は、削除できません。

* **[!UICONTROL アーカイブ]**:判定ステータスを「アーカイブ済 **[!UICONTROL み]**」に設定します。判定はリストから引き続き利用できますが、ステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;または&#x200B;**[!UICONTROL 承認済み]**&#x200B;に戻すことはできません。 複製または削除できるのは、これだけです。

また、複数の決定のステータスを同時に削除または変更するには、対応するチェックボックスをオンにします。

![](../../assets/decision_multiple-selection.png)

複数の判定のステータスを異なるステータスに変更する場合、関連するステータスのみが変更されます。

![](../../assets/decision_change-status.png)

決定が作成されたら、リストからその名前をクリックできます。

![](../../assets/decision_click-name.png)

これにより、その判定の詳細情報にアクセスできます。 **[!UICONTROL 変更ログ]**&#x200B;タブを選択して、[決定に加えられたすべての変更](../get-started/user-interface.md#changes-log)を監視します。

![](../../assets/decision_information.png)

## チュートリアルビデオ {#video}

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
