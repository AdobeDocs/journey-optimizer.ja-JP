---
solution: Journey Optimizer
product: journey optimizer
title: 必須の DMARC の更新
description: Journey Optimizerで DMARC レコードを設定する必要がある理由とタイミングを説明します
feature: Subdomains, Channel Configuration
topic: Administration
role: Admin
level: Experienced
keywords: サブドメイン，ドメイン，メール， dmarc，レコード
hide: true
hidefromtoc: true
source-git-commit: a93f1c81cceaee4f55cd7555284c4d8016ed4e21
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 3%

---

# 必須の DMARC の更新 {#dmarc-record-update}

>[!CONTEXTUALHELP]
>id="ajo_admin_dmarc_banner_link"
>title="必須の DMARC 更新の詳細を説明します"
>abstract="業界のベストプラクティスの実施の一環として、Googleと Yahoo は共に、 **DMARC レコード** 電子メールを送信する際に使用するすべてのドメインの（最初は） **2024 年 2 月 2 日**. <br>その結果、Journey OptimizerのAdobeにデリゲートしたすべてのサブドメインに対して DMARC レコードが設定されていることを確認する必要があります。"

業界のベストプラクティスの実施の一環として、Googleと Yahoo は共に、 **DMARC レコード** 電子メールを送信するために使用するすべてのドメイン用。 この新しい要件は、次の日から始まります。 **2024 年 2 月 2 日**.

Googleと Yahoo の要件について詳しくは、 [この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

>[!CAUTION]
>
>Gmail および Yahoo のこの新しい要件に準拠しないと、E メールがスパムフォルダーにランディングしたりブロックされたりする可能性があります。

そのため、Adobeでは、Adobeにデリゲートしたすべてのサブドメインに対して DMARC レコードを必ず設定することを強くお勧めします [!DNL Journey Optimizer]. お客様のケースに適用される以下の手順に従います。

<!--
* Set up DMARC on your subdomains, or on the parent domain of your subdomains, **in your hosting solution**. You can do it as of now.

* Set up DMARC on your delegated subdomains **using the upcoming feature in the [!DNL Journey Optimizer] administration UI** - with no extra work on your hosting solution. This feature will be available on January 30, 2024.

    >[!CAUTION]
    >
    >If you have set up [CNAME delegation](delegate-subdomain.md#cname-subdomain-delegation) for your sending subdomains, it will also require some entry into your hosting solution. Make sure you coordinate with your IT department so that they can perform the update as soon as the [!DNL Journey Optimizer] feature is available (on January 30, 2024). (and be ready on February 1st, 2024)

    More details on the [!DNL Journey Optimizer] DMARC upcoming feature will come soon.
-->

* 次の条件を満たしている場合： [完全に委任された](delegate-subdomain.md#full-subdomain-delegation) サブドメインをAdobeに送信する場合は、次の 2 つのオプションのいずれかに従います。

   * デリゲートされたサブドメインの親ドメインに DMARC を設定します **をホスティングソリューションで使用**.

   * デリゲートされたサブドメインに対する DMARC の設定 **の今後の機能の使用 [!DNL Journey Optimizer] 管理 UI**  — ホスティングソリューションで余分な作業をおこなう必要はありません。

* 次の設定が完了している場合、 [CNAME デリゲーション](delegate-subdomain.md#cname-subdomain-delegation) 送信サブドメインの場合は、次の 2 つのオプションのいずれかに従います。
   * サブドメインまたはサブドメインの親ドメインで DMARC を設定する **をホスティングソリューションで使用**.
   * デリゲートされたサブドメインに対する DMARC の設定 **の今後の機能の使用 [!DNL Journey Optimizer] 管理 UI**. ただし、ホスティングソリューションにもエントリが必要になります。 その結果、IT 部門との連携を図り、IT 部門が [!DNL Journey Optimizer] 機能が利用可能になった（1 月 30 日）。 <!--and be ready on February 1st, 2024-->

**詳細は、 [!DNL Journey Optimizer] DMARC の今後の機能は近日中に提供されます。**

>[!NOTE]
>
>ご質問やサポートが必要な場合は、担当のAdobe配信品質コンサルタントまたはAdobe担当者にお問い合わせください。

Googleと Yahoo が共有する最新のタイムラインは次のとおりです。

* GOOGLE:

   * **2024 年 2 月**  — コンプライアンス違反の警告を提供するために設計された一時的なバウンスが開始されます。 お客様がまだ準拠していない場合、メールは少し遅れてから通常どおり配信されます。完全に準拠している場合、一時的なバウンスはなく、影響を受けません。

   * **2024 年 4 月** - DMARC 要件に準拠していない送信者に対して、ブロックが開始されます。 ブロックの割合は時間の経過と共に増加し、準拠していない E メールの一部のみが最初にブロックされます。

   * **2024 年 6 月 2 日**  — 送信者が完全に準拠していない場合、ブロックが発生します。

* Yahoo は正確な日付を提供していませんが、「実施のロールアウトは 2024 年 2 月に始まります。 実施は徐々に展開される」と述べた。

>[!NOTE]
>
>での DMARC の実装の詳細 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/technotes/implement-dmarc.html#about){target="_blank"} e メール配信品質への影響をより深く理解する。
