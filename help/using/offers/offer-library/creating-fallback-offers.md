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
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
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

>[!VIDEO](https://video.tv.adobe.com/v/329383?quality=12)

