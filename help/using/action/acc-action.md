---
title: Adobe Campaign v7／v8 との統合
description: Adobe Campaign v7／v8 との統合方法を学ぶ
feature: アクション
topic: 管理
role: Admin
level: Intermediate
source-git-commit: 63de381ea3a87b9a77bc6f1643272597b50ed575
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 98%

---

# Adobe Campaign v7／v8 との統合 {#integrating-with-adobe-campaign-classic}

この統合は、Adobe Campaign Classic v7 リリース 21.1 以降および Adobe Campaign v8 で利用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。

Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。

エンドツーエンドの使用例については、[この節](../building-journeys/campaign-classic-use-case.md)を参照してください。

設定したアクションごとに、1 つのアクションアクティビティをジャーニーデザイナーパレットで使用できます。[この節](../building-journeys/using-adobe-campaign-classic.md)を参照してください。

## 重要な注意事項

* メッセージのスロットル処理はおこなわれません。Campaign の現行の SLA に基づいて、送信できるメッセージの数を 1 時間あたり 50,000 件に制限しています。この理由から、Journey Optimizer は単一のユースケース（セグメントではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。Adobe Campaign から使用する各テンプレートに対して、Journey Optimizer でアクションを 1 つずつ設定する必要があります。

* この統合にホストしている専用の Message Center インスタンスを使用して、実行中の 他の Campaign 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。 必要なビルドは、リリース候補 21.1 以降です。

* ペイロード、または Campaign メッセージが正しいかどうかは検証されません。

* セグメントの認定イベントでは、Campaign アクションを使用できません。

## 前提条件

Campaign では、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。[Adobe Campaignのドキュメント](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=ja#transactional-messaging){target=&quot;_blank&quot;}を参照してください。

以下のパターンに従って、各メッセージに対応する JSON ペイロードを作成できます。Journey Orchestration でアクションを設定する際に、このペイロードを貼り付けてください（以下を参照）。

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

## アクションの設定

Journey Optimizer では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。次の手順に従います。

1. 新規アクションを作成します。[この節](../action/action.md)を参照してください。
1. 名前と説明を入力します。
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
1. 「**ペイロード**」フィールドをクリックし、 Campaign メッセージに対応する JSON ペイロードの例を貼り付けます。アドビに問い合わせて、このペイロードを取得してください。 
1. ジャーニー キャンバスでマッピングするかどうかに応じて、さまざまなフィールドを静的または可変に調整します。メールアドレスのチャネルパラメーターやパーソナライゼーションフィールド（ctx）など、特定のフィールドは、ジャーニーのコンテキストでマッピングの変数として定義する必要があります。
1. 「**保存**」をクリックします。

![](../assets/accintegration1.png)


