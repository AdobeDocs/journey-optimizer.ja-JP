---
title: ビジュアル編集ヘルパー拡張機能
description: 旅のオプティマイザーで web ページを作成およびプレビューするための視覚的な編集ヘルパー Chrome の拡張機能の発見
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: f4a0ec45-d624-4f80-b888-42e5987cdc4f
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# ビジュアル編集ヘルパー拡張機能 {#visual-editing-helper}

Web エクスペリエンスを迅速に作成およびプレビューするには、Google Chrome 用の Adobe エクスペリエンスクラウドビジュアル編集ヘルパーブラウザー拡張機能を使用すると、アドビシステムズ社 [!DNL Journey Optimizer] の web デザイナーに web サイトを確実に読み込むことができます。

>[!NOTE]
>
>Web チャンネル機能は、現在のところユーザーのみを選択するためのベータ版として提供されています。

## Visual 編集ヘルパー拡張機能のインストール {#install-visual-editing-helper}

Visual 編集ヘルパーブラウザー拡張機能を入手してインストールするには、次の手順を実行します。

1. Google Chrome Web Store から、Adobe エクスペリエンスクラウドビジュアル編集ヘルパー ](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca) {target = &quot;_blank&quot;} ブラウザー拡張機能に [ 移動します。

1. 「> **[!UICONTROL Add Extension]** 」をクリックし **[!UICONTROL Add to Chrome]** ます。

1. で [!DNL Journey Optimizer] web channel キャンペーンを作成します。 [方法について説明します。](author-web.md#create-web-campaign)

1. Web デザイナーを開き、 [!DNL Journey Optimizer] web エクスペリエンスのオーサリングを開始します。 [詳細情報](author-web.md)

1. 適切なアイコンをクリックして、Chrome ブラウザーのツールバーでビジュアル編集ヘルパーブラウザー拡張機能が有効になっていることを確認してください。

   ![](assets/web-visual-editing-extension.png)

Adobe エクスペリエンスクラウドのビジュアル編集ヘルパーは、web デザイナーで [!DNL Journey Optimizer] web サイトを開き、パワーオーサリングの際に自動的に有効になりました。

拡張機能には条件付き設定がなく、SameSite cookie 設定を含むすべての設定が自動的に処理されます。

>[!NOTE]
>
>Web デザイナーによっては、次のいずれかの理由により、 [!DNL Journey Optimizer] 表示が不安定になる場合があります。
>
> * この web サイトには厳格なセキュリティポリシーが含まれています。
> * Web サイトが iframe に含まれています。
> * お客様の QA またはステージサイトは、外界では利用できません (サイトは内部)。


## 解決

Adobe [!DNL Journey Optimizer] web デザイナーを使用している場合、ロードに失敗した web サイトをロードしようとすると、Visual 編集ヘルパーブラウザー拡張機能 ](#install-visual-editing-helper) をインストール [ することを推奨するメッセージが表示されます。

Adobe エクスペリエンス Platform Web SDK がまだ web サイトに実装されていない場合、web デザイナーには Visual 編集ヘルパーブラウザー拡張機能をインストールして、web SDK ](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html) {target = &quot;_blank&quot;} を実装 [ することを推奨するメッセージが表示されます。

サイトの読み込みや予期しない動作が発生した場合は、web サイト上の cookie をブラウザーに入力してから、Adobe [!DNL Journey Optimizer] での読み込みを試みることにより、問題を解決することができます。

認証でページが表示されている場合、ログインページのロードに失敗した場合、またはログインしていない場合はまだログインしていない場合は、まず、ログインしてブラウザーの別のタブに記録してから、アドビシステムズ社 [!DNL Journey Optimizer] の web デザイナーに web サイトをロードしてください。
