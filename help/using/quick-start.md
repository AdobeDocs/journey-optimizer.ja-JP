---
title: クイックスタート
description: Journey Optimizer クイックスタート
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: 71ab7369-fd84-46eb-95d2-941bd887d565
source-git-commit: c6592d16dc8bd9ea2bada4fc351c844985a1042f
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 40%

---

# クイックスタート {#cjm-quick-start}

## 開始の主な手順 {#cjm-key-steps}

[!DNL Adobe Journey Optimizer] では、既存コンテンツの読み込み、新しいコンテンツの設計、顧客プロファイルデータを使用したメッセージのパーソナライズ、メッセージをトリガーするイベントの作成、セグメントの定義、オーディエンスの絞り込み、複数チャネルメッセージの送信、レポートおよび監視ツール一式の利用が可能です。

組織に基づいて、複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

## 環境の準備と設定

[!DNL Adobe Journey Optimizer]の使用を開始する前に、環境の準備にいくつかの手順が必要です。

システム管理者は、製品プロファイルを&#x200B;**理解し、サンドボックス管理とチャネル設定の権限**を割り当てる必要があります。 また、サンドボックスを設定し、使用可能な製品プロファイルに対してサンドボックスを管理する必要があります。
その後、チームメンバーを製品プロファイルに割り当て、メッセージング用に**チャネル設定**&#x200B;を設定できます。

詳しくは、次のページを参照してください。

* **製品プロファイルと権限の概要**

* **ユーザー権限を** 設定し、チームメンバーにアクセス権を付与します。[詳細情報](../using/administration/permissions.md)

* **メッセージ[!DNL Adobe Experience Manager Assets Essentials]** 内のアセットと画像を管理するには、次の手順を実行します。へのアクセス権を必要とするユ [!DNL Assets Essentials] ーザーは、 **Assets Essentials Consumer Usersまたは** Assets Essentials UsersProductプロファイルの一部である必要があ **** ります。[詳細を読む](https://experienceleague.adobe.com/docs/experience-manager-assets-essentials/help/deploy-administer.html?lang=ja){target=&quot;_blank&quot;}

* **チャネルを設** 定し、電子メールおよびプッシュ通知の設定を定義します。[詳細情報](../using/configuration/get-started-configuration.md)

* **プリセットを定** 義し、ブランディングパラメーターを設定します。[詳細情報](../using/configuration/message-presets.md)

* **サンドボ** ックスを管理して、インスタンスを別々の仮想環境に分割します。[詳細情報](../using/administration/sandboxes.md)


## データの準備とジャーニーの設定

データ管理者は、データを&#x200B;**識別し、スキーマとデータセット**&#x200B;を作成して、データをAdobe Experience Platformに送信する必要があります。

ID名前空間と、プロファイルに対して有効なデータセットを作成し、セグメントとテストプロファイルを作成する手順については、以下の節で詳しく説明します。

* [Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;}で&#x200B;**データセット**&#x200B;をプレビューし作成する方法を説明します

* [Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja#manage-namespaces){target=&quot;_blank&quot;}で&#x200B;**ID名前空間**&#x200B;を作成する方法を説明します

* **テストプロファイル**&#x200B;を[で作成する方法については、このページ](../using/building-journeys/creating-test-profiles.md)を参照してください。

* **データ取り込み**&#x200B;について詳しくは、[Adobe Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください

* **オーディエンス**&#x200B;の定義、セグメントの作成、同意とプライバシーの管理の方法については、[このページ](../using/segment/about-segments.md)を参照してください。

また、ジャーニーでメッセージを送信するには、**[!UICONTROL データソース]**、**[!UICONTROL イベント]**、**[!UICONTROL アクション]**&#x200B;を設定する必要があります。 詳しくは、[この節](../using/configuration/about-data-sources-events-actions.md)を参照してください。

## メッセージ、オファー、ジャーニーの作成

ジャーニープラクティショナーとして、以下の節を参照して、ファーストジャーニーの設定、オファー、アセットの追加、メッセージの送信をおこないます。

* **メッセージの作成**：メッセージへのアクセス、メールおよびプッシュコンテンツの設計と読み込み、パーソナライゼーションとプレビューメッセージの追加をおこないます。[詳細を読む](create-message.md)

* **アセットのアップロード**：Adobe Experience Manager Assets Essentials を使用して、アセットや画像を管理します。[詳細を読む](assets-essentials.md)

* **オファーの追加**：Journey Optimizer Decision Management を使用して、パーソナライズされたオファーをメッセージに追加する。[詳細を読む](../using/offers/get-started/starting-offer-decisioning.md)

* **ジャーニーの作成**：メッセージの送信、コンテキストデータの活用、オーディエンスの絞り込み、複数手順のユースケースの設計と実行をおこないます。[詳細を読む](building-journeys/journey.md)

* **メッセージとジャーニーの監視**：メッセージ実行の制御、メッセージおよびジャーニーレポートの確認、配信品質指標のフォローアップを行います。 [詳細を読む](message-monitoring.md)
