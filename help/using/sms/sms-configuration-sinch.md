---
solution: Journey Optimizer
product: journey optimizer
title: Sinch プロバイダーの設定
description: Sinch を使用して Journey Optimizer でテキストメッセージを送信するように環境を設定する方法を説明します
feature: SMS, Channel Configuration
role: Admin
level: Intermediate
exl-id: 85412a85-edf0-4069-8bc7-b80371375f1f
source-git-commit: 25b1e6050e0cec3ae166532f47626d99ed68fe80
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 78%

---

# Sinch プロバイダーの設定 {#sms-configuration-sinch}

Journey Optimizerで Sinch プロバイダーを使用する場合は、次の 3 つの異なるオプションがあります。

* **SMS 設定**：SMS メッセージをシームレスに送信するための Sinch API 資格情報を設定します。

* **MMS 設定**：マルチメディアメッセージ（MMS）用に Sinch MMS API 資格情報を設定します。なお、インバウンドメッセージのトラッキングと応答は、SMS 設定で処理されます。MMS セットアップは、MMS メッセージのアウトバウンド配信にのみ使用されます。

* **RCS 設定**:RCS メッセージをシームレスに送信するための Sinch API 資格情報を設定します。

## SMS の API 資格情報の設定{#create-api}

>[!BEGINSHADEBOX]

オプトインキーワードやオプトアウトキーワードを指定していない場合は、ユーザーのプライバシーを遵守するために標準の同意メッセージが使用されます。カスタムキーワードを追加すると、デフォルト設定が自動的に上書きされます。

**デフォルトのキーワード：**

* **オプトイン**：SUBSCRIBE、YES、UNSTOP、START、CONTINUE、RESUME、BEGIN
* **オプトアウト**：STOP、QUIT、CANCEL、END、UNSUBSCRIBE、NO
* **ヘルプ**：HELP

>[!ENDSHADEBOX]

Journey Optimizer で SMS メッセージと MMS を送信するように Sinch プロバイダーを設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／`>`**[!UICONTROL SMS 設定]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、SMS API 資格情報を設定します。

