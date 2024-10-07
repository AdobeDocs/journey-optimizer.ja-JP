---
title: コンテンツカードの設定
description: コンテンツカードチャネルの前提条件
feature: Channel Configuration
topic: Content Management
role: Admin
level: Experienced
source-git-commit: d4dce7b31d898d86c330048e6d0a1587e87a617c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 18%

---

# コンテンツカードの前提条件 {#content-card-configuration-prereq}

Adobe Journey Optimizerでコンテンツカードを正しく表示するには、次のAdobe Experience Platformを設定する必要があります。

* **Adobe Experience Platform データ収集**

  [ データストリームを作成 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) および [Experience Platformサービスを追加 ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure#aep) します。 「**[!UICONTROL Edgeのセグメント化]**」オプションと「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。 これにより、Journey Optimizer イベントがAdobe Experience Platform Edge Networkで処理されます。
**エクスペリエンスイベント – 提案インタラクション** フィールドグループをデータセットに追加して、このデータをレポートに含めます。 [ 詳しくは、データストリームを参照してください ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)

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

  コンテンツ実験のレポート用にデータセットを追加する方法については、[この節](../reports/reporting-configuration.md)を参照してください。
