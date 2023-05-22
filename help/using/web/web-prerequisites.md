---
title: Web チャネルの前提条件
description: Journey Optimizer のユーザーインターフェイスで web ページにアクセスして作成できるようにするには、このページに記載されている前提条件に従ってください。
feature: Web Channel
topic: Content Management
role: User
level: Beginner
exl-id: 6cb4f8ab-77ad-44a2-b2bf-a97f87b8f1db
source-git-commit: 65a33d6836c43564ef7c93660a8076677ea5cba8
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 100%

---

# 前提条件とガードレール {#web-prerequisites}

[!DNL Journey Optimizer] ユーザーインターフェイスで web ページにアクセスして作成できるようにするには、次の前提条件に従ってください。

* Web サイトに変更を追加するには、特定の実装が必要です。 [詳細情報](#implementation-prerequisites)

* [!DNL Journey Optimizer] Web デザイナーにアクセスするには、特定の Google Chrome ブラウザー拡張機能がインストールされている必要があります。[詳細情報](#visual-authoring-prerequesites)

* Web エクスペリエンスが正しく配信されるように、[こちら](#delivery-prerequisites)に詳しく記載されている Adobe Experience Platform の設定を定義します。

## 注意

現在、[!DNL Journey Optimizer] では、**キャンペーン**&#x200B;を使用してのみ web エクスペリエンスを作成できます。[詳細情報](../campaigns/create-campaign.md#configure)


[!DNL Journey Optimizer] web キャンペーンは、他のチャネルでこれまで関わってこなかった新しいプロファイルをターゲットにします。これにより、エンゲージメント可能なプロファイルの総数が増え、ユーザーが購入した、エンゲージメント可能なプロファイルの契約上の数を超えると、コストに影響する可能性があります。各パッケージのライセンス指標は、[Journey Optimizer の製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html)ページにリストされています。

## 実装の前提条件 {#implementation-prerequisites}

現在、web プロパティで web チャネルキャンペーンのオーサリングと配信を可能にする、次の 2 種類の実装がサポートされています。

* クライアントサイドのみ - web サイトに変更を追加するには、web サイトに [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target="_blank"} を実装する必要があります。

* ハイブリッドモード - [AEP Edge Network Server API](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=ja){target="_blank"} to request for personalization server-side; the response is provided to the Adobe Experience Platform Web SDK to render the modifications client-side. Learn more in the Adobe Experience Platform [Edge Network Server API documentation](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=ja){target="_blank"}. You can find out more about the hybrid mode and check some implementation samples in [this blog post](https://blog.developer.adobe.com/hybrid-personalization-in-the-adobe-experience-platform-web-sdk-6a1bb674bf41){target="_blank"} を使用できます。

>[!NOTE]
>
>サーバーサイドのみの実装は、現在のところサポートされていません。

<!--If the Adobe Experience Platform Web SDK is not yet implemented on the website, a message displays in the web designer suggesting that you install the Visual Editing Helper browser extension and implement the [Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target="_blank"}.-->

## ビジュアルオーサリングの前提条件 {#visual-authoring-prerequisites}

<!--In order to rapidly author and preview your web experiences, the Adobe Experience Cloud Visual Editing Helper browser extension for Google Chrome lets you load websites reliably within the Adobe [!DNL Journey Optimizer] web designer.-->

[!DNL Journey Optimizer] web デザイナーで web ページを確実に開いて作成、プレビューするには [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} のブラウザー拡張機能が web ブラウザーにインストールされている必要があります。

>[!CAUTION]
>
>現在、[!DNL Journey Optimizer] での web ページのオーサリングをサポートしているブラウザーは、Google Chrome とMicrosoft Edge のみです。

### Visual Editing Helper 拡張機能のインストール {#install-visual-editing-helper}

Visual Editing Helper のブラウザー拡張機能をダウンロードしてインストールするには、次の手順に従います。

1. ブラウザー（Google Chrome または Microsoft Edge）で新しいタブを開きます。

1. [Google Chrome web ストア](https://chrome.google.com/webstore/category/extensions){target="_blank"}に移動します。

1. Microsoft Edge を使用している場合は、上部のバナーで「**[!UICONTROL 他のストアの拡張機能を許可]**」を選択します。これにより、Chrome web ストアから Microsoft Edge に拡張機能を追加できます。

1. [Adobe Experience Cloud Visual Editing Helper](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"} のブラウザー拡張機能を検索して移動します。

1. **[!UICONTROL Chrome に追加]**／**[!UICONTROL 拡張機能を追加]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >Microsoft Edge を使用している場合は、ボタンに「**[!UICONTROL Chrome に追加]**」というラベルが付いていても拡張機能が Edge に追加されます。

1. ブラウザーのツールバーで、Visual Editing Helper のブラウザー拡張が正しく有効になっていることを確認します。

   ![](assets/web-visual-editing-extension-edge.png)

<!--1. Launch [!DNL Journey Optimizer] in a new tab of your browser with the extension installed.

1. Create a web channel campaign in [!DNL Journey Optimizer]. [Learn how](author-web.md#create-web-campaign)

1. Open the [!DNL Journey Optimizer] web designer to start authoring your web experience. [Learn more](author-web.md)-->

[!DNL Journey Optimizer] Web Designer で web サイトを開くと、Adobe Experience Cloud Visual Editing Helper が自動的に有効になり、作成が強化されます。

この拡張機能には条件付きの設定はなく、SameSite Cookie の設定を含むすべての設定を自動処理します。

>[!NOTE]
>
>次のいずれかの理由により、[!DNL Journey Optimizer] Web Designer で一部の web サイトが正しく開けない場合があります。
>
> * Web サイトには厳格なセキュリティポリシーがあります。
> * Web サイトで iframe が使用されています。
> * 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。


### Web サイトが読み込まれない場合のトラブルシューティング {#troubleshooting}

Adobe [!DNL Journey Optimizer] web デザイナーでは、読み込みに失敗した web サイトを読み込もうとすると、[Visual Editing Helper ブラウザー拡張機能](#install-visual-editing-helper)をインストールするよう促すメッセージが表示されます。

Visual Editing Helper のブラウザー拡張機能が正しくインストールされても、web サイトの読み込みに失敗したり、予期しない動作が発生した場合は、ブラウザーで web サイトを開いて Cookie を受け入れてから、[!DNL Journey Optimizer] Web デザイナーで読み込んでみてください。

認証されているページでログインページの読み込みに失敗した場合、またはログインを試みてもログインできない場合：

* まず新しいブラウザータブでログインし、目的のページに移動してから、URL をコピーして [!DNL Journey Optimizer] web デザイナーで開いてみます。

* それでも [!DNL Journey Optimizer] web デザイナーで web サイトを読み込めない場合は、問題が発生したことをアドビのカスタマーケアに報告してください。その際は必ず 該当の URL をお知らせください。

## 配信の前提条件 {#delivery-prerequisites}

Web エクスペリエンスが正しく配信されるようにするには、次の設定を定義する必要があります。

* [Adobe Experience Platform データ収集](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=ja){target="_blank"}で、**[!UICONTROL Adobe Experience Platform]** サービスの下で「**[!UICONTROL Edge セグメント化]**」オプションと「**[!UICONTROL Adobe Journey Optimizer]**」オプションの両方を有効にするなど、データストリームが定義されていることを確認します。

   これにより、Journey Optimizer インバウンドイベントが Adobe Experience Platform Edge で正しく処理されます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ja){target="_blank"}

   ![](assets/web-aep-datastream-ajo.png)

   >[!NOTE]
   >
   >「**[!UICONTROL Adobe Journey Optimizer]**」オプションは、「**[!UICONTROL Edge セグメント化]**」オプションが既に有効になっている場合にのみ有効にできます。

* [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}, make sure you have one merge policy with the **[!UICONTROL Active-On-Edge Merge Policy]** option enabled. To do this, select a policy under the **[!UICONTROL Customer]** > **[!UICONTROL Profiles]** > **[!UICONTROL Merge Policies]** Experience Platform menu. [Learn more](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja#configure){target="_blank"} で

   この結合ポリシーは、[!DNL Journey Optimizer] インバウンドチャネルで使用すると、エッジでインバウンドキャンペーンを正しくアクティブ化して公開できます。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=ja){target="_blank"}

   ![](assets/web-aep-merge-policy.png)

## アセットのブランドドメイン {#branded-domains-for-assets}

Web エクスペリエンスの作成時に [Adobe Experience Manager Assets Essentials](../email/assets-essentials.md) ライブラリのコンテンツを追加する場合は、このコンテンツの公開に使用するサブドメインを設定する必要があります。[詳細情報](web-delegated-subdomains.md)
