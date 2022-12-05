---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign v7／v8 との統合
description: Adobe Campaign v7／v8 との統合方法を学ぶ
feature: Actions
topic: Administration
role: Admin
level: Intermediate
exl-id: 109ba212-f04b-425f-9447-708c8e0b3f51
source-git-commit: f6db4f7cbb1951c009fa7915f340da96eea74120
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 100%

---

# Adobe Campaign v7/v8 との統合 {#integrating-with-adobe-campaign-classic}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_acc"
>title="Adobe Campaign v7/v8 のアクション"
>abstract="この統合は、Adobe Campaign Classic v7 および v8 で利用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。"

この統合は、Adobe Campaign Classic v7 リリース 7.1 以降および Adobe Campaign v8 で利用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。

Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。

エンドツーエンドの使用例については、[この節](../building-journeys/ajo-ac.md)を参照してください。

設定したアクションごとに、1 つのアクションアクティビティをジャーニーデザイナーパレットで使用できます。[この節](../building-journeys/using-adobe-campaign-classic.md)を参照してください。

## 重要な注意事項 {#important-notes}

* メッセージのスロットル処理はおこなわれません。システムは現在の Campaign SLA に基づいて、送信できるメッセージ数を 5 分ごとに 4,000 件までに制限します。この理由から、Journey Optimizer は単一のユースケース（セグメントではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。Adobe Campaign から使用する各テンプレートに対して、Journey Optimizer でアクションを 1 つずつ設定する必要があります。

* この統合にホストしている専用の Message Center インスタンスを使用して、実行中の 他の Campaign 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。必要なビルドは、リリース候補 21.1 以降です。

* ペイロード、または Campaign メッセージが正しいかどうかは検証されません。

* セグメントの選定イベントでは、Campaign アクションを使用できません。


## 前提条件 {#prerequisites}

Campaign では、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。[Adobe Campaign のドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=ja#transactional-messaging){target=&quot;_blank&quot;}を参照してください。

以下のパターンに従って、各メッセージに対応する JSON ペイロードを作成できます。Journey Optimizer でアクションを設定する際に、このペイロードを貼り付けます（以下を参照）。

次に例を示します。

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "Email address",
    "ctx": {
        "firstName": "First name"
    }
}
```

* **channel**：Campaign トランザクションテンプレート用に定義したチャネル
* **eventType**：Campaign イベントの内部名
* **ctx**：メッセージに含めるパーソナライズ機能に基づく変数。

## アクションの設定 {#configure-action}

Journey Optimizer では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。次の手順に従います。

1. 新規アクションを作成します。[この節](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
1. 「**ペイロード**」フィールドをクリックし、 Campaign メッセージに対応する JSON ペイロードの例を貼り付けます。アドビに問い合わせて、このペイロードを取得してください。 
1. ジャーニー キャンバスでマッピングするかどうかに応じて、さまざまなフィールドを静的または可変に調整します。メールアドレスのチャネルパラメーターやパーソナライゼーションフィールド（ctx）など、特定のフィールドは、ジャーニーのコンテキストでマッピングの変数として定義する必要があります。
1. 「**保存**」をクリックします。

![](assets/accintegration1.png)
