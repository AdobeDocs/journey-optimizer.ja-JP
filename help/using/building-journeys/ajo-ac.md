---
solution: Journey Optimizer
product: journey optimizer
title: Campaign v7／v8 を使用したメッセージの送信
description: Campaign v7／v8 を使用したメッセージの送信方法を学ぶ
feature: Journeys, Integrations, Custom Actions, Use Cases
topic: Administration
role: Admin, Developer, User
level: Intermediate, Experienced
keywords: ジャーニー, メッセージ, キャンペーン, 統合
exl-id: b07feb98-b2ae-476c-8fcb-873b308176f0
version: Journey Orchestration
source-git-commit: 70653bafbbe8f1ece409e3005256d9dff035b518
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 85%

---

# Campaign v7／v8 を使用したメッセージの送信 {#campaign-v7-v8-use-case}

このユースケースでは、[!DNL Adobe Campaign] v7 および [!DNL Adobe Campaign] v8 との統合を使用してメールを送信するために必要なすべての手順を説明します。

>[!NOTE]
>
>この統合を使用するには、Campaign v7/v8 ビルド 9125 以降が必要です。

まず、Campaign でトランザクションメールテンプレートを作成します。次に、Journey Optimizer で、イベント、アクションを作成し、ジャーニーをデザインします。

Campaign の統合について詳しくは、次のページを参照してください。

* [Campaign アクションの作成](../action/acc-action.md)
* [ジャーニーでのアクションの使用](../building-journeys/using-adobe-campaign-v7-v8.md)。

**[!DNL Adobe Campaign]**

Campaign インスタンスをこの統合用にプロビジョニングする必要があります。トランザクションメッセージ機能を設定する必要があります。

1. Campaign コントロールインスタンスにログインします。

1. **管理**／**プラットフォーム**／**列挙**&#x200B;で、**イベントタイプ**（eventType）列挙を選択します。新しいイベントタイプ（この例では「journey-event」）を作成します。イベントタイプの内部名は、後で JSON ファイルを書き込む際に使用します。

   ![&#x200B; スキーマとフィールドの選択を使用した [!DNL Adobe Journey Optimizer] でのイベントの設定 &#x200B;](assets/accintegration-uc-1.png)

1. 作成を有効にするには、インスタンスを切断して、再接続します。

1. **Message Center**／**トランザクションメッセージテンプレート**&#x200B;で、以前に作成したイベントタイプに基づいて新しいメールテンプレートを作成します。

   ![名前空間とプロファイル識別子の設定を示すイベント設定](assets/accintegration-uc-2.png)

1. テンプレートをデザインします。この例では、プロファイルの名と注文番号にパーソナライゼーションを適用します。名は [!DNL Adobe Experience Platform] データソースにあり、注文番号はJourney Optimizer イベントのフィールドにあります。 Campaign で正しいフィールド名を使用していることを確認します。

   ![プロファイルとイベントデータを含む JSON 構造を示すイベントペイロードプレビュー](assets/accintegration-uc-3.png)

1. トランザクションテンプレートを公開します。

   ![API 統合用のペイロード ID をコピーするイベントコピーボタン](assets/accintegration-uc-4.png)

1. テンプレートに対応する JSON ペイロードを記述します。

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

1. イベントを作成します。「purchaseOrderNumber」フィールドを含めます。

   ![[!DNL Adobe Campaign] Classic 統合のカスタムアクション設定画面 &#x200B;](assets/accintegration-uc-5.png)

1. Journey Optimizer で、Campaign テンプレートに対応するアクションを作成します。**アクションタイプ** ドロップダウンで、**[!DNL Adobe Campaign]Classic** を選択します。

   ![&#x200B; 「クラシック」オプションが表示され [!DNL Adobe Campaign] いるアクションタイプの選択 &#x200B;](assets/accintegration-uc-6.png)

1. 「**ペイロードフィールド**」をクリックし、以前に作成した JSON を貼り付けます。

   ![アクション統合の Campaign アカウント選択ドロップダウン](assets/accintegration-uc-7.png)

1. メールアドレスと 2 つのパーソナライゼーションフィールドで、「**定数**」を「**変数**」に変更します。

   ![Campaign 統合のフィールドマッピングを示すアクションペイロード設定](assets/accintegration-uc-8.png)

1. 次に、新しいジャーニーを作成し、以前に作成したイベントから開始します。

   ![イベントと Campaign アクションが設定されたジャーニーキャンバス](assets/accintegration-uc-9.png)

1. アクションを追加し、Journey Optimizer の正しいフィールドに各フィールドをマッピングします。

   ![動的な値の式エディターを含むアクションパラメーターのマッピング](assets/accintegration-uc-10.png)

1. ジャーニーのテスト：

   ![イベントトリガーと Campaign アクションの実行を使用してジャーニーフローを完了する](assets/accintegration-uc-11.png)

1. これで、ジャーニーを公開できます。
