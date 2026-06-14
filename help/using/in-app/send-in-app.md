---
title: アプリ内通知の確認および送信
description: Journey Optimizer でアプリ内メッセージを確認および送信する方法を学ぶ
feature: In App
topic: Content Management
role: User
level: Beginner
keywords: アプリ内, メッセージ, 作成, 開始
exl-id: 9e9c235a-b78c-4669-af82-822b6f1e6fca
TQID: https://experienceleague.adobe.com/lInGr6DN0-ED3ouErpV09-9ovLvOL1oHiSZEO-NBA7c
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2:
  - id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7
  - id: cc5c44e2-54a1-4927-b794-442cd87d8f74
  - id: c96d2aa5-76a2-443d-8d23-5de95577c909
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 686aa52541f2790d6d9853f31dd2a5c1b22c4b16
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 81%

---

# アプリ内通知の確認および送信 {#create-in-app}

>[!BEGINSHADEBOX]

**このページ：** オーディエンスに送信する前に、Adobe Journey Optimizerでアプリ内メッセージをプレビュー、テスト、レビュー、アクティベートする方法を説明します。

>[!ENDSHADEBOX]

## デバイスでのプレビュー {#preview-device}

すべてのユーザーに公開される前にアプリ内通知を確認する場合は、特定のデバイスでプレビューできます。 この機能を使用すると、選択したデバイスで意図したとおりに通知が表示され、機能するようになり、オーディエンスのユーザーエクスペリエンスが向上します。

手順は次のとおりです。

1. 「**[!UICONTROL デバイスでプレビュー]**」をクリックします。

   ![](assets/in_app_create_6.png)

1. **[!UICONTROL デバイスに接続]**&#x200B;ウィンドウから、「**[!UICONTROL 開始]**」をクリックします。

1. アプリケーションの&#x200B;**[!UICONTROL ベース URL]** を入力し、「**[!UICONTROL 次へ]**」をクリックします。

   ![](assets/in_app_create_7.png)

1. デバイスで QR コードをスキャンし、表示された PIN コードを入力します。

アプリ内メッセージをデバイスで直接トリガーできるようになり、実際のデバイスでメッセージをプレビューし、レビューできます。

## テストプロファイルでプレビュー {#simulate}

アプリ内メッセージを定義したら、次のいずれかのシミュレーションメソッドを使用してプレビューできます。

* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックして、サンプル入力データまたはAI自動生成を使用してコンテンツのバリエーションをテストします。 [コンテンツバリエーションのシミュレート方法を学ぶ](../test-approve/simulate-sample-input.md)
* 「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択して、テストプロファイルでプレビューし、テストプロファイルを追加してメッセージを確認します。

テストプロファイルの選択およびコンテンツのプレビュー方法について詳しくは、「[コンテンツ管理](../content-management/preview-test.md)」の節を参照してください。

## アプリ内通知のレビューとアクティブ化{#in-app-review}

>[!IMPORTANT]
>
> キャンペーンが承認ポリシーの対象となっている場合、アプリ内通知を送信できるようにするには、承認をリクエストする必要があります。 [詳細情報](../test-approve/gs-approval.md)

アプリ内メッセージを作成し、そのコンテンツを定義してパーソナライズしたら、そのメッセージをレビューしてアクティブ化できます。

手順は次のとおりです。

1. 「**[!UICONTROL アクティブ化するレビュー]**」ボタンを使用して、メッセージの概要を表示します。

   概要では、必要に応じてキャンペーンを変更し、パラメーターが正しくないか、または見つからないかを確認できます。

   ![](assets/in_app_create_5.png)

1. キャンペーンが正しく設定されていることを確認してから、「**[!UICONTROL アクティブ化]**」をクリックします。

これで、キャンペーンがアクティブ化されました。 キャンペーンで設定されたアプリ内通知は、すぐに送信されるか、指定日に送信されます。

送信したら、キャンペーンまたはジャーニーレポート内でアプリ内メッセージの影響を測定できます。 レポートについて詳しくは、[この節](../reports/campaign-global-report-cja-inapp.md)を参照してください。

**関連トピック：**

* [アプリ内メッセージの作成](create-in-app.md)
* [アプリ内メッセージのデザイン](design-in-app.md)
* [アプリ内レポート](../reports/campaign-global-report-cja-inapp.md)
* [アプリ内設定](inapp-configuration.md)
