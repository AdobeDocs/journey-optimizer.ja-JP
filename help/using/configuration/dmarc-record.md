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
source-git-commit: 49cb9734d66dc1aa2a3531c71a687aac00834d82
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# DMARC レコード {#dmarc-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_record"
>title="DMARC レコードを設定"
>abstract="ISP での配信品質の問題を回避するために DMARC レコードを設定"

>[!CAUTION]
>
>一括送信者に対する Gmail および Yahoo の最近のお知らせに従い、Journey Optimizerは DMARC 認証テクノロジーをサポートするようになりました。//DMARC サポートを含めるには、インスタンスで作成済みのすべてのサブドメインを更新する必要があります。//

2 月 1 日までにそれを行うことが重要です。

開始日

次の 2 つのオプションがあります。

* 今の時点で、IT 部門との連携を可能にします。

* AJO で実行します。ただし、その場合は 1 月 30 日まで待つ必要があります。

   * 完全なデリゲーション： 1 月 30 日（AJO リリース）に実行できます。

   * CNAME は、IT 部門と共に計画を立てるので、時間はかかりませんが、計画を立てる必要があります

Googleと Yahoo は、業界のベストプラクティスの実施の一環として、電子メールを送信する際に使用するすべてのドメインに対して DMARC レコードを持っている必要があります。 この新しい要件は、次の日から始まります。 **2024 年 2 月 2 日**.

Googleと Yahoo の DMARC レコードに対する要件について詳しくは、 [この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

Googleと Yahoo で発表された変更の詳細 [このページ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

DMARC（の略） **ドメインベースのメッセージ認証、レポート、適合**&#x200B;は、電子メールのスプーフィング、フィッシング、その他の不正アクティビティから保護するのに役立つ電子メール認証プロトコルです。

* 電子メール認証：

   * SPF (Sender Policy Framework): DMARC は SPF に基づいて送信メールサーバーの ID を認証します。 SPF は、送信サーバーの IP アドレスをドメインの承認済み IP アドレスのリストと照らし合わせて確認することで、E メールメッセージが承認されたソースから送信されたことを確認するのに役立ちます。
   * DKIM(DomainKeys Identified Mail): DMARC は、DKIM を使用して電子署名を E メールメッセージに追加し、受信者がメッセージの整合性と信頼性を検証できるようにします。

* DMARC は、悪意のあるアクターがドメインから来たような E メールを送信するのを防ぐのに役立ちます。 DMARC を設定すると、認証チェックに失敗したメッセージを電子メールプロバイダが処理する方法を指定して、フィッシング E メールが受信者に到達する可能性を減らすことができます。

* DMARC は、ドメインから送信されたと主張するメッセージが発生した場合に従うべき E メールプロバイダー向けの明確なポリシーを提供し、E メールの配信品質の向上に役立ちます。 これにより、正当な E メールがスパムとしてマークされたり拒否されたりする可能性が低くなります。

* DMARC を実装すると、不正な当事者がドメインをフィッシングやその他の悪意のあるアクティビティで悪用しないようにすることで、ブランドの評判を保護できます。 これは、顧客やパートナーとの E メール通信に依存する企業や組織で特に重要です。

DMARC レコードの設定では、ドメインの DNS 設定に DNS TXT レコードを追加します。 このレコードは、認証に失敗したメッセージを強制隔離するか拒否するかなど、DMARC ポリシーを指定します。 DMARC の実装は、メールセキュリティを強化し、組織と受信者の両方をメールベースの脅威から保護するための積極的なステップです。

[DMARC の詳細については、配信品質のベストプラクティスガイドを参照してください。](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} DMARC が e メールの配信品質に与える影響をより深く理解する。

DMARC を追加しない場合、強制隔離されます（少なくとも）。

正規の受信トレイがあり、自分のコントロールで受け取れることを確認してください — この受信トレイを管理します (Adobe受信トレイではないはずです )

24 をお勧めします。一般的に、それより少ない場合は、容量を評価する/あなたの/チャット GPT を確認してください

Googleと Yahoo、およびおそらく他のすべての主要 ISP

エディションフローの CNAME の場合、CSV ファイルを再度ダウンロードする必要があります（完全にデリゲートされたものではありません）。

新しい DMARC レコード

RN > put it first すべてのサブドメインを DMARC サポートで更新する必要があります。



