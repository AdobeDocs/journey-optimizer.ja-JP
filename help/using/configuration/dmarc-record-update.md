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
TQID: https://experienceleague.adobe.com/B-gnzjRpmhxELBiXRZxkBvE2yNNgozy-Hed5-k1oaIQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: cf64c7f6-7428-4ae5-b158-8df9771f38f4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 100%

---

# 新しい DMARC 要件への準拠 {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="必須の DMARC アップデートについて説明します"
>abstract="Google と Yahoo は、業界のベストプラクティス実施の一環として、**2024年2月1日（PT）**&#x200B;からメールを送信する際に使用するすべてのドメインに対して **DMARC レコード**&#x200B;を設定することを要求しています。<br>したがって、Journey Optimizer でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認する必要があります。"

DMARC（Domain-based Message Authentication, Reporting, and Conformance）は、ドメイン所有者が自身のドメインを不正使用から保護できるようにするメール認証方式です。 メールプロバイダーや ISP に明確なポリシーを提供することで、自分のドメインから悪意のある関係者がメールを送信するのを防ぐことができます。 DMARC を実装すると、正当なメールがスパムとしてマークまたは拒否されるリスクが軽減され、メールの配信品質が向上します。

Google と Yahoo! は、業界のベストプラクティス実施の一環として、 メール送信に使用するすべてのドメインに対して **DMARC レコード**&#x200B;を要求しています。 この新しい要件は、**2024年2月1日（PT）**&#x200B;から適用されます。

>[!CAUTION]
>
>Gmail と Yahoo! のこの新しい要件に準拠しない場合、 メールがスパムフォルダーに分類されたり、ブロックされたりすることが予想されます。

そのため、[!DNL Journey Optimizer] でアドビにデリゲートしたすべてのサブドメインに対して、DMARC レコードが設定されていることを確認することを強くお勧めします。 お客様のケースに適用される、以下の手順に従います。

* 送信サブドメインをアドビに[完全にデリゲート](delegate-subdomain.md#set-up-subdomain)している場合は、以下のオプションのいずれかに従います。

   * **ホスティングソリューション**のデリゲートされたサブドメインの親ドメインに DMARC を設定します。
または
   * **[!DNL Journey Optimizer]** 設定ユーザーインターフェイスで、デリゲートされたサブドメインに DMARC を設定します。ホスティングソリューションで追加の作業を行う必要はありません。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

* [CNAME](delegate-subdomain.md#cname-subdomain-setup) を使用して送信サブドメインを設定している場合は、以下のいずれかのオプションに従います。

   * **ホスティングソリューション**のサブドメインまたはサブドメインの親ドメインに DMARC を設定します。
または
   * **[!DNL Journey Optimizer]** 設定ユーザーインターフェイスで、デリゲートされたサブドメインに DMARC を設定します。 [方法についてはこちらを参照](dmarc-record.md#implement-dmarc)

  ただし、CNAME の設定では、ホスティングソリューションに追加のエントリも必要です。 したがって、[この節](dmarc-record.md#implement-dmarc)で説明しているアップデートを実行できるように、IT 部門と必ず調整してください。

<!--
The most recent timelines shared by Google and Yahoo! are as follows:

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
* [Yahoo! のお知らせ](https://blog.postmaster.yahooinc.com/post/730172167494483968/more-secure-less-spam){target="_blank"}を参照してください

<!--Find more guidance about these changes in the [Deliverability Best Practice Guide]-->
