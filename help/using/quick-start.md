---
title: クイックスタート
description: Journey Optimizer クイックスタート
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 71ab7369-fd84-46eb-95d2-941bd887d565
source-git-commit: 9c1edc8d79c58fcf4f2048b9fe81cd31ea621777
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 40%

---

# クイックスタート {#cjm-quick-start}

## 開始の主な手順 {#cjm-key-steps}

[!DNL Adobe Journey Optimizer] では、既存コンテンツの読み込み、新しいコンテンツの設計、顧客プロファイルデータを使用したメッセージのパーソナライズ、メッセージをトリガーするイベントの作成、セグメントの定義、オーディエンスの絞り込み、複数チャネルメッセージの送信、レポートおよび監視ツール一式の利用が可能です。

組織に基づいて、複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

## 環境の準備と設定

[!DNL Adobe Journey Optimizer] の使用を開始する前に、環境の準備にいくつかの手順が必要です。

システム管理者は、製品プロファイルを **理解し、サンドボックス管理とチャネル設定に対する権限** を割り当てる必要があります。 また、サンドボックスを設定し、使用可能な製品プロファイル用にサンドボックスを管理する必要もあります。
その後、チームメンバーを製品プロファイルに割り当て、メッセージング用に **チャネル設定** を設定できます。

詳しくは、次のページを参照してください。

* **ユーザー権限を** 設定し、チームメンバーにアクセス権を付与します。[詳細情報](../using/administration/permissions.md)

* **メッセージ[!DNL Adobe Experience Manager Assets Essentials]** 内のアセットと画像を管理するには、次のようにデプロイします。へのアクセス権を必要とするユ [!DNL Assets Essentials] ーザーは、 **Assets Essentials Consumer Users または** Assets Essentials UsersProduct プロ **ファイルの一部である必要が** あります。[詳しくは、Assets Essentialsのドキュメント](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html?lang=ja){target=&quot;_blank&quot;} を参照してください

* **チャネルを設** 定し、電子メールおよびプッシュ通知の設定を定義します。[詳細情報](../using/configuration/get-started-configuration.md)

* **プリセットを定** 義し、ブランディングパラメーターを設定します。[詳細情報](../using/configuration/message-presets.md)

* **サンドボ** ックスを管理して、インスタンスを別々の仮想環境に分割します。[詳細情報](../using/administration/sandboxes.md)


## データの準備とジャーニーの設定

データ管理者は、データを **識別し、データをAdobe Experience Platformに送信するスキーマとデータセット** を作成する必要があります。

ID 名前空間と、プロファイルに対して有効なデータセットを作成する手順、セグメントおよびテストプロファイルを作成する手順については、次の節で詳しく説明します。

* [Adobe Experience Platformのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;} で **データセット** をプレビューして作成する方法を説明します

* **ID 名前空間** を [Adobe Experience Platformのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces){target=&quot;_blank&quot;} で作成する方法を説明します

* **テストプロファイル** を [ このページ ](../using/building-journeys/creating-test-profiles.md) で作成する方法を説明します。

* **データ取り込み** について詳しくは、[Adobe Experience Platformのドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target=&quot;_blank&quot;} を参照してください

* **オーディエンスの定義**、セグメントの作成、同意とプライバシーの管理の方法については、[ このページ ](../using/segment/about-segments.md) を参照してください。

また、ジャーニーでメッセージを送信するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**、**[!UICONTROL アクション]** を設定する必要があります。 詳しくは、[この節](../using/configuration/about-data-sources-events-actions.md)を参照してください。

## メッセージ、オファー、ジャーニーの作成

ジャーニープラクティショナーは、次の節を参照して、最初のジャーニーの設定、オファーとアセットの追加、メッセージの送信をおこないます。

* **メッセージの作成**：メッセージへのアクセス、メールおよびプッシュコンテンツの設計と読み込み、パーソナライゼーションとプレビューメッセージの追加をおこないます。[詳細を読む](create-message.md)

* **アセットのアップロード**：Adobe Experience Manager Assets Essentials を使用して、アセットや画像を管理します。[詳細を読む](assets-essentials.md)

* **オファーの追加**：Journey Optimizer Decision Management を使用して、パーソナライズされたオファーをメッセージに追加する。[詳細を読む](../using/offers/get-started/starting-offer-decisioning.md)

* **ジャーニーの作成**：メッセージの送信、コンテキストデータの活用、オーディエンスの絞り込み、複数手順のユースケースの設計と実行をおこないます。[詳細を読む](building-journeys/journey.md)

* **メッセージとジャーニーの監視**：メッセージ実行の制御、メッセージおよびジャーニーレポートの確認、配信品質指標のフォローアップを行います。 [詳細を読む](message-monitoring.md)