+++ 設定用の SMS 資格情報のリスト

   | 設定フィールド | 説明 |
   |---|---|    
   | SMS ベンダー | Sinch |
   | 名前 | API 資格情報の名前を選択します。 |
   | サービス ID および API トークン | API ページにアクセスして、「SMS」タブで資格情報を検索します。詳しくは、[Sinch のドキュメント](https://developers.sinch.com/docs/sms/getting-started/){target="_blank"}を参照してください。 |
   | オプトインキーワード | オプトインメッセージを自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | オプトインメッセージ | オプトインメッセージとして自動的に送信されるカスタム応答を入力します。 |
   | オプトアウトキーワード | オプトアウトメッセージを自動的にトリガーするデフォルトキーワードまたはカスタムキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | オプトアウトメッセージ | オプトアウトメッセージとして自動的に送信されるカスタム応答を入力します。 |
   | ヘルプキーワード | **ヘルプメッセージ**&#x200B;を自動的にトリガーするデフォルトまたはカスタムのキーワードを入力します。複数のキーワードの場合は、コンマ区切り値を使用します。 |
   | ヘルプメッセージ | **ヘルプメッセージ**&#x200B;として自動的に送信されるカスタム応答を入力します。 |
   | ダブルオプトインキーワード | ダブルオプトイン処理をトリガーするキーワードを入力します。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。複数のキーワードの場合は、コンマ区切り値を使用します。[詳しくは、SMS ダブルオプトインを参照してください](https://video.tv.adobe.com/v/3440273/?learn=on&captions=jpn)。 |
   | ダブルオプトインメッセージ | ダブルオプトインの確認に応じて自動的に送信されるカスタム応答を入力します。 |
   | インバウンド番号 | ユニークなインバウンド番号またはショートコードを追加します。これにより、それぞれに独自のインバウンド番号またはショートコードを持つ異なるサンドボックス間で同じ API 資格情報を使用できます。 |
   | カスタム受信キーワード | 特定のアクションに対して一意のキーワードを定義します（割引、オファー、登録など）。これらのキーワードはプロファイル内の属性として取得され、保存されるので、ユーザーはジャーニー内でストリーミングセグメントの選定をトリガーし、カスタマイズされた応答やアクションを提供できます。 |
   | デフォルトのインバウンド返信メッセージ | 定義されたキーワードのいずれにも一致しないインバウンド SMS をエンドユーザーが送信した際に送信されるデフォルトの返信を入力します。 |
   | 上書き URL | SMS 配信レポート、フィードバックデータ、インバウンドメッセージまたはイベント通知のデフォルトのエンドポイントを置き換えるカスタム URL を入力します。Sinch は、事前定義された更新ではなく、関連するすべての更新をこの URL に送信します。 |

+++

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成し設定したら、SMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)

## MMS の API 資格情報の設定{#sinch-mms}

>[!IMPORTANT]
>
> MMS セットアップに加えて、特にインバウンドメッセージのトラッキングと同意リクエストの管理のために Sinch API 資格情報を作成する必要もあります。

Journey Optimizer で MMS を送信するように Sinch MMS を設定するには、次の手順に従います。

1. 左側のパネルで、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／`>`**[!UICONTROL SMS 設定]**&#x200B;を参照し、**[!UICONTROL API 資格情報]**&#x200B;メニューを選択します。「**[!UICONTROL 新しい API 資格情報を作成]**」ボタンをクリックします。

1. 以下で説明するように、MMS API 資格情報を設定します。

   * **[!UICONTROL SMS ベンダー]**：Sinch MMS。

   * **[!UICONTROL 名前]**：API 資格情報の名前を選択します。

   * **[!UICONTROL プロジェクト ID]**、**[!UICONTROL アプリ ID]** および **[!UICONTROL API トークン]**：MMS API 資格情報を収集するには、以下の手順に従います。

      * **[!UICONTROL プロジェクト ID]** および&#x200B;**[!UICONTROL アプリ ID]** の場合：Sinch ダッシュボードで Sinch プロジェクトの [Conversation API の概要](https://dashboard.sinch.com/convapi/overview)ページにアクセスします。
      * **[!UICONTROL API トークン]**&#x200B;の場合：Sinch プロジェクトの[アクセスキー](https://community.sinch.com/t5/Customer-Dashboard/Sinch-Access-Keys/ta-p/12638)を取得し、Sinch プロジェクトの&#x200B;**アクセスキー**&#x200B;から **Base64 API トークン**&#x200B;を取得します。

1. API 資格情報の設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。

1. **[!UICONTROL API 資格情報]**&#x200B;メニューで、ごみ箱アイコンをクリックして、API 資格情報を削除します。

1. 既存の資格情報を変更するには、目的の API 資格情報を見つけて、「**[!UICONTROL 編集]**」オプションをクリックして必要な変更を行います。

API 資格情報を作成し設定したら、MMS メッセージ用のチャネル設定を作成する必要があります。[詳細情報](sms-configuration-surface.md)

## RCS の API 認証情報の設定

<!--![](assets/do-not-localize/rcs-sms.png)-->

RCS （Rich Communication Services）メッセージは、Sinch を通じてJourney Optimizerでサポートされ、ロゴや送信者名などのブランディング要素を含む検証済みのビジネスプロファイルを使用して、基本的なメッセージを送信できます。

プロファイルのデバイスが RCS をサポートしていない場合や、RCS 経由で一時的に到達できない場合は、メッセージは自動的に SMS にフォールバックします。

Sinch を使用して RCS を設定するには：

1. **ブランドの RCS エージェントのセットアップ**

   ブランドの RCS エージェントをセットアップするには、Adobe担当者にお問い合わせください。 [ ブランド RCS エージェントの詳細 ](https://community.sinch.com/t5/RCS/Getting-Started-with-RCS-using-Conversation-API/ta-p/17844)

1. **[Sinch API 資格情報の設定](#create-api)**

   RCS エージェントが承認されたら、アクセスキー、シークレット、サービスプラン ID を含む Sinch API 資格情報を設定する必要があります。 これらの資格情報は、Journey Optimizerが Sinch のプラットフォームを通じてメッセージを認証および送信するために使用します。

1. **RCS メッセージ用の [ チャネル設定 ](sms-configuration-surface.md) の作成**

   Sinch 資格情報をリンクし、メッセージパラメーターを定義して、Journey Optimizerでチャネルサーフェスを設定します。 この設定により、Journey Optimizerから RCS メッセージを作成して送信できます。

