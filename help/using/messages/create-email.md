---
title: E メールの作成
description: Journey Optimizer でメールを作成する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
exl-id: c77dc420-a375-4376-ad86-ac740e214c3c
source-git-commit: 0e978d0eab570a28c187f3e7779c450437f16cfb
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 21%

---

# メールの作成 {#configure-email}

>[!CONTEXTUALHELP]
>id="ajo_message_email"
>title="メールの作成"
>abstract="メールのパラメーターを 3 つの簡単な手順で定義します。"


一度 [電子メールを追加しました](get-started-content.md) ジャーニー内 <!--or a campaign--> を設定し、基本的な設定を定義したら、e メールを設定して、そのコンテンツを定義できます。

## E メールコンテンツを定義{#email-content}

次をクリック： **[!UICONTROL コンテンツを編集]** ボタンをクリックして、E メールをデザインします。

![](assets/email-edit-content.png)

用途 [!DNL Journey Optimizer] メールデザイナーの宛先 [メールをゼロからデザインする](../design/create-email-content.md). 既存のコンテンツがある場合は、 [E メールデザイナーに読み込む](../design/existing-content.md)または [独自のコンテンツをコーディング](../design/code-content.md) in [!DNL Journey Optimizer].

[!DNL Journey Optimizer] 一連の [ビルトインテンプレート](../design/email-templates.md) 足を止めるために どの電子メールもテンプレートとして保存できます。

電子メールデザインの詳細 [この節](../design/design-emails.md).

用途 [!DNL Journey Optimizer] 式エディターを使用して、プロファイルのデータを使用してメッセージをパーソナライズします。 パーソナライズ機能について詳しくは、[この節](../personalization/personalize.md)参照してください。

## E メールトラッキング{#email-tracking}

リンクの開封やクリックを通じて受信者の行動を追跡する場合は、次のオプションを有効にします。 **[!UICONTROL メール開封数]** および **[!UICONTROL メールをクリック]**. トラッキングの詳細については、[この節](../design/message-tracking.md)を参照してください。


## E メールコンテンツの検証{#email-content-validate}

左側のプレビューセクションを使用して、E メールのレンダリングを制御し、テストプロファイルでパーソナライゼーション設定を確認します。 詳しくは、[この節](../design/preview.md)を参照してください。

![](assets/messages-simple-preview.png)


また、エディターの上部セクションでアラートを確認する必要があります。  単純な警告もありますが、メッセージの使用を妨げる可能性もあります。 詳しくは、[この節](alerts.md)を参照してください。


>[!NOTE]
>
>この **[!UICONTROL 送信元メール]** および **[!UICONTROL 送信者名]** は、 **[!UICONTROL サーフェス]** が選択された回数： [メッセージの作成](get-started-content.md).

