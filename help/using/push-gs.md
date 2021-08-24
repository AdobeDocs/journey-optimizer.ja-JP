---
title: プッシュ設定の概要
description: プッシュ通知のデータフローとコンポーネントについて
feature: アプリケーション設定, プッシュ
role: Admin
level: Intermediate
source-git-commit: 1b11ff3848434a4cac1ca17318950481f20537c8
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 100%

---

# プッシュ設定の概要 {#get-started-push}

プッシュ通知は、モバイルアプリのユーザー、特にアプリを積極的に使用していないユーザーにいつでもリーチするのに役立ちます。プッシュ通知は、サービスに関するアップデートのお知らせ、ユーザーに対するアクションの実行の依頼、新しい取引に対するユーザーへの警告など、様々なユースケースの実現に役立ちます。 デバイスプラットフォームでは、エンドユーザーが通知を受信または表示する前にオプトインが必要です。 ユーザーのオプトインは、アプリを初めてインストールした後、または必要に応じて後続のセッションまたはワークフローでアプリを起動後、なるべく早く受け取る場合があります。 [!DNL Journey Optimizer] はプッシュ通知をサポートし、関連性の高い通知を業界最高のスループット率で送信できます。Adobe Experience Cloud でのブランドのデータインサイトを活用するために、プッシュ通知には、パーソナライゼーションとジャーニーベースのコンテキストを含めることができます。

このページは、[!DNL Journey Optimizer] でのプッシュ通知に関連する主要なサービスとワークフローの設定と理解に役立ちます。

[!DNL Adobe Journey Optimizer] でプッシュチャネルを設定する手順について詳しくは、[このページ](push-configuration.md)を参照してください。

## プッシュ通知と [!DNL Adobe Journey Optimizer]

次の図は、関連付けられたデータフローを使用するシステムおよびサービスを示しています。エンドツーエンドのサービスの観点から、プッシュ通知がどのように配信されるかを重点的に示しています。

![](assets/push-flow.png)

1. Apple の APNs および Google FCM プッシュメッセージのメッセージサービスを使用したブランドモバイルアプリ（Android または iOS）の登録
1. メッセージサービスがプッシュトークンを生成します。プッシュトークンは、[!DNL Adobe Journey Optimizer] で特定のデバイスをプッシュ通知のターゲットとするために使用される識別子です。
1. 生成済みのプッシュトークンが Adobe Experience Platform に渡され、リアルタイム顧客プロファイルと同期されます。これは、統合しやすいクライアント SDK を使用して標準で実行されます。
1.  [!DNL Adobe Journey Optimizer]で、プッシュメッセージがメッセージプリセットに対して作成されます
1. プッシュメッセージは、ジャーニーのオーケストレーションキャンバスに含めることができます
1. ジャーニーを公開すると、ジャーニー条件に基づく顧客プロファイルがプッシュ通知を受信する資格を得ます。プッシュメッセージペイロードは、この手順でパーソナライズされます。
1. パーソナライズされたプッシュペイロードは、内部のプッシュメッセージ配信サービスに転送されます
1. 次に、この内部サービスは、メッセージに関連付けられたアプリの資格情報を検証し、
1. 最終配信用に Apple および Google のメッセージサービスにメッセージを送信します
1. メッセージサービスからのフィードバックは記録され、エラーと成功はジャーニーのライブおよびグローバルレポートに記録されます
1. プッシュ通知はエンドユーザーのデバイスに配信されます
1. エンドユーザーのプッシュ通知インタラクションは、SDK 統合を介して、エンドユーザークライアントからエクスペリエンスのイベントとして送信されます

## プッシュ通知における主要サービスの役割

* **プッシュ通知サービスプロバイダー**&#x200B;は、リモートサーバーからモバイルアプリに通知を配信するコアコンポーネント Web サービスです。

   [!DNL Adobe Journey Optimizer] は、Android と iOS の両方のプラットフォームをサポートし、その結果、次と統合されます。
   * [Firebase Cloud Messaging（FCM）](https://firebase.google.com/docs/cloud-messaging) - Android モバイルアプリに通知を送信します。
   * [Apple Push Notification Service（APN）](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html) - iOS モバイルアプリに通知を送信します。

* **Adobe Experience Platform Mobile SDK** は Android および iOS 互換の SDK を介してモバイル用のクライアントサイド統合 API を提供します。SDK に用意されている [!DNL Adobe Journey Optimizer] 拡張機能は、プッシュメッセージ専用の様々な API を公開し、プッシュトークンの登録や、プッシュトラッキングイベントまたはその他の任意のカスタムエクスペリエンスイベントの Adobe Experience Platform への送信といったデータフローを可能にします。また、SDK は、他の Adobe Experience Cloud およびサードパーティパートナー機能を有効にするその他の各種拡張機能も提供します。

   SDK 統合には、次のような Adobe Experience Platform [データ収集](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=ja){target=&quot;_blank&quot;}サービスのセットアップも必要です。

   * Adobe Experience Platform にデータが取り込まれる、プロファイルおよびエクスペリエンスイベントデータセットを設定するデータストリームの作成
   * クライアントサイドモバイルプロパティの作成と拡張機能の追加。 SDK は、これらの拡張機能と密接に統合し、シームレスなデータ収集エクスペリエンスを提供します。
   * モバイルアプリバンドル識別子とアプリの資格情報の登録

* **Adobe Experience Platform リアルタイム顧客プロファイル**&#x200B;は、Web、モバイル、CRM、サードパーティなど複数のチャネルのデータを組み合わせることで、各顧客の全体像を把握します。プロファイルを使用すると、個別の顧客データを統合ビューに表示し、顧客インタラクションごとに実用的なタイムスタンプ付きの説明を提供できます。特定のアプリユーザーのプッシュトークンは、レコードデータとしてユーザーのプロファイルに保存されますが、プッシュ通知とのインタラクションは、時系列イベントデータとして追跡されます。[Adobe Experience Platform リアルタイム顧客プロファイルの詳細](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target=&quot;_blank&quot;}。

* **[!DNL Adobe Journey Optimizer]**：上記のコンポーネントとのモバイルアプリ統合が確立され、Adobe Experience Platform に顧客プロファイルが作成されたら、[!DNL Adobe Journey Optimizer] でプッシュ通知の作成と調整を行って、ユーザーのエンゲージメントを促進することができます。

## プッシュテクニカルセットアップおよび実践者ワークフロー

次の図は、プッシュデータフローの骨格を構成するコンポーネントの設定に関する様々な手順をエンドツーエンドで示しています。 アクション項目は、設定を実行する役割と設定するコンポーネントに基づいて分類されています。

![](assets/user-flow.png)
