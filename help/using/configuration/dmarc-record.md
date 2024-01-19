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
source-git-commit: f9d3234a64ad659660c2d2c4ad24ab5c240cb857
workflow-type: tm+mt
source-wordcount: '680'
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

そのため、Adobeでは、Adobeにデリゲートしたすべてのサブドメインに対して DMARC レコードを必ず設定することを強くお勧めします [!DNL Journey Optimizer]. 次の 2 つのオプションのいずれかに従います。

* サブドメインまたはサブドメインの親ドメインで DMARC を設定します。 **をホスティングソリューションで使用**.

* デリゲートされたサブドメインに対する DMARC の設定 **新機能を [!DNL Journey Optimizer] 管理 UI**  — ホスティングソリューションで余分な作業をおこなう必要はありません。 [詳細情報](#implement-dmarc)

  >[!CAUTION]
  >
  >次の設定が完了している場合、 [CNAME デリゲーション](delegate-subdomain.md#cname-subdomain-delegation) 送信サブドメインの場合は、ホスティングソリューションへのエントリも必要になります。 IT 部門との連携を図り、IT 部門が [!DNL Journey Optimizer] の機能は（2024 年 1 月 31 日）に利用できます。 <!--and be ready on February 1st, 2024-->

>[!NOTE]
>
>での DMARC の実装の詳細 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} e メール配信品質への影響をより深く理解する。

## DMARC とは

DMARC（の略） **ドメインベースのメッセージ認証、レポート、適合**&#x200B;は、電子メールのスプーフィング、フィッシング、その他の不正アクティビティから保護するのに役立つ電子メール認証プロトコルです。

* 電子メール認証：

   * SPF (Sender Policy Framework): DMARC は SPF に基づいて送信メールサーバーの ID を認証します。 SPF は、送信サーバーの IP アドレスをドメインの承認済み IP アドレスのリストと照らし合わせて確認することで、E メールメッセージが承認されたソースから送信されたことを確認するのに役立ちます。
   * DKIM(DomainKeys Identified Mail): DMARC は、DKIM を使用して電子署名を E メールメッセージに追加し、受信者がメッセージの整合性と信頼性を検証できるようにします。

* DMARC は、悪意のあるアクターがドメインから来たような E メールを送信するのを防ぐのに役立ちます。 DMARC を設定すると、認証チェックに失敗したメッセージを電子メールプロバイダが処理する方法を指定して、フィッシング E メールが受信者に到達する可能性を減らすことができます。

* DMARC は、ドメインから送信されたと主張するメッセージが発生した場合に従うべき E メールプロバイダー向けの明確なポリシーを提供し、E メールの配信品質の向上に役立ちます。 これにより、正当な E メールがスパムとしてマークされたり拒否されたりする可能性が低くなります。

* DMARC を実装すると、不正な当事者がドメインをフィッシングやその他の悪意のあるアクティビティで悪用しないようにすることで、ブランドの評判を保護できます。 これは、顧客やパートナーとの E メール通信に依存する企業や組織で特に重要です。

DMARC レコードの設定では、ドメインの DNS 設定に DNS TXT レコードを追加します。 このレコードは、認証に失敗したメッセージを強制隔離するか拒否するかなど、DMARC ポリシーを指定します。 DMARC の実装は、メールセキュリティを強化し、組織と受信者の両方をメールベースの脅威から保護するための積極的なステップです。

## DMARC の実装 {#implement-dmarc}

* DMARC を追加しない場合、強制隔離されます（少なくとも）。

* 正規のインボックスを持っていることを確認し、コントロールで受け取ることができます — このインボックスを管理します (Adobeインボックスではないはずです )

推奨事項は 24 です。これは、通常、ISP が持つものです。
それ以外の場合は、容量を評価する/ /チャット GPT を確認

DMARC レコードが検出された場合は、リストと同じ値をコピー&amp;ペーストしたり、必要に応じて値を変更したりできます。

何も指定しない場合は、デフォルト値が使用されます。

### 完全にデリゲートされたサブドメイン

### CNAME を使用してデリゲートされたサブドメイン

エディションフローの CNAME の場合、CSV ファイルを再度ダウンロードする必要があります（完全にデリゲートされたものではありません）。





