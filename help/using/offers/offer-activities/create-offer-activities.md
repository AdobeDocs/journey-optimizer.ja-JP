---
title: 決定の作成
description: 決定の作成方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 7a217c97-57e1-4f04-a92c-37632f8dfe91
source-git-commit: 7f8871fdaf5bb543ce8dc894f3a7dc7304eccf36
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 58%

---

# 決定の作成 {#create-offer-activities}

決定（旧称：オファーアクティビティ）はオファーのコンテナで、配信のターゲットに応じて、配信する最適なオファーを選ぶために Offer Decisioning エンジンを利用します。

➡️ [ビデオでこの機能を確認する](#video)

**[!UICONTROL オファー]**&#x200B;メニューの「**[!UICONTROL 決定]**」タブに決定が一覧表示されます。フィルターは、ステータスや開始日、終了日に応じて決定を取得するのに役立ちます。

![](../../assets/activities-list.png)

決定を作成する前に、以下のコンポーネントがオファーライブラリに作成されていることを確認してください。

* [プレースメント](../offer-library/creating-placements.md)
* [コレクション](../offer-library/creating-collections.md)
* [パーソナライズされたオファー](../offer-library/creating-personalized-offers.md)
* [フォールバックオファー](../offer-library/creating-fallback-offers.md)

## 決定の作成 {#create-activity}

1. 決定リストにアクセスし、「 **[!UICONTROL 決定を作成]**.

1. 決定の名前を指定します。

1. 必要に応じて、開始日と終了日時を定義し、 **[!UICONTROL 次へ]**.

   ![](../../assets/activities-name.png)

## 決定範囲の定義 {#add-decision-scopes}

1. ドロップダウンリストから配置を選択します。 これは、決定の最初の決定範囲に追加されます。

   ![](../../assets/activities-placement.png)

1. クリック **[!UICONTROL 追加]** をクリックして、この配置の評価条件を選択します。

   ![](../../assets/activities-evaluation-criteria.png)

   各条件は、実施要件制約に関連付けられたオファーコレクションと、配置に表示されるオファーを決定するためのランキング方法で構成されます。

   >[!NOTE]
   >
   >少なくとも 1 つの評価基準が必要です。

1. 考慮するオファーが含まれるオファーコレクションを選択し、「 **[!UICONTROL 追加]**.

   ![](../../assets/activities-collection.png)

   >[!NOTE]
   >
   >次の項目をクリックします。 **[!UICONTROL オファーコレクションを開く]** コレクションのリストを新しいタブに表示するリンク。これを使用して、コレクションとそれに含まれるオファーを参照できます。

   選択したコレクションが条件に追加されます。

   ![](../../assets/activities-collection-added.png)

1. 以下を使用： **[!UICONTROL 適格要件]** フィールドを使用して、この配置のオファーの選択を制限します。

   この制約は、**決定ルール**&#x200B;または 1 つ以上の **Adobe Experience Platform セグメント**&#x200B;を使用して適用できます。この両方について詳しくは、[この節](#segments-vs-decision-rules)を参照してください。

   * オファーセグメントのメンバーに対してオファーの選択を制限するには、「Experience Platform」セグメントで **[!UICONTROL セグメント]**&#x200B;を選択し、「 **[!UICONTROL セグメントを追加]**.

      ![](../../assets/activity_constraint_segment.png)

      左側のパネルから 1 つまたは複数のセグメントを追加し、 **[!UICONTROL および]** / **[!UICONTROL または]** 論理演算子。

      ![](../../assets/activity_constraint_segment2.png)

      でセグメントを操作する方法を説明します。 [この節](../../segment/about-segments.md).

   * 決定ルールに選択制約を追加する場合は、 **[!UICONTROL 決定ルール]** 」オプションを選択し、選択したルールを選択します。

      ![](../../assets/activity_constraint_rule.png)

      で決定ルールを作成する方法を説明します。 [この節](../offer-library/creating-decision-rules.md).

1. 各プロファイルに最適なオファーの選択に使用するランキング方法を定義します。

   ![](../../assets/activity_ranking-method.png)

   * デフォルトでは、複数のオファーがこのプレースメントの実施要件を満たす場合、優先順位が最も高いオファーが顧客に配信されます。

   * 特定の数式を使用して提供する適格なオファーを選択する場合は、 **[!UICONTROL ランキング式]**. でオファーをランク付けする方法を説明します。 [この節](../offer-activities/configure-offer-selection.md).

1. クリック **[!UICONTROL 追加]** をクリックして、同じ配置に対するさらに多くの条件を定義します。

   ![](../../assets/activity_add-collection.png)

1. 複数の条件を追加する場合、特定の順序で評価されます。 シーケンスに最初に追加されたコレクションが最初に評価され、以降も同様に続きます。

   デフォルトのシーケンスを変更するには、コレクションをドラッグ&amp;ドロップして必要に応じて並べ替えます。

   ![](../../assets/activity_reorder-collections.png)

1. また、複数の条件を同時に評価することもできます。 これをおこなうには、コレクションを別のコレクションの上にドラッグ&amp;ドロップします。

   ![](../../assets/activity_move-collection.png)

   現在は同じランクなので、同時に評価されます。

   ![](../../assets/activity_same-rank-collections.png)

1. この決定の一部としてオファーに別の配置を追加するには、 **[!UICONTROL 新しいスコープ]** 」ボタンをクリックします。 判定範囲ごとに、上記の手順を繰り返します。

   ![](../../assets/activity_new-scope.png)

### セグメントと決定ルールの使用上の違い {#segments-vs-decision-rules}

<!--to move to create-offers?-->

制約を適用するには、1 つまたは複数の **Adobe Experience Platform セグメント**&#x200B;のメンバーにオファーの選択を限定するか、**決定ルール**&#x200B;を使用します。どちらの手段もそれぞれ異なる使用法に対応します。

基本的に、セグメントの出力はプロファイルのリストです。一方、決定ルールは、決定プロセス中に単一プロファイルに対してオンデマンドで実行される関数です。 この 2 つの使用法の違いを以下に詳しく説明します。

* **セグメント**

   セグメントは、プロファイル属性とエクスペリエンスイベントに基づく特定のロジックに一致する Adobe Experience Platform プロファイルのグループです。 ただし、オファー管理ではセグメントの再計算は行われないので、オファーを提示する際にセグメントが最新でない可能性があります。

   セグメントの詳細については、[この節](../../segment/about-segments.md)を参照してください。

* **決定ルール**

   一方、決定ルールは、Adobe Experience Platform で使用可能なデータに基づいており、オファーを誰に表示できるかを決定します。 特定のプレースメントのオファーまたは決定でルールが選択されると、決定が行われるたびにそのルールが実行されるので、各プロファイルが最新かつ最適なオファーを確実に取得できます。

   決定ルールについて詳しくは、[この節](../offer-library/creating-decision-rules.md)を参照してください。

## フォールバックオファーの追加 {#add-fallback}

決定範囲を定義したら、オファーの実施要件ルールと制約に一致しない顧客への最後の手段として提示されるフォールバックオファーを定義します。

これをおこなうには、決定で定義された配置に使用可能なフォールバックオファーのリストから選択し、「 **[!UICONTROL 次へ]**.

![](../../assets/add-fallback-offer.png)

>[!NOTE]
>
>次の項目をクリックします。 **[!UICONTROL オファーライブラリを開く]** リンクをクリックして、新しいタブにオファーのリストを表示します。

## 決定のレビューと保存 {#review}

すべてが正しく設定されている場合は、決定プロパティの概要が表示されます。

1. 顧客にオファーを提示するために、決定を使用する準備が整っていることを確認します。 すべての決定範囲と、その中に含まれるフォールバックオファーが表示されます。

   ![](../../assets/review-decision.png)

   各配置を展開または折りたたむことができます。 また、各配置に使用可能なオファー、実施要件、ランキングの詳細をプレビューすることもできます。

   ![](../../assets/review-decision-details.png)

1. 「**[!UICONTROL 完了]**」をクリックします。
1. 選択 **[!UICONTROL 保存してアクティブ化]**.

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
