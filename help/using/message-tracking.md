---
title: メッセージの追跡
description: リンクを追加し、送信済みメッセージをトラッキングする方法を説明します
feature: 監視
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: f5a6a9b6c786b39b492a177de0b19a54b81729f7
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 8%

---

# リンクの追加とメッセージのトラッキング {#tracking}

[!DNL Journey Optimizer]を使用して、コンテンツにリンクを追加し、送信されたメッセージをトラッキングして、受信者の行動を監視します。

## トラッキングの有効化 {#enable-tracking}

**[!UICONTROL Open Tracking for email]**&#x200B;や&#x200B;**[!UICONTROL Click Tracking for email]**（[メッセージ](create-message.md)を作成する際）オプションをオンにすることで、メッセージレベルで追跡を有効にできます。

![](assets/message-tracking.png)

>[!NOTE]
>
>デフォルトでは、両方のオプションが有効になっています。

これにより、次の方法で受信者の行動を追跡できます。
* **[!UICONTROL Eメールの追跡を開く]**:開封されたメッセージ。
* **[!UICONTROL Eメールのクリック追跡]**:Eメール内のリンクのクリック数。

## リンクの挿入 {#insert-links}

メッセージをデザインする際に、コンテンツにリンクを追加できます。

>[!NOTE]
>
>[トラッキングが有効](#enable-tracking)の場合、メッセージコンテンツに含まれるすべてのリンクがトラッキングされます。

Eメールコンテンツにリンクを挿入するには、次の手順に従います。

1. 要素を選択し、コンテキストツールバーの「**[!UICONTROL リンクを挿入]**」をクリックします。

   ![](assets/message-tracking-insert-link.png)

1. 作成するリンクのタイプを選択します。

   * **[!UICONTROL 外部リンク]**:外部URLへのリンクを挿入します。

   * **[!UICONTROL 購読解除リンク]**:ブランドからのコミュニケーションの受信を登録解除するリンクを挿入します。オプトアウト管理について詳しくは、[この節](consent.md#opt-out-management)を参照してください。

   * **[!UICONTROL ミラーページ]**:WebブラウザーにEメールコンテンツを表示するためのリンクを挿入します。詳しくは、[この節](#mirror-page)を参照してください。

   ![](assets/message-tracking-links.png)

1. 単純な式のみを使用して、リンクをパーソナライズできます。 パーソナライゼーションについて詳しくは、[この節](personalization/personalization-syntax.md)を参照してください。

1. 変更を保存します。

1. リンクを作成した後も、右側の&#x200B;**[!UICONTROL コンポーネント設定]**&#x200B;ペインから変更できます。

   * 鉛筆アイコンをクリックして、リンクを編集します。
   * リンクに下線を引くかどうかは、対応するオプションをオンにして選択できます。

   ![](assets/message-tracking-link-settings.png)

## ミラーページへのリンク {#mirror-page}

ミラーページは、web ブラウザーからオンラインアクセス可能な HTML ページです。コンテンツはEメールの内容と同じです。

Eメール内のミラーページにリンクを追加するには、[リンク](#insert-links)を挿入し、リンクのタイプとして&#x200B;**[!UICONTROL ミラーページ]**&#x200B;を選択します。

![](assets/message-tracking-mirror-page.png)

ミラーページが自動的に作成されます。

>[!NOTE]
>
>自動生成されたリンクは編集できません。

Eメールが送信されると、受信者がミラーページのリンクをクリックすると、EメールのコンテンツがデフォルトのWebブラウザーに表示されます。

>[!NOTE]
>
>テストプロファイルに送信される[配達確認](preview.md#send-proofs)では、ミラーページへのリンクがアクティブになっていません。 有効にするのは、最終的なメッセージ内のみです。

ミラーページの保持期間は60日です。 その後、ミラーページは使用できなくなります。

## トラッキングの管理 {#manage-tracking}

[Eメールデザイナー](create-email-content.md)を使用すると、追跡するURLを管理できます（各リンクのトラッキングタイプの編集など）。

1. 左側のウィンドウの&#x200B;**[!UICONTROL リンク]**&#x200B;アイコンをクリックして、追跡するコンテンツのすべてのURLのリストを表示します。

   このリストを使用すると、一元表示を作成し、Eメールコンテンツ内の各URLを特定できます。

1. リンクを編集するには、対応する鉛筆アイコンをクリックします。

   ![](assets/message-tracking-edit-links.png)

1. 必要に応じて、「**[!UICONTROL トラッキングタイプ]**」を変更できます。


   ![](assets/message-tracking-edit-a-link.png)

   トラッキングするURLごとに、トラッキングモードを次のいずれかの値に設定できます。

   * **[!UICONTROL 追跡]**:このURLのトラッキングを有効化します。
   * **[!UICONTROL オプトアウト]**:このURLをオプトアウトまたは購読解除URLと見なします。
   * **[!UICONTROL ミラーページ]**:このURLをミラーページのURLとみなします。
   * **[!UICONTROL なし]**:このURLのトラッキングを有効化しません。  <!--This information is saved: if the URL appears again in a future message, its tracking is automatically deactivated.-->

開封されたメッセージの数とクリックされたリンクの数が、[「実行」タブ](message-monitoring.md)に表示されます。

開封数とクリック数のレポートは、[Eメールのライブレポート](reports/email-live-report.md)と[Eメールのグローバルレポート](reports/email-global-report.md)で利用できます。


