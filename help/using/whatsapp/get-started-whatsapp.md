---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp メッセージの基本を学ぶ
description: Journey Optimizer で WhatsApp メッセージを作成して送信する方法を学ぶ
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
exl-id: 22df2bfa-4d86-464e-ad83-3aa457e3a747
source-git-commit: 73a347c104fe28799c264f9a8b6c3e5e12c8d892
workflow-type: ht
source-wordcount: '340'
ht-degree: 100%

---

# WhatsApp メッセージの基本を学ぶ {#get-started-whatsapp}

Meta の [Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/) 経由で、Journey Optimizer を通じて WhatsApp メッセージを直接送信できるようになりました。この機能を使用すると、ジャーニーとキャンペーンへの WhatsApp のシームレスな統合を実現し、受信者との通信とエンゲージメントを強化できます。

* **ジャーニー**&#x200B;の場合：ジャーニーを作成し、**WhatsApp** アクティビティを追加し、基本設定を定義してから、右側の&#x200B;**[!UICONTROL アクション：WhatsApp]** パネルを参照して WhatsApp メッセージのコンテンツを作成します。ジャーニーを作成する方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

* **キャンペーン**&#x200B;の場合：キャンペーンを作成し、アクションとして「**WhatsApp**」を選択し、基本設定を定義してから、メッセージのコンテンツを編集して送信する WhatsApp メッセージを定義します。詳しくは、[アクションキャンペーン](../campaigns/campaign-action.md#action-campaign-action) | [API トリガーキャンペーン](../campaigns/api-triggered-campaigns.md) | [オーケストレーションキャンペーン](../orchestrated/create-orchestrated-campaign.md#create)の作成方法を参照してください

![](assets/do-not-localize/whatsapp-beta.png){zoomable="yes"}

## 前提条件 {#prereq}

WhatsApp を Journey Optimizer と統合するには、次が必要です。

* Meta Business Manager アカウント
* [送信者名と電話番号が認証された WhatsApp Business アカウント](https://developers.facebook.com/docs/whatsapp/overview/business-accounts/)
* [適切な権限を持つユーザー認証トークン](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [承認済み Meta テンプレート](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)

統合を進める前に、次も確認する必要があります。

* [WhatsApp コンテンツルール](https://www.whatsapp.com/legal/messaging-guidelines)
* [Meta ポリシーへの準拠](https://www.whatsapp.com/legal)
* [24 時間の会話の制限](https://developers.facebook.com/docs/whatsapp/messaging-limits/)

## 制限事項 {#limitations}

次の制限が WhatsApp チャネルに適用されます。

* Adobe Journey Optimizer の WhatsApp チャネルは HIPAA に対応していますが、サードパーティベンダーはアドビの BAA の対象ではありません。顧客は、独自のコンプライアンスとベンダー検証に責任を負います。

* 自動応答メッセージまたは定義済み応答メッセージはまだサポートされていません。

* 2025年4月以降、米国の電話番号（+1 ダイヤルコードと米国の市外局番で構成される番号）を持つ WhatsApp ユーザーに対するすべてのマーケティングテンプレートメッセージの配信が一時的に停止されました。[詳しくは、Meta ドキュメントを参照してください](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/send-message-templates#per-user-marketing-template-message-limits)。

* ネイティブ統合機能では、サードパーティのビジネスサービスプロバイダー（BSP）との統合は許可されていません。

## チュートリアルビデオ {#video}

以下のビデオでは、Adobe Journey Optimizer のネイティブチャネルとして WhatsApp を統合し、安全でリアルタイムのパーソナライズされたメッセージを大規模に配信する方法について説明します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3470245?captions=jpn&learn=on)

+++

## その他の学習リソース

WhatsApp のメッセージと設定に関するその他のビデオチュートリアルを参照してください。

➡️ [WhatsApp チャネルのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction){target="_blank"}

