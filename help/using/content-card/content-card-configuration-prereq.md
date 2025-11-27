---
title: コンテンツカードの設定
description: コンテンツカードチャネルの前提条件
feature: Channel Configuration, Content Cards
topic: Content Management
role: Admin
level: Experienced
exl-id: df92e319-1e42-486f-b688-595964a762c9
source-git-commit: 3d5ed7c5efd76616c8dbc89078f7368eedc5f1af
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 73%

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
  >カスタムの&#x200B;**[!UICONTROL データセット設定]**&#x200B;結合ポリシーを使用する場合は、指定した結合ポリシー内に&#x200B;**[!UICONTROL ジャーニーインバウンド]**&#x200B;データセットを必ず追加してください。

* **Adobe Experience Platform Mobile または Platform Web SDK**

  モバイルアプリケーションおよび web アプリケーションの場合、web ページやモバイルアプリに変更を追加するには、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/platform-learn/implement-web-sdk/overview){target="_blank"} を web サイトに実装するか、[Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/){target="_blank"} をモバイルアプリに実装する必要があります。

* **Journey Optimizer**

  [コンテンツカード設定](#content-card-configuration)の作成

* **トラブルシューティング**

  **Adobe Experience Platform Assurance** 内の **Edge Delivery** ビューを使用してモバイルエクスペリエンスのトラブルシューティングを行います。リクエストの調査、Edge 呼び出しの検証、プロファイルデータの調査を行うことができます。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}

* **コンテンツ実験**

  アプリの[データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview#_blank){target="_blank"}で使用されるデータセットが、コンテンツ実験レポーティング設定にも含まれていることを確認します。データセットが一致しない場合、アプリデータはレポートに表示されません。

  コンテンツ実験のレポート用にデータセットを追加する方法について詳しくは、[この節](../reports/reporting-configuration.md)を参照してください。

## プロファイル管理ガードレール {#profile-management-guardrail}

[!DNL Journey Optimizer] コンテンツカードは、偽名プロファイルをターゲットにすることができます。つまり、他のチャネルでこれまで関与したことがないので、認証されていないプロファイルや、まだ知られていないプロファイルをターゲットにします。 これは、例えば、すべての訪問者やオーディエンスを ECID などの一時 ID に基づいてターゲティングしている場合です。

これにより、エンゲージメント可能なプロファイルの総数が増え、ユーザーが購入した、エンゲージメント可能なプロファイルの契約上の数を超えると、コストに影響する可能性があります。各パッケージのライセンス指標は、[Journey Optimizer の製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}ページにリストされています。エンゲージメント可能なプロファイルの数は、[ライセンス使用状況ダッシュボード](../audience/license-usage.md)で確認できます。

エンゲージメント可能なプロファイルを適切な制限内に保つために、Adobeでは、偽名プロファイルが特定の期間内に表示または関与していない場合は、偽名プロファイルをリアルタイム顧客プロファイルから自動的に削除するように、Time-To-Live （TTL）を設定することをお勧めします。

>[!NOTE]
>
>偽名プロファイルのデータの有効期限を設定する方法については、[Experience Platform ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/pseudonymous-profiles){target="_blank"} を参照してください。

Adobeでは、現在のEdge プロファイル TTL に一致するように TTL 値を 14 日に設定することをお勧めします。