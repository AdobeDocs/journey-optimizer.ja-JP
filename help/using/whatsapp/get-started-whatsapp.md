---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp メッセージの基本を学ぶ
description: Journey Optimizer で WhatsApp メッセージを作成して送信する方法を学ぶ
feature: Whatsapp
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 22df2bfa-4d86-464e-ad83-3aa457e3a747
source-git-commit: 7f507dc0113e85191429c2c48b873112b590e3ce
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 55%

---

# WhatsApp メッセージの基本を学ぶ {#get-started-whatsapp}

>[!BEGINSHADEBOX]

**目次**

* **[WhatsApp メッセージの基本を学ぶ](get-started-whatsapp.md)**
* [WhatsApp 設定の基本を学ぶ](whatsapp-configuration.md)
* [WhatsApp メッセージの作成](create-whatsapp.md)
* [WhatsApp メッセージの確認および送信](send-whatsapp.md)

>[!ENDSHADEBOX]

Meta の [Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/) を使用して、Journey Optimizerから直接 WhatsApp メッセージを送信できるようになりました。 この機能により、WhatsApp をジャーニーやキャンペーンにシームレスに統合し、受信者とのコミュニケーションとエンゲージメントを強化できます。

* **ジャーニー**&#x200B;の場合：ジャーニーを作成し、**WhatsApp** アクティビティを追加し、基本設定を定義してから、右側の&#x200B;**[!UICONTROL アクション：WhatsApp]** パネルを参照して WhatsApp メッセージのコンテンツを作成します。ジャーニーを作成する方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

* **キャンペーン**&#x200B;の場合：キャンペーンを作成し、アクションとして「**WhatsApp**」を選択し、基本設定を定義してから、メッセージのコンテンツを編集して送信する WhatsApp メッセージを定義します。キャンペーンを作成する方法について詳しくは、[このページ](../campaigns/create-campaign.md#configure)を参照してください。

![](assets/do-not-localize/whatsapp-beta.png){zoomable="yes"}

## 前提条件 {#prereq}

WhatsApp を Journey Optimizer と統合するには、次が必要です。

* Meta Business Manager アカウント
* WhatsApp Business アカウント
* WhatsApp 電話番号
* [ 適切な権限を持つユーザー認証トークン ](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [承認済み Meta テンプレート](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)
* [ メタ Webhook の設定 ](https://developers.facebook.com/docs/whatsapp/webhooks/)


統合を進める前に、次も確認する必要があります。

* [WhatsApp コンテンツルール](https://www.whatsapp.com/legal/messaging-guidelines)
* [Meta ポリシーへの準拠](https://www.whatsapp.com/legal)
* [24 時間の会話の制限](https://developers.facebook.com/docs/whatsapp/messaging-limits/)

## 制限事項 {#limitations}

WhatsApp チャネルには次の制限が適用されます。

* Adobe Journey Optimizerの WhatsApp チャネルは HIPAA に対応していますが、サードパーティベンダーはAdobeの BAA の対象ではありません。 顧客は、独自のコンプライアンスとベンダー検証に責任を負います。

* 自動または事前定義済みの応答メッセージはサポートされていません。

* 2025 年 4 月以降、米国の電話番号（+1 のダイヤル コードと米国の市外局番で構成される番号）を持つ WhatsApp ユーザーに対するすべてのマーケティングテンプレートメッセージの配信が一時的に停止されました。 [ 詳しくは、Meta ドキュメントを参照してください ](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/send-message-templates#per-user-marketing-template-message-limits)

* ネイティブの統合機能では、サードパーティのビジネスサービスプロバイダー（BSP）との統合は許可されていません。

## チュートリアルビデオ {#video}


次のビデオでは、WhatsApp アクションを使用してジャーニーを作成する方法について説明します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3451621?learn=on)

+++
