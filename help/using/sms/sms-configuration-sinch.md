---
solution: Journey Optimizer
product: journey optimizer
title: Sinch プロバイダーの設定
description: Sinch を使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 85412a85-edf0-4069-8bc7-b80371375f1f
source-git-commit: 342b9210f79266cb11628dcdc411f90844a84e37
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 100%

---

# Sinch プロバイダーの設定 {#sms-configuration-sinch}

Journey Optimizer で Sinch プロバイダーを使用する場合は、次の 2 つの異なる選択肢があります。

* **SMS 設定**：SMS メッセージをシームレスに送信するための Sinch API 資格情報を設定します。

* **MMS 設定**：マルチメディアメッセージ（MMS）用に Sinch MMS API 資格情報を設定します。なお、インバウンドメッセージのトラッキングと応答は、SMS 設定で処理されます。MMS セットアップは、MMS メッセージのアウトバウンド配信にのみ使用されます。

## Sinch API 資格情報{#create-api}

Journey Optimizer で SMS メッセージと MMS を送信するように Sinch プロバイダーを設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Sinch。

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

API 資格情報を作成し設定したら、SMS メッセージ用のチャネルサーフェスを作成する必要があります。[詳細情報](sms-configuration-surface.md)

## Sinch MMS API 資格情報 {#sinch-mms}

>[!IMPORTANT]
>
> MMS セットアップに加えて、特にインバウンドメッセージのトラッキングと同意リクエストの管理のために Sinch API 資格情報を作成する必要もあります。

Journey Optimizer で MMS を送信するように Sinch MMS を設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報の作成]**」ボタンをクリックします。

1. 以下で説明するように、MMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Sinch MMS。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL プロジェクト ID]**、**[!UICONTROL アプリ ID]** および **[!UICONTROL API トークン]**：MMS API 資格情報を収集するには、以下の手順に従います。

      * **[!UICONTROL プロジェクト ID]** および&#x200B;**[!UICONTROL アプリ ID]** の場合：Sinch ダッシュボードで Sinch プロジェクトの [Conversation API の概要](https://dashboard.sinch.com/convapi/overview)ページにアクセスします。
      * **[!UICONTROL API トークン]**&#x200B;の場合：Sinch プロジェクトの[アクセスキー](https://community.sinch.com/t5/Customer-Dashboard/Sinch-Access-Keys/ta-p/12638)を取得し、Sinch プロジェクトの&#x200B;**アクセスキー**&#x200B;から **Base64 API トークン**&#x200B;を取得します。

   * **[!UICONTROL サービスプラン ID]** および **[!UICONTROL SMS API トークン]**：**[!UICONTROL サービスプラン ID]** および **[!UICONTROL SMS API トークン]**&#x200B;は、API ページの「SMS」タブにあります。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 資格情報を作成し設定したら、MMS メッセージ用のチャネルサーフェスを作成する必要があります。[詳細情報](sms-configuration-surface.md)
