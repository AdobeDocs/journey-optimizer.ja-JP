---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知と Adobe 旅オプティマイザー
description: プッシュ通知データのフローとコンポーネントについて
topic: Mobile
feature: Push
role: Admin
level: Intermediate
exl-id: 9718c4b6-2558-4dfd-9d8f-f8845def19ba
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# プッシュ通知と Adobe 旅オプティマイザー {#get-started-push}

このページでは、でプッシュ通知に関連する主要なサービスとワークフローを設定して理解するために [!DNL Journey Optimizer] 役立つ情報を提供します。 このページ ](create-push.md) で push 通知を作成する方法について [ 説明します。

このページ ](push-configuration.md) では、 [!DNL Adobe Journey Optimizer] プッシュチャンネルを設定する手順について詳しく説明して [ います。

次の図は、エンドツーエンドのサービスの視点から、プッシュ通知の配信方法が強調表示されている、関連するデータフローに関係するシステムおよびサービスを示しています。

![](assets/push-flow.png)

1. ご使用のブランドモバイルアプリケーション (Android または iOS) を Apple の APNs および Google FCM push messaging messaging サービスと共に登録します。
1. プッシュトークンは、メッセージサービスによって生成されます。これは、push 通知を使用して特定のデバイスをターゲットとするために使用される [!DNL Adobe Journey Optimizer] 識別子です。
1. 既に生成された push トークンは、Adobe エクスペリエンスプラットフォームに渡され、リアルタイムのカスタマープロファイルに同期されます。これは、OOTB の統合が容易なクライアント SDK と共に実行されます。
1. プッシュメッセージはで [!DNL Adobe Journey Optimizer] 作成され、push メッセージはチャンネルサーフェスに対して作成されます (メッセージプリセット)。
1. プッシュメッセージが Journeys のオーケストレーションキャンバスに含まれている可能性があります。
1. 道のりの出版時点では、旅条件に基づいたお客様のプロファイルが push 通知を受け取ることが認められるので、この手順でプッシュメッセージのペイロードがカスタマイズされます。
1. パーソナライズされたプッシュペイロードは、内部の push messaging 配信サービスに転送されます。
1. 次に、この内部サービスは、メッセージに関連付けられたアプリケーションの資格情報を検証します。
1. 最後に配信するために、Apple &amp; Google メッセージサービスにメッセージを送信します。
1. メッセージサービスからのフィードバックが表示されます。エラーと成功が記録され、ライブに対するライブレポートの記録がレポートされます。
1. プッシュ通知はエンドユーザーのデバイスに配信されます。
1. エンドユーザー向けプッシュ通知インタラクションは、エンドユーザークライアントから SDK 統合によって送信されます。

## プッシュ通知での重要なサービスの役割 {#roles-of-key-services}

* **プッシュ通知サービスプロバイダー** は、リモートサーバーからモバイルアプリケーションに通知を配信する、中心的なコンポーネント web サービスです。

   [!DNL Adobe Journey Optimizer]  Android と iOS の両方のプラットフォームをサポートし、次のような連携機能が組み込まれています。
   * [Google モバイルアプリに通知を送信するには、焼討 base Cloud Messaging (FCM) ](https://firebase.google.com/docs/cloud-messaging)
   * [Apple Push Notification Service (APNs) ](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html) -iOS モバイルアプリに通知を送信するには

* **Adobe エクスペリエンス Platform Mobile SDK** では、Android および iOS 互換の sdk を使用して、モバイルに対するクライアントサイド統合 api を提供しています。 SDK には、push messaging 向けに様々な Api が公開される拡張機能が [!DNL Adobe Journey Optimizer] 用意されています。この機能を使用すると、プッシュトークンの登録、プッシュトラッキングイベント、その他のカスタムエクスペリエンスイベントを Adobe エクスペリエンスプラットフォームに送信するような場合でも、データフローが有効になります。 また、SDK には、他の Adobe エクスペリエンスクラウドや、サードパーティのパートナー機能を可能にする拡張機能が他にも多数用意されています。

   また、SDK 統合には、次のような Adobe エクスペリエンスプラットフォーム [ データコレクション ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) の設定 {target = &quot;_blank&quot;} サービスが必要です。

   * データが Adobe エクスペリエンスプラットフォームへ流れるプロファイリングとエクスペリエンスイベントデータセットを設定するためのデータストリームの作成
   * クライアント側モバイルプロパティを作成し、拡張機能を追加します。 SDK では、これらの拡張機能と緊密に統合され、データを収集するための操作性が提供されています。
   * モバイルアプリバンドル id とアプリ資格情報を登録しています

* **Adobe エクスペリエンスプラットフォームのリアルタイムのカスタマープロファイル**  によって、web、mobile、CRM、サードパーティなどの複数のチャネルのデータを組み合わせることによって、個々の顧客の全体像を把握することができます。 プロファイルによって、お客様のデータを統合ビューに統合することができます。これは、お客様のあらゆる操作についてアクション可能なタイムスタンプを提供します。 指定された app users の push トークンはレコードデータとして格納されますが、ユーザーがプッシュ通知に対して行う操作は時系列イベントデータとして追跡されます。 [Adobe Experience Platform のリアルタイムのカスタマープロファイル ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html) について詳しくは、{target = &quot;_blank&quot;} を参照してください。

* **[!DNL Adobe Journey Optimizer]** : 上記のコンポーネントとモバイルアプリの統合が適切に実行され、Adobe エクスペリエンスプラットフォームにお客様のプロファイルがある場合は、を使用して、ユーザーとともに参加できるように、で [!DNL Adobe Journey Optimizer] プッシュ通知を作成して調整することができます。

## 技術設定および実践用のワークフローをプッシュ {#push-technical-setup}

次の図は、push データフローのスケルトンを形成するコンポーネントを設定する際に、エンドツーエンドで行うさまざまな手順を示しています。 アクションアイテムは、設定対象のコンポーネントを実行する役割に基づいて分類されています。

![](assets/user-flow.png)
