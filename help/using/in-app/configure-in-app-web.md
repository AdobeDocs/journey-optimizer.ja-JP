---
title: Journey Optimizer での web アプリ内メッセージの作成
description: Journey Optimizer で web アプリ内メッセージを作成する方法を学ぶ
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: アプリ内, メッセージ, 作成, 開始
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 100%

---


# Web アプリ内チャネルの設定 {#configure-in-app-web}

## 前提条件 {#prerequisites}

* **Adobe Experience Platform Web SDK** 拡張機能の最新バージョンを使用していることを確認します。

* **Adobe Experience Platform Web SDK** 拡張機能を&#x200B;**タグのプロパティ**&#x200B;にインストールし、「**パーソナライゼーションストレージ**」オプションを有効にします。

  この設定は、クライアントにイベント履歴を保存するために不可欠で、ルールビルダーで頻度ルールを実装するための前提条件です。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html?lang=ja)

  ![](assets/configure_web_inapp_1.png)

## プラットフォームにデータを送信済みルールの設定 {#configure-sent-data-trigger}

1. **Adobe Experience Platform データ収集**&#x200B;インスタンスにアクセスし、**Adobe Experience Platform Web SDK** 拡張機能で設定した&#x200B;**タグのプロパティ**&#x200B;に移動します。

1. **オーサリング**&#x200B;メニューから「**ルール**」を選択してから、「**新しいルールを作成**」または「**ルールを追加**」を選択します。

   ![](assets/configure_web_inapp_2.png)

1. 「**イベント**」セクションで「**追加**」をクリックし、次のように設定します。

   * **拡張機能**：コア

   * **イベントタイプ**：読み込まれたライブラリ（ページ上部）

   ![](assets/configure_web_inapp_3.png)

1. 「**変更を保持**」をクリックして、イベント設定を保存します。

1. 「**アクション**」セクションで「**追加**」をクリックし、次のように設定します。

   * **拡張機能**：Adobe Experience Platform Web SDK

   * **アクションタイプ**：イベントを送信

   ![](assets/configure_web_inapp_4.png)

1. **アクション**&#x200B;タイプの「**パーソナライゼーション**」セクションで、「**視覚的なパーソナライゼーションの決定をレンダリング**」オプションを有効にします。

   ![](assets/configure_web_inapp_5.png)

1. 「**決定コンテキスト**」セクションで、提供するエクスペリエンスを決定する&#x200B;**キー**&#x200B;と&#x200B;**値**&#x200B;のペアを定義します。

   ![](assets/configure_web_inapp_6.png)

1. 「**変更を保持**」をクリックして&#x200B;**アクション**&#x200B;の設定を保存します。

1. **公開フロー**&#x200B;メニューに移動します。新しい&#x200B;**ライブラリ**&#x200B;を作成するか、既存の&#x200B;**ライブラリ**&#x200B;を選択して、そこに新しく作成した&#x200B;**ルール**&#x200B;を追加します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=ja#create-a-library)

1. **ライブラリ**&#x200B;から、「**開発用に保存およびビルド**」を選択します。

   ![](assets/configure_web_inapp_7.png)

## 手動ルールの設定 {#configure-manual-trigger}

1. **Adobe Experience Platform データ収集**&#x200B;インスタンスにアクセスし、**Adobe Experience Platform Web SDK** 拡張機能で設定した&#x200B;**タグプロパティ**&#x200B;に移動します。

1. **オーサリング**&#x200B;メニューから「**ルール**」を選択してから、「**新しいルールを作成**」または「**ルールを追加**」を選択します。

   ![](assets/configure_web_inapp_8.png)

1. 「**イベント**」セクションで「**追加**」をクリックし、次のように設定します。

   * **拡張機能**：コア

   * **イベントタイプ**：クリック

   ![](assets/configure_web_inapp_9.png)

1. **クリック設定**&#x200B;で、評価する&#x200B;**セレクター**&#x200B;を定義します。

   ![](assets/configure_web_inapp_10.png)

1. 「**変更を保持**」をクリックして、**イベント**&#x200B;設定を保存します。

1. 「**アクション**」セクションで「**追加**」をクリックし、次のように設定します。

   * **拡張機能**：Adobe Experience Platform Web SDK

   * **アクションタイプ**：ルールセットを評価

   ![](assets/configure_web_inapp_11.png)

1. **アクション**&#x200B;タイプの「**ルールセットアクションを評価**」セクションで、「**視覚的なパーソナライゼーションの決定をレンダリング**」オプションを有効にします。

   ![](assets/configure_web_inapp_13.png)

1. 「**決定コンテキスト**」セクションで、実現するエクスペリエンスを決定する&#x200B;**キー**&#x200B;と&#x200B;**値**&#x200B;のペアを定義します。

1. **公開フロー**&#x200B;メニューにアクセスし、新しい&#x200B;**ライブラリ**&#x200B;を作成するか、既存の&#x200B;**ライブラリ**&#x200B;を選択して、新しく作成した&#x200B;**ルール**&#x200B;を追加します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/libraries.html?lang=ja#create-a-library)

1. **ライブラリ**&#x200B;から、「**開発用に保存およびビルド**」を選択します。

   ![](assets/configure_web_inapp_14.png)

