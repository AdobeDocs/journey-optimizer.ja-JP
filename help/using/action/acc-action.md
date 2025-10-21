---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Campaign v7／v8 との統合
description: Journey Optimizer を Adobe Campaign v7／v8 と統合する方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Developer, Admin
level: Intermediate
keywords: キャンペーン, acc, 統合
exl-id: 109ba212-f04b-425f-9447-708c8e0b3f51
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 100%

---

# Adobe Campaign v7／v8 との統合 {#integrating-with-adobe-campaign-v7-v8}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_acc"
>title="Adobe Campaign v7／v8 のアクション"
>abstract="この統合は、Adobe Campaign v7 および v8 で利用できます。Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。Journey Optimizer と Campaign インスタンスとの接続は、プロビジョニング時にアドビによって設定されます。"

Adobe Campaign Classic v7 や Campaign v8 を使用している場合は、Adobe Journey Optimizer と Adobe Campaign を統合するための特定のカスタムアクションがジャーニーで使用できます。この統合により、Adobe Campaign のトランザクションメッセージ機能を使用して、メール、プッシュ通知、SMS などを送信できるようになります。詳しくは、この[エンドツーエンドのユースケース](../building-journeys/ajo-ac.md)を参照してください。

設定したアクションごとに、ジャーニー designer パレットで [Campaign アクションアクティビティ](../building-journeys/using-adobe-campaign-v7-v8.md)を使用できます。

## アクティブ化 {#access}

リクエストに応じて、Journey Optimizer と Adobe Campaign 環境間の接続は、プロビジョニング時にアドビによって設定されます。プロビジョニング時に接続をリクエストしていない場合は、Adobe Journey Optimizer サポートに連絡し、アクティブ化をリクエストしてください。次の詳細を入力する必要があります。

>[!BEGINTABS]

>[!TAB Adobe Journey Optimizer の場合]

* 組織 ID（Adobe OrgID）
* サンドボックス名

>[!TAB Adobe Campaign の場合]

* Campaign サーバー URL
* リアルタイムサーバー URL
* Adobe Campaign のバージョン

>[!ENDTABS]


## ガードレールと制限 {#important-notes}

* メッセージのスロットルはありません。システムは現在の Campaign SLA に基づいて、送信できるメッセージ数を 5 分ごとに 4,000 件までにキャップします。この理由から、Journey Optimizer は単一ユースケース（オーディエンスではなく個々のイベント）でのみ使用してください。

* 使用するテンプレートごとに、1 つのアクションをキャンバス上に設定する必要があります。Adobe Campaign から使用する各テンプレートに対して、Journey Optimizer でアクションを 1 つずつ設定する必要があります。

* この統合にホストしている専用の Message Center インスタンスまたは Managed Services インスタンスを使用して、実行中の他の Campaign 操作に影響を与えないようにすることをお勧めします。マーケティングサーバーはホスト型でもオンプレミス型でも構いません。<!--The build required is 21.1 Release Candidate or greater. -->

* ペイロード、または Campaign メッセージが正しいかどうかは検証されません。

* オーディエンスの選定イベントでは、Campaign アクションを使用できません。

## 前提条件 {#prerequisites}

Adobe Campaign では、トランザクションメッセージとそれに関連するイベントを作成して公開する必要があります。[Adobe Campaign ドキュメント](https://experienceleague.adobe.com/ja/docs/campaign/campaign-v8/send/real-time/transactional){target="_blank"}を参照してください。

以下のパターンに従って、各メッセージに対応する JSON ペイロードを作成できます。Journey Optimizer でアクションを設定する際に、このペイロードを貼り付けます（以下を参照）。

+++ 例

```json
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
* **ctx**：メッセージに含めるパーソナライゼーションに基づく変数。

+++

## アクションの設定 {#configure-action}

Journey Optimizer では、トランザクションメッセージごとに 1 つのアクションを設定する必要があります。

Campaign アクションを作成するには、次の手順に従います。

1. 新しいアクションを作成します。[カスタムアクションの作成方法の詳細情報](../action/action.md)
1. 名前と説明を入力
1. 「**アクションタイプ**」フィールドで、**Adobe Campaign Classic** を選択します。
   ![](assets/accintegration1.png)
1. 「**ペイロード**」フィールドをクリックし、 Campaign メッセージに対応する JSON ペイロードの例を貼り付けます。アドビに問い合わせて、このペイロードを取得してください。 
1. ジャーニーキャンバスでマッピングするかどうかに基づいて、各フィールドを静的または変数に設定します。例えば、メールチャネルパラメーターやパーソナライゼーションフィールド（`ctx`）などのフィールドは通常、ジャーニー内で動的に適応できるように変数として設定する必要があります。
1. 「**保存**」をクリックします。

