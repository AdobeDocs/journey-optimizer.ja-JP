---
title: Visual Editing Helper 拡張機能
description: Journey Optimizerで Web ページの作成とプレビューを可能にする、Visual Editing Helper Chrome 拡張機能を紹介します。
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 50bafd20671912ecbcb595a59fed0e7bad95a200
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 13%

---

# Visual Editing Helper 拡張機能 {#visual-editing-helper}

Web エクスペリエンスをすばやく作成およびプレビューするために、Google Chrome 用Adobe Experience Cloud Visual Editing Helper ブラウザー拡張機能を使用すると、Adobe内で確実に Web サイトを読み込むことができます [!DNL Journey Optimizer] web デザイナー。

>[!NOTE]
>
>現在、Web チャネル機能は、一部のユーザーのみが利用できるベータ版として使用できます。

## Visual Editing Helper 拡張機能のインストール {#install-visual-editing-helper}

Visual Editing Helper ブラウザ拡張機能を取得してインストールするには、次の手順に従います。

1. Google Chrome Web Store で、 [Adobe Experience Cloud Visual Editing Helper ]((https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target="_blank"}) ブラウザー拡張機能。

1. **[!UICONTROL Chrome に追加]**／**[!UICONTROL 拡張機能を追加]**&#x200B;をクリックします。

1. で Web チャネルキャンペーンを作成する [!DNL Journey Optimizer]. [方法についてはこちらを参照](author-web.md#create-web-campaign)

1. を開きます。 [!DNL Journey Optimizer] web デザイナーを使用して、web エクスペリエンスのオーサリングを開始します。 [詳細情報](author-web.md)

1. 対応するアイコンをクリックして、Chrome ブラウザーのツールバーで Visual Editing Helper ブラウザー拡張が有効になっていることを確認します。

   ![](assets/web-visual-editing-extension.png)

Adobe Experience Cloud Visual Editing Helper は、 [!DNL Journey Optimizer] オーサリングを強化する web デザイナー

拡張機能には条件付きの設定はなく、SameSite cookie 設定を含むすべての設定を自動的に処理します。

>[!NOTE]
>
>一部の Web サイトは、 [!DNL Journey Optimizer] web デザイナーは、次のいずれかの理由により実行されます。
>
> * Web サイトには厳格なセキュリティポリシーがあります。
> * Web サイトで iframe が使用されています。
> * 顧客の QA またはステージサイトが外部から利用できません（サイトは内部）。


## トラブルシューティング

Adobe [!DNL Journey Optimizer] web designer では、読み込みに失敗した web サイトを読み込もうとすると、 [Visual Editing Helper ブラウザー拡張機能](#install-visual-editing-helper).

Adobe Experience Platform Web SDK がまだ Web サイトに実装されていない場合は、Visual Editing ヘルパーブラウザー拡張機能をインストールして [Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html?lang=ja){target=&quot;_blank&quot;}。

サイトの読み込みに失敗した場合や、予期しない動作が発生した場合は、Adobeで読み込む前に、ブラウザーで Web サイトの Cookie を受け入れることが修正される可能性があります [!DNL Journey Optimizer].

認証中のページの場合、ログインページの読み込みに失敗した場合、またはログインを試みた後でまだログインしていない場合は、最初にブラウザーの別のタブでログインしてから、Adobeーに Web サイトを読み込んでみます [!DNL Journey Optimizer] web デザイナー。
