---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランの基本を学ぶ
description: IP ウォームアッププランの実装方法を学ぶ
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP、配信品質
exl-id: 393f051d-b86d-4b4f-b564-7a9ae3a5d4b8
TQID: https://experienceleague.adobe.com/xjJKrCXUmQY5sZu2w-B09agQh-tb4qkSXM0Vh2-TDnc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: c343082f-e963-4f57-a96b-b64d27f8118eid: d2e8a157-b3b0-4143-9ff3-809bf400be56id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0d9c480cc48c4352e82d1f4624c65fc16a60b959
workflow-type: tm+mt
source-wordcount: 489
ht-degree: 93%

---

# IP ウォームアッププランの基本を学ぶ {#ip-warmup-gs}

>[!BEGINSHADEBOX]

**このページでは、** IP ウォームアッププランを使用して、送信量を徐々に増やして送信者のレピュテーションを構築する方法を説明し、Adobe Journey Optimizerで送信量を実装するための主な手順を説明します。

>[!ENDSHADEBOX]

[!DNL Journey Optimizer] を使用すると、最適な配信品質を実現するためのベストプラクティスに従って、標準化された効率的な方法で、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できます。 新しいプラットフォームを使用してメールが送信された場合、インターネットサービスプロバイダー（ISP）は認識されない IP アドレスを疑わしく思います。 多くの場合、大量のメールが突然送信されると、ISP はそれらのメールをスパムとしてマークします。

IP ウォームアッププラン機能を使用すると、送信量を徐々に増やすことができ、スパムとしてマークされないようにできます。 **[!UICONTROL 管理]**&#x200B;メニューのこの新しいオプションを使用すると、ボリューム管理を自動化し、複雑なジャーニー設定を必要とせずにウォームアッププロセスを簡素化できます。

>[!NOTE]
>
>IP ウォームアッププランを実装する前に、配信品質の基本、評判の確立、ベストプラクティスについて詳しくは、この [IP ウォームアップ配信品質ガイド](ip-warmup-deliverability-guide.md)を参照してください。

➡️ [IP ウォームアッププランの作成および実行方法について詳しくは、このビデオをご覧ください](#video)

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

1. まず、IP ウォームアップオプションを有効にして、1 つ以上のキャンペーンを作成する必要があります。 [詳細情報](ip-warmup-campaign.md)

1. [!DNL Journey Optimizer] で IP ウォームアッププランを作成し、配信品質コンサルタントの支援を得て作成した Excel シートをアップロードします。 [詳細情報](ip-warmup-plan.md)

1. プランの各フェーズのキャンペーンを選択し、対応する実行をアクティベートします。 [詳細情報](ip-warmup-execution.md)

## チュートリアルビデオ {#video}

IP ウォームアッププランの作成および実行方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3432637/?learn=on)

>[!NOTE]
>
>IP ウォーミングを使用してメールの評判を高める方法については、[配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/generic-resources/increase-reputation-with-ip-warming.html?lang=ja)をご参照ください。

## その他のリソース {#additional-resources}

IP ウォームアップに関するガイダンスについて詳しくは、以下の役立つブログ投稿を参照してください。

* [Adobe Journey Optimizer 配信品質ガイド：ゼロ評判からインボックスヒーローまで](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/adobe-journey-optimizer-deliverability-guide-from-zero/ba-p/761950) - 評判の基本、ウォームアップカレンダー、監視、トラブルシューティングのベストプラクティスを対象とした包括的なガイド。

* [IP ウォームアップの設定方法について](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warmup-understanding-how-to-set-up-the-ip-warmup/ba-p/761949) - IP ウォームアッププランの設定の基本と、実装を成功させるためのベストプラクティスについて説明します。

* [IP ウォームアッププランの高度な機能](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/advanced-features-in-ajo-ip-warm-up-plans-granular-controls-for/ba-p/761958) - IP ウォームアップ戦略を最適化するための高度な機能と詳細なコントロールについて説明します。

* [IP ウォームアップのトラブルシューティング](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/ajo-ip-warm-up-troubleshooting-audience-delays-and-smart-retry/ba-p/761952) - オーディエンスの遅延などの一般的な問題の解決策と、スマート再試行メカニズムについて説明します。
