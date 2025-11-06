---
solution: Journey Optimizer
product: journey optimizer
title: プッシュ通知のデザイン
description: Journey Optimizer で web プッシュ通知をデザインする方法について説明します
feature: Push
topic: Content Management
role: User
level: Beginner
hidefromtoc: true
hide: true
source-git-commit: 36056208cd1e435c4801bd178bdc5f2d74068dc5
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---

# Web プッシュ通知のデザイン {#design-push-notification}

>[!AVAILABILITY]
>
>現在、Journey Optimizer の web プッシュ通知では、**サイレント通知**&#x200B;機能と&#x200B;**コンテンツをシミュレート**&#x200B;機能をサポートしていませんが、今後使用できる予定です。

Web プッシュ通知キャンペーンやジャーニーを作成したら、要件に応じてそのコンテンツと構造のデザインに進むことができます。Web プッシュ通知を送信する前に、まず[チャネル設定](push-configuration-web.md)内でこのチャネルを設定する必要があります。

<!--
## Send a silent notification {#silent-notification}

A silent push notification (also called a background notification) is a hidden message sent to your web application without alerting the user.

To enable a silent notification, enable the **[!UICONTROL Silent Notification]** option. When this option is used, the notification is delivered directly to the application, and no alert, banner, or sound is shown to the user.

Use the **Custom Data** section to include additional information in the form of key-value pairs. 

![](assets/web-silent.png)
-->

## タイトルと本文 {#push-title-body}

メッセージを作成するには、「**[!UICONTROL タイトル]**」フィールドと「**[!UICONTROL 本文]**」フィールドをクリックします。パーソナライゼーションエディターを使用して、コンテンツの定義、[データのパーソナライズ](../personalization/personalize.md)、[動的コンテンツの追加](../personalization/get-started-dynamic-content.md)を行います。

「**[!UICONTROL AI アシスタントでテキストを編集]**」をクリックすると、Journey Optimizer AI アシスタントを使用してコンテンツを簡単に生成できます。

![](assets/web-design-body.png)

## クリック時の動作 {#on-click-behavior}

「**[!UICONTROL 本文クリック動作]**」フィールドを使用して、ユーザーが通知本文をクリックした際に発生する動作を決定するディープリンクを定義します。これにより、ユーザーを web アプリケーションの特定のページやセクションに直接送信できます。

![](assets/web-onclick.png)

## メディアの追加 {#add-media-push}

「**[!UICONTROL メディアを追加]**」フィールドにメディア URL を入力します。また、URL にパーソナライゼーショントークンを含めて、各ユーザーのコンテンツをカスタマイズすることもできます。

「![AI アシスタントでテキストを編集](assets/do-not-localize/Smock_ImageAdd_18_N.svg)」をクリックすると、Journey Optimizer AI アシスタントを使用してメディアをすばやく生成できます。

![](assets/web-media.png)

## ボタンの追加 {#add-buttons-push}

コンテンツにボタンを追加して、web プッシュ通知をインタラクティブにします。

ボタンは、デバイスがロック解除されている場合にのみ表示されます。画面がロックされている場合は、**[!UICONTROL タイトル]**&#x200B;と&#x200B;**[!UICONTROL メッセージ]**&#x200B;のみが表示されます。

「**[!UICONTROL ボタンを追加]**」オプションを使用して、次に示すように、各ボタンのラベルと関連するアクションを定義します。

* **[!UICONTROL ディープリンク]**：ユーザーをアプリ内の特定のビュー、セクション、タブにリダイレクトします。関連するフィールドにディープリンク URL を入力します。

* **[!UICONTROL Web URL]**：外部の web ページにユーザーをリダイレクトします。関連するフィールドに URL を入力します。

![](assets/push_buttons.png)

## カスタムデータ {#custom-data}

「**[!UICONTROL カスタムデータ]**」セクションでは、通知ペイロードにカスタムのキーと値のペアを追加できます。これらの値は、web アプリケーションで特定のアクションをトリガーすることや、ユーザーエクスペリエンスをカスタマイズするために使用できます。Adobe Experience Platform でのプッシュ通知の設定方法について詳しくは、[この節](push-gs.md)を参照してください。

![](assets/web-custom.png)

