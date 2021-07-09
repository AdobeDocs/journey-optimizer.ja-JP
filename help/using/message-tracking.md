---
title: メッセージの追跡
description: リンクを追加し、送信済みメッセージをトラッキングする方法を説明します
feature: 監視
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: f5a6a9b6c786b39b492a177de0b19a54b81729f7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# リンクの追加とメッセージのトラッキング {#tracking}

[!DNL Journey Optimizer]を使用して、コンテンツにリンクを追加し、送信されたメッセージをトラッキングして、受信者の行動を監視します。

## トラッキングの有効化 {#enable-tracking}

メッセージレベルでのトラッキングを有効にするには、[メッセージ作成](create-message.md)時に「**[!UICONTROL E メールの開封トラッキング]**」または「**[!UICONTROL E メールのクリックトラッキング]**」オプション、あるいはその両方をオンにします。

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

   * **[!UICONTROL ミラーページ]**：Web ブラウザーにメールコンテンツを表示するためのリンクを挿入する。詳しくは、[この節](#mirror-page)を参照してください。

   ![](assets/message-tracking-links.png)

1. 簡単な式のみを使用して、リンクをパーソナライズできます。パーソナライゼーションの詳細については、[この節](personalization/personalization-syntax.md)を参照してください。

1. 変更を保存します。

1. リンクを作成した後も、右側の「**[!UICONTROL コンポーネント設定]**」ウィンドウから変更できます。

   * 鉛筆アイコンをクリックしてリンクを編集します。
   * リンクに下線を引くかどうかは、対応するオプションをオンにすることで選択できます。

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
>テストプロファイルに送信される[配達確認](preview.md#send-proofs)では、ミラーページへのリンクがアクティブになっていません。 最終的なメッセージでのみアクティブ化されます。

ミラーページの保持期間は60日です。 その後、ミラーページは使用できなくなります。

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


