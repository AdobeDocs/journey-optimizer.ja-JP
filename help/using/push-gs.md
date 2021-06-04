---
title: プッシュ設定の基本を学ぶ
description: プッシュ通知のデータフローとコンポーネントについて
source-git-commit: d2f17a273445a92f11eeb8968bd3082295c3aa09
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 2%

---

# プッシュ設定の基本を学ぶ{#get-started-push}

![](assets/do-not-localize/badge.png)

プッシュ通知は、特にアプリを積極的に使用していない場合に、いつでもモバイルアプリのユーザーにリーチするのに役立ちます。 プッシュ通知は、サービスに関する更新の提供、ユーザーに対するアクションの実行の依頼、新しい取引に対するユーザーへの警告など、様々な使用例の実現に役立ちます。 デバイスプラットフォームでは、エンドユーザーが通知を受信または表示する前にオプトインが必要です。 ユーザーのオプトインは、アプリが初めてインストールされた後、または必要に応じて後続のセッションまたはワークフローで起動された後に、早く受け取る場合があります。 [!DNL Journey Optimizer] はプッシュ通知をサポートし、関連性の高い通知を業界最高のスループット率で送信できます。Adobe Experience Cloudでのブランドのデータインサイトを活用するために、プッシュ通知には、パーソナライゼーションとジャーニーベースのコンテキストを含めることができます。

このページは、[!DNL Journey Optimizer]でのプッシュ通知に関連する主要なサービスとワークフローの設定と理解に役立ちます。

## AdobeJourney Optimizerでのプッシュ通知の設定

AdobeJourney Optimizerでプッシュ通知を送信するには、次の手順を実行する必要があります。

1. ドキュメントに従って、アプリでの[AdobeJourney OptimizerおよびAdobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/beta/adobe-journey-optimizer)の設定を取得します。
1. プッシュメッセージチャネル](configuration/message-presets.md)の[プリセットを作成します。

## プッシュ通知とAdobeJourney Optimizer

次の図は、関連するデータフローに関連するシステムおよびサービスを示しています。エンドツーエンドのサービスの観点から、プッシュ通知がどのように配信されるかを重点的に示しています。

![](assets/push-flow.png)

1. AppleのAPNsおよびGoogle FCMプッシュメッセージメッセージングサービスを使用したブランドモバイルアプリ（AndroidまたはiOS）の登録
1. メッセージングサービスは、プッシュトークンを生成します。これは、Journey Optimizerが、プッシュ通知を使用して特定のデバイスをターゲティングするために使用するAdobeの識別子です。
1. 以前に生成されたプッシュトークンはAdobe Experience Platformに渡され、リアルタイム顧客プロファイルと同期されます。これは、簡単に統合できるクライアントSDKでOOTBを実行します。
1. プッシュメッセージは、AdobeJourney Optimizerで作成され、メッセージプリセットに対してプッシュメッセージが作成されます
1. プッシュメッセージは、ジャーニーのオーケストレーションキャンバスに含めることができます
1. ジャーニーを公開すると、ジャーニー条件に基づく顧客プロファイルがプッシュ通知を受信する資格を得ます。プッシュメッセージペイロードは、この手順でパーソナライズされます
1. パーソナライズされたプッシュペイロードは、内部のプッシュメッセージ配信サービスに転送されます
1. 次に、この内部サービスは、メッセージに関連付けられたアプリの資格情報を検証し、
1. 最終配信用にAppleおよびGoogleのメッセージングサービスにメッセージを送信します
1. メッセージングサービスからのフィードバックは注目され、エラーと成功がジャーニーライブおよびグローバルレポートに記録されます
1. プッシュ通知はエンドユーザーデバイスに配信されます
1. エンドユーザーのプッシュ通知インタラクションは、SDK統合を介して、エンドユーザークライアントからエクスペリエンスイベントとして送信されます

## プッシュ通知における主要サービスの役割

* **プッシュ通知サービスプロ** バイダーは、リモートサーバーからモバイルアプリに通知を配信するコアコンポーネントWebサービスです。

   [!DNL Adobe Journey Optimizer]  は、AndroidとiOSの両方のプラットフォームをサポートし、その結果、次と統合されます。
   * [Firebase Cloud Messaging(FCM)](https://firebase.google.com/docs/cloud-messaging)  - Androidモバイルアプリに通知を送信します。
   * [Apple Push Notification Service(APNs)](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html)  - iOSモバイルアプリに通知を送信します。

* **Adobe Experience Platform** Mobile SDK:AndroidおよびiOS互換のSDKを介してモバイル用のクライアント側統合APIを提供します。SDKは、プッシュメッセージ専用の様々なAPIを公開するAdobeJourney Optimizer拡張機能を提供し、プッシュトークンの登録や、Adobe Experience Platformへのプッシュトラッキングイベントやその他のカスタムエクスペリエンスイベントの送信など、データフローを有効にします。 また、SDKは、他のAdobe Experience Cloudおよびサードパーティパートナー機能を有効にする、その他の様々な拡張機能も提供します。

   SDK統合には、次のようなAdobe Experience Platform [データ収集](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=ja)サービスのセットアップも必要です。

   * データがAdobe Experience Platformにフローされるプロファイルおよびエクスペリエンスイベントデータセットを設定するデータストリームの作成
   * クライアント側モバイルプロパティの作成と拡張機能の追加。 SDKは、これらの拡張機能と密接に統合され、シームレスなデータ収集エクスペリエンスを提供します。
   * モバイルアプリバンドル識別子とアプリの資格情報の登録

* **Adobe Experience Platformリアルタイム顧客プロファ**  イルは、Web、モバイル、CRM、サードパーティなど複数のチャネルのデータを組み合わせることで、各顧客の全体像を把握します。プロファイルを使用すると、顧客データを統合ビューに統合し、顧客とのやり取りごとに実用的なタイムスタンプ付きの説明を提供できます。 特定のアプリユーザーのプッシュトークンは、レコードデータとしてユーザーのプロファイルに対して保存されますが、プッシュ通知とのインタラクションは、時系列イベントデータとして追跡されます。 [Adobe Experience Platformリアルタイム顧客プロファイルの詳細](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)

* **[!DNL Adobe Journey Optimizer]** :上記のコンポーネントとのモバイルアプリ統合が確立され、Adobe Experience Platformの顧客プロファイルが作成されたら、AdobeJourney Optimizerでプッシュ通知の作成と調整をおこなって、ユーザーと関わり合うことができます。

## プッシュテクニカルセットアップおよび実践者ワークフロー

次の図は、プッシュデータフローのスケルトンを構成するコンポーネントの設定に関する様々な手順をエンドツーエンドで示しています。 アクション項目は、設定を実行する役割と設定するコンポーネントに基づいて分類されています。

![](assets/user-flow.png)


[!DNL Journey Optimizer]でプッシュチャネルを設定し、プッシュ通知を有効にする詳細な手順については、[このページ](push-configuration.md)を参照してください。
