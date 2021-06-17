---
title: メッセージの追跡
description: 送信済みメッセージを追跡する方法を学ぶ
feature: 監視
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: e27472cc6186cf7cb25fdb93d15720fc837c58bb
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 9%

---

# メッセージトラッキング {#tracking}

[!DNL Journey Optimizer]を使用して、送信されたメッセージと受信者の行動を追跡します。

## 追跡を有効にする{#enable-tracking}

**[!UICONTROL Open Tracking for email]**&#x200B;や&#x200B;**[!UICONTROL Click Tracking for email]**（[メッセージ](create-message.md)を作成する際）オプションをオンにすることで、メッセージレベルで追跡を有効にできます。

![](assets/message-tracking.png)

>[!NOTE]
>
>デフォルトでは、両方のオプションが有効になっています。

これにより、次の方法で受信者の行動を追跡できます。
* **[!UICONTROL Eメールの追跡を開く]**:開封されたメッセージ。
* **[!UICONTROL Eメールのクリック追跡]**:Eメール内のリンクのクリック数。

## リンクを挿入{#insert-links}

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

   * **[!UICONTROL ミラーページ]**:WebブラウザーにEメールコンテンツを表示するためのリンクを挿入します。

   ![](assets/message-tracking-links.png)

1. 単純な式のみを使用して、リンクをパーソナライズできます。 パーソナライゼーションについて詳しくは、[この節](personalization/personalization-syntax.md)を参照してください。

1. 変更を保存します。

1. リンクを作成した後も、右側の&#x200B;**[!UICONTROL コンポーネント設定]**&#x200B;ペインから変更できます。

   * 鉛筆アイコンをクリックして、リンクを編集します。
   * リンクに下線を引くかどうかは、対応するオプションをオンにして選択できます。

   ![](assets/message-tracking-link-settings.png)

## 追跡を管理{#manage-tracking}

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


