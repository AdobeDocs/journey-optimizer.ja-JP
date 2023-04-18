---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知の設定
description: Journey Optimizer でプッシュ通知を送信するように環境を設定する方法を説明します
role: Admin
level: Intermediate
exl-id: 7099d44e-5d5d-4eef-9477-f68f4eaa1983
source-git-commit: c0358b039f038705aa67e6b779b6b8da228a603b
workflow-type: tm+mt
source-wordcount: '1536'
ht-degree: 100%

---

# プッシュ通知チャネルの設定 {#push-notification-configuration}

[!DNL Journey Optimizer] では、ジャーニーを作成し、ターゲットとなるオーディエンスにメッセージを送信できます。[!DNL Journey Optimizer] でプッシュ通知の送信を開始する前に、モバイルアプリと Adobe Experience Platform のタグで設定と統合が行われていることを確認する必要があります。[!DNL Adobe Journey Optimizer] でのプッシュ通知のデータフローについては、[このページ](push-gs.md)を参照してください。

<!--
>[!AVAILABILITY]
>
>The new **mobile onboarding quick start workflow** is now available. Use this new product feature to rapidly configure the Mobile SDK to start collecting and validating mobile event data, and to send mobile push notifications. This capability is accessible via the Data Collection home page as a public beta. [Learn more](mobile-onboarding-wf.md)
>
-->

## 開始する前に {#before-starting}

<!--
### Check provisioning

Your Adobe Experience Platform account must be provisioned to contain following schemas and datasets for push notification data flow to function correctly:

| Schema <br>Dataset                                                                       | Group of fields                                                                                                                                                                         | Operation                                                |
| -------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| CJM Push Profile Schema <br>CJM Push Profile Dataset                                     | Push Notification Details<br>Adobe CJM ExperienceEvent - Message Profile Details<br>Adobe CJM ExperienceEvent - Message Execution Details<br>Application Details<br>Environment Details | Register Push Token                                      |
| CJM Push Tracking Experience Event Schema<br>CJM Push Tracking Experience Event Dataset | Push Notification Tracking                                                                                                                                                              | Track interactions and provide data for the reporting UI |
-->

### 権限の設定 {#setup-permissions}

モバイルアプリケーションを作成する前に、まず、Adobe Experience Platform のタグに適切なユーザー権限が既にあるか、もしくは割り当てられているかを確認する必要があります。詳しくは、[タグのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html?lang=ja){target="_blank"}を参照してください。

>[!CAUTION]
>
>プッシュ設定は、エキスパートユーザーが実行する必要があります。実装モデルとこの実装に関わるペルソナに応じて、権限のすべてを単一の製品プロファイルに割り当てるか、アプリ開発者と **Adobe Journey Optimizer** 管理者の間で権限を共有する必要が生じる場合があります。**タグ**&#x200B;について詳しくは、[このドキュメント](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/user-permissions.html?lang=ja){target="_blank"}を参照してください。

<!--ou need to your have access to perform following roles :

* Manage Datastreams
* Manage Client-side Properties
* Manage App Configurations
-->

**プロパティ**&#x200B;と&#x200B;**会社**&#x200B;の権限を割り当てるには、次の手順に従います。

1. **[!DNL Admin Console]** にアクセスします。

1. 「**[!UICONTROL 製品]**」タブから、**[!UICONTROL Adobe Experience Platform データ収集]**&#x200B;カードを選択します。

   ![](assets/push_product_1.png)

1. 既存の&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;を選択するか、「**[!UICONTROL 新規プロファイル]**」ボタンで新しい製品プロファイルを作成します。**[!UICONTROL 新規プロファイル]**&#x200B;を作成する方法については、[Admin Console のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html?lang=ja#ui){target="_blank"}を参照してください。

1. 「**[!UICONTROL 権限]**」タブで、「**[!UICONTROL プロパティ権限]**」を選択します。

   ![](assets/push_product_2.png)

1. 「**[!UICONTROL すべて追加]**」をクリックします。これにより、製品プロファイルに次の権限が追加されます。
   * **[!UICONTROL 承認]**
   * **[!UICONTROL 開発]**
   * **[!UICONTROL 環境の管理]**
   * **[!UICONTROL 拡張機能の管理]**
   * **[!UICONTROL 公開]**

   これらの権限は、 Adobe Journey Optimizer 拡張機能をインストールして公開し、Adobe Experience Platform Mobile SDK でアプリプロパティを公開するために必要です。

