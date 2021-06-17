---
title: Adobe Campaign v7/v8アクション
description: Adobe Campaign v7/v8のアクションについて説明します
feature: アクション
topic: 管理
role: Administrator
level: Intermediate
source-git-commit: 9ca747c4f46fd7eb24dbbf12350d7bbe409b1617
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 49%

---

# Adobe Campaign v7/v8アクション {#using_campaign_classic}

統合は、Adobe Campaign v7またはv8がある場合に使用できます。 Adobe Campaignのトランザクションメッセージ機能を使用して、Eメール、プッシュ通知、SMSを送信できます。

Journey OptimizerインスタンスとCampaignインスタンス間の接続は、プロビジョニング時にAdobeによって設定されます。 連絡先Adobe。

これを機能させるには、専用のアクションを設定する必要があります。 [この節](../action/acc-action.md)を参照してください。

エンドツーエンドの使用例については、この[節](../building-journeys/campaign-classic-use-case.md)で説明します。

1. イベントから始めて、ジャーニーを設計します。 この[節](../building-journeys/journey.md)を参照してください。
1. パレットの「**アクション**」セクションで、Campaign アクションを選択してジャーニーに追加します。
1. **アクションパラメーター**&#x200B;には、メッセージペイロードで想定されるすべてのフィールドが表示されます。 これらの各フィールドを、イベントまたはデータソースのいずれかから使用するフィールドにマッピングする必要があります。これはカスタムアクションと似ています。 [この節](../building-journeys/using-custom-actions.md)を参照してください。

![](../assets/accintegration2.png)
