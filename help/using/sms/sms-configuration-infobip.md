---
solution: Journey Optimizer
product: journey optimizer
title: Infobip プロバイダーの設定
description: Infobip を使用して Journey Optimizer でテキストメッセージおよび MMS を送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 7b6dc89a-1a81-49c2-b2a7-bf24b9d215e3
source-git-commit: b9208544b08b474db386cce3d4fab0a4429a5f54
workflow-type: ht
source-wordcount: '382'
ht-degree: 100%

---

# Infobip プロバイダーの設定 {#sms-configuration-infobip}

Journey Optimizer に Infobip を設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Infobip。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL API ベース URL]** および **[!UICONTROL API キー]**：web インターフェイスのホームページまたは API キー管理ページにアクセスして、資格情報を検索します。詳しくは、[Infobip のドキュメント](https://www.infobip.com/docs/api){target="_blank"}を参照してください。

   * **[!UICONTROL オプトインキーワード]**：**[!UICONTROL オプトインメッセージ]**&#x200B;を自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトインメッセージ]**：**[!UICONTROL オプトインメッセージ]**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL オプトアウトキーワード]**：**[!UICONTROL オプトアウトメッセージ]**&#x200B;を自動的にトリガーするデフォルトキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL オプトアウトメッセージ]**：**[!UICONTROL オプトアウトメッセージ]**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL ヘルプキーワード]**：**ヘルプメッセージ**&#x200B;を自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL ヘルプメッセージ]**：**ヘルプメッセージ**&#x200B;として自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL ダブルオプトインキーワード]**：ダブルオプトイン処理をトリガーするキーワードを入力します。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。複数のキーワードの場合は、コンマ区切り値を使用します。

   * **[!UICONTROL ダブルオプトインメッセージ]**：ダブルオプトインの確認に応じて自動的に送信されるカスタム応答を入力します。

   * **[!UICONTROL プリンシパルエンティティ ID]**：割り当てられた DLT プリンシパルエンティティ ID を入力します。

   * **[!UICONTROL コンテンツテンプレート ID]**：登録済みの DLT コンテンツテンプレート ID を入力します。

   * **[!UICONTROL 有効期間]**：メッセージの有効期間を時間単位で入力します。この時間枠内にメッセージを配信できない場合は、システムは追加の再送信を試みます。デフォルトの有効期間は 48 時間に設定されています。

   * **[!UICONTROL コールバックデータ]**：通知 URL で送信する追加のクライアントデータを入力します。

   * **[!UICONTROL インバウンド番号]**：ユニークなインバウンド番号を追加します。これにより、それぞれに独自のインバウンド番号を持つ異なるサンドボックス間で同じ API 資格情報を使用できます。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

API 資格情報を作成して設定したら、SMS および MMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)
