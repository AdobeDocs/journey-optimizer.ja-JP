---
title: クイックスタート
description: Journey Optimizer クイックスタート
feature: 概要
topic: コンテンツ管理
role: User
level: Beginner
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 41%

---

# クイックスタート {#cjm-quick-start}

## 開始の主な手順 {#cjm-key-steps}

[!DNL Adobe Journey Optimizer]を使用すると、既存のメッセージコンテンツをインポートしたり、新しいコンテンツをデザインしたり、顧客プロファイルデータでメッセージをパーソナライズしたり、トリガーメッセージのイベントを作成したり、セグメントを定義してオーディエンスを絞り込んだりできます。

組織に基づいて、複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

### 前提条件 {#cjm-prerequisites}

[!DNL Adobe Journey Optimizer]の使用を開始する前に、次の操作が必要です。

* **ユーザー権限の設定**:にログインし [!DNL Adobe Journey Optimizer] て、チームメンバーにアクセス権を付与します。[詳細情報](../using/administration/permissions.md)

* **デプロイ[!DNL Adobe Experience Manager Assets Essentials]**:メッセージのアセットや画像を管理するには、組織にをデプロイ [!DNL Assets Essentials] し、へのアクセスを必要とするユーザーが、 [!DNL Assets Essentials]Assets Essentials Consumer Users(または **Assets Essentials** UsersProduct)プロファイルの一部であることを確認する必要がありま **** す。[詳細を表示](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html){target=&quot;_blank&quot;}

* **チャネルの設定**:eメール通知とプッシュ通知の設定を定義します。[詳細情報](../using/configuration/get-started-configuration.md)

* **プリセットを定義します**。プリセットを作成し、ブランディングパラメーターを設定します。[詳細情報](../using/configuration/message-presets.md)

* **データの特定とスキーマおよびデータセットの作成**：Adobe Experience Platform にデータを取り込み、プロファイルに対して有効な ID 名前空間とデータセットを作成し、セグメントを作成してプロファイルをテストします。

   * [Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;}でデータセットをプレビューして作成する方法を説明します

   * [Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces){target=&quot;_blank&quot;}でID名前空間を作成する方法を説明します

   * [このページ](../using/building-journeys/creating-test-profiles.md)でテストプロファイルを作成する方法を説明します。

   * データ取り込みについて詳しくは、[Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください


### 使用状況フロー

最初のジャーニーの設定とメッセージの送信については、次の節を参照してください。

* **メッセージの作成**：メッセージへのアクセス、メールおよびプッシュコンテンツの設計と読み込み、パーソナライゼーションとプレビューメッセージの追加をおこないます。[詳細を読む](create-message.md)

* **アセットのアップロード**：Adobe Experience Manager Assets Essentials を使用して、アセットや画像を管理します。[詳細を読む](assets-essentials.md)

* **オファーの追加**:Journey Optimizer Decision Managementを使用して、パーソナライズされたオファーをメッセージに追加します。[詳細情報](../using/offers/get-started/starting-offer-decisioning.md)

* **オーディエンスの定義**:セグメントの作成、イベントの作成、同意とプライバシーの管理を行います。[詳細を読む](../using/segment/about-segments.md)

* **ジャーニーの作成**：メッセージの送信、コンテキストデータの活用、オーディエンスの絞り込み、複数手順のユースケースの設計と実行をおこないます。[詳細を読む](building-journeys/journey.md)

* **メッセージとジャーニーの監視**:メッセージの実行、メッセージおよびジャーニーレポートの確認、フォローアップ配信品質の指標を制御します。[詳細情報](message-monitoring.md)
