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
exl-id: 393f051d-b86d-4b4f-b564-7a9ae3a5d4b8
source-git-commit: 5dd6ebadd7b8c7490cb10496282697ce32ff3693
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 57%

---

# IP ウォームアッププランの概要 {#ip-warmup-gs}

[!DNL Journey Optimizer] を使用すると、最適な配信品質を実現するためのベストプラクティスに従って、標準化された効率的な方法で、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できます。新しいプラットフォームを使用してメールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。多くの場合、大量のメールが突然送信されると、ISP はそれらのメールをスパムとしてマークします。

IP ウォームアッププラン機能を使用すると、送信量を徐々に増やすことができ、スパムとしてマークされないようにできます。**[!UICONTROL 管理]** メニューのこの新しいオプションを使用すると、ボリューム管理を自動化し、複雑なジャーニー設定を必要とせずにウォームアッププロセスを簡素化できます。

>[!NOTE]
>
>IP ウォームアッププランを実装する前に、この [IP ウォームアップ配信品質ガイド ](ip-warmup-deliverability-guide.md) で、配信品質の基礎、評判の構築、ベストプラクティスについて学びます。

➡️ [ このビデオで IP ウォームアッププランを作成して実行する方法を説明します ](#video)

>[!AVAILABILITY]
>
>この機能は、実稼動タイプのサンドボックスでのみ有効にできます。

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

>[!VIDEO](https://video.tv.adobe.com/v/3432637/?learn=on)

>[!NOTE]
>
>IP ウォーミングを使用してメールの評判を高める方法については、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja)をご参照ください。

## その他のリソース {#additional-resources}

IP ウォームアップに関する詳細なガイダンスについては、次の役立つブログ投稿を参照してください。

* [Adobe Journey Optimizer配信品質ガイド：評価ゼロからインボックスヒーローまで ](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/adobe-journey-optimizer-deliverability-guide-from-zero/ba-p/761950) – 評価の基礎、ウォームアップカレンダー、監視、トラブルシューティングのベストプラクティスを含む包括的なガイドです。

* [IP ウォームアップの設定方法について ](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warmup-understanding-how-to-set-up-the-ip-warmup/ba-p/761949) - IP ウォームアッププランの設定の基本と、実装を成功させるためのベストプラクティスについて説明します。

* [IP ウォームアッププランの高度な機能 ](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/advanced-features-in-ajo-ip-warm-up-plans-granular-controls-for/ba-p/761958) - IP ウォームアップ戦略を最適化するための高度な機能と詳細な制御を見つけます。

* [IP ウォームアップトラブルシューティング ](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warm-up-troubleshooting-audience-delays-and-smart-retry/ba-p/761952) - オーディエンスの遅延などの一般的な問題の解決策と、スマート再試行メカニズムについて説明します。
