---
title: コンテンツのプレビューとテスト
description: コンテンツのプレビューとテスト方法について説明します。
feature: Preview, Proofs
role: User
level: Beginner
exl-id: 736fc861-17f2-47b7-8635-9afd261ea3a8
source-git-commit: feae2cb9d0bed35f12eb117cf2969c9290ebc06f
workflow-type: tm+mt
source-wordcount: '309'
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

## コンテンツのプレビューとテストについて {#about}

コンテンツを定義したら、テストプロファイルを使用して、メッセージを送信する前にそのコンテンツを[プレビュー](preview.md)できます。これは、コンテンツが正確であると同時に、コンテンツとパーソナライゼーション設定の両方にエラーがないことを確認するための重要な手順です。

また、テストと検証のために特定の受信者または購読者にメールメッセージの[テスト配信を送信](proofs.md)（配達確認）したり、一般的なデスクトップ、モバイル、web ベースのクライアントで[レンダリングを確認](rendering.md)したりすることもできます。

これらのアクションはすべて、「**[!UICONTROL コンテンツをシミュレート]**」ボタンを使用して実行できます。このボタンには、メッセージのコンテンツを編集画面からアクセスするか、メールチャネルのメールデザイナーや web チャネルの web デザイナーからアクセスできます。

![](../email/assets/email-preview-button.png)

>[!CAUTION]
>
>メッセージをプレビューしたり、配達確認を送信したりすると、プロファイルのパーソナライゼーションデータのみが表示されます。イベント情報などのコンテキストデータに基づくパーソナライゼーションは、ジャーニーのコンテキストでのみテストできます。[こちらのユースケース](../personalization/personalization-use-case.md)では、パーソナライゼーションのテスト方法を説明します。

➡️ メールのプレビューと配達確認の方法については、[このビデオ](#video-preview)をご覧ください

## 前提条件 {#prerequisites}

コンテンツをシミュレートするには、**[!DNL Content Library Manager]** 製品プロファイルに含まれる **[!DNL Manage Simulate Content]** 権限が必要です。[詳細情報](../administration/ootb-product-profiles.md#content-library-manager)。

また、メッセージのプレビューを行うには、テストプロファイルも使用可能にしておく必要があります。[詳しくは、テストプロファイルの作成方法を参照してください](../audience/creating-test-profiles.md)

## チュートリアルビデオ {#video-preview}

複数のインボックスをまたいでメールのレンダリングをテストする方法、パーソナライズされたメールをテストプロファイルに照らしてプレビューする方法、および配達確認を送信する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334239?quality=12)
