---
title: メールのレンダリングのテスト
description: 詳しくは、メールのレンダリングをテストする方法を参照してください。
feature: Preview
role: User
level: Beginner
exl-id: fe077a8b-9788-4723-a1e7-32816a879af9
feature_v2: []
subfeature_v2:
  - id: f8d2e9f0-69c9-40cd-890f-71336c8dfff7
source-git-commit: c3c86c6eb2e3717ce348ac562899c4f18dc7007d
workflow-type: tm+mt
source-wordcount: 166
ht-degree: 84%

---

# メールのレンダリングのテスト {#email-rendering}

**Litmus** アカウントを [!DNL Journey Optimizer] に使用すると、よく使うメールクライアントで&#x200B;**メールのレンダリング**&#x200B;を即座にプレビューできます。 すべてのインボックスでメールコンテンツが適切に表示され、正しく機能することを確認できます。

メールのレンダリングを確認するには、次の手順に従います。

1. メッセージのコンテンツを編集画面またはメールDesignerで、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、ドロップダウンから「**[!UICONTROL コンテンツをシミュレート（AEP プロファイル）]**」を選択します。

1. 「**[!UICONTROL メールをレンダリング]**」ボタンを選択します。

   ![](../email/assets/email-rendering-button.png)

1. 右上のセクションで、「**Litmus アカウントを接続**」をクリックします。

   ![](../email/assets/email-rendering-litmus.png)

1. 資格情報を入力し、ログインします。

   ![](../email/assets/email-rendering-credentials.png)

1. 「**テストを実行**」ボタンをクリックして、メールのプレビューを生成します。

1. 一般的なデスクトップ、モバイル、Web ベースのクライアントでメールの内容を確認します。

   ![](../email/assets/email-rendering-previews.png)

>[!CAUTION]
>
>**Litmus** アカウントを [!DNL Journey Optimizer] に接続する際は、テストメッセージが Litmus に送信されることに同意する必要があります。一度送信すると、これらのメールはアドビでは管理できなくなります。 その結果、テストメッセージに含まれる可能性のあるパーソナライゼーションデータも含め、Litmus データ保持メールポリシーがこれらのメールに適用されます。
