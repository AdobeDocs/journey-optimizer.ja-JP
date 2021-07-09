---
title: クイックスタート
description: Journey Optimizer クイックスタート
feature: 概要
topic: コンテンツ管理
role: User
level: Beginner
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# クイックスタート {#cjm-quick-start}

## 開始の主な手順 {#cjm-key-steps}

[!DNL Adobe Journey Optimizer] では、既存コンテンツの読み込み、新しいコンテンツの設計、顧客プロファイルデータを使用したメッセージのパーソナライズ、メッセージをトリガーするイベントの作成、セグメントの定義、オーディエンスの絞り込み、複数チャネルメッセージの送信、レポートおよび監視ツール一式の利用が可能です。

組織に基づいて、複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

### 前提条件 {#cjm-prerequisites}

 [!DNL Adobe Journey Optimizer] の使用を開始する前に、次の操作をおこなう必要があります。

* **ユーザー権限の設定**：[!DNL Adobe Journey Optimizer] にログインし、チームメンバーにアクセス権を与えます。[詳細を読む](../using/administration/permissions.md)

* **デプロイ[!DNL Adobe Experience Manager Assets Essentials]**:メッセージのアセットや画像を管理するには、組織にをデプロイ [!DNL Assets Essentials] し、へのアクセスを必要とするユーザーが、 [!DNL Assets Essentials]Assets Essentials Consumer Users(または **Assets Essentials** UsersProduct)プロファイルの一部であることを確認する必要がありま **** す。[詳細を表示](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target=&quot;_blank&quot;}

* **チャネルの設定**：メール通知とプッシュ通知の設定を定義する。[詳細を読む](../using/configuration/get-started-configuration.md)

* **プリセットの定義**：プリセットを作成し、ブランディングパラメーターを設定する。[詳細を読む](../using/configuration/message-presets.md)

* **データの特定とスキーマおよびデータセットの作成**：Adobe Experience Platform にデータを取り込み、プロファイルに対して有効な ID 名前空間とデータセットを作成し、セグメントを作成してプロファイルをテストする。

   * [Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja)では、データセットのプレビュー方法と作成方法を説明します。{target=&quot;_blank&quot;}

   * [Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces){target=&quot;_blank&quot;}でID名前空間を作成する方法を説明します

   * テストプロファイルの作成方法については、 [このページ](../using/building-journeys/creating-test-profiles.md)を参照してください。

   * データ取得について詳しくは、[Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja)を参照してください。{target=&quot;_blank&quot;}


### 使用状況フロー

最初のジャーニーの設定とメッセージの送信については、次の節を参照してください。

* **メッセージの作成**：メッセージへのアクセス、メールおよびプッシュコンテンツの設計と読み込み、パーソナライゼーションとプレビューメッセージの追加をおこないます。[詳細を読む](create-message.md)

* **アセットのアップロード**：Adobe Experience Manager Assets Essentials を使用して、アセットや画像を管理します。[詳細を読む](assets-essentials.md)

* **オファーの追加**：Journey Optimizer Decision Management を使用して、パーソナライズされたオファーをメッセージに追加する。[詳細を読む](../using/offers/get-started/starting-offer-decisioning.md)

* **オーディエンスの定義**：セグメントの作成、イベントの作成、同意とプライバシーの管理をおこないます。[詳細を読む](../using/segment/about-segments.md)

* **ジャーニーの作成**：メッセージの送信、コンテキストデータの活用、オーディエンスの絞り込み、複数手順のユースケースの設計と実行をおこないます。[詳細を読む](building-journeys/journey.md)

* **メッセージとジャーニーの監視**:メッセージの実行、メッセージおよびジャーニーレポートの確認、フォローアップ配信品質の指標を制御します。[詳細を読む](message-monitoring.md)
