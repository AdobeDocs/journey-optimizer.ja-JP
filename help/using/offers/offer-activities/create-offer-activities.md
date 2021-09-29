---
title: 決定の作成
description: 決定の作成方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 7a217c97-57e1-4f04-a92c-37632f8dfe91
source-git-commit: 89e0223ebbf5015b61b55da693e0c6401307ce9f
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 72%

---

# 決定の作成 {#create-offer-activities}

決定（旧称：オファーアクティビティ）はオファーのコンテナで、配信のターゲットに応じて、配信する最適なオファーを選ぶために Offer Decisioning エンジンを利用します。

➡️ [この機能をビデオで確認](#video)

決定のリストは、**[!UICONTROL オファー]**&#x200B;メニュー/**[!UICONTROL 決定]**&#x200B;タブでアクセスできます。 フィルターは、ステータスや開始日、終了日に応じて決定を取得するのに役立ちます。

![](../../assets/activities-list.png)

決定を作成する前に、以下のコンポーネントがオファーライブラリに作成されていることを確認してください。

* [プレースメント](../offer-library/creating-placements.md)
* [コレクション](../offer-library/creating-collections.md)
* [パーソナライズされたオファー](../offer-library/creating-personalized-offers.md)
* [フォールバックオファー](../offer-library/creating-fallback-offers.md)

## 決定の作成 {#create-activity}

1. 決定リストにアクセスし、「**[!UICONTROL 決定を作成]**」をクリックします。

1. 判定の名前を指定します。

1. 開始日時と終了日時を定義し、「**[!UICONTROL 次へ]**」をクリックします。

   ![](../../assets/activities-name.png)

## 決定範囲の追加 {#add-decision-scopes}

1. リストからプレースメントをドラッグ＆ドロップして決定に追加し、「 **[!UICONTROL コレクションを追加]**」をクリックします。

   ![](../../assets/activities-placement.png)

   >[!NOTE]
   >
   >決定では、同じプレースメントを複数回選択できます。

1. 考慮するオファーを含んだコレクションを選択し、「**[!UICONTROL 追加]**」をクリックします。

   ![](../../assets/activities-collection.png)

1. 選択したオファーがプレースメントに追加されます。

   この例では、コールセンターソリューションにオファーを提示することを目的とした JSON タイプのプレースメントに表示される 2 つのオファーを選択しました。

   ![](../../assets/offers-added.png)

1. このプレースメントに対して、実施要件を満たすオファーが複数ある場合、デフォルトでは、優先度スコアが最も高いオファーが顧客に配信されます。

   特定の数式またはランキング戦略を使用して、実施要件を満たすオファーを選択する場合は、「**[!UICONTROL オファーを]**&#x200B;でランク付け」ドロップダウンリストからランキング式を選択します。 詳しくは、[この節](../offer-activities/configure-offer-selection.md)を参照してください。

1. 「**[!UICONTROL 制約]**」フィールドにより、このプレースメントのオファーの選択が制限されます。この制約は、**判定ルール**、または1つまたは複数の&#x200B;**Adobe Experience Platformセグメント**&#x200B;を使用して適用できます。 [この節](#segments-vs-decision-rules)では、両方について詳しく説明します。

   * オファーの選択を Adobe Experience Platform セグメントのメンバーに限定するには、「**[!UICONTROL セグメント]**」を選択し、「**[!UICONTROL セグメントを追加]**」をクリックします。

      ![](../../assets/activity_constraint_segment.png)

      左側のペインから 1 つまたは複数のセグメントを追加し、**[!UICONTROL かつ]**／**[!UICONTROL または]**&#x200B;論理演算子を使用してそれらを結合したあと、「**[!UICONTROL 選択]**」をクリックして確認します。

      ![](../../assets/activity_constraint_segment2.png)

      [この節](../../segment/about-segments.md)でセグメントを使用する方法について詳しく説明します。

   * 決定ルールを使用してこのプレースメントに選択制約を追加する場合は、「**[!UICONTROL 決定ルール]**」オプションを選択し、目的のルールを左ペインから「**[!UICONTROL 決定ルール]**」領域にドラッグします。

      ![](../../assets/activity_constraint_rule.png)

      [この節](../offer-library/creating-decision-rules.md)で決定ルールを作成する方法について詳しく説明します。

### セグメントと判定ルールの使用 {#segments-vs-decision-rules}

<!--to move to create-offers?-->

制約を適用するには、1つまたは複数の&#x200B;**Adobe Experience Platformセグメント**&#x200B;のメンバーにオファーの選択を制限するか、異なる用途に対応する&#x200B;**判定ルール**&#x200B;を使用します。

基本的に、セグメントの出力はプロファイルのリストです。一方、判定ルールは、判定プロセス中に単一のプロファイルに対してオンデマンドで実行される関数です。 この2つの用途の違いについては、以下で説明します。

* **セグメント**

   一方、セグメントは、プロファイル属性とエクスペリエンスイベントに基づく特定のロジックに一致するAdobe Experience Platformプロファイルのグループです。 ただし、オファー管理ではセグメントが再計算されず、オファーを提示する際に最新でない可能性があります。

   セグメントの詳細については、[この節](../../segment/about-segments.md)を参照してください。

* **決定ルール**

   一方、決定ルールは、Adobe Experience Platformで使用可能なデータに基づいており、オファーを表示できるユーザーを決定します。 特定の配置に関するオファーまたは決定で選択されると、決定がおこなわれるたびにルールが実行され、各プロファイルが最新で最適なオファーを受け取るようになります。

   [この節](../offer-library/creating-decision-rules.md)では、判定ルールについて詳しく説明します。

## フォールバックオファーの追加 {#add-fallback}

オファーの実施要件ルールと制約に一致しない顧客に、最後の手段として提示するフォールバックオファーを選択し「**[!UICONTROL 次へ]**」をクリックします。

![](../../assets/add-fallback-offer.png)

## 決定のレビューと保存 {#review}

すべてが正しく設定されている場合は、決定プロパティの概要が表示されます。

1. 顧客にオファーを提示するために、決定を使用する準備ができていることを確認します。
1. 「**[!UICONTROL 完了]**」をクリックします。
1. 次に、「**[!UICONTROL 保存して有効化]**」を選択します。

   ![](../../assets/save-activities.png)

   また、決定をドラフトとして保存し、後で編集して有効にすることもできます。

決定は、前のステップで有効にしたかどうかに応じて、**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL ドラフト]**&#x200B;のステータスでリストに表示されます。

