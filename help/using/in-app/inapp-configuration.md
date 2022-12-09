---
title: アプリ内設定
description: 旅のオプティマイザーによってアプリケーション内のメッセージを送信する環境を設定する方法について説明します。
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# アプリ内チャンネルの設定 {#inapp-configuration}

アプリ内メッセージを送信する前に、で [!DNL Adobe Experience Platform Data Collection] アプリ内チャンネルを設定する必要があります。

1. アカウントを使用 [!DNL Adobe Experience Platform Data Collection] してメニューに **[!UICONTROL Datastream]** アクセスし、をクリック **[!UICONTROL New datastream]** します。 データストリームの作成について詳しくは、このページ ](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams) を [ 参照してください。

1. [!DNL Adobe Experience Platform]サービスを選択します。

   [!DNL Edge Segmentation]、 [!DNL Offer Decisioning] は選択されて [!DNL Adobe Journey Optimizer] いる必要があります。

   ![](assets/inapp_config_6.png)

1. メニューにアクセス **[!UICONTROL App surfaces]** し、をクリック **[!UICONTROL Create App surface]** します。

   ![](assets/inapp_config_1.png)

1. に **[!UICONTROL App surface]** 名前を付けることができます。

1. アップル iOS のドロップダウンリストから、iOS バンドル ID **を入力** します。バンドル ID **に** ついて詳しくは、Apple のマニュアル ](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids) を [ 参照してください。

   ![](assets/inapp_config_2.png)

1. 「Android」ドロップダウンで、android パッケージ名 **を入力** します。パッケージ名 **に** ついて詳しくは、Android のマニュアル ](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores) を [ 参照してください。

1. の **[!UICONTROL App surface]** 設定が終了したら、「」をクリックし **[!UICONTROL Save]** ます。

   ![](assets/inapp_config_3.png)

   アプリ内メッセージを使用して新しいキャンペーンを作成すると、 **[!UICONTROL App surface]** が使用できるようになります。 [詳細情報](create-in-app.md)

1. アプリケーションサーフェイスを作成した後で、モバイルプロパティを作成する必要があります。

   詳細な手順については、このページ ](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-mobile) を [ 参照してください。

   ![](assets/inapp_config_4.png)

1. 新しく作成したプロパティの拡張機能メニューに、次の拡張機能がインストールされています。

   * Adobe エクスペリエンスプラットフォームエッジネットワーク
   * Adobe 旅のオプティマイザー
   * AEP 保証
   * 同意
   * 検出
   * モバイルコア
   * 薄型

   詳細な手順については、このページ ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=en#add-a-new-extension) を [ 参照してください。

   ![](assets/inapp_config_5.png)

アプリ内チャンネルが設定されました。 では、ユーザーにアプリ内メッセージを送信することができます。

**関連トピック:**

* [アプリ内メッセージの作成](create-in-app.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](inapp-report.md)
