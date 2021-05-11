---
title: プッシュ通知の設定
description: Journey Optimizerでプッシュ通知を送信するように環境を設定する方法を説明します
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 0%

---

# プッシュ通知の構成{#push-notification-configuration}

![](assets/do-not-localize/badge.png)

## プッシュ構成を使用する前に{#gs-push}

[!DNL Journey Optimizer]でプッシュ通知の送信を開始する前に、[!DNL Adobe Experience Platform]と[!DNL Adobe Experience Platform Launch]の両方で設定を定義する必要があります。

## Adobe Experience Platform設定{#platform-settings}

[!DNL Adobe Experience Platform Launch]でモバイルアプリを設定するには、次の手順に従います。

1. [プロパティと会社権限の割り当て](#push-rights)
1. [platform launch内追加のモバイルアプリケーションのプッシュ資格情報](#push-credentials-launch)。
1. [モバイルデバイスからにカスタムデータを送信する際に](#edge-configuration) Edgeextensionで使用されるエッジ **** 設定を作成 [!DNL Adobe Experience Platform]します。
1. [platform launchプロパティを設定します](#launch-property)。
1. [プロパティを発行します](#publish-property)。
1. [ProfileDataSourceを設定します](#configure-profiledatasource)。

### 手順1:プロパティと会社の権限を割り当てる{#push-rights}

モバイルアプリケーションを作成する前に、まず、適切なユーザー権限を持っているか、割り当てている必要があります。

[!DNL Adobe Experience Platform Launch]を使用したユーザー管理について詳しくは、[Platform launchドキュメント](https://experienceleague.adobe.com/docs/launch/using/admin/user-permissions.html#experience-cloud-permissions)を参照してください。

プロパティと会社の権限を割り当てるには：

1. [!DNL Admin Console]にアクセスします。

1. 「**[!UICONTROL 製品]**」タブから、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;カードを選択します。

   ![](assets/push_product_1.png)

1. 既存の&#x200B;**[!UICONTROL 製品のプロファイル]**&#x200B;を選択するか、「**[!UICONTROL 新しいプロファイル]**」ボタンを使用して新しい製品を作成します。 新しい&#x200B;**[!UICONTROL 新しいプロファイル]**&#x200B;の作成方法の詳細については、[管理コンソールのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/access-control/ui/create-profile.html#ui)を参照してください。

1. 「**[!UICONTROL 権限]**」タブで、「**[!UICONTROL プロパティ権限]**」を選択します。

   ![](assets/push_product_2.png)

1. **[!UICONTROL す追加べて]**&#x200B;をクリックします。 これにより、製品プロファイルに次の権限が追加されます。
   * **[!UICONTROL 承認]**
   * **[!UICONTROL 開発]**
   * **[!UICONTROL 環境の管理]**
   * **[!UICONTROL 拡張機能の管理]**
   * **[!UICONTROL 公開]**

   ![](assets/push_product_3.png)

1. 次に、左側のメニューで「**[!UICONTROL 会社権限]**」を選択します。

   ![](assets/push_product_4.png)

1. 追加次の権限

   * **[!UICONTROL アプリ設定の管理]**
   * **[!UICONTROL プロパティの管理]**

   ![](assets/push_product_5.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

この&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;をユーザーに割り当てるには：

1. [!DNL Admin Console]の「**[!UICONTROL 製品]**」タブで、**[!UICONTROL Adobe Experience Platform Launch]**&#x200B;カードを選択します。

1. 以前に設定した&#x200B;**[!UICONTROL 製品プロファイル]**&#x200B;を選択します。

1. 「**[!UICONTROL ユーザー]**」タブで、「**[!UICONTROL 追加ユーザー]**」をクリックします。

   ![](assets/push_product_6.png)

1. ユーザーの名前または電子メールアドレスを入力し、ユーザーを選択します。 次に、「**[!UICONTROL 保存]**」をクリックします。

   >[!NOTE]
   >
   >ユーザーが管理コンソールで作成されていない場合は、[追加ユーザードキュメント](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users)を参照してください。

   ![](assets/push_product_7.png)


これで、[!DNL Adobe Experience Platform Launch]でモバイルアプリケーションを作成および設定するための適切なユーザー権限が与えられました。

### 手順2:platform launch&lt;a0/追加>のモバイルアプリケーションプッシュ証明書{#push-credentials-launch}

>[!NOTE]
>
> [!DNL Adobe Experience Platform Launch]にプッシュ証明書を追加するには、モバイルアプリの所有者がAPNs/FCMからそれらを取得する必要があります。

1. [!DNL Adobe Experience Platform Launch]から、ドロップダウンメニューで「**[!UICONTROL クライアント側]**」が選択されていることを確認します。

1. 左側のパネルの「**[!UICONTROL アプリ設定]**」タブを選択し、「**[!UICONTROL アプリ設定]**」をクリックして新しい設定を作成します。

1. 構成の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. 「**[!UICONTROL Messaging Service Type]**」ドロップダウンメニューから、これらの資格情報に使用する&#x200B;**[!UICONTROL Messagingサービスの種類]**&#x200B;を選択します。 ここでは、iOSを扱うので、**[!UICONTROL Apple Push Notification Service]**&#x200B;を選択しました。

1. Appleのプッシュ通知サービスを使用している場合は「**[!UICONTROL アプリID（iOSバンドルID）]**」フィールドに、Firebase Cloud Messagingを使用している場合は「**[!UICONTROL アプリID（Androidパッケージ名）]**」フィールドに、モバイルアプリ&#x200B;**[!UICONTROL バンドルID]**&#x200B;を入力します。

   ![](assets/push_launch_app_configuration.png)

1. .p8キーファイルまたは.json秘密鍵ファイルを&#x200B;**[!UICONTROL プッシュ証明書]**&#x200B;フィールドにドラッグ&amp;ドロップします。

1. Appleのプッシュ通知サービスを使用している場合は、**[!UICONTROL キーID]**&#x200B;と&#x200B;**[!UICONTROL チームID]**&#x200B;を入力します。

1. 「**[!UICONTROL 保存]**」をクリックして、アプリ設定を作成します。

### 手順3:エッジ構成の作成{#edge-configuration}

**[!UICONTROL エッジ]** 設定は、 **** Edgeextensionがモバイルデバイスからにカスタムデータを送信する際に使用 [!DNL Adobe Experience Platform]します。[!DNL Adobe Experience Platform]を設定するには、**[!UICONTROL Sandbox]**&#x200B;名と&#x200B;**[!UICONTROL イベントデータセット]**&#x200B;を指定する必要があります。

1. [!DNL Adobe Experience Platform Launch]から、「**[!UICONTROL エッジ設定]**」タブを選択し、「**[!UICONTROL エッジ設定]**」をクリックします。

1. 「**[!UICONTROL New Edge Configuration]**」を選択して、新しい&#x200B;**[!UICONTROL Edge Configuration]**&#x200B;を追加します。
1. **[!UICONTROL 名前]**&#x200B;を入力し、**[!UICONTROL 保存]**&#x200B;をクリックします

1. **[!UICONTROL Adobe Experience Platform]**&#x200B;の切り替えをクリックして有効にします。

1. **[!UICONTROL Sandbox]**、**[!UICONTROL イベントデータセット]**、**[!UICONTROL プロファイルデータセット]**&#x200B;の各フィールドに入力します。 次に、「**[!UICONTROL 保存]**」をクリックします。

   ![](assets/push-config-4.png)

### 手順4:platform launchプロパティ{#launch-property}の設定

[!DNL Adobe Experience Platform Launch]プロパティを設定すると、モバイルアプリ開発者やマーケティング担当者は、セッションタイムアウト、[!DNL Adobe Experience Platform]サンドボックスをターゲットにし、**[!UICONTROL Adobe Experience Platformデータセット]**&#x200B;をモバイルSDKからのデータの送信に使用できます。

1. [!DNL Adobe Experience Platform Launch]から、ドロップダウンメニューで「**[!UICONTROL クライアント側]**」が選択されていることを確認します。

1. 「**[!UICONTROL プロパティ]**」タブを選択し、「**[!UICONTROL 新しいプロパティ]**」をクリックします。

   ![](assets/push-config-6.png)

1. 新しいプロパティの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. 「**[!UICONTROL モバイル]**」を&#x200B;**[!UICONTROL プラットフォーム]**&#x200B;として選択します。

   ![](assets/push-config-7.png)

1. 「**[!UICONTROL 保存]**」をクリックして、新しいプロパティを作成します。

プッシュ通知が機能するために必要なSDKを取得するには、AndroidとiOSの両方に対して、次のSDK拡張が必要です。

* **[!UICONTROL Mobile Core]** （自動的にインストール）
* **[!UICONTROL プロファイル]** （自動的にインストール）
* **[!UICONTROL Adobe Experience Platformエッジ]**
* **[!UICONTROL Adobe Experience Platformアシュアランス]**（オプションですが、モバイル実装のデバッグに推奨します）。

[!DNL Adobe Experience Platform Launch]拡張機能の詳細については、[Platform launchドキュメント](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-mobile-android-apps-with-launch/configure-launch/launch-add-extensions.html)を参照してください。

**[!UICONTROL Adobe Experience Platformエッジ拡張機能]**&#x200B;を設定して、モバイルデバイスから[!DNL Adobe Experience Platform]にカスタムデータを送信する。

1. 以前に作成したプロパティを選択し、「**[!UICONTROL 拡張子]**」タブを選択して、このプロパティの拡張子を表示します。

   ![](assets/push-config-8.png)

1. **[!UICONTROL Adobe Experience Platformエッジ]**&#x200B;ネットワーク&#39;拡張子の下の&#x200B;**[!UICONTROL 設定]**&#x200B;をクリックします。

1. 「**[!UICONTROL エッジの設定]**」ドロップダウンリストから、前の手順で作成した「**[!UICONTROL エッジの設定]**」を選択します。 **[!UICONTROL エッジ設定]**&#x200B;の詳細については、[](#edge-configuration)を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

プッシュプロファイルとプッシュ操作を正しいデータセットに送信するように&#x200B;**[!UICONTROL Adobe Experience Platformメッセージング]**&#x200B;拡張を設定するには、上記と同じ手順に従います。 [Adobe Experience Platformセットアップ](#edge-configuration)で作成した&#x200B;**[!UICONTROL Sandbox]**、**[!UICONTROL イベントデータセット]**、**[!UICONTROL プロファイルデータセット]**&#x200B;を使用します。

### 手順5:プロパティを発行{#publish-property}

設定を統合し、モバイルアプリで使用するには、プロパティを公開する必要があります。
プロパティを公開するには、[Adobe Experience PlatformモバイルSDKドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration)に詳しく記載されている手順を参照してください。

### 手順6:ProfileDataSource {#configure-profiledatasource}の設定

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
