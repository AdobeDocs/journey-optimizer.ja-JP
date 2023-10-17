---
solution: Journey Optimizer
product: journey optimizer
title: メールのデザイン
description: メールの設計方法を学ぶ
feature: Email Design
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: メール, デザイン, Stock, アセット
exl-id: e4f91870-f06a-4cd3-98b7-4c413233e310
source-git-commit: 2eb5ac0a9220dfca7110082cd1bbf40afbcb8f40
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 100%

---

# メールデザインの基本を学ぶ {#get-started-content-design}

[!DNL Journey Optimizer] に既存のコンテンツを読み込むことも、コンテンツデザイン機能を活用することもできます。

* [!DNL Journey Optimizer] **メールデザイン機能**&#x200B;を使用して、レスポンシブなメールのデザインや読み込みを行います。[詳細情報](content-from-scratch.md)

* **Adobe Experience Manager Assets Essentials** を活用してメールを強化し、独自のアセットデータベースを作成および管理します。[詳細情報](../content-management/assets-essentials.md)

* **Adobe Stock の写真**&#x200B;を検索しコンテンツを作成し、メールデザインを向上します。[詳細情報](../content-management/stock.md)

* プロファイル属性に基づいてパーソナライズされたメッセージと動的メッセージを作成し、カスタマーエクスペリエンスを強化します。[パーソナライズ機能](../personalization/personalize.md)および[動的コンテンツ](../personalization/get-started-dynamic-content.md)の詳細をご覧ください。

➡️ [この機能をビデオで確認](#video)

## メールデザインのベストプラクティス {#best-practices}

メールを送信する際は、受信者がメールを転送する可能性があることを考慮することが重要です。これにより、メールのレンダリングで問題が発生する可能性があります。これは、転送に使用されるメールプロバイダーでサポートされていない可能性がある CSS クラスを使用する場合に特に当てはまります。例えば、モバイルデバイスで画像を非表示にするために「is-desktop-hidden」CSS クラスを使用している場合などです。

こうしたレンダリングの問題を最小限にするために、メールのデザイン構造をできるだけ簡単に保つことをお勧めします。デスクトップデバイスとモバイルデバイスの両方で適切に機能する単一のデザインを使用し、複雑な CSS クラスや、すべてのメールクライアントで完全にはサポートされない他のデザイン要素を使用しないようにします。これらのベストプラクティスに従うと、受信者による表示や転送の方法に関係なく、一貫して正しくメールをレンダリングできます。

## メールコンテンツを作成するための主な手順 {#key-steps}

ジャーニーまたはキャンペーンに[メールを追加](create-email.md)したら、メールコンテンツの作成を開始できます。

1. ジャーニーまたはキャンペーンの設定画面から、**[!UICONTROL コンテンツを編集]**&#x200B;画面に進み、E メールデザイナーにアクセスします。[詳細情報](create-email.md#define-email-content)

   ![](assets/email_designer_edit_email_body.png)

1. E メールデザイナーのホームページで、次のオプションからメールのデザイン方法を選択します。

   * E メールデザイナーのインターフェイスで&#x200B;**メールをゼロから設計**&#x200B;し、[Adobe Experience Manager Assets Essentials](../content-management/assets-essentials.md) の画像を活用します。メールコンテンツのデザイン方法については、[この節](content-from-scratch.md)を参照してください。

   * E メールデザイナーで直接 **Raw HTML をコーディングまたは貼り付け**&#x200B;ます。独自のコンテンツのコーディング方法については、[この節](code-content.md)を参照してください。

     >[!NOTE]
     >
     >キャンペーンでは、**[!UICONTROL コンテンツを編集]**&#x200B;画面から「**[!UICONTROL コードエディター]**」ボタンを選択することもできます。[詳細情報](create-email.md#define-email-content)

   * ファイルまたは .zip フォルダーから&#x200B;**既存の HTML コンテンツを読み込み**&#x200B;ます。メールコンテンツの読み込み方法については、[この節](existing-content.md)を参照してください。

   * 組み込みまたはカスタムテンプレートのリストから&#x200B;**既存のコンテンツを選択します**。メールテンプレートの操作方法については、[この節](../email/use-email-templates.md)を参照してください。

   ![](assets/email_designer_create_options.png)

1. メールコンテンツを定義し、パーソナライズしたら、コンテンツを書き出して、検証したり、後で使用したりできます。 「**[!UICONTROL HTML を書き出す]**」をクリックして、 コンピューターに HTML とアセットを含む zip ファイルを保存します。

   ![](assets/email_designer_export.png)

## チュートリアルビデオ {#video}

メッセージエディターでメールコンテンツを作成する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334150?quality=12)

A/B テストを行うようにコンテンツ実験を設定し、ビジネス目標を最大限に推進するメールコンテンツを探索する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419893)
