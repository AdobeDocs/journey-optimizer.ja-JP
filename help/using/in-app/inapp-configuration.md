---
title: アプリ内設定
description: Journey Optimizer でアプリ内メッセージを送信するように環境を設定する方法を学ぶ
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 100%

---

# アプリ内チャネルの設定 {#inapp-configuration}

アプリ内メッセージを送信する前に、[!DNL Adobe Experience Platform Data Collection] でアプリ内チャネルを設定する必要があります。

1. お使いの [!DNL Adobe Experience Platform Data Collection] アカウントから、**[!UICONTROL データストリーム]**&#x200B;メニューにアクセスし、**[!UICONTROL 新しいデータストリーム]**&#x200B;をクリックします。データストリーム作成について詳しくは、[このページ](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)を参照してください。

1. [!DNL Adobe Experience Platform] サービスを選択します。 

   [!DNL Edge Segmentation]、[!DNL Offer Decisioning] および [!DNL Adobe Journey Optimizer] を選択する必要があります。

   ![](assets/inapp_config_6.png)

1. 次に、**[!UICONTROL アプリサーフェス]**&#x200B;メニューにアクセスして、「**[!UICONTROL アプリサーフェスを作成]**」をクリックします。

   ![](assets/inapp_config_1.png)

1. **[!UICONTROL アプリサーフェス]**&#x200B;に名前を追加します。

1. Apple iOS ドロップダウンで、**iOS バンドル ID** を入力します。**バンドル ID** について詳しくは、[Apple ドキュメント](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids)を参照してください。

   ![](assets/inapp_config_2.png)

1. Android ドロップダウンで、**Android パッケージ名**&#x200B;を入力します。**パッケージ名**&#x200B;について詳しくは、[Android ドキュメント](https://support.google.com/admob/answer/9972781?hl=ja#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores)を参照してください。

1. **[!UICONTROL アプリサーフェス]**&#x200B;の設定が完了したら、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/inapp_config_3.png)

   アプリ内メッセージを含む新しいキャンペーンを作成する際に、**[!UICONTROL アプリサーフェス]**&#x200B;を使用できるようになりました。 [詳細情報](create-in-app.md)

1. アプリサーフェスを作成したら、モバイルプロパティを作成する必要があります。

   詳しい手順は、[このページ](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=ja#for-mobile)を参照してください。

   ![](assets/inapp_config_4.png)

1. 新しく作成したプロパティの拡張機能メニューから、次の拡張機能をインストールします。

   * Adobe Experience Platform Edge Network
   * Adobe Journey Optimizer
   * AEP Assurance
   * 同意
   * ID
   * Mobile Core
   * プロファイル

   詳しい手順は、[このページ](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/extensions/overview.html?lang=ja#add-a-new-extension)を参照してください。

   ![](assets/inapp_config_5.png)

アプリ内チャネルが設定されました。 ユーザーへのアプリ内メッセージの送信を開始できます。

**関連トピック：**

* [アプリ内メッセージの作成 ](create-in-app.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](inapp-report.md)
