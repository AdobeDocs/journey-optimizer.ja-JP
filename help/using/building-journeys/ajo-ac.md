---
solution: Journey Optimizer
product: journey optimizer
title: Campaign v7／v8 を使用したメッセージの送信
description: Campaign v7／v8 を使用したメッセージの送信方法を学ぶ
feature: Journeys, Integrations, Custom Actions, Use Cases
topic: Administration
role: Admin, Data Engineer, User
level: Intermediate, Experienced
keywords: ジャーニー, メッセージ, キャンペーン, 統合
exl-id: b07feb98-b2ae-476c-8fcb-873b308176f0
source-git-commit: f8d62a702824bcfca4221c857acf1d1294427543
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# ユースケース：Campaign v7／v8 を使用したメッセージの送信 {#campaign-v7-v8-use-case}

このユースケースでは、Adobe Campaign v7 および Adobe Campaign v8 との統合を使用してメールを送信するために必要なすべての手順を示します。

>[!NOTE]
>
>この統合を使用するには、Campaign v7/v8 ビルド 9125 以降が必要です。

まず、Campaign でトランザクションメールテンプレートを作成します。次に、Journey Optimizer で、イベント、アクションを作成し、ジャーニーをデザインします。

Campaign の統合について詳しくは、次のページを参照してください。

* [Campaign アクションの作成](../action/acc-action.md)
* [ジャーニーでのアクションの使用](../building-journeys/using-adobe-campaign-v7-v8.md)。

**Adobe Campaign**

Campaign インスタンスをこの統合用にプロビジョニングする必要があります。トランザクションメッセージ機能を設定する必要があります。

1. Campaign コントロールインスタンスにログインします。

1. **管理**／**プラットフォーム**／**列挙**&#x200B;で、**イベントタイプ**（eventType）列挙を選択します。新しいイベントタイプ（この例では「journey-event」）を作成します。後で JSON ファイルを書き込む際には、イベントタイプの内部名を使用する必要があります。

   ![](assets/accintegration-uc-1.png)

1. 作成を有効にするには、インスタンスを切断して、再接続します。

1. **Message Center**／**トランザクションメッセージテンプレート**&#x200B;で、以前に作成したイベントタイプに基づいて新しいメールテンプレートを作成します。

   ![](assets/accintegration-uc-2.png)

1. テンプレートをデザインします。この例では、プロファイルの名と注文番号にパーソナライゼーションを使用します。名は Adobe Experience Platform データソースにあり、注文番号は Journey Optimizer イベントのフィールドです。Campaign で正しいフィールド名を使用していることを確認します。

   ![](assets/accintegration-uc-3.png)

1. トランザクションテンプレートを公開します。

   ![](assets/accintegration-uc-4.png)

1. 次に、テンプレートに対応する JSON ペイロードを記述する必要があります。

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* チャネルには、「email」と入力する必要があります。
* eventType には、以前に作成したイベントタイプの内部名を使用します。
* メールアドレスは変数なので、任意のラベルを入力できます。
* ctx では、パーソナライゼーションフィールドも変数です。

**Journey Optimizer**

1. まず、イベントを作成する必要があります。「purchaseOrderNumber」フィールドを必ず含めてください。

   ![](assets/accintegration-uc-5.png)

1. 次に、Journey Optimizer で、Campaign テンプレートに対応するアクションを作成する必要があります。「**アクションタイプ**」ドロップダウンで、**Adobe Campaign Classic** を選択します。

   ![](assets/accintegration-uc-6.png)

1. 「**ペイロードフィールド**」をクリックし、以前に作成した JSON を貼り付けます。

   ![](assets/accintegration-uc-7.png)

1. メールアドレスと 2 つのパーソナライゼーションフィールドで、「**定数**」を「**変数**」に変更します。

   ![](assets/accintegration-uc-8.png)

1. 次に、新しいジャーニーを作成し、以前に作成したイベントから開始します。

   ![](assets/accintegration-uc-9.png)

1. アクションを追加し、Journey Optimizer の正しいフィールドに各フィールドをマッピングします。

   ![](assets/accintegration-uc-10.png)

1. ジャーニーのテスト.

   ![](assets/accintegration-uc-11.png)

1. これで、ジャーニーを公開できます。
