---
title: コードベースのエクスペリエンスのガードレールと前提条件
description: Journey Optimizer のコードベースの機能を使用してアプリや web ページを編集できるようにするには、このページの前提条件に従います
feature: Code-based Experiences
topic: Content Management
role: Admin
level: Experienced
exl-id: ac901f88-5fde-4220-88c6-fe05433866cc
source-git-commit: c4444b67313cda81fda9ad16b7ee59226fd7c88a
workflow-type: ht
source-wordcount: '425'
ht-degree: 100%

---

# ガードレールと前提条件 {#web-prerequisites}

[!DNL Journey Optimizer] でコードベースのエクスペリエンスアクションを使用して、アプリケーションで使用できるコードコンテンツペイロードを配信するには、次の前提条件に従います。

* アプリケーションに変更を追加するには、特定の実装が必要です。[詳細情報](#implementation-prerequisites)

* コードベースエクスペリエンスが正しく配信されるように、[こちら](#delivery-prerequisites)を参照して、Adobe Experience Platform の設定を定義します。

>[!CAUTION]
>
>* Adobe **Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織では、コードベースのエクスペリエンスチャネルを使用できません。
>
>* **キャンペーン**&#x200B;にコードベースのエクスペリエンスのみを作成できます。[詳細情報](../campaigns/create-campaign.md#configure)。


## 実装の前提条件 {#implementation-prerequisites}

コードベースのエクスペリエンスは、以下のオプションに示すように、あらゆるタイプの顧客実装をサポートします。プロパティには、クライアントサイド、サーバーサイドまたはハイブリッド実装のいずれかの方法を使用できます。

* クライアントサイドのみ – web ページやモバイルアプリに変更を追加するには、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja) {target="_blank"} on your website or [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} をモバイルアプリに実装する必要があります。

* ハイブリッドモード - [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} to request for personalization server-side; the response is provided to the Adobe Experience Platform Web SDK to render the modifications client-side. Learn more in the Adobe Experience Platform [Edge Network Server API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=ja){target="_blank"}. You can find out more about the hybrid mode and check some implementation samples in [this blog post](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"} を使用できます。

* サーバーサイド - [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja) {target="_blank"} を使用して、サーバーサイドでパーソナライゼーションをリクエストできます。開発チームは、応答を処理し、アプリ実装でクライアントサイドで変更をレンダリングする必要があります。

上記の各実装方法の例について詳しくは、[この節](code-based-implementation-samples.md)を参照してください。

## 配信の前提条件 {#delivery-prerequisites}

コードベースエクスペリエンスが正しく配信されるようにするには、次の設定を定義する必要があります。

* [Adobe Experience Platform データ収集](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}で、**[!UICONTROL Adobe Experience Platform]** サービスの下で「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にするなど、データストリームが定義されていることを確認します。

  これにより、Journey Optimizer インバウンドイベントが Adobe Experience Platform Edge で正しく処理されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja){target="_blank"}

  ![](../web/assets/web-aep-datastream-ajo.png)

* [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}, make sure you have one merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"} で

  この結合ポリシーは、[!DNL Journey Optimizer] インバウンドチャネルで使用すると、エッジでインバウンドキャンペーンを正しくアクティブ化して公開できます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target="_blank"}

  ![](../web/assets/web-aep-merge-policy.png)

## コンテンツ実験の前提条件 {#experiment-prerequisites}

コードベースチャネルのコンテンツ実験を有効にするには、アプリ実装[データストリーム](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja){target="_blank"}で使用される[データセット](../data/get-started-datasets.md)もレポート設定に含まれていることを確認する必要があります。

つまり、実験レポートを設定する際に、アプリデータストリームに存在しないデータセットを追加すると、アプリデータはコンテンツ実験レポートに表示されません。

コンテンツ実験のレポート用にデータセットを追加する方法については、[この節](../campaigns/reporting-configuration.md#add-datasets)を参照してください。

>[!NOTE]
>
>データセットは、[!DNL Journey Optimizer] レポートシステムによって読み取り専用で使用され、データ収集やデータの取り込みには影響しません。
