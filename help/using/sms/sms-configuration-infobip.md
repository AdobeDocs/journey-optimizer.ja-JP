---
solution: Journey Optimizer
product: journey optimizer
title: Infobip プロバイダーの設定
description: Infobip を使用して Journey Optimizer でテキストメッセージおよび MMS を送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 7b6dc89a-1a81-49c2-b2a7-bf24b9d215e3
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 63%

---

# Infobip プロバイダーの設定 {#sms-configuration-infobip}

>[!BEGINSHADEBOX]

オプトインキーワードやオプトアウトキーワードを指定していない場合は、ユーザーのプライバシーを遵守するために標準の同意メッセージが使用されます。カスタムキーワードを追加すると、デフォルト設定が自動的に上書きされます。

**デフォルトのキーワード：**

* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **ヘルプ**：HELP

>[!ENDSHADEBOX]

## SMS の API 資格情報の設定

Journey Optimizer に Infobip を設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]** `>` **[!UICONTROL チャネル]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

+++ 設定用の SMS 資格情報のリスト

   | 設定フィールド | 説明 |
   |---|---|    
   | SMS ベンダー | Infobip |
   | 名前 | API 資格情報の名前を選択します。 |
   | API ベース URL と API キー | Web インターフェイスのホームページまたは API キー管理ページにアクセスして、資格情報を検索します。 詳しくは、[Infobip ドキュメント ](https://www.infobip.com/docs/api){target="_blank"} を参照してください。 |
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
   | 有効期間 | メッセージの有効期間を時間単位で入力します。 この時間枠内にメッセージを配信できない場合は、システムは追加の再送信を試みます。デフォルトの有効期間は 48 時間に設定されています。 |
   | コールバックデータ | 通知 URL で送信される追加のクライアントデータを入力します。 |
   | インバウンド番号 | 一意のインバウンド番号を追加します。 これにより、それぞれに独自のインバウンド番号を持つ異なるサンドボックス間で同じ API 資格情報を使用できます。 |
   | カスタム受信キーワード | 特定のアクションに対して一意のキーワードを定義します（割引、オファー、登録など）。これらのキーワードはプロファイル内の属性として取得され、保存されるので、ユーザーはジャーニー内でストリーミングセグメントの選定をトリガーし、カスタマイズされた応答やアクションを提供できます。 |
   | デフォルトのインバウンド返信メッセージ | 定義されたキーワードのいずれにも一致しないインバウンド SMS をエンドユーザーが送信した際に送信されるデフォルトの返信を入力します。 |

+++

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成して設定したら、SMS および MMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)

## RCS の API 認証情報の設定

Adobe Journey Optimizerでは、[ カスタム SMS プロバイダー ](sms-configuration-custom.md) 機能を使用した Infobip を通じて、RCS メッセージングがサポートされています。 これにより、カルーセル、ボタン、マルチメディアコンテンツなどの要素を組み込んだ、検証済みのビジネスプロファイルを介して、リッチでインタラクティブなメッセージを配信できます。

Infobip で RCS メッセージングを有効にするには、カスタム SMS プロバイダーを介して新しい API 資格情報を設定する必要があります。 RCS では個別のペイロード形式が必要なので、既存の Infobip SMS 資格情報には互換性がありません。

1. **Infobip を使用した RCS へのビジネス登録**

   Infobip プラットフォーム内で RCS のオンボーディングと登録プロセスを完了することから始めます。 これには、RCS 送信者プロファイルの設定と、アカウントが RCS 対応であることの確認が含まれます。 詳しくは、[Infobip のドキュメント ](https://www.infobip.com/docs/rcs/get-started) を参照してください。

1. **SMS Webhook の作成**

   Journey Optimizerで [ カスタム SMS Webhook を設定 ](sms-configuration-custom.md#webhook) します。 この Webhook は、Infobip のプラットフォームから配信レシート、インバウンド RCS メッセージ、およびステータス更新を処理する役割を担います。

1. **カスタムを SMS ベンダーとして使用した API 認証情報の作成**

   Journey Optimizer内で [ カスタム ](sms-configuration-custom.md#api-credential) を SMS プロバイダーとして選択し、新しい API 認証情報を作成します。 適切な RCS エンドポイント認証方法、ベース URL およびヘッダーを使用します。

API 認証情報を作成して設定した後、RCS メッセージ用のチャネル設定を作成する必要があります。 [詳細情報](sms-configuration-surface.md)
