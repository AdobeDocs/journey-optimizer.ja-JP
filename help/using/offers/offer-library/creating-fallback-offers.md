---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: フォールバックオファーの作成
description: オファーを受ける資格を持たない顧客に表示するフォールバックオファーを作成する方法を説明します
badge: label="レガシー" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
exl-id: 9ba16ad9-a5e7-4ce7-8ed6-7707d37178c6
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/Du6LWrtaD6lS54qfxT7K8YIRvft8gO8ZlZabCMJ84tk
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 411
ht-degree: 100%

---

# フォールバックオファーの作成 {#create-fallback-offers}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

>[!CONTEXTUALHELP]
>id="ajo_decisioning_new_fallback"
>title="フォールバックオファー"
>abstract="フォールバックオファーは、エンドユーザーがパーソナライズされたオファーの対象でない場合に表示されるデフォルトのオファーです。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_fallback_offer_details "
>title="フォールバックオファーの詳細"
>abstract="フォールバックオファーの名前を指定します。 また、既存の 1 つまたは複数のコレクション修飾子を関連付けることで、オファーライブラリの検索と整理がしやすくなります。"

フォールバックオファーは、他のオファーに対する資格がない場合に顧客に送信されます。 フォールバックオファーの作成手順は、オファーを作成する際のように、1 つまたは複数の表示域を作成することで構成されます。

➡️ [ビデオでこの機能を確認する](#video)

フォールバックオファーのリストは、**[!UICONTROL オファー]**&#x200B;メニューからアクセスできます。

![](../assets/offers_list.png)

フォールバックオファーを作成するには、次の手順に従います。

>[!NOTE]
>
>パーソナライズされたオファーとは異なり、フォールバックオファーは、最後の手段として条件なしで顧客に提示されるので、実施要件ルールや制約パラメーターを持ちません。

1. 「**[!UICONTROL オファーの作成]**」をクリックし、「**[!UICONTROL フォールバックオファー]**」を選択します。

   ![](../assets/create_fallback.png)

1. フォールバックオファーの名前を指定します。 また、既存の 1 つまたは複数のコレクション修飾子（旧称「タグ」）を関連付けることで、オファーライブラリの検索と整理がしやすくなります。

   ![](../assets/fallback_details.png)

1. オファーにカスタムデータ使用ラベルまたはコアデータ使用ラベルを割り当てるには、「**[!UICONTROL アクセスを管理]**」を選択します。 [オブジェクトレベルのアクセス制御（OLAC）の詳細情報](../../administration/object-based-access.md)

1. フォールバックオファーの 1 つまたは複数の表示域を作成します。 パーソナライズされたオファーを作成する場合などに、これを行うには、左側のペインからプレースメントをドラッグ&amp;ドロップします。 [パーソナライズされたオファーの作成](../offer-library/creating-personalized-offers.md)を参照してください。

   ![](../assets/fallback_content.png)

   >[!CAUTION]
   >
   >フォールバックオファーには、[決定](../offer-activities/create-offer-activities.md)内で使用されるすべての表示域を含める必要があります。 例えば、決定に 5 つのオファーがあり、それぞれに異なる表示域がある場合、フォールバックオファーには 5 つの表示域を含める必要があります。

1. フォールバックオファーの表示域が追加されると、概要が表示されます。 すべてが適切に設定され、フォールバックオファーが顧客に提示できる状態になったら、「**[!UICONTROL 終了]**」をクリックしたあと、「**[!UICONTROL 保存して承認]**」を選択します。

   フォールバックオファーは、ドラフトとして保存し、後で編集して承認することもできます。

   ![](../assets/fallback_review.png)

1. フォールバックオファーは、前のステップで承認したかどうかに応じて、**[!UICONTROL ライブ]**&#x200B;または&#x200B;**[!UICONTROL ドラフト]**&#x200B;のステータスでリストに表示されます。

   これで、顧客に配信する準備が整いました。 選択してプロパティを表示し、編集できます。<!-- no suppression? -->

   ![](../assets/fallback_created.png)

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/341357?captions=jpn&quality=12)

