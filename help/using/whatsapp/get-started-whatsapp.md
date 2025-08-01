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
source-git-commit: 31e25c511d8873e54c7b92e65511108a77f84941
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 44%

---

# WhatsApp メッセージの基本を学ぶ {#get-started-whatsapp}

Meta の [Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/) を使用して、Journey Optimizerから直接 WhatsApp メッセージを送信できるようになりました。 この機能により、WhatsApp をジャーニーやキャンペーンにシームレスに統合し、受信者とのコミュニケーションとエンゲージメントを強化できます。

* **ジャーニー**&#x200B;の場合：ジャーニーを作成し、**WhatsApp** アクティビティを追加し、基本設定を定義してから、右側の&#x200B;**[!UICONTROL アクション：WhatsApp]** パネルを参照して WhatsApp メッセージのコンテンツを作成します。ジャーニーを作成する方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

* **キャンペーン**&#x200B;の場合：キャンペーンを作成し、アクションとして「**WhatsApp**」を選択し、基本設定を定義してから、メッセージのコンテンツを編集して送信する WhatsApp メッセージを定義します。キャンペーンを作成する方法について詳しくは、[このページ](../campaigns/create-campaign.md#configure)を参照してください。

![](assets/do-not-localize/whatsapp-beta.png){zoomable="yes"}

## 前提条件 {#prereq}

WhatsApp を Journey Optimizer と統合するには、次が必要です。

* Meta Business Manager アカウント
* [ 確認された送信者名と電話番号を持つ WhatsApp ビジネスアカウント ](https://developers.facebook.com/docs/whatsapp/overview/business-accounts/)
* [ 適切な権限を持つユーザー認証トークン ](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [承認済み Meta テンプレート](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)

統合を進める前に、次も確認する必要があります。

* [WhatsApp コンテンツルール](https://www.whatsapp.com/legal/messaging-guidelines)
* [Meta ポリシーへの準拠](https://www.whatsapp.com/legal)
* [24 時間の会話の制限](https://developers.facebook.com/docs/whatsapp/messaging-limits/)

## 制限事項 {#limitations}

WhatsApp チャネルには次の制限が適用されます。

* Adobe Journey Optimizerの WhatsApp チャネルは HIPAA に対応していますが、サードパーティベンダーはAdobeの BAA の対象ではありません。 顧客は、独自のコンプライアンスとベンダー検証に責任を負います。

* 自動または事前定義済みの応答メッセージは、まだサポートされていません。

* 2025 年 4 月以降、米国の電話番号（+1 のダイヤル コードと米国の市外局番で構成される番号）を持つ WhatsApp ユーザーに対するすべてのマーケティングテンプレートメッセージの配信が一時的に停止されました。 [ 詳しくは、Meta ドキュメントを参照してください ](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/send-message-templates#per-user-marketing-template-message-limits)

* ネイティブの統合機能では、サードパーティのビジネスサービスプロバイダー（BSP）との統合は許可されていません。

## チュートリアルビデオ {#video}

以下のビデオでは、WhatsApp をAdobe Journey Optimizerのネイティブチャネルとして統合して、安全でリアルタイムの、パーソナライズされたメッセージを大規模に提供する方法を示します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3470244?learn=on)

+++

