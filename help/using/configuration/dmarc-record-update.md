---
solution: Journey Optimizer
product: journey optimizer
title: 新しい DMARC 要件に準拠
description: Journey Optimizerで DMARC レコードを設定する必要がある理由とタイミングを説明します
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン，ドメイン，メール， dmarc，レコード
source-git-commit: e1fda25bb16f6d1e304d600dfce39df07fc570b0
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 5%

---

# 新しい DMARC 要件に準拠 {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="必須の DMARC 更新の詳細を説明します"
>abstract="業界のベストプラクティスの実施の一環として、Googleと Yahoo は共に、 **DMARC レコード** 電子メールを送信する際に使用するすべてのドメインの（最初は） **2024 年 2 月 2 日**.<br>その結果、Journey OptimizerのAdobeにデリゲートしたすべてのサブドメインに対して DMARC レコードが設定されていることを確認する必要があります。"

ドメインベースのメッセージ認証、レポート、準拠 (DMARC) は、ドメイン所有者がドメインを不正使用から保護できる電子メール認証方法です。 E メールプロバイダーや ISP に明確なポリシーを提供することで、悪意のある関係者がドメインからの E メールを送信するのを防ぐことができます。 DMARC を実装すると、正当な E メールがスパムとしてマークまたは拒否されるリスクが軽減され、E メールの配信品質が向上します。


業界のベストプラクティスの一環として、Googleと Yahoo! どちらも必要としている **DMARC レコード** 電子メールを送信するために使用するすべてのドメイン用。 この新しい要件は、次から適用されます： **2024 年 2 月 2 日**. [詳細情報](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html#dmarc){target="_blank"}。

>[!CAUTION]
>
>Gmail および Yahoo! は、e メールがスパムフォルダーにランディングしたりブロックされたりする原因となる可能性があります。

そのため、Adobeでは、Adobeにデリゲートしたすべてのサブドメインに対して DMARC レコードを必ず設定することを強くお勧めします [!DNL Journey Optimizer]. お客様のケースに適用される以下の手順に従います。

* 次の条件を満たしている場合： [完全に委任された](delegate-subdomain.md#full-subdomain-delegation) サブドメインをAdobeに送信する場合は、次のいずれかのオプションに従います。

   * デリゲートされたサブドメインの親ドメインに DMARC を設定します **をホスティングソリューションで使用**.
or
   * デリゲートされたサブドメインに対する DMARC の設定 **（内）[!DNL Journey Optimizer]** 設定ユーザーインターフェイス — ホスティングソリューションで余分な作業をおこなう必要がありません。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

* 送信サブドメインを [CNAME](delegate-subdomain.md#cname-subdomain-delegation)、次のいずれかのオプションに従います。

   * サブドメインまたはサブドメインの親ドメインで DMARC を設定する **をホスティングソリューションで使用**.
or
   * デリゲートされたサブドメインに対する DMARC の設定 **（内）[!DNL Journey Optimizer]** 設定ユーザーインターフェイス。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

     ただし、CNAME のデリゲーションでは、ホスティングソリューションでのエントリも必要になります。 その結果、IT 部門との連携を図り、IT 部門が [!DNL Journey Optimizer] 機能が利用可能になった（1 月 30 日）。 [詳細情報](dmarc-record.md#implement-dmarc)

**1 月 30 日より、DMARC 実装用のセルフサービスインターフェイスをご利用いただけます。 詳しくは、[この節](dmarc-record.md#implement-dmarc)を参照してください。**

Googleと Yahoo が共有する最新のタイムラインは次のとおりです。

* GOOGLE:

   * **2024 年 2 月**  — コンプライアンス違反の警告を提供するために設計された一時的なバウンスが開始されます。 お客様がまだ準拠していない場合、メールは少し遅れてから通常どおり配信されます。完全に準拠している場合、一時的なバウンスはなく、影響を受けません。

   * **2024 年 4 月** - DMARC 要件に準拠していない送信者に対して、ブロックが開始されます。 ブロックの割合は時間の経過と共に増加し、準拠していない E メールの一部のみが最初にブロックされます。

   * **2024 年 6 月 2 日**  — 送信者が完全に準拠していない場合、ブロックが発生します。

* Yahoo は正確な日付を提供していませんが、「実施のロールアウトは 2024 年 2 月に始まります。 実施は徐々に展開される」と述べた。

>[!NOTE]
>
>ご質問やサポートが必要な場合は、担当のAdobe配信品質コンサルタントまたはAdobe担当者にお問い合わせください。

**役に立つリンク**

* DMARC の詳細については、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"}
* これらの変更に関する詳細なガイダンスについては、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html){target="_blank"}
* 読み取り [Google Gmail のお知らせ](https://blog.google/products/gmail/gmail-security-authentication-spam-protection/){target="_blank"}
* 読み取り [Yahoo! お知らせ](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}
