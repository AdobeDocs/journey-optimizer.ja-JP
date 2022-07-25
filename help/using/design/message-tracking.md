---
title: メッセージのトラッキング
description: リンクを追加し送信済みメッセージをトラッキングする方法を説明します
feature: Monitoring
topic: Content Management
role: User
level: Intermediate
exl-id: 689e630a-00ca-4893-8bf5-6d1ec60c52e7
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 87%

---

# リンクの追加とメッセージのトラッキング {#tracking}

[!DNL Journey Optimizer] を使用すると、受信者の行動を監視するために、コンテンツにリンクを追加し送信済みメッセージをトラッキングすることができます。

## トラッキングの有効化 {#enable-tracking}

E メールメッセージレベルでトラッキングを有効にするには、 **[!UICONTROL メール開封数]** および/または **[!UICONTROL メールをクリック]** オプション [メッセージの作成](../messages/get-started-content.md).

![](assets/message-tracking.png)

>[!NOTE]
>
>デフォルトでは、両方のオプションが有効になっています。

これにより、次の方法で受信者の行動を追跡できます。

* **[!UICONTROL メール開封数]**:開封されたメッセージ。
* **[!UICONTROL メールをクリック]**:E メール内のリンクのクリック数。

## リンクの挿入 {#insert-links}

メッセージをデザインする際に、リンクをコンテンツに追加できます。

>[!NOTE]
>
>[トラッキングが有効](#enable-tracking)になっている場合、メッセージコンテンツに含まれるすべてのリンクがトラッキングされます。

メールコンテンツにリンクを挿入するには、次の手順に従います。

1. 要素を選択し、コンテキストツールバーの「**[!UICONTROL リンクを挿入]**」をクリックします。

   ![](assets/message-tracking-insert-link.png)

1. 作成するリンクのタイプを選択します。

   * **[!UICONTROL 外部リンク]**：外部 URL へのリンクを挿入します。

   * **[!UICONTROL ランディングページ]**：ランディングページへのリンクを挿入します。詳しくは、[この節](../landing-pages/get-started-lp.md)を参照してください。

   * **[!UICONTROL ワンクリックオプトアウト]**：ユーザーがオプトアウトの確認を求められることなく、コミュニケーションを素早く購読解除できるリンクを挿入します。詳しくは、[この節](../messages/consent.md#one-click-opt-out)を参照してください。

   * **[!UICONTROL 外部のオプトイン／購読]**：ブランドからのコミュニケーションの受信を同意するリンクを挿入します。

   * **[!UICONTROL 外部オプトアウト／購読解除]**：ブランドからのコミュニケーションの受信を解除するリンクを挿入します。オプトアウト管理の詳細については、[この節](../messages/consent.md#opt-out-management)を参照してください。

   * **[!UICONTROL ミラーページ]**：web ブラウザーにメールコンテンツを表示するためのリンクを挿入します。詳しくは、[この節](#mirror-page)を参照してください。

   ![](assets/message-tracking-links.png)

1. リンクをパーソナライズできます。パーソナライズされた URL について詳しくは、[この節](../personalization/personalization-syntax.md#perso-urls)を参照してください。

1. 変更を保存します。

1. リンクを作成した後も、右側の「**[!UICONTROL コンポーネント設定]**」ペインから変更できます。


   * リンクを編集してタイプを変更できます。
   * リンクに下線を引くかどうかは、対応するオプションをオンにすることで選択できます。

   ![](assets/message-tracking-link-settings.png)

>[!NOTE]
>
>マーケティングタイプの電子メールメッセージには、[オプトアウトリンク](../messages/consent.md#opt-out-management)を含める必要があります。これはトランザクションメッセージには必要ありません。メッセージカテゴリ (**[!UICONTROL マーケティング]** または **[!UICONTROL トランザクション]**) が [チャンネル表面](../configuration/message-presets.md#email-type) （例：メッセージプリセット）レベルとタイミング [メッセージの作成](../messages/get-started-content.md#create-new-message).

## ミラーページへのリンク {#mirror-page}

ミラーページは、web ブラウザーを使用してオンラインでアクセス可能な HTML ページです。その内容はメールの内容と同じです。

メールにミラーページへのリンクを追加するには、[リンクを挿入](#insert-links)し、リンクのタイプとして「**[!UICONTROL ミラーページ]**」を選択します。

![](assets/message-tracking-mirror-page.png)

ミラーページが自動的に作成されます。

>[!NOTE]
>
>自動生成されたリンクは編集できません。

メールが送信され、受信者がミラーページのリンクをクリックすると、メールの内容がデフォルトの web ブラウザーに表示されます。

>[!NOTE]
>
>テストプロファイルに送信される[配達確認](preview.md#send-proofs)では、ミラーページへのリンクはアクティブになっていません。最終的なメッセージでのみアクティブ化されます。

ミラーページの保持期間は 60 日です。この期間が経過すると、ミラーページは使用できなくなります。

## トラッキングの管理 {#manage-tracking}

[E メールデザイナー](create-email-content.md)を使用すると、追跡する URL を管理できます（各リンクのトラッキングタイプの編集など）。

1. 左側のペインの「**[!UICONTROL リンク]**」アイコンをクリックし、追跡するコンテンツのすべての URL のリストを表示します。


   このリストを使用すると、一元的なビューを表示したり、メールコンテンツ内の各 URL を見つけたりできます。

1. リンクを編集するには、対応する鉛筆アイコンをクリックします。

   ![](assets/message-tracking-edit-links.png)

1. 必要に応じて、「**[!UICONTROL トラッキングタイプ]**」を変更できます。

   ![](assets/message-tracking-edit-a-link.png)

   追跡する URL ごとに、トラッキングモードを次のいずれかの値に設定できます。

   * **[!UICONTROL トラッキング対象]**：この URL のトラッキングを有効化します。
   * **[!UICONTROL オプトアウト]**：この URL をオプトアウトまたは購読解除 URL とみなします。
   * **[!UICONTROL ミラーページ]**：この URL をミラーページの URL とみなします。
   * **[!UICONTROL なし]**：この URL のトラッキングを有効化しません。<!--This information is saved: if the URL appears again in a future message, its tracking is automatically deactivated.-->

開封数とクリック数のレポートは、 [ライブレポート](../reports/live-report.md) そして [グローバルレポート](../reports/global-report.md).
