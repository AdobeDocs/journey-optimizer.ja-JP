---
title: フォールバックオファーの作成
description: オファーを受ける資格を持たない顧客に表示するフォールバックオファーを作成する方法を説明します
Feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 9ba16ad9-a5e7-4ce7-8ed6-7707d37178c6
source-git-commit: 3f96cc0037b5bcdb2ce94e2721b02ba13b3cff36
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 100%

---

# フォールバックオファーの作成 {#create-fallback-offers}

フォールバックオファーは、他のオファーに対する資格がない場合に顧客に送信されます。フォールバックオファーを作成する手順は、オファーを作成する場合など、1 つまたは複数の表示域を作成することで構成されます。

➡️ [ビデオでこの機能を確認する](#video)

フォールバックオファーのリストは、**[!UICONTROL オファー]**&#x200B;メニューからアクセスできます。

![](../assets/offers_list.png)

フォールバックオファーを作成するには、次の手順に従います。

>[!NOTE]
>
>パーソナライズされたオファーとは異なり、フォールバックオファーは、最後の手段として条件なしで顧客に提示されるので、実施要件ルールや制約パラメーターを持ちません。

1. 「**[!UICONTROL オファーの作成]**」をクリックし、「**[!UICONTROL フォールバックオファー]**」を選択します。

   ![](../assets/create_fallback.png)

1. フォールバックオファーの名前を指定します。また、既存の 1 つまたは複数のコレクション修飾子（旧称「タグ」）を関連付けることで、オファーライブラリの検索と整理がしやすくなります。

   ![](../assets/fallback_details.png)

1. オファーにカスタムデータ使用ラベルまたはコアデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。 [オブジェクトレベルのアクセス制御（OLAC）の詳細情報](../../administration/object-based-access.md)

1. フォールバックオファーの 1 つまたは複数の表示域を作成します。パーソナライズされたオファーを作成する場合などに、これを行うには、左側のペインからプレースメントをドラッグ&amp;ドロップします。
[パーソナライズされたオファーの作成](../offer-library/creating-personalized-offers.md)を参照してください。

   ![](../assets/fallback_content.png)

1. フォールバックオファーの表示域が追加されると、概要が表示されます。すべてが適切に設定され、フォールバックオファーが顧客に提示できる状態になったら、「**[!UICONTROL 終了]**」をクリックしたあと、「**[!UICONTROL 保存して承認]**」を選択します。

   フォールバックオファーは、ドラフトとして保存し、後で編集して承認することもできます。

   ![](../assets/fallback_review.png)

1. フォールバックオファーは、前のステップで承認したかどうかに応じて、**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL ドラフト]**&#x200B;のステータスでリストに表示されます。

   これで、顧客に配信する準備が整いました。選択してプロパティを表示し、編集できます。<!-- no suppression? -->

   ![](../assets/fallback_created.png)

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329383?quality=12)

