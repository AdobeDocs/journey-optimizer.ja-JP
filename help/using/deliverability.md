---
title: メッセージ実行の監視
description: 監視と配信品質のガイドラインについて説明します
source-git-commit: f04e73187439462fc1e22c6c66398a139fbeaa5a
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 98%

---

# 配信品質の管理{#manage-deliverability}

![](assets/do-not-localize/badge.png)

配信品質は、受信者のインボックスに届く配信の成否を測定する手法です。

**メール配信品質**&#x200B;とは、期待される品質のコンテンツとフォーマットを持つメッセージが、個人のメールアドレスを通じて短時間で宛先に到達する能力を判断する一連の特性のことを指します。これらの特性は、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、レピュテーションの 4 つの主なカテゴリに分類されます。これらにより、成功するメール配信品質プログラムの基礎が形成されます。

**配信品質率**&#x200B;は、受信者のインボックスに届いたメッセージの数と配信されたメッセージの数との比率です配信品質率は、多くの要因に左右されます。特に次のような要因があげられます。

* 限られたスパムの苦情
* 低いハードバウンス率
* ターゲットアドレスの品質
* メッセージコンテンツ
* 送信者のレピュテーション

[!DNL Journey Optimizer]エクスペリエンスの配信品質を最適化するには、このセクションに示すベストプラクティスを使用することをお勧めします。配信品質の問題は、通常、インターネットサービスプロバイダー（ISP）およびメールサーバー管理者が実行するスパムに対する保護に関連しています。

## 苦情の発生率の低減{#reduce-complaint-rate}

ISP は、通常、受け取ったメッセージをスパムとしてレポートする優れた手段を持っています。これにより、信頼性を欠くソースの特定が可能です。オプトアウト要求を迅速に実行し、信頼できる送信者であることを示すことで、苦情の発生率を低減できます。 [オプトアウト管理について説明します](consent.md#opt-out-management)。

原則として、例えばメールアドレスや名前などのフィールドを入力するよう求めることで、オプトアウトしたい受信者を邪魔しないでください。購読解除ランディングページには、検証ボタンが 1 つだけ必要です。

追加の確認を要求するときは特に注意が必要です。ユーザーが 2 つのメールアドレス（例：firstname.lastname@club.com および firstname.lastname@internet-club.com）を同じボックスにリダイレクトする場合があります。受信者が最初のアドレスのみを覚えていて、もう 1 つのアドレスに送信されたメッセージを使用して購読解除する場合、暗号化された識別子と入力されたメールアドレスが一致しないので、フォームはこれを拒否します。

## 抑制リストの活用{#suppression-lists}

[!DNL Journey Optimizer] は、絶えず発生するスパムの苦情、ハードバウンス、ソフトバウンスを収集した抑制リストを管理します。

配信品質を保護するため、アドレスが抑制リストにある受信者は、デフォルトでは今後のすべての配信から除外されます。これらの連絡先に送信すると、送信のレピュテーションが低下する可能性があるからです。

[抑制リストの詳細を説明します](suppression-list.md)。

## 監視ツールの使用{#monitoring-tools}

[!DNL Journey Optimizer] が提供する機能を使用して、配信品質を監視します。

メッセージリストの「**[!UICONTROL 実行]**」タブを使用すると、一連のリアルタイムインジケーターを使用して、配信のパフォーマンスを確認できます。その他の機能の中で、このタブには次の項目が表示されます。
* 正常に実行、送信および配信されたメッセージの数。
* 開かれたメッセージの数と、クリックされたメッセージ/リンクの数。

[監視メッセージの実行について説明します](message-monitoring.md)。

## メッセージコンテンツの適応{#adapt-message-content}

より少ない程度までは、特定のメッセージコンテンツをスパムとして検出することができます。

<!--The use of certain words or of exclamation points in the subject line and within the messages can be read as signs of spam.

Spammers are also known to replace text with images to stop offending text from being analyzed automatically by anti-spam filters. In response to this, a message (in HTML format) with a high proportion of images, or images as attachments, may end up being blocked.-->

配信品質率を向上させ、メールが受信者に届くようにするには、メッセージコンテンツをデザインする際に、次の原則に従ってください。

* **送信者の名前とアドレス**：アドレスは送信者を明示的に識別する必要があります。ドメインは、送信者に所有および登録されている必要があります。ドメイン登録は非公開にはしません。

<!--* **Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).
* **Personalize your email**: Personalizing the email increases the chances of your message being opened.
* **Images and text**: Respect a decent text/image ratio (for example 60% text and 40% images).-->
* **購読解除リンクとランディングページ**：購読解除リンクは必須です。表示されており、有効である必要があります。また、フォームは機能している必要があります。

<!--**Use tools** offered by Journey Optimizer to optimize the content of your email (delivery analysis, anti-spam analysis).-->

[メールコンテンツのデザインについて説明します](design-emails.md)。
