---
solution: Journey Optimizer
product: journey optimizer
title: WhatsApp チャネルの設定
description: Journey Optimizerで WhatsApp メッセージを送信するように環境を設定する方法を説明します
feature: Whatsapp, Channel Configuration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版" type="Informative"
exl-id: d1f40cd8-f311-4df6-b401-8858095cef3e
source-git-commit: 514e9072ba2154bdb5d587ed91111f1b3941f6d1
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 45%

---

# WhatsApp 設定の基本を学ぶ {#whatsapp-config}

>[!BEGINSHADEBOX]

**目次**

* [WhatsApp メッセージの基本を学ぶ](get-started-whatsapp.md)
* **[WhatsApp 設定の概要](whatsapp-configuration.md)**
* [WhatsApp メッセージの作成](create-whatsapp.md)
* [WhatsApp メッセージをチェックして送信する](send-whatsapp.md)

>[!ENDSHADEBOX]

WhatsApp のメッセージを送る前に、WhatsApp のアカウントに関連付ける必要があります。Adobe Journey Optimizerを設定する必要があります。 次の手順を実行します。

1. [WhatsApp API 認証情報の作成](#WhatsApp-credentials)
1. [WhatsApp 設定の作成](#WhatsApp-configuration)

これらの手順は、Adobe Journey Optimizer [システム管理者](../start/path/administrator.md)が実行する必要があります。

## WhatsApp API 認証情報の作成 {#whatsapp-credentials}

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下に説明するように、API 資格情報を設定します。

   * **API トークン**:API トークンを入力します。 詳しくは、[Meta ドキュメント ](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/) を参照してください。
   * **ビジネスアカウント ID**：ビジネスポートフォリオに関連する一意の番号を入力します。 詳しくは、[Meta ドキュメント ](https://www.facebook.com/business/help/1181250022022158?id=180505742745347) を参照してください。

   ![](assets/whatsapp-api.png)

1. 「**[!UICONTROL 続行]**」をクリックします。

1. WhatsApp API 認証情報に接続する **ビジネスアカウント** を選択します。

   ![](assets/whatsapp-api-2.png)

1. Whatsapp メッセージの送信に使用する **電話番号** を選択します。

1. 電話番号の設定は自動的に入力されます：

   * **品質評価**：過去 24 時間以内に送信されたメッセージに対する顧客のフィードバックを反映します。
      * 緑：高品質
      * 黄：Mediumの画質
      * 赤：低画質

     [ 品質評価 ](https://www.facebook.com/business/help/766346674749731#) の詳細情報

   * **スループット**：電話番号がメッセージを送信できる割合を示します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 認証情報を作成して設定した後、WhatsApp メッセージ用のチャネル設定を作成する必要があります。 [詳細情報](#whatsapp-configuration)

## WhatsApp 設定の作成 {#whatsapp-configuration}

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL 一般設定]**／**[!UICONTROL チャネル設定]**&#x200B;を選択します。「**[!UICONTROL チャネル設定を作成]**」ボタンをクリックします。

   ![](assets/whatsapp-config-1.png)

1. 設定の名前と説明（オプション）を入力し、WhatsApp チャネルを選択します。

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. チャネルとして **[!DNL WhatsApp]** を選択します。

   ![](assets/whatsapp-config-2.png)

1. 「**[!UICONTROL マーケティングアクション]**」を選択し、この設定を使用してメッセージに同意ポリシーを関連付けます。 顧客の環境設定に従うために、そのマーケティングアクションに関連付けられているすべての同意ポリシーが活用されます。詳細情報

1. 作成済みの **[!UICONTROL WhatsApp API 設定]** を選択します。

   ![](assets/whatsapp-config-3.png)

1. コミュニケーションに使用する「**[!UICONTROL 送信者番号]**」を入力します。

1. すべてのパラメーターを設定したら、「**[!UICONTROL 送信]**」をクリックして確定します。なお、チャネル設定をドラフトとして保存し、後で設定を再開することもできます。

1. チャネル設定が作成されると、リストに「**[!UICONTROL 処理中]**」のステータスで表示されます。

   >[!NOTE]
   >
   >チェックが成功しなかった場合、考えられる失敗理由について詳しくは[この節](../configuration/channel-surfaces.md)を参照してください。

1. チェックが正常に完了すると、チャネル設定のステータスが「**[!UICONTROL アクティブ]**」になります。メッセージの配信に使用する準備が整いました。

これで、Journey Optimizerで WhatsApp メッセージを送信する準備が整いました。

