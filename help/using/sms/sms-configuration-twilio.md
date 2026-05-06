---
solution: Journey Optimizer
product: journey optimizer
title: Twilio プロバイダーの設定
description: Twilio を使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: d6f74566-c913-4727-83b9-473a798a0158
source-git-commit: ea2753bd9ce7372e53fefc7816d19a7a3c73b87d
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 83%

---

# Twilio プロバイダーの設定 {#sms-configuration-twilio}

TwilioとAdobe Journey Optimizerを統合することで、ジャーニーやキャンペーンの一環として、プロフィールにテキストメッセージを配信できます。

TwilioをSMS プロバイダーとして設定するには、次の手順に従います。

1. [API 資格情報の作成](#api-credential)
1. [Webhook の作成](sms-webhook.md)
1. [チャネル設定の作成](sms-configuration-surface.md)
1. [SMS チャネルアクションを使用したジャーニーまたはキャンペーンの作成](create-sms.md)

## SMS／MMS 用の API 資格情報の設定 {#api-credential}

Journey Optimizer に Twilio を設定するには、Twilio 用の新しい API 資格情報を作成する必要があります。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／`>`**[!UICONTROL SMS 設定]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。 「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Twilio。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL アカウント SID]** および&#x200B;**[!UICONTROL 認証トークン]**：Twilio コンソールダッシュボードページの&#x200B;**アカウント情報**&#x200B;パネルにアクセスして、資格情報を検索します。

   * **[!UICONTROL メッセージ SID]**：Twilio の API で作成されたすべてのメッセージに割り当てられる一意の ID を入力します。 詳しくは、[Twilio のドキュメント](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"}を参照してください。

   * **[!UICONTROL インバウンド番号]**：ユニークなインバウンド番号を追加します。 これにより、それぞれに独自のインバウンド番号を持つ異なるサンドボックス間で同じ API 資格情報を使用できます。

1. 「**[!UICONTROL インバウンドのカスタムデータセットを使用]**」を選択して、この資格情報のインバウンド SMSを、ドロップダウンから選択した事前作成データセットにルーティングします。 [&#x200B; データセットの作成について詳しく見る](../experience-decisioning/data-collection/create-dataset.md)

   >[!NOTE]
   >
   >データセットスキーマは&#x200B;**[!UICONTROL XDM ExperienceEvent]**&#x200B;である必要があり、少なくとも次のフィールドグループを含める必要があります。
   >* Adobe CJM ExperienceEvent - メッセージインタラクションの詳細
   >* Adobe CJM ExperienceEvent - Message Execution Details
   >* Adobe CJM ExperienceEvent - メッセージプロファイル詳細
   >
   >プロファイルに対してスキーマとデータセットを有効にする必要があります。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

1. 既存の API 資格情報から「**[!UICONTROL SMS 接続を検証]**」をクリックし、指定されたデバイスにサンプルメッセージを送信して、SMS API 資格情報をテストおよび検証します。

1. 「**番号**」フィールドと「**メッセージ**」フィールドに入力し、「**[!UICONTROL 接続を確認]**」をクリックします。

   >[!IMPORTANT]
   >
   >メッセージは、プロバイダーのペイロード形式に合わせて構造化する必要があります。

   ![](assets/verify-connection.png)

API 資格情報を作成して設定したら、SMS および MMS メッセージ用のチャネル設定を作成する必要があります。 [詳細情報](sms-configuration-surface.md)

## RCS 用の API 資格情報の設定

RCS メッセージは、[カスタム SMS プロバイダー](sms-configuration-custom.md)機能を使用する Twilio を通じて Adobe Journey Optimizer でサポートされます。 これにより、カルーセル、ボタン、マルチメディアコンテンツなどの要素を組み込んだ、検証済みのビジネスプロファイルを通じてリッチでインタラクティブなメッセージを配信できます。

➡️ [Twilio ドキュメントで Twilio が RCS をサポートする方法を見る](https://www.twilio.com/docs/rcs)

Twilio で RCS メッセージを有効にするには、カスタム SMS プロバイダー経由で新しい API 資格情報を設定する必要があります。 RCS では異なるペイロード形式が必要なので、既存の Twilio SMS 資格情報とは互換性がありません。

Twilio で RCS を設定するには：

1. **Twilio での RCS メッセージの登録**

   まず、Twilio プラットフォームで RCS 登録プロセスを完了します。 これには、ビジネスプロファイルの設定と、アカウントの RCS 機能の有効化が含まれます。

1. **SMS Webhook の作成**

   受信 RCS メッセージ応答または配信更新を受信できる [SMS Webhook を設定](sms-configuration-custom.md#webhook)します。 双方向通信を行うには、この webhook を Twilio 設定に適切にリンクする必要があります。

1. **SMS ベンダーとしてカスタムを使用した API 資格情報の作成**

   Journey Optimizer で、SMS ベンダーとして「カスタム」を使用して、RCS 専用の[新しい API 資格情報](sms-configuration-custom.md#api-credential)を定義します。 適切な RCS エンドポイント認証方法、ベース URL およびヘッダーを使用します。

API 資格情報を作成および設定したら、RCS メッセージ用のチャネル設定を作成する必要があります。 [詳細情報](sms-configuration-surface.md)







