---
solution: Journey Optimizer
product: journey optimizer
title: Deliverability での作業の開始
description: Deliverability について学習します。
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
exl-id: 8f33dda7-9bd5-4293-8d0d-222205cbc7d5
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Deliverability での作業の開始 {#manage-deliverability}

Deliverability は、宛先の受信者に配信が成功したかを示すものです。

>[!NOTE]
>
>お客様の皆様向け医療シールドは、ユーザーのシステム (受信者) と旅のオプティマイザー (sender) との間でデータが交換されるように、1.2 TLS (トランスポートレイヤーセキュリティ) を使用しています。 受信側のメールサーバーが TLS 1.2 をサポートしていない場合は、deliverability の問題が発生する可能性があります。これは、宛先に電子メールを送信する場合を含みます。

**電子メール deliverability** は、メッセージが、その送信先に到達する機能、短い期間、およびコンテンツと形式について予想される画質を指定する一連の特性を表します。 この特性は、データの質、メッセージとコンテンツ、送信元のインフラストラクチャー、評判という4つの主なカテゴリーに大別されます。 これによって、電子メール deliverability プログラムの成功の基礎が形成されます。

**Deliverability rate** は、配信されたメッセージの数と受信者の受信トレイをヒットしたメッセージの数を示します。これは、特に次のような数多くの要因に左右されます。

* 限定的なスパムの苦情
* 低: バウンスレート
* ターゲットアドレスの質
* メッセージの内容
* 差出人の評判

Deliverability の [!DNL Journey Optimizer] 操作を最適化するには、この節で説明されているベストプラクティスを使用することをお勧めします。 Deliverability の問題は、インターネットサービスプロバイダー (Isp) およびメールサーバー管理者によって実装されるスパムに対する保護に一般にリンクされています。

Deliverability が何であるかについて詳しく説明し、主な deliverability 用語、概念、およびアプローチについて詳しくは、Adobe Deliverability ベストプラクティスガイド ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) {target = &quot;_blank 「」を [ 参照してください。

## クレームレートを下げる {#reduce-complaint-rate}

通常、Isp には受信したメッセージをスパムとして報告するのに最も目立つ手段が用意されています。 これにより、不安定なソースを識別することができます。 オプトアウト要求に直ちに同意することによって、ユーザーが信頼できる差出人である場合は、不満率が低くなる可能性があります。 [オプトアウトの管理 ](../privacy/opt-out.md#opt-out-management) について詳しく説明します。

原則として、例えば、電子メールアドレス、名前などのフィールドに入力するように要求することによって、オプトアウトしようとしている宛先には手を付けないようにします。 Unsubscription ランディングページには、1つの検証ボタンのみが含まれている必要があります。

その他の確認を依頼する場合は、さらに注意してください。ユーザーは、2つの電子メールアドレスを同じボックスにリダイレクトすることができます (例: firstname.lastname@club.com および firstname.lastname@internet-club.com)。 プロファイルによって最初のアドレスのみが記憶され、他のアドレスに送信されたメッセージによって購読が解除されるようにする場合は、暗号化された識別子と入力された電子メールアドレスが一致しないので、フォームにそれが拒否されます。

## 抑制リストの活用 {#suppression-lists}

[!DNL Journey Optimizer] では、スパムの苦情、ハードバウンス、およびソフトバウンスが一貫して発生するという、抑制リストを管理しています。

Deliverability を保護するために、抑制リストに含まれている受信者は、送信された評判に悪影響を受ける可能性があるため、デフォルトでは今後のすべての出荷により除外されます。

[抑制リスト ](suppression-list.md) について詳しくは、こちらを参照してください。

## 監視ツールを使用する {#monitoring-tools}

に [!DNL Journey Optimizer] 用意されている機能を使用して、deliverability を監視してください。

**[!UICONTROL Executions]**&#x200B;メッセージリストのタブを使用すると、リアルタイムインジケーターのセットを使用して、送信の実行状況を確認できます。特に、次のようなタブが表示されます。
* 正常に実行されたことを示すメッセージの数、送信および配信が成功したメッセージ数です。
* 開かれたメッセージの数と、クリックされたメッセージまたはリンクの数が表示されます。

## メッセージコンテンツの調整 {#adapt-message-content}

特定のメッセージのコンテンツがスパムとして検出される場合があります。

Deliverability レートを改善し、電子メールが宛先に送信されるようにするには、メッセージコンテンツをデザインする際に以下の原則に従う必要があります。

* **差出人の名前とアドレス** : アドレスは、差出人を明示的に指定することができます。 ドメインは、送信者が送信者に登録されている必要があります。 ドメインレジストリは privatized ではありません。

* **購読解除リンクおよびランディングページ** : 購読解除リンクは必須です。 これは、表示可能であり、有効である必要があります。

[電子メールコンテンツ ](../email/get-started-email-design.md) のデザインについて詳しくは、こちらを参照してください。

## 送信者としての評判を設定します。

最近別の電子メールサービスプロバイダー、IP アドレスまたは e-mail ドメインまたはサブドメインに移動した場合は、送信者としての評判を確認する必要があります。 それ以外の場合は、配信がブロックされるか、または受信者のメールボックスのスパムフォルダーに移動されます。

IP をウォームアップするには、配信数をしだいに増やします。 この [ ような使用例 ](../building-journeys/ramp-up-deliveries-uc.md) を参照してください。
