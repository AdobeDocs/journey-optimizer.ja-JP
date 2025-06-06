---
title: コンテンツのプレビューとテスト
description: コンテンツのプレビューとテスト方法について説明します。
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 736fc861-17f2-47b7-8635-9afd261ea3a8
source-git-commit: aa28d13b2ad874e4dc61510bfdc250415e8e8be1
workflow-type: ht
source-wordcount: '500'
ht-degree: 100%

---

# コンテンツのプレビューとテスト {#preview-test}

>[!CONTEXTUALHELP]
>id="ac_preview_testprofiles"
>title="コンテンツのレンダリング方法の確認"
>abstract="コンテンツを定義したら、テストプロファイルを使用してプレビューし、使用しているチャネルに従ってレンダリングが正しいかどうかを確認できます。"

>[!CONTEXTUALHELP]
>id="ajo_preview_simulate"
>title="コンテンツのレンダリング方法の確認"
>abstract="コンテンツを定義したら、プレビューし、使用しているチャネルに従ってレンダリングが正しいかどうかを確認できます。"

コンテンツを定義したら、メッセージを送信する前にそのコンテンツをプレビューできます。これは、コンテンツが正確であると同時に、コンテンツとパーソナライゼーション設定の両方にエラーがないことを確認するための重要な手順です。

また、テストと検証のために特定の受信者または購読者にメールメッセージのテスト配信を送信したり、一般的なデスクトップ、モバイル、web ベースのクライアントでレンダリングを確認したりすることもできます。

これらのアクションはすべて、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して実行できます。このボタンには、メッセージのコンテンツ編集画面からアクセスするか、メールチャネルのE メールデザイナーや web チャネルの web デザイナーからアクセスできます。

![](../email/assets/email-preview-button.png)

## テストプロファイルデータまたはサンプル入力データを使用したテスト {#methods}

Journey Optimizer には、コンテンツをテストするための次の 2 つのエクスペリエンスがあります。

* **テストプロファイルデータを使用したコンテンツのテスト**

  テストプロファイルを使用すると、コンテンツをプレビューしたり、メール本配信前確認を送信したり、メールのレンダリングを確認したりできます。パーソナライズされたフィールドを追加した場合は、テストプロファイルデータを使用して、その表示方法を確認できます。詳しくは、次の節を参照してください。

  ➡️ [テストプロファイルの選択](test-profiles.md)
➡️ [テストプロファイルを使用したプレビュー](preview.md)
➡️ [メール本配信前確認の送信](proofs.md)
➡️ [メールのレンダリングの確認](rendering.md)
➡️ [メールのプレビューと本配信前確認（ビデオ）](#video-preview)

* **サンプル入力データを使用したコンテンツバリエーションのテスト**

  [!DNL Journey optimizer] を使用すると、CSV／JSON ファイルからアップロードした、または手動で追加したサンプル入力データを使用して、コンテンツの様々なバリエーションの本配信前確認をプレビューおよび送信できます。

  パーソナライズ機能のコンテンツで使用されるすべてのプロファイル属性は、システムによって自動的に検出され、テストで複数のバリアントを作成するのに使用できます。

  ➡️ [コンテンツのバリエーションをシミュレート](../test-approve/simulate-sample-input.md)

## 必読

* **必要な権限** - **[!DNL Content Library Manager]** 製品プロファイルに含まれる **[!DNL Manage Simulate Content]** 権限が必要です。[詳細情報](../administration/ootb-product-profiles.md#content-library-manager)

  配達確認を送信するには、メールに関連付けられた特定のリソース（キャンペーンまたはジャーニー）に対する&#x200B;**承認および公開**&#x200B;権限を持っている必要があります。また、ジャーニーで配達確認を送信するには、**ジャーニーを公開**&#x200B;権限も必要です。[詳しくは、権限を参照してください](../administration/ootb-permissions.md)。

* **コンテキストデータを使用したパーソナライゼーション** - メッセージをプレビューしたり、本配信前確認を送信したりすると、プロファイルのパーソナライゼーションデータのみが表示されます。イベント情報などのコンテキストデータに基づくパーソナライゼーションは、ジャーニーのコンテキストでのみテストできます。方法について詳しくは、[このユースケース](../personalization/personalization-use-case.md)を参照してください。

* **複数の条件付きバリアントを含むコンテンツのプレビュー** - 複数の条件付きバリアントを含むメールの本配信前確認をシミュレートまたはレンダリングする際、Journey Optimizer ではより多くの処理時間が必要になる場合があります。タイムアウトやエラーメッセージが発生した場合は、バリアントの合計数を減らすか、条件ルールを簡素化することを検討してください。条件付きコンテンツについて詳しくは、[このページ](../personalization/dynamic-content.md)を参照してください。

## チュートリアルビデオ {#video-preview}

テストプロファイルを使用して、複数のインボックスにわたってメールのレンダリングをテストする方法、パーソナライズされたメールをテストプロファイルに対してプレビューする方法、配達確認を送信する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3430339?quality=12&captions=jpn)
