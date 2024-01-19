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
hide: true
hidefromtoc: true
source-git-commit: 5565c98e41e0abc9ae93f85cb12679e372e6d36f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 19%

---

# DMARC レコードの重要な更新{#dmarc-record}


>[!CAUTION]
>
>一括送信者に対する Gmail および Yahoo の最近のお知らせに従い、Journey Optimizerは DMARC 認証テクノロジーをサポートするようになりました。

Googleと Yahoo は、業界のベストプラクティスの実施の一環として、電子メールを送信する際に使用するすべてのドメインに対して DMARC レコードを持っている必要があります。 この新しい要件は、次の日から始まります。 **2024 年 2 月 2 日**.

Googleと Yahoo の DMARC レコードに対する要件について詳しくは、 [この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

Googleと Yahoo で発表された変更の詳細 [このページ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/guidance-around-changes-to-google-and-yahoo.html?lang=en#dmarc%3A){target="_blank"}.

次に、次の手順を示すセクションに対して、アクションまたは次の手順が実行されます。

すべてのサブドメインに対して設定する必要があります
* ドメインを完全にアドビにデリゲートした場合は、2 つのオプションがあります
   * ホスティングソリューションのデリゲートドメインの親ドメインに DMARC を設定します。または
   * ホスティングソリューションでの追加作業なしで、管理 UI の今後の機能を使用してデリゲートされたドメインに DMARC をセットアップ
* 送信ドメインに CNAME を設定している場合は、次の 2 つのオプションがあります
   * サブドメインで DMARC を設定するか、ホスティングソリューションでサブドメインの親ドメインを設定する。または
   * Admin UI の今後の機能を使用して、DMARC を設定します。 ただし、UI だけでなく、ホスティングソリューションにもエントリする必要があります。

近日中に追加予定の機能の詳細が予定されています。

また、DMARC に関連するセクションを下のセクション（上のリンクからコピー）からコピーすることで、設定しない場合は影響を含めることができます。 DMARC 関連のものだけを引き出すか または、DMARC のお知らせと、1 回のクリックで購読解除が行われ、両方の機能の最新のタイムラインがここに表示されます。

10 月の初回発表以降、タイムラインの更新が予定されています。

最新のタイムラインは次のようになります。

Gmail:

* 2024年2月 - コンプライアンス違反の警告を提供するために設計された、一時的なバウンスが開始されます。お客様がまだ準拠していない場合、メールは少し遅れてから通常どおり配信されます。完全に準拠している場合、一時的なバウンスはなく、何も気付きません。
* 2024年4月 - ワンクリックリスト登録解除を除くすべてに準拠していない送信者に対して、ブロックが開始されます。最初は準拠していないメールの一部のみがブロックされ、時間の経過と共にブロック対象の割合が増加します。
* 2024年6月1日（PT）- ワンクリックリスト登録解除など、完全に準拠していない送信者はブロックされます。

Yahoo:

正確な日付を指定していませんが、「実施のロールアウトは 2024 年 2 月に始まります。 実施は徐々に展開される」と述べた。
