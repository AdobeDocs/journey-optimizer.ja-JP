---
title: メッセージ実行の監視
description: 監視と配信品質のガイドラインについて学ぶ
feature: 配信品質
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 4be1d6f4034a0bb0a24fe5e4f634253dc1ca798e
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 100%

---

# 配信品質の管理 {#manage-deliverability}

配信品質は、受信者のインボックスに配信が正常に届いたかどうかを測定する手法です。

**メール配信品質**&#x200B;とは、期待される品質のコンテンツと形式を備えたメッセージが、個人のメールアドレスを通じて短時間で宛先に到達する能力を判断する、一連の特性のことを指します。これらの特性は、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、評価の 4 つの主なカテゴリに分類されます。これらのカテゴリを合わせて、成功するメール配信品質プログラムの基礎が形成されます。

**配信率**&#x200B;は、受信者のインボックスに届いたメッセージの数と配信されたメッセージの数との比率です。配信率は、多くの要因に左右されます。特に次のような要因があげられます。

* 限定的なスパム通報
* 低いハードバウンス率
* ターゲットアドレスの品質
* メッセージコンテンツ
* 送信者の評価

[!DNL Journey Optimizer] エクスペリエンスの配信品質を最適化するには、この節に示すベストプラクティスを使用することをお勧めします。配信品質の問題は通常、インターネットサービスプロバイダー（ISP）およびメールサーバー管理者が実行するスパム対策に関係しています。

## 苦情の発生率の低減 {#reduce-complaint-rate}

ISP は、通常、受け取ったメッセージをスパムとしてレポートする優れた手段を持っています。これにより、信頼性を欠くソースの特定が可能です。オプトアウト要求に迅速に対応し、自身が信頼できる送信者であることを示すことで、苦情の発生率を低減できます。[オプトアウト管理の詳細情報](consent.md#opt-out-management)。

原則として、オプトアウトを希望する受信者がスムーズに手続きできるよう、メールアドレスや名前などのフィールドへの入力を要求しないようにしてください。購読解除ランディングページには、確認ボタンを 1 つだけ配置してください。

追加の確認を要求するときは特に注意が必要です。ユーザーが 2 つのメールアドレス（例：firstname.lastname@club.com および firstname.lastname@internet-club.com）を同じボックスにリダイレクトする場合があります。プロファイルが最初のアドレスしか覚えておらず、もう 1 つのアドレスに送信されたメッセージ経由で購読解除しようとすると、暗号化された識別情報と入力されたメールアドレスが一致しないことから、フォームは購読解除を拒否します。

## 抑制リストの活用 {#suppression-lists}

[!DNL Journey Optimizer] は、絶えず発生するスパム通報、ハードバウンス、ソフトバウンスを収集した抑制リストを管理します。

配信品質を保護するため、受信者のアドレスが抑制リストに含まれている場合、デフォルトでは、今後のすべての配信からそのアドレスが除外されます。これらの連絡先に送信すると、評価が下がる可能性があるからです。

[抑制リストについての詳細](suppression-list.md)。

## 監視ツールの使用 {#monitoring-tools}

[!DNL Journey Optimizer] が提供する機能を使用して、配信品質を監視します。

メッセージリストの「**[!UICONTROL 実行]**」タブを使用すると、一連のリアルタイムインジケーターを使用して、配信のパフォーマンスを確認できます。このタブには次の項目も表示されます。
* 正常に実行、送信および配信されたメッセージの数。
* 開封されたメッセージの数と、クリックされたメッセージやリンクの数。

[メッセージ実行の監視の詳細情報](message-monitoring.md)。

## メッセージコンテンツの調整 {#adapt-message-content}

それほど影響はありませんが、特定のメッセージコンテンツをスパムとして検出することができます。

<!--The use of certain words or of exclamation points in the subject line and within the messages can be read as signs of spam.

Spammers are also known to replace text with images to stop offending text from being analyzed automatically by anti-spam filters. In response to this, a message (in HTML format) with a high proportion of images, or images as attachments, may end up being blocked.-->

配信率を向上させ、メールが受信者に届くようにするには、メッセージコンテンツを設計する際に、次の原則に従ってください。

* **送信者の名前とアドレス**：アドレスは送信者を明示的に識別する必要があります。ドメインは、送信者に所有および登録されている必要があります。ドメイン登録は非公開にはしません。

<!--* **Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).
* **Personalize your email**: Personalizing the email increases the chances of your message being opened.
* **Images and text**: Respect a decent text/image ratio (for example 60% text and 40% images).-->
* **購読解除リンクとランディングページ**：購読解除リンクは必須です。わかりやすく、有効である必要があります。また、フォームが機能する必要があります。

<!--**Use tools** offered by Journey Optimizer to optimize the content of your email (delivery analysis, anti-spam analysis).-->

[メールコンテンツのデザインの詳細情報](design-emails.md)。