これで、顧客にオファーを提供するために決定を使用する準備が整いました。

## 決定リスト {#decision-list}

決定リストから決定を選択して、プロパティを表示できます。ここから編集したり、ステータス（**ドラフト**、**ライブ**、**完了**、**アーカイブ済み**）を変更したり、決定を複製したり、削除したりできます。

![](../../assets/decision_created.png)

「**[!UICONTROL 編集]**」ボタンを選択して、決定編集モードに戻ります。このモードで、決定の[詳細](#create-activity)、[決定範囲](#add-decision-scopes)および[フォールバックオファー](#add-fallback)を変更できます。

ライブ決定を選択し、「**[!UICONTROL 無効化]**」をクリックして、決定のステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;に戻します。

ステータスを再度「**[!UICONTROL ライブ]**」に設定するには、表示されている「**[!UICONTROL 有効化]**」ボタンを選択します。

![](../../assets/decision_activate.png)

「**[!UICONTROL その他のアクション]**」ボタンをクリックすると、以下に示すアクションが有効になります。

![](../../assets/decision_more-actions.png)

* **[!UICONTROL 完了]**：決定のステータスを&#x200B;**[!UICONTROL 完了]**&#x200B;に設定します。これは、決定を呼び出すことができなくなったことを意味します。このアクションは、有効化された決定に対してのみ使用できます。 決定は引き続きリストから利用できますが、ステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;または&#x200B;**[!UICONTROL 承認済み]**&#x200B;に戻すことはできません。複製、削除またはアーカイブのみが可能です。

* **[!UICONTROL 複製]**：同じプロパティ、決定範囲およびフォールバックオファーを持つ決定を作成します。デフォルトでは、新しい決定のステータスは&#x200B;**[!UICONTROL ドラフト]**&#x200B;になります。

* **[!UICONTROL 削除]**：決定をリストから削除します。

   >[!CAUTION]
   >
   >決定とその内容にアクセスできなくなります。 このアクションは取り消しできません。
   >
   >決定が別のオブジェクトで使用されている場合は、削除できません。

* **[!UICONTROL アーカイブ]**：決定のステータスを&#x200B;**[!UICONTROL アーカイブ済み]**&#x200B;に設定します。決定は引き続きリストから使用できますが、ステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;または&#x200B;**[!UICONTROL 承認済み]**&#x200B;に戻すことはできません。複製または削除のみ可能です。

該当するチェックボックスを選択することで、複数の決定のステータスを同時に削除または変更することもできます。

![](../../assets/decision_multiple-selection.png)

異なるステータスを持つ複数の決定のステータスを変更する場合は、関係のあるステータスのみ変更されます。

![](../../assets/decision_change-status.png)

決定が作成されたら、その名前をリストからクリックできます。

![](../../assets/decision_click-name.png)

これにより、その決定の詳細情報にアクセスできます。「**[!UICONTROL 変更ログ]**」タブを選択して、決定に加えられた[すべての変更を監視](../get-started/user-interface.md#changes-log)します。

![](../../assets/decision_information.png)

## チュートリアルビデオ {#video}

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
