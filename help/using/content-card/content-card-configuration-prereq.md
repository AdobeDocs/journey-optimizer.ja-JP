---
title: コンテンツカードの設定
description: コンテンツカードチャネルの前提条件
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
exl-id: df92e319-1e42-486f-b688-595964a762c9
source-git-commit: 598be5d2c5aca0262063c61e80e6b36020983131
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 100%

---

# コンテンツカードの前提条件 {#content-card-configuration-prereq}

Adobe Journey Optimizer でコンテンツカードを正しく表示するには、次の Adobe Experience Platform を設定する必要があります。

* **Adobe Experience Platform のデータ収集**

  [データストリームを作成](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure){target="_blank"}し、[Experience Platform サービスを追加](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure#aep){target="_blank"}します。「**[!UICONTROL Edge のセグメント化]**」オプションと「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。これにより、Journey Optimizer イベントが Adobe Experience Platform Edge Network で正しく処理されます。
「**エクスペリエンスイベント - 提案インタラクション**」フィールドグループをデータセットに追加して、このデータをレポートに含めます。[詳しくは、データストリームを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure){target="_blank"}

* **Adobe Experience Platform**

  デフォルトの結合ポリシーで、**顧客]**／**[!UICONTROL プロファイル**／**[!UICONTROL 結合ポリシー]** Experience Platform メニューで「**[!UICONTROL Active-On-Edge 結合ポリシー]**」がアクティブになっていることを確認します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"}

  >[!NOTE]
  >
  >カスタムの&#x200B;**[!UICONTROL データセット設定]**&#x200B;マージポリシーを使用する場合は、指定したマージポリシー内に&#x200B;**[!UICONTROL ジャーニーインバウンド]**&#x200B;データセットを必ず追加してください。

* **Adobe Experience Platform Mobile または Platform Web SDK**

  モバイルアプリケーションおよび web アプリケーションの場合、web ページやモバイルアプリに変更を追加するには、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-web-sdk/overview){target="_blank"} を web サイトに実装するか、[Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/){target="_blank"} をモバイルアプリに実装する必要があります。

* **Journey Optimizer**

  [コンテンツカード設定](#content-card-configuration)の作成

* **トラブルシューティング**

  **Adobe Experience Platform Assurance** 内の **Edge Delivery** ビューを使用してモバイルエクスペリエンスのトラブルシューティングを行います。リクエストの調査、Edge 呼び出しの検証、プロファイルデータの調査を行うことができます。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}

* **コンテンツ実験**

  アプリの[データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview#_blank){target="_blank"}で使用されるデータセットが、コンテンツ実験レポーティング設定にも含まれていることを確認します。データセットが一致しない場合、アプリデータはレポートに表示されません。

  コンテンツ実験のレポート用にデータセットを追加する方法について詳しくは、[この節](../reports/reporting-configuration.md)を参照してください。
