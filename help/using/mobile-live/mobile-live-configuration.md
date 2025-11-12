---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティチャネルの設定
description: Journey Optimizerでライブアクティビティを送信するように環境を設定する方法を説明します
feature: Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 62%

---

# ライブアクティビティ設定の基本を学ぶ {#mobile-live-config}

>[!BEGINSHADEBOX]

* [ライブアクティビティの基本を学ぶ](get-started-mobile-live.md)
* **[ライブアクティビティ設定](mobile-live-configuration.md)**
* [Adobe Experience Platform Mobile SDKとライブアクティビティの統合](mobile-live-configuration-sdk.md)
* [ライブアクティビティの作成](create-mobile-live.md)
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

ライブアクティビティを送信する前に、Adobe Journey Optimizerを設定する必要があります。 これを実行するには、次の手順を実行します。

## 手順 1:Journey Optimizerにアプリのプッシュ資格情報を追加する（オプション）{#push-credentials-launch}

モバイルアプリのプッシュ資格情報の登録は、自分の代わりにAdobeがプッシュ通知を送信することを承認するために必要です。

プッシュ資格情報が既に設定されている場合は、ライブアクティビティチャネル設定で再利用できるので、手順 1 はオプションです。 資格情報が定義されていない場合は、アプリの新しいプッシュ資格情報を作成する必要があります。 以下に説明する手順を参照してください。

1. **[!UICONTROL チャネル]**／**[!UICONTROL プッシュ設定]**／**[!UICONTROL プッシュ資格情報]**&#x200B;メニューにアクセスします。

1. 「**[!UICONTROL プッシュ認証情報を作成]**」をクリックします。

   ![](assets/credential-1.png)

1. **[!UICONTROL Platform]** ドロップダウンで、オペレーティングシステムを選択します。

1. モバイルアプリの&#x200B;**[!UICONTROL アプリ ID]** を入力します。

   ![](assets/credential-2.png)

1. これらのプッシュ資格情報をすべてのサンドボックスで使用できるようにするには、「**[!UICONTROL すべてのサンドボックスに適用]**」オプションを有効にします。特定のサンドボックスに同じプラットフォームとアプリ ID のペアに対する独自の資格情報がある場合、これらのサンドボックス固有の資格情報が優先されます。

1. 資格情報を追加するには、「**[!UICONTROL プッシュ資格情報を手動で入力]**」ボタンをオンにします。

1. .p8 Apple Push Notification Authentication Key ファイルをドラッグ＆ドロップします。このキーは、**証明書**、**識別子**、**プロファイル**&#x200B;ページから取得できます。

1. **キー ID** を指定します。これは、p8 認証キーの作成中に割り当てられた 10 文字の文字列です。これは、**証明書**、**識別子**&#x200B;および&#x200B;**プロファイル**&#x200B;ページの「**キー**」タブにあります。

1. **チーム ID** を指定します。これは、「メンバーシップ」タブにある文字列値です。

1. 「**[!UICONTROL 送信]**」をクリックして、アプリ設定を作成します。

## 手順 2：ライブアクティビティ設定の作成 {#config-live-activity}

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL 一般設定]**／**[!UICONTROL チャネル設定]**&#x200B;を選択します。「**[!UICONTROL チャネル設定を作成]**」ボタンをクリックします。

   ![](assets/config-1.png)

1. 設定の名前と説明（オプション）を入力し、WhatsApp チャネルを選択します。

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. チャネルとして **[!DNL Live activity]** を選択します。

   ![](assets/config-2.png)

1. この設定を使用してメッセージに同意ポリシーを関連付けるには、**[!UICONTROL マーケティングアクション]**&#x200B;を選択します。顧客の意向に従うために、そのマーケティングアクションに関連付けられているすべての同意ポリシーが活用されます。詳細情報

1. **[!UICONTROL Platform]** としてiOSを選択します。

1. ドロップダウンから、上記で設定した **[!UICONTROL プッシュ資格情報]** と同じ [&#x200B; アプリ ID](#push-credentials-launch) を選択するか、既存の ID を選択します。

   ![](assets/config-3.png)

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。なお、チャネル設定をドラフトとして保存し、後で設定を再開することもできます。

1. チャネル設定が作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](../configuration/channel-surfaces.md)を参照してください。

1. チェックが正常に完了すると、チャネル設定のステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

Adobe Experience Platform モバイルSDKとの統合を開始して、ロック画面と Dynamic Island でリアルタイムの動的な更新を有効にできるようになりました。

➡️ [&#x200B; 詳しくは、Adobe Experience Platform Mobile SDK統合を参照してください &#x200B;](mobile-live-configuration-sdk.md)
