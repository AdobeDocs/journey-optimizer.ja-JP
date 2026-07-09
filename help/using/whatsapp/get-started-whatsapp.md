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
TQID: https://experienceleague.adobe.com/uHzRC9X6rB9EXH4gIFiRxFaeNcrTD0-40RrxZkN4XFg
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: b8df23d2-98a2-4406-86cc-2babe8728d36id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 75ebd043971ce40e2da0f627622441a46a8e667c
workflow-type: tm+mt
source-wordcount: 686
ht-degree: 65%

---

# WhatsApp メッセージの基本を学ぶ {#get-started-whatsapp}

>[!BEGINSHADEBOX]

**このページ：** Journey Optimizer での WhatsApp チャネルの仕組み、前提条件、制限事項について説明します。これにより、ジャーニーやキャンペーンに WhatsApp を追加する方法を決定できます。

>[!ENDSHADEBOX]

Meta の [Cloud API](https://developers.facebook.com/docs/whatsapp/cloud-api/) 経由で、Journey Optimizer を通じて WhatsApp メッセージを直接送信できるようになりました。 この機能を使用すると、ジャーニーとキャンペーンへの WhatsApp のシームレスな統合を実現し、受信者との通信とエンゲージメントを強化できます。

* **ジャーニー**&#x200B;の場合： ジャーニーを作成し、**WhatsApp** アクティビティを追加し、基本設定を定義してから、右側の&#x200B;**[!UICONTROL アクション：WhatsApp]** パネルを参照して WhatsApp メッセージのコンテンツを作成します。 ジャーニーを作成する方法について詳しくは、[このページ](../building-journeys/journey-gs.md)を参照してください。

* **キャンペーン**&#x200B;の場合： キャンペーンを作成し、アクションとして「**WhatsApp**」を選択し、基本設定を定義してから、メッセージのコンテンツを編集して送信する WhatsApp メッセージを定義します。 詳しくは、[アクションキャンペーン](../campaigns/campaign-action.md#action-campaign-action) | [API トリガーキャンペーン](../campaigns/api-triggered-campaigns.md) | [オーケストレーションキャンペーン](../orchestrated/create-orchestrated-campaign.md#create)を作成する方法を参照してください

![](assets/do-not-localize/whatsapp-beta.png){zoomable="yes"}

## ユースケース {#use-cases}

WhatsAppは、オーディエンスが既にプラットフォームを使用しており、リッチコンテンツと真の双方向の会話を組み合わせたい場合に最も効果的に機能します。

| 利点 | 理由 | ユースケースの例 |
| --- | --- | --- |
| グローバルな高いエンゲージメント | 多くの地域で広く利用されているメッセージングプラットフォーム | WhatsAppですでにアクティブな国際的な視聴者にリーチ |
| リッチでインタラクティブなメッセージ | 画像、ビデオ、ボタン、クイック返信をサポート | 商品カタログ、予約確認、クイック返信オプション |
| 双方向の会話体験 | 受信者は同じスレッド内で返信できます | カスタマーサポートとの会話、注文追跡に関する質問 |
| 公式APIによるコンプライアンスと信頼 | Metaの検証済みCloud APIを介して配信され、送信者確認が可能 | 受信者の信頼を築く、ブランド検証済みのコミュニケーション |
| 他のチャネルとの統合 | 他のチャネルと並行して、ジャーニーやキャンペーンのレイヤー化が可能 | WhatsAppを補完的な接点として利用したマルチチャネルジャーニー |

## 使用しない場合 {#when-not-to-use}

WhatsAppは、オーディエンスの導入と明示的な同意に依存しているため、あらゆるシナリオに適しているわけではありません。 次のような状況では、別のチャネルを検討してください。

* オーディエンスはWhatsAppを利用しません。なぜなら、地域やデモグラフィックによって採用は大きく異なるからです
* 受信者は、Metaのメッセージングポリシーで必要とされる明示的なオプトインを行っていません
* メッセージは緊急であり、保証された配信が必要であり、WhatsAppの配信とテンプレートレビューの制約により、SMSまたはプッシュ通知の処理が向上します
* コンテンツは長いまたは複雑で、メールに適しており、よりスペースと豊富なフォーマットが提供されます
* リアルタイムの会話サポートは、双方向のWhatsApp スレッドがタイムリーな返信の期待を設定するため、あなたの側では実現不可能です

## 前提条件 {#prereq}

WhatsApp を Journey Optimizer と統合するには、次が必要です。

* Meta Business Manager アカウント
* [送信者名と電話番号を検証済みの WhatsApp Business アカウント](https://developers.facebook.com/docs/whatsapp/overview/business-accounts/)
* [適切な権限を持つユーザー認証トークン](https://developers.facebook.com/blog/post/2022/12/05/auth-tokens/)
* [承認済み Meta テンプレート](https://developers.facebook.com/docs/whatsapp/message-templates/guidelines/)

統合を進める前に、次も確認する必要があります。

* [WhatsApp コンテンツルール](https://www.whatsapp.com/legal/messaging-guidelines)
* [Meta ポリシーへの準拠](https://www.whatsapp.com/legal)
* [24 時間の会話の制限](https://developers.facebook.com/docs/whatsapp/messaging-limits/)

## 制限事項 {#limitations}

次の制限が WhatsApp チャネルに適用されます。

* Adobe Journey Optimizer の WhatsApp チャネルは HIPAA に対応していますが、サードパーティベンダーはアドビの BAA の対象ではありません。 顧客は、独自のコンプライアンスとベンダー検証に責任を負います。

* 自動応答メッセージまたは定義済み応答メッセージはまだサポートされていません。

* 2025年4月以降、米国の電話番号（+1 ダイヤルコードと米国の市外局番で構成される番号）を持つ WhatsApp ユーザーに対するすべてのマーケティングテンプレートメッセージの配信が一時的に停止されました。 [詳しくは、Meta ドキュメントを参照してください](https://developers.facebook.com/docs/whatsapp/cloud-api/guides/send-message-templates#per-user-marketing-template-message-limits)。

* ネイティブ統合機能では、サードパーティのビジネスサービスプロバイダー（BSP）との統合は許可されていません。

## チュートリアルビデオ {#video}

以下のビデオでは、Adobe Journey Optimizer のネイティブチャネルとして WhatsApp を統合し、安全でリアルタイムのパーソナライズされたメッセージを大規模に配信する方法について説明します。

+++ こちらのビデオをご覧ください

>[!VIDEO](https://video.tv.adobe.com/v/3470244?learn=on)

+++

## その他の学習リソース

WhatsApp のメッセージと設定に関するその他のビデオチュートリアルを参照してください。

➡️ [WhatsApp チャネルのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/whatsapp/whatsapp-introduction){target="_blank"}

