---
title: メッセージの実行の監視
description: 監視と配信品質のガイドラインを学ぶ
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 28%

---

# 配信品質の管理{#manage-deliverability}

![](assets/do-not-localize/badge.png)

配信品質は、受信者のinboxに届く配信の成功度を示す尺度です。

**E メール配信品質**&#x200B;とは、期待される品質のコンテンツとフォーマットを持つメッセージが、個人の E メールアドレスを通じて短時間で宛先に到達する能力を判断する一連の特性のことを指します。これらの特性は、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、レピュテーションの 4 つの主なカテゴリに分類されます。これらにより、成功する E メール配信品質プログラムの基礎が形成されます。

**配信品質率**&#x200B;は、受信者の受信トレイに届いたメッセージの数を、配信されたメッセージの数と比較した数です。 これは、特に多くの要因に左右される。

* 限られたスパム
* ハードバウンス率が低い
* ターゲットアドレスの品質
* メッセージの内容
* 送信者のレピュテーション

[!DNL Journey Optimizer]エクスペリエンスの配信品質を最適化するには、この節に示すベストプラクティスを使用することをお勧めします。 配信品質の問題は、通常、インターネットサービスプロバイダー(ISP)やメールサーバ管理者が実装したスパムに対する保護と関連しています。

## 苦情の発生率を{#reduce-complaint-rate}下げる

ISP は、通常、受け取ったメッセージをスパムとしてレポートする優れた手段を持っています。これにより、信頼性を欠くソースの特定が可能です。オプトアウト要求を迅速に実行し、信頼できる送信者であることを示すことで、苦情の発生率を低減できます。 [オプトアウト管理の詳細を表示します](consent.md#opt-out-management)。

原則として、例えば E メールアドレスや名前などのフィールドを入力するよう求めることで、オプトアウトしたい受信者を邪魔しないでください。購読解除ランディングページには、検証ボタンが1つだけ必要です。

追加の確認をリクエストする場合は、注意が必要です。ユーザーが同じボックスにリダイレクトされる電子メールアドレスを2つ持つ場合があります(例：firstname.lastname@club.comおよびfirstname.lastname@internet-club.com)。 プロファイルが最初のアドレスのみを記憶でき、他のアドレスに送信されたメッセージを介して登録解除を希望する場合、暗号化されたIDと入力された電子メールアドレスが一致しないので、フォームはこの処理を拒否します。

## 抑制リストを活用{#suppression-lists}

[!DNL Journey Optimizer] 一貫して発生するスパム、ハードバウンス、ソフトバウンスを収集する抑制リストを管理します。

配信品質を保護するために、アドレスが抑制リストにある受信者は、デフォルトで、これらの連絡先に送信すると送信の評判が悪くなる可能性があるので、将来の配信から除外されます。

[抑制リストの詳細を表示します](suppression-lists.md)。

## 監視ツールを使用{#monitoring-tools}

[!DNL Journey Optimizer]が提供する機能を使って配信品質を監視します。

メッセージリストの「**[!UICONTROL 実行]**」タブを使用すると、一連のリアルタイムインジケーターを使用して、配信のパフォーマンスを確認できます。 その他の機能の中で、このタブには次の項目が表示されます。
* 正常に実行、送信および配信されたメッセージの数。
* 開かれたメッセージの数と、クリックされたメッセージ/リンクの数。

[メッセージの実行の監視の詳細を表示します](message-monitoring.md)。

## メッセージ内容を適応{#adapt-message-content}

より少ない程度までは、あるメッセージの内容がスパムとして検出される場合がある。

<!--The use of certain words or of exclamation points in the subject line and within the messages can be read as signs of spam.

Spammers are also known to replace text with images to stop offending text from being analyzed automatically by anti-spam filters. In response to this, a message (in HTML format) with a high proportion of images, or images as attachments, may end up being blocked.-->

配信品質を向上させ、電子メールが受信者に届くようにするには、メッセージコンテンツを設計する際に、次の原則に従ってください。

* **送信者の名前とアドレス**:このアドレスは、送信者を明示的に識別する必要があります。ドメインは、送信者に所有および登録されている必要があります。ドメイン登録は非公開にはしません。

<!--* **Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).
* **Personalize your email**: Personalizing the email increases the chances of your message being opened.
* **Images and text**: Respect a decent text/image ratio (for example 60% text and 40% images).-->
* **登録解除リンクとランディングページ**:登録解除リンクは必須です。表示されており、有効である必要があります。また、フォームは機能している必要があります。

<!--**Use tools** offered by Journey Optimizer to optimize the content of your email (delivery analysis, anti-spam analysis).-->

[電子メールコンテンツのデザインについて詳しく説明します](design-emails.md)。
