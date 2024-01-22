---
solution: Journey Optimizer
product: journey optimizer
title: DMARC レコード
description: Journey Optimizerで DMARC レコードを設定する方法を説明します。
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン，ドメイン，メール， dmarc，レコード
source-git-commit: 7d5a2a9b80110505688b5bfda2e286c7a6432441
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---

# DMARC レコード {#dmarc-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_record"
>title="DMARC レコードを設定"
>abstract="ISP での配信品質の問題を回避するために DMARC レコードを設定します。 Googleと Yahoo は、業界のベストプラクティスの実施の一環として、E メールを送信する際に使用するすべてのドメインに対して DMARC レコードを持つことを求めています。"

>[!CAUTION]
>
>一括送信者に対する Gmail および Yahoo の最近のお知らせに従い、Journey Optimizerは DMARC 認証テクノロジーをサポートするようになりました。

<!--TO ADD TO AJO HOME PAGE (first tab)

>[!TAB Mandatory DMARC update]

As part of their enforcing industry best practices, Google and Yahoo will both be requiring that you have a DMARC record for any domain you use to send email to them, starting on **February 1st, 2024**. Make sure that you have DMARC record set up for all the subdomains that you have delegated to Adobe in Journey Optimizer.

[![image](using/assets/do-not-localize/learn-more-button.svg)](using/configuration/dmarc-record-update.md)
-->

業界のベストプラクティスの実施の一環として、Googleと Yahoo は共に、 **DMARC レコード** 電子メールを送信するために使用するすべてのドメイン用。 この新しい要件は、次の日から始まります。 **2024 年 2 月 2 日**.