1. 次に、左側のメニューで「**[!UICONTROL 会社権限]**」を選択します。

   ![](assets/push_product_4.png)

1. 次の権限を追加します。

   * **[!UICONTROL アプリ設定の管理]**
   * **[!UICONTROL プロパティの管理]**

   モバイルアプリ開発者が **Adobe Experience Platform データ収集**&#x200B;でプッシュ資格情報を設定し、**Adobe Journey Optimizer** でプッシュ通知チャネルサーフェス（メッセージプリセット）を定義するには、これらの権限が必要です。

   ![](assets/push_product_5.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

この&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには、次の手順に従います。

1. **[!DNL Admin Console]** にアクセスします。

1. 「**[!UICONTROL 製品]**」タブから、**[!UICONTROL Adobe Experience Platform データ収集]**&#x200B;カードを選択します。

1. 以前に設定した&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;を選択します。

1. 「**[!UICONTROL ユーザー]**」タブで、「**[!UICONTROL ユーザーを追加]**」をクリックします。

   ![](assets/push_product_6.png)

1. ユーザーの名前またはメールアドレスを入力し、ユーザーを選択します。次に、「**[!UICONTROL 保存]**」をクリックします。

   >[!NOTE]
   >
   >Admin Console でユーザーをまだ作成していない場合は、[ユーザーの追加に関するドキュメント](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users)を参照してください。

   ![](assets/push_product_7.png)

### アプリの設定 {#configure-app}

技術的な設定は、アプリ開発者とビジネス管理者の緊密な共同作業を伴います。[!DNL Journey Optimizer] でプッシュ通知の送信を開始する前に、[!DNL Adobe Experience Platform Data Collection] で設定を定義し、モバイルアプリを Adobe Experience Platform Mobile SDK と統合する必要があります。

以下のリンクに記載されている実装手順に従ってください。

* **Apple iOS** の場合：API でアプリを登録する方法については、[Apple ドキュメント](https://developer.apple.com/documentation/usernotifications/registering_your_app_with_apns)を参照してください{target="_blank"}
* **Google Android** の場合：Android に Firebase Cloud Messaging クライアントアプリをセットアップする方法については、[Googleドキュメント](https://firebase.google.com/docs/cloud-messaging/android/client)を参照してください {target="_blank"}

### モバイルアプリの Adobe Experience Platform SDK との統合 {#integrate-mobile-app}

Adobe Experience Platform Mobile SDK は、Android および iOS 互換の SDK を介してモバイル用のクライアントサイド統合 API を提供します。[Adobe Experience Platform Mobile SDK のドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/overview){target="_blank"}に従って、アプリで Adobe Experience Platform Mobile SDK を設定します。

この作業が完了するまでに、[!DNL Adobe Experience Platform Data Collection] でモバイルプロパティも作成および設定する必要があります。通常、管理するモバイルアプリケーションごとにモバイルプロパティを作成します。モバイルプロパティを作成および設定する方法については、[Adobe Experience Platform Mobile SDK ドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property){target="_blank"}を参照してください。


## 手順 1：Adobe Experience Platform データ収集でのアプリのプッシュ認証情報の追加 {#push-credentials-launch}

正しいユーザー権限を付与した後、モバイルアプリケーションのプッシュ認証情報を [!DNL Adobe Experience Platform Data Collection] に追加する必要があります。

モバイルアプリのプッシュ資格情報の登録は、自分の代わりに Adobe がプッシュ通知を送信することを承認するために必要です。以下に説明する手順を参照してください。

1. [!DNL Adobe Experience Platform Data Collection] から、左側のパネルの「**[!UICONTROL アプリのサーフェス]**」タブを選択します。

1. 「**[!UICONTROL アプリサーフェスを作成]**」をクリックして、新しい設定を作成します。

   ![](assets/add-app-config.png)

1. 設定の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. 「**[!UICONTROL モバイルアプリケーションの設定]**」から、オペレーティングシステムを選択します。

   * **iOS の場合**

      ![](assets/add-app-config-ios.png)

      1. 「**[!UICONTROL アプリ ID（iOS バンドル ID）]**」フィールドにモバイルアプリの&#x200B;**バンドル ID** を入力します。アプリのバンドル ID は、**XCode** のメインターゲットの「**一般**」タブにあります。

      1. 「**[!UICONTROL プッシュ認証情報]**」ボタンをオンにして、認証情報を追加します。

      1. .p8 Apple Push Notification Authentication Key ファイルをドラッグ＆ドロップします。このキーは、**証明書**、**識別子**、**プロファイル**&#x200B;ページから取得できます。

      1. **キー ID** を指定します。これは、p8 認証キーの作成中に割り当てられた 10 文字の文字列です。これは、**証明書**、**識別子**&#x200B;および&#x200B;**プロファイル**&#x200B;ページの「**キー**」タブにあります。

      1. **チーム ID** を指定します。これは、「メンバーシップ」タブにある文字列値です。
   * **Android の場合**

      ![](assets/add-app-config-android.png)

      1. **[!UICONTROL アプリ ID（Android パッケージ名）]**&#x200B;を指定します。通常、パッケージ名は`build.gradle`ファイル内のアプリ ID です。

      1. 「**[!UICONTROL プッシュ認証情報]**」ボタンをオンにして、認証情報を追加します。

      1. FCM プッシュ認証情報をドラッグ＆ドロップします。プッシュ資格情報の取得方法について詳しくは、[Google ドキュメント](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}を参照してください



1. 「**[!UICONTROL 保存]**」をクリックして、アプリ設定を作成します。

<!--
## Step 2: Set up a mobile property in Adobe Experience Platform Launch {#launch-property}

Setting up a mobile property allows the mobile app developer or marketer to configure the mobile SDKs attributes such as Session Timeouts, the [!DNL Adobe Experience Platform] sandbox to be targeted and the **[!UICONTROL Adobe Experience Platform Datasets]** to be used for mobile SDK to send data to.

For further details and procedures on how to set up a **[!UICONTROL Platform Launch property]**, refer to the steps detailed in [Adobe Experience Platform Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).


To get the SDKs needed for push notification to work you will need the following SDK extensions, for both Android and iOS:

* **[!UICONTROL Mobile Core]** (installed automatically)
* **[!UICONTROL Profile]** (installed automatically)
* **[!UICONTROL Adobe Experience Platform Edge]**
* **[!UICONTROL Adobe Experience Platform Assurance]**, optional but recommended to debug the mobile implementation.

Learn more about [!DNL Adobe Experience Platform Launch] extensions in [Adobe Experience Platform Launch documentation](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-mobile-android-apps-with-launch/configure-launch/launch-add-extensions.html).
-->

## 手順 2：モバイルプロパティでの Adobe Journey Optimizer 拡張機能の設定 {#configure-journey-optimizer-extension}

Adobe Experience Platform Mobile SDK 用 **Adobe Journey Optimizer 拡張機能**&#x200B;は、モバイルアプリに対するプッシュ通知を強化します。また、ユーザープッシュトークンの収集や、Adobe Experience Platform サービスとのインタラクション測定の管理をサポートします。

Journey Optimizer 拡張機能を設定する方法については、[Adobe Experience Platform Mobile SDK ドキュメント](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-journey-optimizer){target="_blank"}を参照してください。


<!-- 
**[!UICONTROL Edge configuration]** is used by **[!UICONTROL Edge]** extension to send custom data from mobile device to [!DNL Adobe Experience Platform]. 
To configure [!DNL Adobe Experience Platform], you must provide the **[!UICONTROL Sandbox]** name and **[!UICONTROL Event Dataset]**.

For further details and procedures on how to create **[!UICONTROL Edge configuration]**, refer to the steps detailed in [Adobe Experience Platform Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams).

1. From [!DNL Adobe Experience Platform Launch], select the **[!UICONTROL Edge Configurations]** tab and click **[!UICONTROL Edge Configurations]**.
    
1. Select **[!UICONTROL New Edge Configuration]** to add a new **[!UICONTROL Edge Configuration]**.
1. Enter a **[!UICONTROL Name]** and click **[!UICONTROL Save]**

1. Click the **[!UICONTROL Adobe Experience Platform]** toggle to enable it.

1. Fill in the **[!UICONTROL Sandbox]**, **[!UICONTROL Event dataset]** and **[!UICONTROL Profile Dataset]** fields. Then, click **[!UICONTROL Save]**.
    
    ![](assets/push-config-4.png)



1. From [!DNL Adobe Experience Platform Launch], ensure that **[!UICONTROL Client Side]** is selected in the drop-down menu.

1. select the **[!UICONTROL Properties]** tab and click **[!UICONTROL New Property]**.

    ![](assets/push-config-6.png)

1. Enter a **[!UICONTROL Name]** for your new property.

1. Select **[!UICONTROL Mobile]** as **[!UICONTROL Platform]**.

    ![](assets/push-config-7.png)

1. Click **[!UICONTROL Save]** to create your new property.

To configure **[!UICONTROL Adobe Experience Platform Edge Extension]** to send custom data from mobile devices to [!DNL Adobe Experience Platform].

1. Select your previously created property and select the **[!UICONTROL Extensions]** tab to view the extensions for this property.

    ![](assets/push-config-8.png)

1. Click **[!UICONTROL Configure]** under the **[!UICONTROL Adobe Experience Platform Edge]** Network' extension.

1. From the **[!UICONTROL Edge Configuration]** drop-down list, select the **[!UICONTROL Edge Configuration]** created in the previous steps. For more information on **[!UICONTROL Edge Configuration]**, refer to this [section](#edge-configuration).

1. Click **[!UICONTROL Save]**.

To configure **[!UICONTROL Adobe Experience Platform Messaging]** extension to send push profile and push interactions to the correct datasets, follow the same steps as above. Use **[!UICONTROL Sandbox]**, **[!UICONTROL Event dataset]** and **[!UICONTROL Profile Dataset]** created in the [Adobe Experience Platform setup](#edge-configuration).
-->

<!--
## Step 4: Publish the Property {#publish-property}

You now need to publish the property to integrate your configuration and to use it in the mobile app. 

To publish your property, refer to the steps detailed in [Adobe Experience Platform Mobile SDK documentation](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)

## Step 5: Configure the ProfileDataSource {#configure-profiledatasource}

To configure the `ProfileDataSource`, use the `ProfileDCInletURL` from [!DNL Adobe Experience Platform] setup and add the following in the mobile app:

```
    MobileCore.updateConfiguration(
    mutableMapOf("messaging.dccs" to <ProfileDCSInletURL>)
```

-->

## 手順 3：イベントでモバイルアプリをテストする {#mobile-app-test}

Adobe Experience Platform と [!DNL Adobe Experience Platform Data Collection] の両方でモバイルアプリを設定した後、プッシュ通知をテストしてからプロファイルに送信できるようになりました。このユースケースでは、モバイルアプリをターゲットにするジャーニーを作成し、プッシュ通知をトリガーするイベントを設定します。

<!--
You can use a test mobile app for this use case. For more on this, refer to this [page](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=CJM&title=Details+of+setting+the+mobile+test+app) (internal use only).
-->

このジャーニーを機能させるには、XDM スキーマを作成する必要があります。詳しくは、[XDM ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja#schemas-and-data-ingestion){target="_blank"}を参照してください。

1. 左のメニューで、「**[!UICONTROL スキーマ]**」を参照します。

1. 「**[!UICONTROL スキーマを作成]**」をクリックし、「**[!UICONTROL XDM ExperienceEvent]**」を選択します。

   ![](assets/test_push_2.png)

1. 「**[!UICONTROL 新しいフィールドグループを作成]**」を選択します。

1. **[!UICONTROL 表示名]**&#x200B;と&#x200B;**[!UICONTROL 説明]**&#x200B;を入力します。完了したら、「**[!UICONTROL フィールドグループを追加]**」をクリックします。フィールドグループの作成方法について詳しくは、[XDM システムドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja){target="_blank"}を参照してください。


   ![](assets/test_push_4.png)

1. 左側で、スキーマを選択します。右側のペインで、スキーマの名前と説明を入力します。**[!UICONTROL プロファイル]**&#x200B;に対してこのスキーマを有効にします。

   ![](assets/test_push_4b.png)


1. 左側でフィールドグループを選択し、「+」アイコンをクリックして新しいフィールドを作成します。「**[!UICONTROL フィールドグループのプロパティ]**」の右側で、「**[!UICONTROL フィールド名]**」、「**[!UICONTROL 表示名]**」を入力し、「**[!UICONTROL タイプ]**」で「**[!UICONTROL 文字列]**」を選択します。

   ![](assets/test_push_5.png)

1. 「**[!UICONTROL 必須]**」をオンにし、「**[!UICONTROL 適用]**」をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックします。これでスキーマが作成され、イベントで使用できます。

次に、イベントを設定する必要があります。

1. ホームページの左側のメニューの「管理」で、「**[!UICONTROL 設定]**」を選択します。「**[!UICONTROL イベント]**」セクションの「**[!UICONTROL 管理]**」をクリックして、新しいイベントを作成します。

1. 「**[!UICONTROL イベントを作成]**」をクリックすると、画面の右側にイベント設定ペインが開きます。


   ![](assets/test_push_6.png)

1. イベントの名前を入力します。説明を追加することもできます。

1. 「**[!UICONTROL イベント ID タイプ]**」フィールドで、「**[!UICONTROL ルールベース]**」を選択します。

1. 「**[!UICONTROL パラメーター]**」で、以前に作成したスキーマを選択します。

   ![](assets/test_push_7.png)

1. フィールドのリストで、スキーマフィールドグループで作成したフィールドが選択されていることを確認します。

   ![](assets/test_push_7b.png)

1. 「**[!UICONTROL イベント ID 条件]**」フィールドで「**[!UICONTROL 編集]**」をクリックします。以前に追加したフィールドをドラッグ＆ドロップして、システムで使用される条件を定義し、ジャーニーをトリガーするイベントを識別します。

   ![](assets/test_push_8.png)

1. テストアプリでプッシュ通知をトリガーするために使用する構文（この例では&#x200B;**注文確認**）を入力します。

   ![](assets/test_push_9.png)

1. **[!UICONTROL 名前空間]**&#x200B;として **[!UICONTROL ECID]** を選択します。

1. 「**[!UICONTROL OK]**」をクリックしてから「**[!UICONTROL 保存]**」をクリックします。

これでイベントが作成され、ジャーニーで使用できるようになりました。

1. 左のメニューで、「**[!UICONTROL ジャーニー]**」をクリックします。

1. 「**[!UICONTROL ジャーニーを作成]**」をクリックして、新規のジャーニーを作成します。

1. 右側に表示される設定ペインで、ジャーニーのプロパティを編集します。詳しくは、[この節](../building-journeys/journey-gs.md#change-properties)を参照してください。

1. まず、前の手順で作成したイベントを「**[!UICONTROL イベント]**」ドロップダウンからドラッグ＆ドロップします。

   ![](assets/test_push_11.png)

1. 「**[!UICONTROL アクション]**」ドロップダウンから、**[!UICONTROL プッシュ]**&#x200B;アクティビティをジャーニーにドラッグ＆ドロップします。

1. プッシュ通知を設定します。プッシュ通知の作成方法の詳細については、この[ページ](create-push.md)を参照してください。

1. 「**[!UICONTROL テスト]**」トグルをクリックしてプッシュ通知のテストを開始し、「**[!UICONTROL イベントをトリガー]**」をクリックします。

   ![](assets/test_push_12.png)

1. 「**[!UICONTROL キー]**」フィールドに ECID を入力し、2 番目のフィールドに「**注文確認**」と入力します。

   ![](assets/test_push_13.png)

1. 「**[!UICONTROL 送信]**」をクリックします。

イベントがトリガーされ、モバイルアプリにプッシュ通知が届きます。

## 手順 4：プッシュ用のチャネルサーフェスの作成{#message-preset}

モバイルアプリを [!DNL Adobe Experience Platform Data Collection] で設定したら、**[!DNL Journey Optimizer]** からプッシュ通知を送信できるように、サーフェスを作成する必要があります。

チャネルサーフェスを作成して設定する方法については、[この節](../configuration/channel-surfaces.md)を参照してください。

これで、Journey Optimizer でプッシュ通知を送信する準備が整いました。

* プッシュメッセージを作成する方法については、[このページ](create-push.md)を参照してください。
* ジャーニーにメッセージを追加する方法については、[この節](../building-journeys/journeys-message.md)を参照してください。
