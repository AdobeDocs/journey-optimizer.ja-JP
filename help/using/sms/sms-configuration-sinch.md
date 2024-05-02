---
solution: Journey Optimizer
product: journey optimizer
title: Sinch プロバイダーの設定
description: Journey Optimizerと Sinch でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 65%

---

# Sinch プロバイダーの設定 {#sms-configuration-sinch}

Journey Optimizerで Sinch プロバイダーを使用する場合は、次の 2 つの異なるオプションがあります。

* **SMS 設定**:SMS メッセージをシームレスに送信するための Sinch API 資格情報を設定します。

* **MMS 設定**：マルチメディアメッセージ（MMS）用に、Sinch MMS API 資格情報を設定します。 インバウンドメッセージのトラッキングと応答は、SMS 設定で処理されます。 MMS セットアップは、MMS メッセージのアウトバウンド配信にのみ使用されます。

## Sinch API 資格情報{#create-api}

Sinch プロバイダーを設定してJourney Optimizerで SMS メッセージと MMS を送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

   ![](assets/sms_6.png)

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]**：API ページにアクセスして、「SMS」タブで資格情報を検索します。詳しくは、[Sinch のドキュメント](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}を参照してください。

   * **[!UICONTROL オプトインキーワード]**：**[!UICONTROL オプトインメッセージ]**&#x200B;を自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトインメッセージ]**：**[!UICONTROL オプトインメッセージ]**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL オプトアウトキーワード]**：**[!UICONTROL オプトアウトメッセージ]**&#x200B;を自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトアウトメッセージ]**：**[!UICONTROL オプトアウトメッセージ]**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL ヘルプキーワード]**：**ヘルプメッセージ**&#x200B;を自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL ヘルプメッセージ]**：**ヘルプメッセージ**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL ダブルオプトインキーワード]**：ダブルオプトイン処理をトリガーするキーワードを入力します。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。複数のキーワードの場合は、コンマ区切り値を使用します。[詳しくは、SMS ダブルオプトインを参照してください](https://video.tv.adobe.com/v/3427129/?learn=on)。

   * **[!UICONTROL ダブルオプトインメッセージ]**：ダブルオプトインの確認に応じて自動的に送信されるカスタム応答を入力します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 認証情報を作成して設定した後、SMS メッセージのチャネルサーフェスを作成する必要があります。 [詳細情報](sms-configuration-surface.md)

## Sinch MMS API 資格情報 {#sinch-mms}

>[!IMPORTANT]
>
> MMS の設定と共に、インバウンドメッセージのトラッキングと同意リクエストの管理のために特別に Sinch API 資格情報を作成する必要もあります。

Sinch MMS を設定してJourney Optimizerで MMS を送信するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

   ![](assets/sms_6.png)

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL プロジェクト ID]**、**[!UICONTROL アプリ ID]** および **[!UICONTROL API トークン]**：Conversation API メニューから、アプリメニューで資格情報を見つけることができます。詳しくは、[Sinch のドキュメント](https://docs.cc.sinch.com/cloud/service-configuration/en/oxy_ex-1/common/wln1620131604643.html){target="_blank"}を参照してください。

   * **[!UICONTROL サービスプラン ID]** および **[!UICONTROL SMS API トークン]**：**[!UICONTROL サービスプラン ID]** および **[!UICONTROL SMS API トークン]**&#x200B;は、API ページの「SMS」タブにあります。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 認証情報を作成して設定した後、MMS メッセージのチャネルサーフェスを作成する必要があります。 [詳細情報](sms-configuration-surface.md)