Googleと Yahoo の要件について詳しくは、 [この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

>[!CAUTION]
>
>Gmail および Yahoo のこの新しい要件に準拠しないと、E メールがスパムフォルダーにランディングしたりブロックされたりする可能性があります。

そのため、Adobeでは、Adobeにデリゲートしたすべてのサブドメインに対して DMARC レコードを必ず設定することを強くお勧めします [!DNL Journey Optimizer]. お客様のケースに適用される以下の手順に従います。

* 次の条件を満たしている場合： [完全に委任された](delegate-subdomain.md#full-subdomain-delegation) サブドメインをAdobeに送信する場合は、次の 2 つのオプションのいずれかに従います。

   * デリゲートされたサブドメインの親ドメインに DMARC を設定します **をホスティングソリューションで使用**.

   * デリゲートされたサブドメインに対する DMARC の設定 **の今後の機能の使用 [!DNL Journey Optimizer] 管理 UI**  — ホスティングソリューションで余分な作業をおこなう必要はありません。

* 次の設定が完了している場合、 [CNAME デリゲーション](delegate-subdomain.md#cname-subdomain-delegation) 送信サブドメインの場合は、次の 2 つのオプションのいずれかに従います。

   * サブドメインまたはサブドメインの親ドメインで DMARC を設定する **をホスティングソリューションで使用**.

   * デリゲートされたサブドメインに対する DMARC の設定 **の今後の機能の使用 [!DNL Journey Optimizer] 管理 UI**. ただし、ホスティングソリューションにもエントリが必要になります。 その結果、IT 部門との連携を図り、IT 部門が [!DNL Journey Optimizer] 機能が利用可能になった（1 月 30 日）。 <!--and be ready on February 1st, 2024-->

**詳細は、 [!DNL Journey Optimizer] DMARC の今後の機能は近日中に提供されます。**

>[!NOTE]
>
>での DMARC の実装の詳細 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} e メール配信品質への影響をより深く理解する。

## DMARC とは

DMARC（の略） **ドメインベースのメッセージ認証、レポート、適合**&#x200B;は、ドメインの所有者がドメインを不正使用から保護できる電子メール認証方法またはプロトコルです。

送信者のドメインを認証する方法を提供することで、悪意のあるアクターがドメインから来たような E メールを送信するのを防ぐことができます。

また、DMARC は、電子メール認証ステータスに関するフィードバックを提供し、送信者が認証に失敗した電子メールに対して何が起こるかを制御することもできます。 これには、実装されている DMARC ポリシーに応じて、メールを監視、強制隔離、拒否するオプションが含まれます。

<!--Setting up a DMARC record involves adding a DNS TXT record to your domain's DNS settings. This record specifies your DMARC policy, such as whether to quarantine or reject messages that fail authentication. Implementing DMARC is a proactive step towards enhancing email security and protecting both your organization and your recipients from email-based threats.-->

DMARC には次の 3 つのポリシーオプションがあります。

* モニター (p=none)：メールボックスプロバイダーまたは ISP に対し、通常のメッセージに対する処理を何らかの処理で実行するように指示します。
* 強制隔離 (p=quarantine):DMARC を受信者のスパムフォルダーまたは迷惑メールフォルダーに渡さないメールを配信するよう、メールボックスプロバイダーまたは ISP に指示します。
* 拒否 (p=reject):DMARC を渡さずにバウンスに至ったメールをブロックするよう、メールボックスプロバイダーまたは ISP に指示します。

## DMARC の仕組み

SPF と DKIM は、E メールをドメインに関連付け、連携して E メールを認証するために使用されます。 DMARC はこの 1 つの手順をさらに進め、DKIM と SPF でチェックされたドメインと一致させ、スプーフィングを防ぐのに役立ちます。 DMARC を渡すには、メッセージが SPF または DKIM を渡す必要があります。 これらの両方の認証が失敗した場合、DMARC は失敗し、選択した DMARC ポリシーに従って電子メールが配信されます。

* SPF (Sender Policy Framework): DMARC は SPF に基づいて送信メールサーバーの ID を認証します。 SPF は、送信サーバーの IP アドレスをドメインの承認済み IP アドレスのリストと照らし合わせて確認することで、E メールメッセージが承認されたソースから送信されたことを確認するのに役立ちます。
* DKIM(DomainKeys Identified Mail): DMARC は、DKIM を使用して電子署名を E メールメッセージに追加し、受信者がメッセージの整合性と信頼性を検証できるようにします。

>[!NOTE]
>
>DMARC では、「From」と「Return-Path」アドレスの間の位置揃えが必要です。


<!--

* DMARC helps prevent malicious actors from sending emails that appear to come from your domain. By setting up DMARC, you can specify how email providers should handle messages that fail authentication checks, reducing the likelihood that phishing emails will reach recipients.

* DMARC helps improve email deliverability by providing a clear policy for email providers to follow when encountering messages claiming to be from your domain. This can reduce the chances of legitimate emails being marked as spam or rejected.

DMARC helps protect against email spoofing, phishing, and other fraudulent activities.

It allows you to decide how a mailbox provider should handle emails that fail SPF and DKIM checks, providing a way to authenticate the sender's domain and prevent unauthorized use of the domain for malicious purposes.

-->


## DMARC の実装 {#implement-dmarc}

DMARC を実装するには、お客様の事例に適用される以下の手順に従います。

* DMARC を追加しない場合、強制隔離されます（少なくとも）。

### 完全にデリゲートされたサブドメイン

DMARC が失敗した場合に受信者サーバーが実行するアクションを設定します。

DMARC には次の 3 つのポリシーオプションがあります。

* モニター (p=none)：メールボックスプロバイダーまたは ISP に対し、通常のメッセージに対する処理を何らかの処理で実行するように指示します。 これがデフォルト値です。
* 強制隔離 (p=quarantine):DMARC を受信者のスパムフォルダーまたは迷惑メールフォルダーに渡さないメールを配信するよう、メールボックスプロバイダーまたは ISP に指示します。
* 拒否 (p=reject):DMARC を渡さずにバウンスに至ったメールをブロックするよう、メールボックスプロバイダーまたは ISP に指示します。

集計 DMARC レポートとフォレンジック DMARC 失敗レポートを受け取る電子メール：最大 5 つのアドレスを追加できます。

* 正規のインボックスを持っていることを確認し、コントロールで受け取ることができます — このインボックスを管理します (Adobeインボックスではないはずです )

DMARC を適用するメールの適用率：

レポート間隔：通常、これが ISP のものなので、24 をお勧めします。
それ以外の場合は、容量を評価する/ /チャット GPT を確認

DMARC レコードが検出された場合は、リストと同じ値をコピー&amp;ペーストしたり、必要に応じて値を変更したりできます。

何も指定しない場合は、デフォルト値が使用されます。

### CNAME を使用してデリゲートされたサブドメイン

エディションフローの CNAME の場合、CSV ファイルを再度ダウンロードする必要があります（完全にデリゲートされたものではありません）。





