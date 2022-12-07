---
solution: Journey Optimizer
product: journey optimizer
title: 電子メールのオプトアウト管理
description: 電子メールを使用したオプトアウトの管理方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 85%

---

# 電子メールのオプトアウト管理 {#email-opt-out}

受信者が電子メール通信の受信を登録解除する機能を提供するには、必ず **登録解除リンク** 受信者に送信されるすべての e メール内 [プライバシーおよびオプトアウト管理の詳細を説明します](../privacy/opt-out.md)

これは、次のような方法で回避できます。

* 挿入 **外部ランディングページへのリンク** を電子メールに送信して、ユーザーがブランドからのコミュニケーションの受信を登録解除できるようにします。 [外部オプトアウトリンクの追加方法を説明します](#opt-out-external-lp)

* を追加します。 **ワンクリックオプトアウトリンク** を電子メールコンテンツに追加します。 このリンクにより、選択内容の確認が必要なランディングページにリダイレクトされることなく、受信者は通信内容を素早く購読解除できます。これにより、購読解除プロセスを加速することができます。 [ワンクリックオプトアウトリンクの追加方法を説明します](#one-click-opt-out)

また、 **[!UICONTROL List-Unsubscribe]** 「 」オプションがチャネルの表示レベルで有効になっている場合、Journey Optimizerで送信される対応する電子メールの e メールヘッダーに購読解除リンクが含まれます。 [E メールヘッダーのオプトアウトについての詳細](#unsubscribe-header)

>[!NOTE]
>
>マーケティングタイプの電子メールメッセージには、オプトアウトリンクを含める必要があります。これはトランザクションメッセージには必要ありません。メッセージカテゴリ (**[!UICONTROL マーケティング]** または **[!UICONTROL トランザクション]**) が [チャンネル表面](../configuration/channel-surfaces.md#email-type) （例：メッセージプリセット）レベルと、メッセージの作成時 )。

## 外部オプトアウト {#opt-out-external-lp}

### 購読解除リンクの追加 {#add-unsubscribe-link}

最初にメッセージに購読解除リンクを追加する必要があります。これを行うには、以下の手順に従います。

1. 登録解除ランディングページを作成します。

1. 任意のサードパーティ製システムでホストします。

1. ジャーニーでメッセージを作成します。

1. コンテンツ内のテキストを選択し、コンテキストツールバーを使用して[リンクを挿入](../email/message-tracking.md#insert-links)します。

   ![](assets/opt-out-insert-link.png)

1. 「**[!UICONTROL リンクタイプ]**」ドロップダウンリストから「**[!UICONTROL 外部のオプトアウト／購読解除]**」を選択します。

   ![](assets/opt-out-link-type.png)

1. 「**[!UICONTROL リンク]**」フィールドに、サードパーティ製のランディングページへのリンクを貼り付けます。

   ![](assets/opt-out-link-url.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

### オプトアウト用の API 呼び出しの実装 {#opt-out-api}

受信者がランディングページから選択内容を送信する際にオプトアウトするには [Adobe Developer](https://developer.adobe.com/){target=&quot;_blank&quot;} を使用して&#x200B;**購読 API 呼び出し**&#x200B;を実装し、対応するプロファイルの環境設定を更新する必要があります。

この POST 呼び出しは次の通りです。

エンドポイント：platform.adobe.io/journey/imp/consent/preferences

クエリパラメーター：

* **params**：暗号化されたペイロードが格納されています
* **sig**：署名
* **pid**：暗号化されたプロファイル ID

次の 3 つのパラメーターが、受信者に送信されるサードパーティのランディングページ URL に含まれます。

![](assets/opt-out-parameters.png)

ヘッダー要件：

* x-api-key
* x-gw-ims-org-id
* x-sandbox-name
* 認証（技術アカウントからのユーザートークン） 

リクエスト本文：

```
{
   "marketing": [
       {
            "type": "email",           
            "choice": "no",          
            "scope": "channel"       
        }
    ],
 
}
```

[!DNL Journey Optimizer] はこれらのパラメーターを使用し、[Adobe Developer](https://developer.adobe.com){target=&quot;_blank&quot;} API 呼び出しを通じて対応するプロファイルの選択内容を更新します。

### 購読解除リンク付きでメッセージを送信 {#send-message-unsubscribe-link}

ランディングページの購読解除リンクを設定し、API 呼び出しを実装すると、メッセージを送信する準備が整います。

1. [ジャーニー](../building-journeys/journey.md)を通してリンクを含むメッセージを送信します。

1. メッセージを受け取った受信者が購読解除リンクをクリックすると、ランディングページが表示されます。

   ![](assets/opt-out-lp-example.png)

1. 受信者がフォームを送信した場合（ここではランディングページの「**購読解除**」ボタンをクリック）、[API 呼び出し](#opt-out-api)を通してプロファイルデータが更新されます。

1. その後、オプトアウトした受信者は、オプトアウトが成功したことを示す確認メッセージ画面にリダイレクトされます。

   ![](assets/opt-out-confirmation-example.png)

   その結果、購読を再度登録しない限り、このユーザーはブランドから連絡を受けることはありません。

1. 対応するプロファイルの選択が更新されたことを確認するには、Experience Platform に移動し、ID 名前空間と対応する ID 値を選択してプロファイルにアクセスします。詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=ja#getting-started){target=&quot;_blank&quot;}を参照してください。

   ![](assets/opt-out-profile-choice.png)

   「**[!UICONTROL 属性]**」タブで、**[!UICONTROL choice]** の値が **[!UICONTROL no]** に変更されたことを確認できます。

## ワンクリックオプトアウト {#one-click-opt-out}

メールにオプトアウトリンクを追加するには、次の手順に従います。

1. [リンクを挿入](../email/message-tracking.md#insert-links)し、リンクのタイプとして「**[!UICONTROL オプトアウトをワンクリック]**」を選択します。

   ![](assets/message-tracking-opt-out.png)

1. オプトアウトを適用する方法として、チャネル、ID、購読のいずれかのレベルを選択します。

   ![](assets/message-tracking-opt-out-level.png)

   * **[!UICONTROL チャネル]**：オプトアウトは、現在のチャネルのプロファイルのターゲット（メールアドレスなど）に今後送信されるメッセージに適用されます。複数のターゲットが 1 つのプロファイルに関連付けられている場合、オプトアウトはそのチャネルのプロファイル内のすべてのターゲット（メールアドレスなど）に適用されます。
   * **[!UICONTROL ID]**：オプトアウトは、現在のメッセージに使用されている特定のターゲット（メールアドレスなど）に今後送信されるメッセージに適用されます。
   * **[!UICONTROL 購読]**：オプトアウトは、特定の購読リストに関連付けられた今後のメッセージに適用されます。このオプションは、現在のメッセージが購読リストに関連付けられている場合にのみ選択できます。

1. 購読解除後にユーザーがリダイレクトされるランディングページの URL を入力します。このページは、オプトアウトが成功したことを確認するためにのみ表示されます。

   >[!NOTE]
   >
   >**List-Unsubscribe** オプションをチャネルサーフェスレベルで有効にした場合、この URL は、ユーザーがメールヘッダーの購読解除リンクをクリックしたときにも使用されます。[詳細情報](#unsubscribe-header)

   ![](assets/message-tracking-opt-out-confirmation.png)

   リンクをパーソナライズできます。パーソナライズされた URL について詳しくは、[この節](../personalization/personalization-syntax.md)を参照してください。

1. 変更を保存します。

メッセージが[ジャーニー](../building-journeys/journey.md)を通して送信された後、受信者がオプトアウトリンクをクリックすると、受信者のプロファイルは直ちにオプトアウトされます。

## メールヘッダーの購読解除リンク {#unsubscribe-header}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_unsubscribe"
>title="メールヘッダーへの購読解除リンクの追加"
>abstract="List-Unsubscribe を有効にして、メールヘッダーに購読解除リンクを追加します。購読解除 URL を設定するには、メールのコンテンツにワンクリックオプトアウトリンクを挿入します。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html?lang=ja#one-click-opt-out" text="ワンクリックオプトアウト"

[List-Unsubscribe オプション](../configuration/channel-surfaces.md#list-unsubscribe)がチャネルサーフェスレベルで有効になっている場合、対応するメールが [!DNL Journey Optimizer] で送信される際には、メールヘッダーに購読解除リンクが含まれています。

例えば、購読解除リンクは Gmail では次のように表示されます。

![](assets/unsubscribe-header.png)

>[!NOTE]
>
>メールヘッダーに購読解除リンクを表示するには、受信者のメールクライアントがこの機能をサポートしている必要があります。

購読解除アドレスは、対応するチャネルサーフェスに表示されるデフォルトの&#x200B;**[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスです。[詳細情報](../configuration/channel-surfaces.md#list-unsubscribe)。

パーソナライズした購読解除 URL を設定するには、メールメッセージコンテンツにワンクリックオプトアウトリンクを挿入し、自分で選んだ URL を入力します。[詳細情報](#one-click-opt-out)

メールクライアントによっては、ヘッダーの購読解除リンクをクリックすると、次のような影響が出ることがあります。

* 購読解除リクエストがデフォルトの購読解除アドレスに送信されます。

* メッセージにオプトアウトリンクを追加する際に指定したランディングページ URL に受信者が移動します。

   >[!NOTE]
   >
   >メッセージコンテンツにワンクリックオプトアウトリンクを追加しない場合、ランディングページは表示されません。

* 対応するプロファイルが直ちにオプトアウトされ、この選択が Experience Platform で更新されます。詳しくは、[Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started){target=&quot;_blank&quot;}を参照してください。
