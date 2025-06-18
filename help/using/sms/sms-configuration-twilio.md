---
solution: Journey Optimizer
product: journey optimizer
title: Twilio プロバイダーの設定
description: Twilio を使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: d6f74566-c913-4727-83b9-473a798a0158
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 50%

---

# Twilio プロバイダーの設定 {#sms-configuration-twilio}

## SMS/MMS 用の API 資格情報の設定

Journey Optimizer に Twilio を設定するには、Twilio に使用する新しい API 資格情報を作成する必要があります。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／`>`**[!UICONTROL SMS 設定]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Twilio。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL アカウント SID]** および&#x200B;**[!UICONTROL 認証トークン]**：Twilio コンソールダッシュボードページの&#x200B;**アカウント情報**&#x200B;パネルにアクセスして、資格情報を検索します。

   * **[!UICONTROL メッセージ SID]**：Twilio の API で作成されたすべてのメッセージに割り当てられる一意の ID を入力します。詳しくは、[Twilio ドキュメント ](https://support.twilio.com/hc/en-us/articles/223134387-What-is-a-Message-SID-){target="_blank"} を参照してください。

   * **[!UICONTROL インバウンド番号]**：ユニークなインバウンド番号を追加します。これにより、それぞれに独自のインバウンド番号を持つ異なるサンドボックス間で同じ API 資格情報を使用できます。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成して設定したら、SMS および MMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)

## RCS の API 認証情報の設定

Adobe Journey Optimizerでは、[ カスタム SMS プロバイダー ](sms-configuration-custom.md) 機能を使用して、Twilio を通じて RCS メッセージングがサポートされています。 これにより、カルーセル、ボタン、マルチメディアコンテンツなどの要素を組み込んだ、検証済みのビジネスプロファイルを介して、リッチでインタラクティブなメッセージを配信できます。

Twilio で RCS メッセージを有効にするには、カスタム SMS プロバイダーを介して新しい API 資格情報を設定する必要があります。 RCS には個別のペイロード形式が必要なので、既存の Twilio SMS 資格情報には互換性がありません。

1. **Twilio での RCS Messaging への登録**

   まず、Twilio プラットフォームで RCS 登録プロセスを完了します。 これには、ビジネスプロファイルの設定や、アカウントの RCS 機能の有効化が含まれます。

1. **SMS Webhook の作成**

   受信する RCS メッセージ応答または配信更新を受信できる [SMS Webhook を設定 ](sms-configuration-custom.md#webhook) します。 この Webhook は、双方向通信のために Twilio 設定に正しくリンクされている必要があります。

1. **カスタムを SMS ベンダーとして使用した API 認証情報の作成**

   Journey Optimizerで、特に SMS ベンダーとして「カスタム」を使用している RCS 用に ](sms-configuration-custom.md#api-credential) 新しい API 資格情報を定義 [ します。 適切な RCS エンドポイント認証方法、ベース URL およびヘッダーを使用します。

API 認証情報を作成して設定した後、RCS メッセージ用のチャネル設定を作成する必要があります。 [詳細情報](sms-configuration-surface.md)







