---
title: コンテンツカードの設定
description: コンテンツカードチャネルの前提条件
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
exl-id: df92e319-1e42-486f-b688-595964a762c9
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: cc5c44e2-54a1-4927-b794-442cd87d8f74
  - id: c96d2aa5-76a2-443d-8d23-5de95577c909
  - id: cf64c7f6-7428-4ae5-b158-8df9771f38f4
source-git-commit: adc7081f0bd973ab67f23270f8ce467a8e14a322
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 89%

---

# コンテンツカードの前提条件 {#content-card-configuration-prereq}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey Optimizerがコンテンツカードを正しく配信してレポートを作成できるように、必要なAdobe Experience Platform設定を行います。

>[!ENDSHADEBOX]

Adobe Journey Optimizer でコンテンツカードを正しく表示するには、次の Adobe Experience Platform を設定する必要があります。

* **Adobe Experience Platform のデータ収集**

  [&#x200B; データストリームを作成](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure){target="_blank"}し、[Experience Platform サービスを追加](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure#aep){target="_blank"}します。**[!UICONTROL Edge セグメント化]**&#x200B;および&#x200B;**[!UICONTROL Adobe Journey Optimizer]** オプションを有効にします。これにより、Journey Optimizer イベントがAdobe Experience Platform Edge Networkによって処理されるようになります。
データセットに&#x200B;**エクスペリエンスイベント – 提案インタラクション** フィールドグループを追加して、このデータをレポートに含めます。[&#x200B; データストリームの詳細](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure){target="_blank"}

* **Adobe Experience Platform**

  デフォルトの結合ポリシーで、**顧客**／**プロファイル**／**[!UICONTROL 結合ポリシー]** Experience Platform メニューで「**[!UICONTROL Active-On-Edge 結合ポリシー]**」がアクティブになっていることを確認します。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"}

  >[!NOTE]
  >
  >カスタムの&#x200B;**[!UICONTROL データセット設定]**&#x200B;結合ポリシーを使用する場合は、指定した結合ポリシー内に&#x200B;**[!UICONTROL ジャーニーインバウンド]**&#x200B;データセットを必ず追加してください。

* **Adobe Experience Platform Mobile または Platform Web SDK**

  モバイルアプリケーションおよび web アプリケーションの場合、web ページやモバイルアプリに変更を追加するには、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-web-sdk/overview){target="_blank"} を web サイトに実装するか、[Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home){target="_blank"} をモバイルアプリに実装する必要があります。

* **Journey Optimizer**

  [コンテンツカード設定](#content-card-configuration)の作成

* **トラブルシューティング**

  **Adobe Experience Platform Assurance** 内の **Edge Delivery** ビューを使用してモバイルエクスペリエンスのトラブルシューティングを行います。 リクエストの調査、Edge 呼び出しの検証、プロファイルデータの調査を行うことができます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}

* **コンテンツ実験**

  アプリの[データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview#_blank){target="_blank"}で使用されるデータセットが、コンテンツ実験レポーティング設定にも含まれていることを確認します。 データセットが一致しない場合、アプリデータはレポートに表示されません。

  コンテンツ実験のレポート用にデータセットを追加する方法について詳しくは、[この節](../reports/reporting-configuration.md)を参照してください。

>[!CAUTION]
>
>コンテンツカードを使用して偽名プロファイル（未認証の訪問者）をターゲットにする場合は、自動プロファイル削除の有効期間（TTL）を設定することを考慮し、エンゲージメント可能なプロファイル数と関連コストを管理します。 [詳細情報](../start/guardrails.md#profile-management-inbound)