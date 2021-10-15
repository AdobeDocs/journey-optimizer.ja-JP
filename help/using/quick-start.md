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
ht-degree: 100%

---

# クイックスタート {#cjm-quick-start}

## 開始の主な手順 {#cjm-key-steps}

[!DNL Adobe Journey Optimizer] では、既存コンテンツの読み込み、新しいコンテンツの設計、顧客プロファイルデータを使用したメッセージのパーソナライズ、メッセージをトリガーするイベントの作成、セグメントの定義、オーディエンスの絞り込み、複数チャネルメッセージの送信、レポートおよび監視ツール一式の利用が可能です。

組織に基づいて、複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

## 環境の準備と設定

[!DNL Adobe Journey Optimizer] の使用を開始する前に、環境の準備にいくつかの手順が必要です。

システム管理者は、**製品プロファイルを把握し、サンドボックス管理とチャネル設定の権限を割り当てる**必要があります。 また、サンドボックスをセットアップし、使用可能な製品プロファイル用にサンドボックスを管理する必要もあります。
その後、チームメンバーを製品プロファイルに割り当て、メッセージングの**チャネル設定をセットアップ**&#x200B;できます。

詳しくは、次のページを参照してください。

* **ユーザー権限を設定**&#x200B;し、チームメンバーにアクセス権を与えます。[詳細情報](../using/administration/permissions.md)

* **[!DNL Adobe Experience Manager Assets Essentials]** をデプロイして、メッセージ内のアセットと画像を管理します。[!DNL Assets Essentials] へのアクセスを必要とするユーザーは、**Assets Essentials コンシューマーユーザー**&#x200B;または **Assets Essentials ユーザー**&#x200B;の製品プロファイルに登録されている必要があります。詳しくは、[Assets Essentials のドキュメント](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

* **チャネルを設定**&#x200B;し、メールおよびプッシュ通知の設定を定義します。[詳細情報](../using/configuration/get-started-configuration.md)

* **プリセットを定義**&#x200B;し、ブランディングパラメーターを設定します。[詳細情報](../using/configuration/message-presets.md)

* **サンドボックスを管理** して、インスタンスを別個の仮想環境に分割します。[詳細情報](../using/administration/sandboxes.md)


## データの準備とジャーニーの設定

データ管理者は、**データを特定しスキーマとデータセットを作成**&#x200B;して、データを Adobe Experience Platform に取り込む必要があります。

ID 名前空間および、プロファイルに対して有効なデータセットを作成する手順や、セグメントおよびテストプロファイルを作成する手順について詳しくは、下記の節を参照してください。

* **データセット**&#x200B;のプレビュー方法と作成方法：[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;}

* **ID 名前空間**&#x200B;の作成方法： [Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces){target=&quot;_blank&quot;}

* **テストプロファイル**&#x200B;の作成方法：[このページ](../using/building-journeys/creating-test-profiles.md)

* **データ取り込み**&#x200B;の詳細：[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target=&quot;_blank&quot;}

* **オーディエンスの定義**、セグメントの作成、同意とプライバシーの管理の方法：[このページ](../using/segment/about-segments.md)

また、ジャーニーでメッセージを送信するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**&#x200B;および&#x200B;**[!UICONTROL アクション]**&#x200B;を設定する必要があります。 詳しくは、[この節](../using/configuration/about-data-sources-events-actions.md)を参照してください。

## メッセージ、オファーおよびジャーニーの作成

 ジャーニー実務担当者は、下記の節を参照して、最初のジャーニーのセットアップ、オファーとアセットの追加、メッセージの送信を行います。

* **メッセージの作成**：メッセージへのアクセス、メールおよびプッシュコンテンツの設計と読み込み、パーソナライゼーションとプレビューメッセージの追加をおこないます。[詳細を読む](create-message.md)

* **アセットのアップロード**：Adobe Experience Manager Assets Essentials を使用して、アセットや画像を管理します。[詳細を読む](assets-essentials.md)

* **オファーの追加**：Journey Optimizer Decision Management を使用して、パーソナライズされたオファーをメッセージに追加する。[詳細を読む](../using/offers/get-started/starting-offer-decisioning.md)

* **ジャーニーの作成**：メッセージの送信、コンテキストデータの活用、オーディエンスの絞り込み、複数手順のユースケースの設計と実行をおこないます。[詳細を読む](building-journeys/journey.md)

* **メッセージとジャーニーの監視**：メッセージ実行の制御、メッセージおよびジャーニーレポートの確認、配信品質指標のフォローアップを行います。 [詳細を読む](message-monitoring.md)
