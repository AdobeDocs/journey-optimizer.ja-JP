---
title: プッシュ通知の設定
description: プッシュ通知を送信するために Journey Optimizer で環境を設定する方法を説明します
hide: true
hidefromtoc: true
source-git-commit: 03d003682d796906fcf89af02aa98d549b5214a3
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 77%

---

# プッシュ通知チャネルの設定{#push-notification-configuration}

![](assets/do-not-localize/badge.png)

[!DNL Journey Optimizer]でプッシュ通知の送信を開始する前に、[!DNL Adobe Experience Platform] と [!DNL Adobe Experience Platform Launch] の両方で設定を定義する必要があります。

## Adobe Experience Platform 設定 {#platform-settings}

[!DNL Adobe Experience Platform Launch] でモバイルアプリを設定するには、次の手順に従います。

1. [プロパティと会社権限の割り当て](#push-rights)
1. [Platform Launch でモバイルアプリケーションのプッシュ資格情報を追加します](#push-credentials-launch)。
1. [エッジ設定を作成](#edge-configuration)し、**[!UICONTROL エッジ]**&#x200B;拡張がこの設定を使用して、モバイルデバイスから[!DNL Adobe Experience Platform]にカスタムデータを送信できるようにします。
1. [Platform Launch プロパティを設定します](#launch-property)。
1. [プロパティを公開します](#publish-property)。
1. [ProfileDataSource を設定します](#configure-profiledatasource)。

### 手順 1：プロパティと会社権限を割り当てる{#push-rights}

モバイルアプリケーションを作成する前に、まず、適切なユーザー権限が割り当てられている必要があります。

[!DNL Adobe Experience Platform Launch] を使用したユーザー管理の詳細については、[Platform Launch ドキュメント](https://experienceleague.adobe.com/docs/launch/using/admin/user-permissions.html?lang=ja#experience-cloud-permissions)を参照してください。

プロパティと会社権限を割り当てるには：

1. [!DNL Admin Console]にアクセスします。

1. 「**[!UICONTROL 製品]**」タブから、「**[!UICONTROL Adobe Experience Platform のローンチ]**」カードを選択します。

   ![](assets/push_product_1.png)

1. 既存の&#x200B;**[!UICONTROL 製品のプロファイル]**&#x200B;を選択するか、「**[!UICONTROL 新しいプロファイル]**」ボタンを使用して新しい製品を作成します。 **[!UICONTROL 新しいプロファイル]**&#x200B;の作成方法の詳細については、[管理コンソールのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html?lang=ja#ui)を参照してください。

1. 「**[!UICONTROL 権限]**」タブで、「**[!UICONTROL プロパティ権限]**」を選択します。

   ![](assets/push_product_2.png)

1. **[!UICONTROL すべて追加]**&#x200B;をクリックします。これにより、製品プロファイルに次の権限が追加されます。
   * **[!UICONTROL 承認]**
   * **[!UICONTROL 開発]**
   * **[!UICONTROL 環境の管理]**
   * **[!UICONTROL 拡張機能の管理]**
   * **[!UICONTROL 公開]**

   ![](assets/push_product_3.png)

1. 次に、左側のメニューで「**[!UICONTROL 会社権限]**」を選択します。

   ![](assets/push_product_4.png)

1. 次の権限を追加します。

   * **[!UICONTROL アプリ設定の管理]**
   * **[!UICONTROL プロパティの管理]**

   ![](assets/push_product_5.png)

1. **[!UICONTROL 保存]**&#x200B;をクリックします。

この&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには：

1. [!DNL Admin Console]の「**[!UICONTROL 製品]**」タブで、「**[!UICONTROL Adobe Experience Platform のローンチ]**」カードを選択します。

1. 以前に設定した&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;を選択します。

1. 「**[!UICONTROL ユーザー]**」タブで、「**[!UICONTROL ユーザーを追加]**」をクリックします。

   ![](assets/push_product_6.png)

1. ユーザーの名前またはメールアドレスを入力し、ユーザーを選択します。 **[!UICONTROL 保存]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >管理コンソールでユーザーを作成していない場合は、[ユーザー追加ドキュメント](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users)を参照してください。

   ![](assets/push_product_7.png)


これで、[!DNL Adobe Experience Platform Launch]でモバイルアプリケーションを作成および設定するための適切なユーザー権限が与えられました。

### 手順 2：Platform Launch のモバイルアプリケーションのプッシュ資格情報を追加する{#push-credentials-launch}

正しいユーザー権限を付与した後、モバイルアプリケーションのプッシュ資格情報を[!DNL Adobe Experience Platform Launch]に追加する必要があります。

モバイルアプリケーションのプッシュ資格情報の追加方法の詳細と手順については、[Adobe Experience Platform Mobile SDKのドキュメント](https://aep-sdks.gitbook.io/docs/beta/adobe-journey-optimizer#configure-the-journey-optimizer-extension-in-launch)で詳しく説明されている手順を参照してください。

<!--
Note that to add push credentials in [!DNL Adobe Experience Platform Launch], the owner of the mobile app should fetch them from APNs/FCM.
1. From [!DNL Adobe Experience Platform Launch], ensure that **[!UICONTROL Client Side]** is selected in the drop-down menu.

1. Select the **[!UICONTROL App Configurations]** tab in the left-hand panel and click **[!UICONTROL App Configuration]** to create a new configuration.

1. Enter a **[!UICONTROL Name]** for the configuration.

1. From the **[!UICONTROL Messaging Service Type]** drop-down menu, select the **[!UICONTROL Messaging service type]** to be used for these credentials. Here, we selected **[!UICONTROL Apple Push Notification Service]** since we are working with iOS.

1. Enter the mobile app **[!UICONTROL Bundle Id]** in the **[!UICONTROL App ID (iOS Bundle ID)]** field if you are using Apple push notification service or in the **[!UICONTROL App ID (Android package name)]** field if you are using Firebase Cloud Messaging.

    ![](assets/push_launch_app_configuration.png)

1. Drag and drop the .p8 key file or the .json private key file to the **[!UICONTROL Push Credentials]** field.

1. Enter the **[!UICONTROL Key Id]** and **[!UICONTROL Team Id]** if you are using Apple push notification service.

1. Click **[!UICONTROL Save]** to create your app configuration.
-->

### 手順 3：エッジ設定の作成{#edge-configuration}

**[!UICONTROL エッジ設定]**&#x200B;は、 **[!UICONTROL エッジ]**&#x200B;拡張機能がモバイルデバイスからにカスタムデータを送信する際に使用します[!DNL Adobe Experience Platform]。
[!DNL Adobe Experience Platform]を設定するには、**[!UICONTROL サンドボックス]**&#x200B;名と&#x200B;**[!UICONTROL イベントデータセット]**&#x200B;を指定する必要があります。

**[!UICONTROL Edge設定]**&#x200B;の作成方法と手順について詳しくは、[Adobe Experience Platform Mobile SDKのドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)で詳しく説明されている手順を参照してください。


<!--
1. From [!DNL Adobe Experience Platform Launch], select the **[!UICONTROL Edge Configurations]** tab and click **[!UICONTROL Edge Configurations]**.
    
1. Select **[!UICONTROL New Edge Configuration]** to add a new **[!UICONTROL Edge Configuration]**.
1. Enter a **[!UICONTROL Name]** and click **[!UICONTROL Save]**

1. Click the **[!UICONTROL Adobe Experience Platform]** toggle to enable it.

1. Fill in the **[!UICONTROL Sandbox]**, **[!UICONTROL Event dataset]** and **[!UICONTROL Profile Dataset]** fields. Then, click **[!UICONTROL Save]**.
    
    ![](assets/push-config-4.png)
-->

### 手順 4：Platform Launch プロパティの設定{#launch-property}

[!DNL Adobe Experience Platform Launch]プロパティを設定すると、モバイルアプリ開発者やマーケターはモバイル SDK の属性を設定することができます。属性には、セッションタイムアウト、ターゲットにする[!DNL Adobe Experience Platform]サンドボックス、**[!UICONTROL Adobe Experience Platform データセット]**&#x200B;などがあり、モバイル SDK からのデータの送信に使用できます。

**[!UICONTROL Platform launchプロパティ]**&#x200B;の設定方法の詳細と手順については、[Adobe Experience Platform Mobile SDKのドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)で詳しく説明されている手順を参照してください。

プッシュ通知が機能するために必要な SDK を取得するには、Android と iOS の両方に対して、次の SDK 拡張が必要です。

* **[!UICONTROL モバイルコア]**（自動的にインストール）
* **[!UICONTROL プロファイル]**（自動的にインストール）
* **[!UICONTROL Adobe Experience Platform エッジ]**
* **[!UICONTROL Adobe Experience Platform アシュアランス]**（オプションですが、モバイル実装のデバッグに推奨します）。

[!DNL Adobe Experience Platform Launch]拡張機能の詳細については、[プラットフォームローンチドキュメント](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-mobile-android-apps-with-launch/configure-launch/launch-add-extensions.html?lang=ja)を参照してください。

<!--

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

### 手順 5：プロパティの公開{#publish-property}

設定を統合し、モバイルアプリで使用するには、プロパティを公開する必要があります。


プロパティを公開するための手順の詳細については、[Adobe Experience Platform モバイル SDK ドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)を参照してください。

### 手順 6：ProfileDataSource の設定{#configure-profiledatasource}

`ProfileDataSource`を設定するには、[!DNL Adobe Experience Platform]設定の`ProfileDCInletURL`を使用し、モバイルアプリに次の内容を追加します。

```
    MobileCore.updateConfiguration(
    mutableMapOf("messaging.dccs" to <ProfileDCSInletURL>)
```

<!--
## Test your mobile app with custom action {#mobile-app-test}

After configuring your mobile app in both Adobe Experience Platform and Adobe Launch, you can now test it before sending push notifications to your profiles. In this use case, we will create a journey to target our mobile app and set a custom action which will trigger the push notification.

You can use a test mobile app for this use case. For more on this, refer to this [page](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=CJM&title=Details+of+setting+the+mobile+test+app) (internal use only).

For this journey to work, you need to create an XDM schema. For more information, refer to [XDM documentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#schemas-and-data-ingestion).

1. In the left menu, click **[!UICONTROL Data]** then **[!UICONTROL Schemas]** under **[!UICONTROL Data management]** to create your XDM schema.

    ![](assets/test_push_1.png)

1. Click **[!UICONTROL Create schema]** then select **[!UICONTROL XDM Experience event]**.

    ![](assets/test_push_2.png)

1. In the right pane, enter the name of your schema and description. Enable this schema for **[!UICONTROL Profile]**.

1. In the left pane, click **[!UICONTROL Add]** under **[!UICONTROL Mixins]** and select  **[!UICONTROL Create a new Mixin]**. For more information on how to create mixin, refer to [XDM System documentation](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/create-mixin.html?lang=en#api).

    ![](assets/test_push_3.png)

1. Enter a **[!UICONTROL Display Name]** and a **[!UICONTROL Description]**. Click **[!UICONTROL Add mixin]** when done.

    ![](assets/test_push_4.png)

1. In the **[!UICONTROL Field properties]** window, add a **[!UICONTROL Field name]**, **[!UICONTROL Display name]** and select **[!UICONTROL String]** as **[!UICONTROL Type]**.

    ![](assets/test_push_5.png)

1. Check **[!UICONTROL Required]** and click **[!UICONTROL Apply]**.

1. Click **[!UICONTROL Save]**. Your schema is now created and can be used in an **[!UICONTROL Event schema]**.

You then need to set up an **[!UICONTROL Event schema]** where you will set the custom action which you will need to enter in your mobile app to trigger your push notification.

1. From the left menu of the home page, click the **[!UICONTROL Admin]** icon, then click **[!UICONTROL Manage]** from the **[!UICONTROL Events]** card to create your new **[!UICONTROL Event schema]**.

1. Click **[!UICONTROL Add]**, the event configuration pane opens on the right side of the screen.

    ![](assets/test_push_6.png)

1. Enter the name of your event. You can also add a description.

1. In the **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

1. In the **[!UICONTROL Parameters]**, select your previously created XDM event.

    ![](assets/test_push_7.png)

1. Click **[!UICONTROL Edit]** in the **[!UICONTROL Event ID condition]** field.

1. Drag and your previously added mixin to define the condition that will be used by the system to identify the events that will trigger your journey.

    ![](assets/test_push_8.png)

1. Type in the syntax that you will need to use to trigger your push notification in your test app, in this example **order confirmation**.

    ![](assets/test_push_9.png)

1. Select **[!UICONTROL ECID]** as your **[!UICONTROL Namespace]**.

1. Click **[!UICONTROL Ok]** then **[!UICONTROL Save]**.

Your **[!UICONTROL Event schema]** is now created and can now be used in a journey.

1. In the left menu from [!DNL Journey Optimizer] homepage, click **[!UICONTROL Journeys]**.

1. Click **[!UICONTROL Create]** to create a new journey.

    ![](assets/test_push_10.png)

1. Edit the journey's properties in the configuration pane displayed on the right side. Learn more in this [section](building-journeys/journey-gs.md#change-properties).

1. Start by drag and dropping the **[!UICONTROL Event schema]** created in the previous steps from the **[!UICONTROL Events]** drop-down.

    ![](assets/test_push_11.png)

1. From the **[!UICONTROL Actions]** drop-down, drag and drop a **[!UICONTROL Message]** activity to your journey.

1. Select a previously created message. For more information on how to create push notifications, refer to this [page](create-message.md).

1. Drag and drop an **[!UICONTROL End]** activity to your journey.

1. Activate **[!UICONTROL Test]** to your journey to start testing your push notifications and click **[!UICONTROL Trigger an event]**.

    ![](assets/test_push_12.png)

1. Enter your ECID in the **[!UICONTROL Key]** field then your event that will trigger the push notification in our case **order confirmation**.

    ![](assets/test_push_13.png)

1. Click **[!UICONTROL Send]**.

Your event will be triggered and you will receive your push notification to your mobile app.

![](assets/test_push_14.png)
-->

### 手順7:メッセージプリセット{#message-preset}の作成

モバイルアプリを[!DNL Adobe Experience Platform Launch]で設定したら、**[!DNL Journey Optimizer]**&#x200B;からプッシュ通知を送信できるように、メッセージプリセットを作成する必要があります。

[この節](configuration/message-presets.md)でメッセージプリセットを作成して設定する方法を説明します。