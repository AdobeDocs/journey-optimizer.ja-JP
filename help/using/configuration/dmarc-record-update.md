---
solution: Journey Optimizer
product: journey optimizer
title: 新しい DMARC 要件への準拠
description: Journey Optimizer で DMARC レコードを設定する必要がある理由とタイミングについて学ぶ
feature: Subdomains, Channel Configuration, Deliverability
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン、ドメイン、メール、DMARC、レコード
exl-id: 15b10a61-6ecd-4ffa-b1c2-21e862263f6d
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 98%

---

# 新しい DMARC 要件への準拠 {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="必須のDMARC更新の詳細"
>abstract="Google と Yahoo は、業界のベストプラクティス実施の一環として、**2024年2月1日（PT）**&#x200B;から、メールを送信する際に使用するすべてのドメインに対して **DMARC レコード**&#x200B;を設定することを要求します。<br>したがって、Journey Optimizer でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認する必要があります。"

Domain-based Message Authentication、Reporting、および Conformance（DMARC）は、ドメイン所有者が自身のドメインを不正使用から保護するメール認証方法です。メールプロバイダーや ISP に明確なポリシーを提供することで、自分のドメインから悪意のある関係者がメールを送信するのを防ぐことができます。DMARC を実装すると、正当なメールがスパムとしてマークまたは拒否されるリスクが軽減され、メールの配信品質が向上します。

Google と Yahoo! は、業界のベストプラクティス実施の一環として、メール送信に使用するすべてのドメインに対して **DMARC レコード**&#x200B;を要求しています。この新しい要件は、**2024年2月1日（PT）**&#x200B;から適用されます。

>[!CAUTION]
>
>Gmail と Yahoo! のこの新しい要件に準拠しない場合、メールがスパムフォルダーに分類されたり、ブロックされたりすることが予想されます。

そのため、[!DNL Journey Optimizer] でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認することを強くお勧めします。お客様のケースに適用される、以下の手順に従います。

* 送信サブドメインをアドビに[完全にデリゲート](delegate-subdomain.md#full-subdomain-delegation)している場合は、以下のオプションのいずれかに従います。

   * **ホスティングソリューション**のデリゲートされたサブドメインの親ドメインに DMARC を設定します。
または
   * **[!DNL Journey Optimizer]** 設定ユーザーインターフェイスで、デリゲートされたサブドメインに DMARC を設定します。ホスティングソリューションで追加の作業を行う必要はありません。[方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

* [CNAME](delegate-subdomain.md#cname-subdomain-delegation) を使用して送信サブドメインを設定している場合は、以下のいずれかのオプションに従います。

   * **ホスティングソリューション**のサブドメインまたはサブドメインの親ドメインに DMARC を設定します。
または
   * **[!DNL Journey Optimizer]** 設定ユーザーインターフェイスで、デリゲートされたサブドメインに DMARC を設定します。[方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

  ただし、CNAME の設定では、ホスティングソリューションに追加のエントリも必要です。したがって、[この節](dmarc-record.md#implement-dmarc)で説明しているアップデートを実行できるように、IT 部門と必ず調整してください。

<!--The most recent timelines shared by Google and Yahoo! are as follows:

* Google:

    * **February 2024** – Temporary bounces designed to provide warning of non-compliance will begin. Emails will still be delivered as normal after a short delay if you are not yet in compliance. If you are fully in compliance there will be no temporary bounces and you will not be affected.

    * **April 2024** – Blocks will begin for senders who are not in compliance with DMARC requirement. Only a portion of non-compliant email will be blocked at first, with the percentage blocked increasing over time.

    * **June 1st, 2024** – Any sender not in full compliance will experience blocking.

* Yahoo! has not provided exact dates, but has said "the rollout of enforcement will begin in February 2024. Enforcement will be gradually rolled out".
-->

>[!NOTE]
>
>ご質問やサポートが必要な場合は、アドビ配信品質コンサルタントまたはアドビ担当者にお問い合わせください。

**役立つリンク**

* DMARC について詳しくは、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html?lang=ja#about){target="_blank"}を参照してください
* [Google Gmail のお知らせ](https://blog.google/products/gmail/gmail-security-authentication-spam-protection/){target="_blank"}を参照してください
* [Yahoo!のお知らせ](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}を参照してください

<!--Find more guidance about these changes in the [Deliverability Best Practice Guide]-->
