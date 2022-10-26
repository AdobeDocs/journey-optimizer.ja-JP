---
title: アプリ内設定
description: Journey Optimizerでアプリ内メッセージを送信するように環境を設定する方法を説明します
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: e7431d1b69e460471b01439c9bd2577fd69944ed
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---

# アプリ内チャネルの設定 {#inapp-configuration}

アプリ内メッセージを送信する前に、 [!DNL Adobe Experience Platform Data Collection].

1. お使いの [!DNL Adobe Experience Platform Data Collection] アカウントに、 **[!UICONTROL Datastream]** メニューとクリック **[!UICONTROL 新しいデータストリーム]**. データストリームの作成について詳しくは、 [このページ](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams).

1. を選択します。 [!DNL Adobe Experience Platform] サービス。

   [!DNL Edge Segmentation], [!DNL Offer Decisioning] および [!DNL Adobe Journey Optimizer] を選択する必要があります。

   ![](assets/inapp_config_6.png)

1. 次に、 **[!UICONTROL アプリのサーフェス]** メニュー、次に「 **[!UICONTROL アプリサーフェスを作成]**.

   ![](assets/inapp_config_1.png)

1. 名前を **[!UICONTROL アプリサーフェス]**.

1. 「 Apple iOS 」ドロップダウンで、 **iOS Bundle ID**. 参照： [Appleドキュメント](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) 詳しくは、 **バンドル ID**.

   ![](assets/inapp_config_2.png)

1. Android ドロップダウンから、 **Android パッケージ名**. 参照： [Android ドキュメント](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores) 詳しくは、 **パッケージ名**.

1. クリック **[!UICONTROL 保存]** の設定が完了したら、 **[!UICONTROL アプリサーフェス]**.

   ![](assets/inapp_config_3.png)

   お使いの **[!UICONTROL アプリサーフェス]** は、アプリ内メッセージを使用して新しいキャンペーンを作成する際に使用できるようになりました。 [詳細情報](create-in-app.md)

1. アプリのサーフェスを作成したら、モバイルプロパティを作成する必要があります。

   参照： [このページ](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-mobile) を参照してください。

   ![](assets/inapp_config_4.png)

1. 新しく作成したプロパティの拡張機能メニューから、次の拡張機能をインストールします。

   * Adobe Experience Platform Edge Network
   * Adobe Journey Optimizer
   * AEP アシュランス
   * 同意
   * 特定
   * Mobile Core
   * プロファイル

   参照： [このページ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=en#add-a-new-extension) を参照してください。

   ![](assets/inapp_config_5.png)

これで、アプリ内チャネルが設定されました。 ユーザーへのアプリ内メッセージの送信を開始できます。

**関連トピック：**

* [アプリ内メッセージの作成](create-in-app.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](inapp-report.md)
