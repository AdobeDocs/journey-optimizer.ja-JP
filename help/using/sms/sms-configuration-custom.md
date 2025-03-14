---
solution: Journey Optimizer
product: journey optimizer
title: カスタムプロバイダーの設定
description: カスタムプロバイダーを使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
badge: label="ベータ版" type="Informative"
role: Admin
level: Intermediate
exl-id: fd713864-96b9-4687-91bd-84e3533273ff
source-git-commit: f41426bd41078b98a26c32ce259a848ab49d724c
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---

# カスタムプロバイダーの設定 {#sms-configuration-custom}

>[!AVAILABILITY]
>
>カスタムプロバイダーは現在、一部のユーザーのみを対象としたベータ版として提供されています。ベータ版に参加するには、アドビの担当者にお問い合わせください。
>
>このベータ版では、オプトイン／オプトアウトの同意管理と配信レポートのインバウンドメッセージはサポートされていません。

アドビで標準で使用できないカスタムプロバイダー（Sinch、Infobip、Twilio など）を使用して Journey Optimizer でメッセージを送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。

1. 「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

   ![](assets/sms_byo_1.png)

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：カスタム。

   * **[!UICONTROL 名前]**：API 資格情報の名前を入力します。

   * **[!UICONTROL プロバイダーのアプリ ID]**：SMS プロバイダーから提供されたアプリケーション ID を入力します。

   * **[!UICONTROL プロバイダー名]**：SMS プロバイダーの名前を入力します。

   * **[!UICONTROL プロバイダーの URL]**：SMS プロバイダーの URL を入力します。

   * **[!UICONTROL 認証タイプ]**：認証タイプを選択します。サポートされる認証タイプは、**ベアラーアプリ**&#x200B;または&#x200B;**基本**&#x200B;です。

   * **[!UICONTROL API トークン]**：SMS プロバイダーから提供された API トークンを入力します。

   * **[!UICONTROL プロバイダーのペイロード]**：プロバイダーのペイロードを追加します（例：`{"from": "+1234XXXXXX", "to": "+1374XXXXXX", "content": "This is a test message", "contentType": "TEXT"}`）。

     ペイロードに `{{toNumber}}`、`{{fromNumber}}`、`{{message}}` が含まれていることを確認します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成し設定したら、SMS メッセージ用のチャネルサーフェスを作成する必要があります。[詳細情報](sms-configuration-surface.md)

設定が完了すると、メッセージオーサリング、パーソナライゼーション、リンクトラッキング、レポートなど、すべての標準のチャネル機能を活用できます。

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/3431625)
