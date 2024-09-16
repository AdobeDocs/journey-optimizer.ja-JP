---
title: コンテンツカードの設定
description: コンテンツカードチャネルの前提条件
feature: Channel Configuration
topic: Content Management
role: Admin
level: Experienced
badge: label="限定提供" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: 8a902298bbbac5689b4f84266dd9c9027e45fad5
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 19%

---

# コンテンツカードの前提条件 {#content-card-configuration-prereq}

>[!BEGINSHADEBOX]

**目次**

* [コンテンツカードの基本を学ぶ](get-started-content-card.md)
* **コンテンツカードの前提条件**
* [Journey Optimizerでのコンテンツカードチャネルの設定](content-card-configuration.md)
* [コンテンツカードの作成](create-content-card.md)
* [コンテンツカードのデザイン](design-content-card.md)
* [コンテンツカードレポート](content-card-report.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>コンテンツカードは現在、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。

Adobe Journey Optimizerでコンテンツカードを正しく表示するには、次のAdobe Experience Platformを設定する必要があります。

* **Adobe Experience Platform データ収集**

  [ データストリームを作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) および [Experience Platformサービスを追加 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#aep) します。 「**[!UICONTROL Edgeのセグメント化]**」オプションと「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。 これにより、Journey Optimizer イベントがAdobe Experience Platform Edge Networkで処理されます。 データストリームの設定方法について詳しくは、[ データストリームのドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) を参照してください。

* **Adobe Experience Platform**

  デフォルトの結合ポリシーで、**顧客]** / **[!UICONTROL プロファイル** / **[!UICONTROL 結合ポリシー]** Experience Platformメニューで **[!UICONTROL Edge時にアクティブ]** 結合ポリシーが有効になっていることを確認します。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"}

  >[!NOTE]
  >
  >カスタムの&#x200B;**[!UICONTROL データセット設定]**&#x200B;マージポリシーを使用する場合は、指定したマージポリシー内に&#x200B;**[!UICONTROL ジャーニーインバウンド]**&#x200B;データセットを必ず追加してください。

* **Adobe Experience Platform Mobile または Platform Web SDK**

  モバイルおよび web アプリケーションで、web ページやモバイルアプリに変更を加えるには、web サイトに [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-web-sdk/overview) を実装するか、モバイルアプリに [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) を実装する必要があります。

* **Journey Optimizer**

  [ コンテンツカード設定 ](#content-card-configuration) を作成します。

* **トラブルシューティング**

  **Adobe Experience Platform Assurance** 内の **Edge Delivery} ビューを使用して** モバイルエクスペリエンスのトラブルシューティングを行います。 リクエストの調査、エッジ呼び出しの検証、プロファイルデータの調査を行えます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery)

* **コンテンツ実験**

  アプリの [ データストリーム ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview#_blank) で使用されるデータセットが、コンテンツ実験レポート設定にも含まれていることを確認します。 データセットが一致しない場合、アプリデータはレポートに表示されません。

  コンテンツ実験のレポート用にデータセットを追加する方法については、[この節](../content-management/reporting-configuration.md)を参照してください。
