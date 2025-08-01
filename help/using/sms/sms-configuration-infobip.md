---
solution: Journey Optimizer
product: journey optimizer
title: Infobip プロバイダーの設定
description: Infobip を使用して Journey Optimizer でテキストメッセージおよび MMS を送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 7b6dc89a-1a81-49c2-b2a7-bf24b9d215e3
source-git-commit: 604af3a0ac9febb62f2e2b1705e2751b2c476e04
workflow-type: ht
source-wordcount: '762'
ht-degree: 100%

---

# Infobip プロバイダーの設定 {#sms-configuration-infobip}

>[!BEGINSHADEBOX]

オプトインキーワードやオプトアウトキーワードを指定していない場合は、ユーザーのプライバシーを遵守するために標準の同意メッセージが使用されます。カスタムキーワードを追加すると、デフォルト設定が自動的に上書きされます。

**デフォルトのキーワード：**

* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **ヘルプ**：HELP

>[!ENDSHADEBOX]

## SMS 用の API 資格情報の設定

Journey Optimizer に Infobip を設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

+++ 設定用の SMS 資格情報のリスト

   | 設定フィールド | 説明 |
   |---|---|    
   | SMS ベンダー | Infobip |
   | 名前 | API 資格情報の名前を選択します。 |
   | API ベース URL と API キー | 資格情報を検索するには、web インターフェイスのホームページまたは API キー管理ページにアクセスします。詳しくは、[Infobip のドキュメント](https://www.infobip.com/docs/api){target="_blank"}を参照してください。 |
   | オプトインキーワード | オプトインメッセージを自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | オプトインメッセージ | オプトインメッセージとして自動的に送信されるカスタム応答を入力します。 |
   | オプトアウトキーワード | オプトアウトメッセージを自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | オプトアウトメッセージ | オプトアウトメッセージとして自動的に送信されるカスタム応答を入力します。 |
   | ヘルプキーワード | **ヘルプメッセージ**&#x200B;を自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | ヘルプメッセージ | **ヘルプメッセージ**&#x200B;として自動的に送信されるカスタム応答を入力します。 |
   | ダブルオプトインキーワード | ダブルオプトイン処理をトリガーするキーワードを入力します。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。複数のキーワードの場合は、コンマ区切り値を使用します。[詳しくは、SMS ダブルオプトインを参照してください](https://video.tv.adobe.com/v/3440273/?learn=on&captions=jpn)。 |
   | ダブルオプトインメッセージ | ダブルオプトインの確認に応じて自動的に送信されるカスタム応答を入力します。 |
   | プリンシパルエンティティ ID | 割り当てられた DLT プリンシパルエンティティ ID を入力します。 |
   | コンテンツテンプレート ID | 登録済みの DLT コンテンツテンプレート ID を入力します。 |
   | 有効期間 | メッセージの有効期間を時間単位で入力します。この時間枠内にメッセージを配信できない場合は、システムは追加の再送信を試みます。デフォルトの有効期間は 48 時間に設定されています。 |
   | コールバックデータ | 通知 URL で送信する追加のクライアントデータを入力します。 |
   | インバウンド番号 | ユニークなインバウンド番号を追加します。これにより、それぞれに独自のインバウンド番号を持つ異なるサンドボックス間で同じ API 資格情報を使用できます。 |
   | カスタム受信キーワード | 特定のアクションに対して一意のキーワードを定義します（割引、オファー、登録など）。これらのキーワードはプロファイル内の属性として取得され、保存されるので、ユーザーはジャーニー内でストリーミングセグメントの選定をトリガーし、カスタマイズされた応答やアクションを提供できます。 |
   | デフォルトのインバウンド返信メッセージ | 定義されたキーワードのいずれにも一致しないインバウンド SMS をエンドユーザーが送信した際に送信されるデフォルトの返信を入力します。 |

+++

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成して設定したら、SMS および MMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)

## RCS 用の API 資格情報の設定

RCS メッセージは、[カスタム SMS プロバイダー](sms-configuration-custom.md)機能を使用する Infobip を通じて Adobe Journey Optimizer でサポートされます。これにより、カルーセル、ボタン、マルチメディアコンテンツなどの要素を組み込んだ、検証済みのビジネスプロファイルを通じてリッチでインタラクティブなメッセージを配信できます。

➡️ [Infobip ドキュメントで Infobip が RCS をサポートする方法を見る](https://www.infobip.com/docs/api/channels/rcs)

Infobip で RCS メッセージを有効にするには、カスタム SMS プロバイダー経由で新しい API 資格情報を設定する必要があります。RCS では異なるペイロード形式が必要なので、既存の Infobip SMS 資格情報とは互換性がありません。

Infobip で RCS を設定するには：

1. **Infobip 経由での RCS のビジネスの登録**

   まず、Infobip プラットフォーム内で RCS オンボーディングと登録のプロセスを完了します。 これには、RCS 送信者プロファイルの設定と、アカウントが RCS 対応であることの確認が含まれます。詳しくは、[Infobip のドキュメント](https://www.infobip.com/docs/rcs/get-started)を参照してください。

1. **SMS Webhook の作成**

   Journey Optimizer で[カスタム SMS webhook を設定](sms-configuration-custom.md#webhook)します。この webhook は、Infobip のプラットフォームからの配信レシート、インバウンド RCS メッセージおよびステータス更新の処理を担当します。

1. **SMS ベンダーとしてカスタムを使用した API 資格情報の作成**

   Journey Optimizer 内で、SMS プロバイダーとして「カスタム」を選択して、[新しい API 資格情報を作成](sms-configuration-custom.md#api-credential)します。適切な RCS エンドポイント認証方法、ベース URL およびヘッダーを使用します。

API 資格情報を作成および設定したら、RCS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)
