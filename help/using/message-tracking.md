---
title: メッセージのトラッキング
description: リンクを追加し送信済みメッセージをトラッキングする方法を説明します
feature: Monitoring
topic: Content Management
role: User
level: Intermediate
source-git-commit: 6ff5d093bac20248106be1f4478102c29703cb1d
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 65%

---

# リンクの追加とメッセージのトラッキング {#tracking}

[!DNL Journey Optimizer] を使用すると、受信者の行動を監視するために、コンテンツにリンクを追加し送信済みメッセージをトラッキングすることができます。

## トラッキングの有効化 {#enable-tracking}

**[!UICONTROL Open Tracking for email]**&#x200B;や&#x200B;**[!UICONTROL Click Tracking for email]**（[メッセージ](create-message.md)を作成する際）オプションをオンにすることで、Eメールメッセージレベルでのトラッキングを有効にできます。

![](assets/message-tracking.png)

>[!NOTE]
>
>デフォルトでは、両方のオプションが有効になっています。

これにより、次の方法で受信者の行動を追跡できます。
* **[!UICONTROL E メールの開封トラッキング]**：開封されたメッセージ。
* **[!UICONTROL E メールのクリックトラッキング]**：メール内のリンクのクリック数。

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

   * **[!UICONTROL 購読解除リンク]**：ブランドからのコミュニケーションの受信を解除するリンクを挿入する。オプトアウト管理の詳細については、[この節](consent.md#opt-out-management)を参照してください。

   * **[!UICONTROL ミラーページ]**：web ブラウザーにメールコンテンツを表示するためのリンクを挿入します。詳しくは、[この節](#mirror-page)を参照してください。

   * **[!UICONTROL オプトアウト]**:ユーザーがオプトアウトを確認する必要なく、通信をすばやく購読解除できるようにするリンクを挿入します。詳しくは、[この節](#one-click-opt-out-link)を参照してください。

   ![](assets/message-tracking-links.png)

1. リンクをパーソナライズできます。 パーソナライズされたURLについて詳しくは、[この節](personalization/personalization-syntax.md)を参照してください。

1. 変更を保存します。

1. リンクを作成した後も、右側の「**[!UICONTROL コンポーネント設定]**」ウィンドウから変更できます。

   * 鉛筆アイコンをクリックしてリンクを編集します。
   * リンクに下線を引くかどうかは、対応するオプションをオンにすることで選択できます。

   ![](assets/message-tracking-link-settings.png)

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
>テストプロファイルに送信される[配達確認](preview.md#send-proofs)では、ミラーページへのリンクはアクティブになっていません。 最終的なメッセージでのみアクティブ化されます。

ミラーページの保持期間は 60 日です。 この期間が経過すると、ミラーページは使用できなくなります。

## ワンクリックオプトアウトリンク {#one-click-opt-out-link}

受信者がブランドからの通信をすばやく購読解除できるようにするには、1回のクリックでのオプトアウトリンクをEメールコンテンツに挿入します。 この機能を利用すると、ユーザーが選択を確認する必要があるランディングページにリダイレクトされるのを防ぎ、購読解除プロセスを高速化できます。

Eメールにオプトアウトリンクを追加するには、以下の手順に従います。

1. [リンクを挿入](#insert-links) し、リンクのタ **[!UICONTROL イプとし]** て「オプトアウト」を選択します。

   ![](assets/message-tracking-opt-out.png)

1. オプトアウトの適用方法を選択します。チャネル、IDまたはサブスクリプションレベル。

   ![](assets/message-tracking-opt-out-level.png)

   * **[!UICONTROL チャネル]**:オプトアウトは、現在のチャネルのプロファイルのターゲット（Eメールアドレス）に送信される今後のメッセージに適用されます。複数のターゲットが1つのプロファイルに関連付けられている場合、オプトアウトはそのチャネルのプロファイル内のすべてのターゲット（Eメールアドレス）に適用されます。
   * **[!UICONTROL ID]**:オプトアウトは、現在のメッセージで使用されている特定のターゲット（Eメールアドレス）に送信される以降のメッセージに適用されます。
   * **[!UICONTROL 購読]**:オプトアウトは、特定の購読リストに関連付けられた今後のメッセージに適用されます。このオプションは、現在のメッセージが購読リストに関連付けられている場合にのみ選択できます。

1. 購読解除後にユーザーがリダイレクトされるランディングページのURLを入力します。 このページは、オプトアウトが成功したことを確認するためにのみ表示されます。

   ![](assets/message-tracking-opt-out-confirmation.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

メッセージが送信されると、受信者がオプトアウトリンクをクリックすると、受信者は直ちにオプトアウトされます。

## トラッキングの管理 {#manage-tracking}

[E メールデザイナー](create-email-content.md)を使用すると、追跡する URL を管理できます（各リンクのトラッキングタイプの編集など）。

1. 左側のウィンドウの「**[!UICONTROL リンク]**」アイコンをクリックし、追跡するコンテンツのすべての URL のリストを表示します。

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

開封されたメッセージの数とクリックされたリンクの数が、[「実行」タブ](message-monitoring.md)に表示されます。

開封数とクリック数に関するレポートは、[E メールのライブレポート](reports/email-live-report.md)と[E メールのグローバルレポート](reports/email-global-report.md)で利用できます。


