---
title: アプリ内チャネルの前提条件と設定
description: Journey Optimizer でアプリ内メッセージを送信するように環境を設定する方法を学ぶ
role: Admin
feature: In App
level: Intermediate
keywords: アプリ内, メッセージ, 設定, プラットフォーム
exl-id: 469c05f2-652a-4899-a657-ddc4cebe3b42
source-git-commit: 07c453366280b21f5546322430a90752fd996099
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 85%

---

# 前提条件と設定 {#inapp-configuration}

## 設定の手順 {#inapp-steps}

[!DNL Journey Optimizer] を使用してジャーニーとキャンペーンでアプリ内メッセージを送信するには、次の設定手順を実行する必要があります。

1. ジャーニーでアプリ内メッセージのみを使用する予定がある場合でも、開始する前に、Journey Optimizer キャンペーンに対する正しい権限を持っていることを確認してください。キャンペーン権限は引き続き必要です。[詳細情報](../campaigns/get-started-with-campaigns.md#campaign-prerequisites)。
Adobe Experience Platform データ収集の**アプリサーフェス**&#x200B;メニューにアクセスするには、特定の権限を付与する必要があります。詳しくは、[このビデオ](#video)を参照してください。
1. Adobe Experience Platform データ収集データストリームで Adobe Journey Optimizer を有効にし、Adobe Experience Platform のデフォルトの結合ポリシーを確認します。詳細は、[配信の前提条件](#delivery-prerequisites)で詳しく説明しています。
1. Adobe Experience Platform データ収集でのアプリサーフェスの作成と設定について詳しくは、[この節](#channel-prerequisites)を参照してください。
1. コンテンツ実験を使用している場合は、[この節](#experiment-prerequisite)に記載されている要件に従ってください。

完了したら、最初のアプリ内メッセージを作成、設定および送信できます。 これを実現する方法については、[この節](create-in-app.md)を参照してください。

## 配信の前提条件 {#delivery-prerequisites}

アプリ内メッセージが正常に配信されるようにするには、次の設定を定義する必要があります。

* [Adobe Experience Platform データ収集](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}で、**[!UICONTROL Adobe Experience Platform]** サービスの下にある「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にするなど、データストリームが定義されていることを確認します。

  これにより、Journey Optimizer インバウンドイベントが Adobe Experience Platform Edge で正しく処理されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja){target="_blank"}

  ![](assets/inapp_config_6.png)

* 対象： [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}にデフォルトの結合ポリシーがあることを確認してください。 **[!UICONTROL アクティブオンエッジ結合ポリシー]** 有効なオプション。 これを行うには、**[!UICONTROL 顧客r]**／**[!UICONTROL プロファイル]**／**[!UICONTROL 結合ポリシー]** Experience Platform メニューでポリシーを選択します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"}

  この結合ポリシーは、[!DNL Journey Optimizer] インバウンドチャネルで使用すると、エッジでインバウンドキャンペーンを正しくアクティブ化して公開できます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target="_blank"}

  >[!NOTE]
  >
  >カスタムの&#x200B;**[!UICONTROL データセット設定]**&#x200B;マージポリシーを使用する場合は、指定したマージポリシー内に&#x200B;**[!UICONTROL ジャーニーインバウンド]**&#x200B;データセットを必ず追加してください。

  ![](assets/inapp_config_8.png)

* Journey Optimizer モバイルエクスペリエンスの配信のトラブルシューティングを行うには、を使用できます。 **エッジ配信** 内で表示 **Adobe Experience Platform Assurance**. このプラグインを使用すると、リクエスト呼び出しを詳細に調べ、期待されるエッジ呼び出しが予想どおりに発生するかどうかを確認し、ID マップ、セグメントメンバーシップ、同意設定を含むプロファイルデータを調べることができます。 さらに、リクエストが認定されたアクティビティを確認し、認定されなかったアクティビティを特定することもできます。

  使用， **エッジ配信** プラグインは、インバウンド実装を効果的に理解し、トラブルシューティングを行うために必要なインサイトを得るのに役立ちます。

  [エッジ配信ビューの詳細情報](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery)

## チャネル設定の前提条件 {#channel-prerequisites}

1. 次に、**[!UICONTROL アプリサーフェス]**&#x200B;メニューにアクセスして、「**[!UICONTROL アプリサーフェスを作成]**」をクリックします。

1. **[!UICONTROL アプリサーフェス]**&#x200B;に名前を追加します。

   ![](assets/inapp_config_2b.png)

1. **[!UICONTROL Apple iOS]** ドロップダウンから、Apple iOS 用のモバイルアプリケーションを設定します。

+++ 詳細情報

   1. **[!UICONTROL iOS バンドル ID]**&#x200B;を入力します。**バンドル ID** について詳しくは、[Apple ドキュメント](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids)を参照してください。

   1. （オプション）プッシュ通知の送信元となる「**[!UICONTROL サンドボックス]**」を選択します。特定のサンドボックスを選択するには、必要なアクセス権限が必要であることに注意してください。

      サンドボックス管理について詳しくは、[こちらのページ](../administration/sandboxes.md#assign-sandboxes)を参照してください。

   1. 「**[!UICONTROL プッシュ資格情報]**」オプションを有効にして、必要に応じて .p8 auth キーファイルをドラッグ＆ドロップします。

      また、「**[!UICONTROL プッシュ資格情報を手動で入力]**」オプションを有効にして、APNS 認証キーを直接コピー＆ペーストできます。

   1. **[!UICONTROL キー ID]** および **[!UICONTROL チーム ID]** を入力します。

      ![](assets/inapp_config_2.png)

+++

1. **[!UICONTROL Android]**&#x200B;ドロップダウンから、Android 用のモバイルアプリケーションを設定します。

+++ 詳細情報

   1. **[!UICONTROL Android パッケージ名]**&#x200B;を入力します。**パッケージ名**&#x200B;について詳しくは、[Android ドキュメント](https://support.google.com/admob/answer/9972781?hl=ja#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores)を参照してください。

   1. （オプション）プッシュ通知の送信元となる「**[!UICONTROL サンドボックス]**」を選択します。特定のサンドボックスを選択するには、必要なアクセス権限が必要であることに注意してください。

      サンドボックス管理について詳しくは、[こちらのページ](../administration/sandboxes.md#assign-sandboxes)を参照してください。

   1. 「**[!UICONTROL プッシュ資格情報]**」オプションを有効にして、必要に応じて.json 秘密鍵ファイルをドラッグ＆ドロップします。

      また、「**[!UICONTROL プッシュ資格情報を手動で入力]**」オプションを有効して、FCM 秘密鍵を直接コピー＆ペーストすることもできます。

      ![](assets/inapp_config_7.png)

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

## コンテンツ実験の前提条件 {#experiment-prerequisites}

アプリ内チャネルのコンテンツ実験を有効にするには、レポート設定に、アプリ内実装[データストリーム](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja){target="_blank"}で使用する[データセット](../data/get-started-datasets.md)も含まれていることを確認する必要があります。

つまり、実験レポートを設定する際に、web データストリームに存在しないデータセットを追加すると、web データはコンテンツ実験レポートに表示されません。

コンテンツ実験のレポート用にデータセットを追加する方法については、[この節](../campaigns/reporting-configuration.md#add-datasets)を参照してください。

>[!NOTE]
>
>データセットは、[!DNL Journey Optimizer] レポートシステムによって読み取り専用で使用され、データ収集やデータの取り込みには影響しません。

次の場合： **ではない** 次の事前定義済みを使用 [フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#field-group){target="_blank"} データセットスキーマの場合： `AEP Web SDK ExperienceEvent` および `Consumer Experience Event` （で定義） [このページ](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/initial-configuration/configure-schemas.html?lang=ja#add-field-groups){target="_blank"}）を選択します。必ず次のフィールドグループを追加します。 `Experience Event - Proposition Interactions`, `Application Details`, `Commerce Details`、および `Web Details`. これらは、[!DNL Journey Optimizer] のコンテンツ実験レポートで、各プロファイル参加している実験と処理を追跡するために必要です。

>[!NOTE]
>
>これらのフィールドグループを追加しても、通常のデータ収集には影響しません。実験が実行されているページに対してのみ追加され、他のすべての追跡は変更されません。

## チュートリアルビデオ{#video}

以下のビデオでは、アプリサーフェスメニューにアクセスするための&#x200B;**アプリ設定を管理**&#x200B;権限を割り当てる方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/3421607)


**関連トピック：**

* [アプリ内メッセージの作成 ](create-in-app.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](../reports/campaign-global-report.md#inapp-report)

