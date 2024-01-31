---
solution: Journey Optimizer
product: journey optimizer
title: 新しい DMARC 要件に準拠
description: Journey Optimizer で DMARC レコードを設定する必要がある理由とタイミングについて学ぶ
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン、ドメイン、メール、DMARC、レコード
source-git-commit: c5da9e9cfd5c03d7c6898e492582e5cc3e466447
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 41%

---

# 新しい DMARC 要件に準拠 {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="必須の DMARC アップデートの詳細を学ぶ"
>abstract="業界のベストプラクティスの実施の一環として、Googleと Yahoo は共に、 **DMARC レコード** 電子メールを送信する際に使用するすべてのドメインの（最初は） **2024 年 2 月 2 日**.<br>したがって、Journey Optimizer でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認する必要があります。"

ドメインベースのメッセージ認証、レポート、準拠 (DMARC) は、ドメイン所有者がドメインを不正使用から保護できる電子メール認証方法です。 E メールプロバイダーや ISP に明確なポリシーを提供することで、悪意のある関係者がドメインからの E メールを送信するのを防ぐことができます。 DMARC を実装すると、正当な E メールがスパムとしてマークまたは拒否されるリスクが軽減され、E メールの配信品質が向上します。


業界のベストプラクティスの一環として、Googleと Yahoo! どちらも必要としている **DMARC レコード** 電子メールを送信するために使用するすべてのドメイン用。 この新しい要件は、次から適用されます： **2024 年 2 月 2 日**. [詳細情報](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html#dmarc){target="_blank"}

>[!CAUTION]
>
>Gmail および Yahoo! は、e メールがスパムフォルダーにランディングしたりブロックされたりする原因となる可能性があります。

そのため、[!DNL Journey Optimizer] でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認することを強くお勧めします。お客様のケースに適用される、以下の手順に従います。

* 次の条件を満たしている場合： [完全に委任された](delegate-subdomain.md#full-subdomain-delegation) サブドメインをAdobeに送信する場合は、次のいずれかのオプションに従います。

   * デリゲートされたサブドメインの親ドメインに DMARC を設定します **をホスティングソリューションで使用**.
or
   * デリゲートされたサブドメインに対する DMARC の設定 **（内）[!DNL Journey Optimizer]** 設定ユーザーインターフェイス — ホスティングソリューションで余分な作業をおこなう必要がありません。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

* 送信サブドメインを [CNAME](delegate-subdomain.md#cname-subdomain-delegation)、次のいずれかのオプションに従います。

   * サブドメインまたはサブドメインの親ドメインで DMARC を設定する **をホスティングソリューションで使用**.
or
   * デリゲートされたサブドメインに対する DMARC の設定 **（内）[!DNL Journey Optimizer]** 設定ユーザーインターフェイス。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

  ただし、CNAME のデリゲーションでは、ホスティングソリューションでのエントリも必要になります。 その結果、IT 部門との連携を図り、「 [この節](dmarc-record.md#implement-dmarc).


Google と Yahoo が共有する最新のタイムラインは次のとおりです。

* Google：

   * **2024年2月**：コンプライアンス違反の警告を提供するために設計された、一時的なバウンスが開始されます。お客様がまだ準拠していない場合、メールは少し遅れてから通常どおり配信されます。完全に準拠している場合は、一時的なバウンスは発生せず、お客様には何の影響もありません。

   * **2024年4月** - DMARC 要件に準拠していない送信者に対して、ブロックが開始されます。最初は準拠していないメールの一部のみがブロックされ、時間の経過と共にブロック対象の割合が増加します。

   * **2024年6月1日（PT）**：完全に準拠していない送信者はブロックされます。

* Yahoo は正確な日付を指定していませんが、「適用のロールアウトは 2024年2月に開始します。適用は徐々にロールアウトされます」と述べています。

>[!NOTE]
>
>ご質問やサポートが必要な場合は、アドビ配信品質コンサルタントまたはアドビ担当者にお問い合わせください。

**役に立つリンク**

* DMARC の詳細については、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ja#about){target="_blank"}
* これらの変更に関する詳細なガイダンスについては、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html){target="_blank"}
* 読み取り [Google Gmail のお知らせ](https://blog.google/products/gmail/gmail-security-authentication-spam-protection/){target="_blank"}
* 読み取り [Yahoo! お知らせ](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}
