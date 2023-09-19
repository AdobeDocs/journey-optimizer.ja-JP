---
title: コードベースのエクスペリエンスの前提条件
description: Journey Optimizerのコードベースの機能を使用してアプリや Web ページを編集できるようにするには、このページの前提条件に従います
feature: Offers
topic: Content Management
role: User
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 4aea5c1434caa07aad26445c49a3d5c6274502ec
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 43%

---

# 前提条件とガードレール {#web-prerequisites}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [コードベースのチャネルを使い始める](get-started-code-based.md)
* **[コードベースの前提条件](code-based-prerequisites.md)**
* [コードベースの実装サンプル](code-based-implementation-samples.md)
* [コードベースのエクスペリエンスの作成](create-code-based.md)

>[!ENDSHADEBOX]

でコードベースのエクスペリエンスアクションを使用できるようにするには、以下を実行します。 [!DNL Journey Optimizer] お使いのアプリケーションで使用できるコードコンテンツペイロードを配信するには、次の前提条件に従います。

* アプリケーションに変更を加えるには、特定の実装が必要です。 [詳細情報](#implementation-prerequisites)

* コードベースのエクスペリエンスが正しく配信されるようにするには、必ずAdobe Experience Platform設定の詳細を定義してください [ここ](#delivery-prerequisites).

## 注意事項 {#caution-notes-web}

* コードベースのエクスペリエンスチャネルは、現在、一部のユーザーに対してのみベータ版として利用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

* 現在の場所 [!DNL Journey Optimizer] で作成できるのは、コードベースのエクスペリエンスのみです。 **campaigns**. [詳細情報](../campaigns/create-campaign.md#configure)

## 実装の前提条件 {#implementation-prerequisites}

コードベースのエクスペリエンスは、以下のオプションに示すように、あらゆるタイプの顧客実装をサポートします。 プロパティには、クライアント側、サーバー側、ハイブリッド実装のいずれかの方法を使用できます。

* クライアント側のみ — Web ページやモバイルアプリに変更を追加するには、 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} on your website or [Adobe Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/documentation/){target="_blank"} をモバイルアプリに追加しました。

* ハイブリッドモード - [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} to request for personalization server-side; the response is provided to the Adobe Experience Platform Web SDK to render the modifications client-side. Learn more in the Adobe Experience Platform [Edge Network Server API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=ja){target="_blank"}. You can find out more about the hybrid mode and check some implementation samples in [this blog post](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"} を使用できます。

* サーバー側 — [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} パーソナライゼーションをリクエストするには、サーバーサイドでを使用します。 開発チームは、応答を処理し、アプリ実装でクライアント側で変更をレンダリングする必要があります。

上記の各実装方法のサンプルは、 [この節](code-based-implementation-samples.md).

## 配信の前提条件 {#delivery-prerequisites}

コードベースのエクスペリエンスを正しく配信するには、次の設定を定義する必要があります。

* [Adobe Experience Platform データ収集](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}で、**[!UICONTROL Adobe Experience Platform]** サービスの下で「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にするなど、データストリームが定義されていることを確認します。

  これにより、Journey Optimizer インバウンドイベントが Adobe Experience Platform Edge で正しく処理されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja){target="_blank"}

  ![](../web/assets/web-aep-datastream-ajo.png)

* [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}, make sure you have one merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"} で

  この結合ポリシーは、[!DNL Journey Optimizer] インバウンドチャネルで使用すると、エッジでインバウンドキャンペーンを正しくアクティブ化して公開できます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target="_blank"}

  ![](../web/assets/web-aep-merge-policy.png)

## コンテンツ実験の前提条件 {#experiment-prerequisites}

コードベースのチャネルでコンテンツ実験を有効にするには、 [データセット](../data/get-started-datasets.md) アプリの実装で使用されている [datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=ja){target="_blank"} は、レポート設定にも含まれます。

つまり、実験レポートを設定する際に、アプリデータストリームに存在しないデータセットを追加すると、アプリのデータはコンテンツ実験レポートに表示されません。

コンテンツ実験のレポート用にデータセットを追加する方法については、[この節](../campaigns/reporting-configuration.md#add-datasets)を参照してください。

>[!NOTE]
>
>データセットは、[!DNL Journey Optimizer] レポートシステムによって読み取り専用で使用され、データ収集やデータの取り込みには影響しません。


