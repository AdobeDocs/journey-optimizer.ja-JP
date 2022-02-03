---
title: パーソナライズされたオファーの追加
description: メッセージにパーソナライズされたオファーを追加する方法を学ぶ
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 1e648eca-b5ca-4767-b45d-c179243e347f
source-git-commit: 695eec156c7d159d2ab10a6aeb27a35108d704c0
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 100%

---

# パーソナライズされたオファーの追加 {#deliver-personalized-offers}

[!DNL Journey Optimizer] のメールメッセージでは、オファー決定エンジンを利用して、顧客に提供する最適なオファーを選択するための決定（旧称：オファーアクティビティ）を挿入できます。

例えば、受信者のロイヤルティレベルに応じて変わる特別割引オファーを、メールに表示する決定を追加できます。

オファーの管理および作成方法について詳しくは、[この節](offers/get-started/starting-offer-decisioning.md)を参照してください。


オファーの設定方法を示す&#x200B;**完全なエンドツーエンドの例**&#x200B;については、オファーを決定で使用し、この決定をメールで活用して、[この節](offers/offers-e2e.md#insert-decision-in-email)を参照してください。

➡️ オファーをパーソナライゼーションとして追加する方法については、[このビデオ](#video-offers)をご覧ください

## メールへの決定の挿入 {#insert-offers}

>[!CAUTION]
>
>開始する前に、[オファーの決定を定義](offers/offer-activities/create-offer-activities.md)する必要があります。

メールメッセージに決定を挿入するには、次の手順に従います。

1. メールを作成し、E メールデザイナーを開いてそのコンテンツを設定します。

1. **[!UICONTROL オファー決定]**&#x200B;コンテンツコンポーネントを追加します。

   ![](assets/deliver-offer-component.png)

   コンテンツコンポーネントの使用方法については、[この節](content-components.md)を参照してください。

1. 右側のパレットに「**[!UICONTROL オファーの決定]**」タブが表示されます。 「**[!UICONTROL オファーの決定を選択]**」をクリックします。

   ![](assets/deliver-offer-tab.png)

1. 表示されるウィンドウで、表示するオファーに対応するプレースメントを選択します。

   [プレースメント](offers/offer-library/creating-placements.md)は、オファーの表示に使用するコンテナです。この例では、「メールトップ画像」のプレースメントを使用しますこのプレースメントは、オファーの上部に配置された画像タイプオファーを表示するために、オファーライブラリで作成されました。

1. コンテンツコンポーネントで使用するオファーアクティビティを選択し、「**[!UICONTROL 追加]**」をクリックします。

   >[!NOTE]
   >
   >選択したプレースメントと互換性のある決定のみがリストに表示されます。この例では、「メールのトップ画像」プレースメントに一致するオファーアクティビティは 1 つだけです。

   ![](assets/deliver-offer-placement.png)

これで、オファーアクティビティがコンポーネントに追加されました。


## メール内のオファーのプレビュー {#preview-offers-in-email}

**[!UICONTROL オファー]**&#x200B;セクションまたはコンテンツコンポーネントの矢印を使用して、決定に含まれる様々なオファーをプレビューできます。

![](assets/deliver-offer-preview.png)

決定に含まれる様々なオファーを顧客プロファイルで表示するには、次の手順に従います。

1. 「**[!UICONTROL プレビュー]**」をクリックします。

   ![](assets/deliver-offer-preview-button.png)

   >[!NOTE]
   >
   >メッセージのプレビューをおこなうには、テストプロファイルを使用可能にしておく必要があります。[テストプロファイルを作成](building-journeys/creating-test-profiles.md)する方法を学びます。

1. テストプロファイルの識別に使用する名前空間を選択するには、「**[!UICONTROL ID 名前空間]**」フィールドから「**[!UICONTROL メール]**」を選択します。

   >[!NOTE]
   >
   >以下の例では、**メール**&#x200B;名前空間を使用します。Adobe Experience Platform の ID 名前空間については、[この節](get-started-identity.md)を参照してください。

1. ID 名前空間のリストで、**[!UICONTROL メール]**&#x200B;を選択し、**[!UICONTROL 選択]**&#x200B;をクリックします。

1. **[!UICONTROL ID 値]**&#x200B;フィールドに、テストプロファイルを識別する値を入力します。 この例では、テストプロファイルのメールアドレスを入力します。

   <!--For example enter smith@adobe.com and click the **[!UICONTROL Add profile]** button.-->

1. 他のプロファイルを追加して、プロファイルデータに応じて様々なバリエーションのメッセージをテストできるようにします。

   ![](assets/deliver-offer-test-profiles.png)

1. 「**[!UICONTROL プレビュー]**」タブをクリックして、メッセージをテストします。

1. テストプロファイルを選択します。選択したプロファイル（女性）に対応するオファーが表示されます。

   ![](assets/deliver-offer-test-profile-female-preview.png)

1. メッセージの各バリエーションに対してメールの内容をプレビューするには、他のテストプロファイルを選択します。メッセージコンテンツに、選択したテストプロファイル（現在は男性）に対応するオファーが表示されます。

   ![](assets/deliver-offer-test-profile-male-preview.png)

メッセージのプレビューを確認する詳細な手順については、[この節](#preview-your-messages)を参照してください。

## ハウツービデオ{#video-offers}

[!DNL Journey Optimizer] でメッセージに Offer Decisioning コンポーネントを追加する方法を参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/334088?quality=12)

