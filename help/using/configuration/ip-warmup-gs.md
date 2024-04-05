---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランの概要
description: IP ウォームアッププランの実装方法を学ぶ
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP、配信品質
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 393f051d-b86d-4b4f-b564-7a9ae3a5d4b8
source-git-commit: 9d48213d8367fdc6c0fae62b73d1706bc4983d9d
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%

---

# IP ウォームアッププランの概要 {#ip-warmup-gs}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* **[IP ウォームアップの概要](ip-warmup-gs.md)**
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* [IP ウォームアッププランを作成](ip-warmup-plan.md)
* [IP ウォームアッププランを実行](ip-warmup-execution.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>現在、IP ウォームアップ機能は、一部のユーザーのみを対象としたベータ版として利用できます。ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

[!DNL Journey Optimizer] を使用すると、最適な配信品質を実現するためのベストプラクティスに従って、標準化された効率的な方法で、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できます。

➡️ [IP ウォームアッププランの作成および実行方法については、このビデオをご覧ください](#video)

>[!CAUTION]
>
>これはメールチャネルにのみ適用されます。

新しいプラットフォームを使用してメールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量のメールが突然送信されると、ISP はそれらのメールをスパムとしてマークします。

IP ウォームアッププラン機能を使用すると、送信量を徐々に増やすことができ、スパムとしてマークされないようにできます。**[!UICONTROL 管理]**&#x200B;メニュー内のこの新しいオプションを使用すると、複雑な毎日のジャーニーを作成するのではなく、統合された方法でより簡単に実行できます。

>[!NOTE]
>
>IP ウォーミングを使用してメールの評判を高める方法については、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja)を参照してください。

<!--
Benefits

* Standardization on Campaign which will be easy for practitioners too > why?

* No more pain of creating queries, audiences and testing those as system will create the audiences. 

* Ease of excluding domains and changing the plan with help of simple toggles to exclude OR by editing numbers inline or create new phases or reupload plan if drastic change. No more pain of editing audience definitions, journey conditions

* There is an expectation that with this, it will ease around 30% of effort and will be much better experience for consultant/partner/practitioner - right from planning to execution to reporting
-->

IP ウォームアッププランを実装するための主な手順を以下に示します。

1. まず、IP ウォームアップオプションを有効にして、1 つ以上のキャンペーンを作成する必要があります。[詳細情報](ip-warmup-campaign.md)

1. [!DNL Journey Optimizer] で IP ウォームアッププランを作成し、配信品質コンサルタントの支援を得て作成した Excel シートをアップロードします。[詳細情報](ip-warmup-plan.md)

1. プランの各フェーズのキャンペーンを選択し、対応する実行をアクティベートします。[詳細情報](ip-warmup-execution.md)

## チュートリアルビデオ {#video}

IP ウォームアッププランの作成および実行方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3425965/?quality=12&learn=on)
