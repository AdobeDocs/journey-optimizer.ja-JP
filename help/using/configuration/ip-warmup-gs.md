---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランの概要
description: IP ウォームアッププランの実装方法を学ぶ
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP、プール、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
source-git-commit: dc1eeb3c199e7db2fc152b682404a547e2ae56c7
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 33%

---

# IP ウォームアッププランの概要 {#ip-warmup-gs}

<!--
>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_plan"
>title="Define your IP warmup plan"
>abstract="You can perform IP warmup workflows directly from the Journey Optimizer interface in a standardized and efficient way that follows the best practices for optimal deliverability."
-->

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* **[IP ウォームアップの概要](ip-warmup-gs.md)**
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* [IP ウォームアッププランを作成する](ip-warmup-plan.md)
* [IP ウォームアッププランを実行する](ip-warmup-running.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>IP ウォームアップ機能は、現在、選択したユーザーのみを対象としたベータ版として利用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

を使用 [!DNL Journey Optimizer]を使用すると、最適な配信品質を実現するベストプラクティスに従って、標準化された効率的な方法で、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できます。

>[!CAUTION]
>
>これはメールチャネルにのみ適用されます。

新しいプラットフォームを使用してメールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量のメールが突然送信されると、ISP はそれらのメールをスパムとしてマークします。

IP ウォームアッププラン機能を使用すると、スパムとしてマークされないように、送信されるボリュームを徐々に増やすことができます。 新しいオプション **[!UICONTROL 管理]** メニューを使用すると、複雑な日次ジャーニーを作成する代わりに、よりスムーズに実行できます。 この方法により、スタートアップフェーズをスムーズに進め、無効なアドレスが全体に占める割合を減らすことができます。

>[!NOTE]
>
>IP ウォーミングを使用した E メールの評判の向上について詳しくは、 [配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja).

<!--
Benefits

* Standardization on Campaign which will be easy for practitioners too > why?

* No more pain of creating queries, audiences and testing those as system will create the audiences. 

* Ease of excluding domains and changing the plan with help of simple toggles to exclude OR by editing numbers inline or create new phases or reupload plan if drastic change. No more pain of editing audience definitions, journey conditions

* There is an expectation that with this, it will ease around 30% of effort and will be much better experience for consultant/partner/practitioner - right from planning to execution to reporting
-->

IP ウォームアップ計画を実装する主な手順は次のとおりです。

1. 最初に、IP ウォームアップオプションを有効にして、1 つ以上のキャンペーンを作成する必要があります。 [詳細情報](ip-warmup-campaign.md) <!--this is usually done by a marketer persona??)-->

1. IP ウォームアッププランを作成し、プランをアップロードします。 [詳細情報](ip-warmup-plan.md) <!--this is usually done by a deliverability consultant??-->

1. プランの各段階を調整し、実行をアクティブにします。 [詳細情報](ip-warmup-running.md)
