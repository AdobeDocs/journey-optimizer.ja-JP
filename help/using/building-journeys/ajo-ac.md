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
TQID: https://experienceleague.adobe.com/btOUMO8tgvwLD7kjVdgpj6I6QXRrj1iTD3P8AUrqJFM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: c2beecbb-b93e-4ae3-baa9-72adcdc06781id: d08afb72-92f6-4856-88e3-11ec34313c2f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1025
ht-degree: 39%

---

# Campaign v7／v8 を使用したメッセージの送信 {#campaign-v7-v8-use-case}

>[!BEGINSHADEBOX]

**このページ：** トランザクションテンプレート、イベント、アクションの作成など、Adobe Campaign v7およびv8との統合を使用してジャーニーからメールを送信する方法を説明します。

>[!ENDSHADEBOX]

このユースケースでは、[!DNL Adobe Campaign] v7および[!DNL Adobe Campaign] v8との統合を使用してメールを送信するために必要なすべての手順について説明します。

>[!NOTE]
>
>この統合を使用するには、Campaign v7/v8 ビルド 9125 以降が必要です。

まず、Campaign でトランザクションメールテンプレートを作成します。 次に、Journey Optimizer で、イベント、アクションを作成し、ジャーニーをデザインします。

Campaign の統合について詳しくは、次のページを参照してください。

* [Campaign アクションの作成](../action/acc-action.md)
* [ジャーニーでのアクションの使用](../building-journeys/using-adobe-campaign-v7-v8.md)。

**[!DNL Adobe Campaign]**

Campaign インスタンスをこの統合用にプロビジョニングする必要があります。 トランザクションメッセージ機能を設定する必要があります。

1. Campaign コントロールインスタンスにログインします。

1. **管理**／**プラットフォーム**／**列挙**&#x200B;で、**イベントタイプ**（eventType）列挙を選択します。 新しいイベントタイプ（この例では「journey-event」）を作成します。 イベントタイプの内部名は、後で JSON ファイルを書き込む際に使用します。

   ![ スキーマとフィールド選択](assets/accintegration-uc-1.png)を使用して[!DNL Adobe Journey Optimizer]のイベントを設定します

1. 作成を有効にするには、インスタンスを切断して、再接続します。

1. **Message Center**／**トランザクションメッセージテンプレート**&#x200B;で、以前に作成したイベントタイプに基づいて新しいメールテンプレートを作成します。

   ![名前空間とプロファイル識別子の設定を示すイベント設定](assets/accintegration-uc-2.png)

1. テンプレートをデザインします。 この例では、プロファイルの名と注文番号にパーソナライゼーションを適用します。 名は[!DNL Adobe Experience Platform] データソースにあり、注文番号はJourney Optimizer イベントのフィールドです。 Campaign で正しいフィールド名を使用していることを確認します。

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

1. イベントを作成します。 「purchaseOrderNumber」フィールドを含めます。

   [!DNL Adobe Campaign] Classic統合](assets/accintegration-uc-5.png)の![ カスタムアクション設定画面

1. Journey Optimizer で、Campaign テンプレートに対応するアクションを作成します。 「**アクションタイプ**」ドロップダウンで、「**[!DNL Adobe Campaign]Classic**」を選択します。

   [!DNL Adobe Campaign] クラシック オプション ](assets/accintegration-uc-6.png)を表示する![ アクションタイプの選択

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

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、Adobe Campaign v7/v8との統合を使用してAdobe Journey Optimizerからトランザクションメールを送信する場合の手順を説明します。Campaign テンプレートの作成、イベントとアクションの設定、ジャーニーデザインについて説明します。

**インテント：**
* Journey Optimizerで使用するAdobe Campaign v7/v8のトランザクションメールテンプレートの設定
* 発注番号などのカスタムフィールドを含むイベントをJourney Optimizerで作成します
* JSON ペイロードを使用して、Journey OptimizerでCampaign Classic アクションを作成および設定する
* ジャーニーイベントフィールドをアクション設定のCampaign パーソナライゼーション変数にマッピングします
* Campaign トランザクションメールをトリガーするジャーニーを作成して公開します

**用語集：**
* **トランザクションメッセージ**: イベントに基づいてリアルタイムのトリガーメールを送信するキャンペーン機能。この統合を使用する前に設定する必要があります&#x200B;*（製品固有）*
* **イベントタイプ（eventType）**: トランザクションイベントのタイプを識別するCampaignで定義された列挙値。内部名はJSON ペイロード *（製品固有）*&#x200B;で参照されます
* **Campaign Classic action**: トランザクションメッセージを送信するためにAdobe Campaign v7/v8に接続するJourney Optimizer アクションタイプ *（製品固有）*
* **ペイロードフィールド**: Campaign *（製品固有）*&#x200B;に送信されたデータフィールドを定義するJourney Optimizer アクションにペーストされたJSON構造

**ガードレール：**
* この統合には、Campaign v7/v8 ビルド 9125以降が必要です
* トランザクションメッセージ機能は、使用する前にCampaign インスタンスで設定する必要があります
* Campaignで新しいイベントタイプを作成したら、そのイベントタイプを有効にするには、そのインスタンスを切断して再接続する必要があります
* 実行時に動的母集団を許可するには、アクションで「定数」として設定されたPersonalization フィールド値を「変数」に変更する必要があります

**用語：**
* 正式名称：Adobe Campaign v7/v8 – 略語：ACC – 変種：Campaign Classic、Campaign v7、Campaign v8
* 同義語：&quot;eventType&quot; = &quot;event type internal name&quot;
* 混同しないでください。「Campaign Classic action」≠「custom action」（Campaign Classic actionは、ACC統合用の特定のビルトインアクションタイプです）

**FAQ:**
* **Q：この統合にはどのCampaign バージョンが必要ですか？** — Campaign v7/v8 ビルド 9125以降が必要です。
* **Q：開始する前にCampaignで何を設定する必要がありますか？** — トランザクションメッセージ機能を設定し、イベントタイプに基づいてトランザクションメールテンプレートを作成する必要があります。
* **Q: Journey Optimizer アクションでパーソナライゼーションフィールドを動的にするにはどうすればよいですか？** — アクションペイロード設定で、実行時に入力されるフィールドのフィールド設定を「定数」から「変数」に変更します。
* **Q：このユースケースでは、名のパーソナライゼーションデータはどこから来ていますか？** — ファーストネームはAdobe Experience Platform データソースから取得し、注文番号はJourney Optimizer イベントペイロードから取得します。
* **Q: Journey Optimizer アクションをCampaign テンプレートに接続するにはどうすればよいですか？** — アクションタイプとして「Adobe Campaign Classic」を選択し、トランザクションメッセージテンプレート構造に一致するJSON ペイロードを貼り付けます。

+++
