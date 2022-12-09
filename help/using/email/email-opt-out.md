---
solution: Journey Optimizer
product: journey optimizer
title: 電子メールのオプトアウト管理
description: 電子メールでオプトアウトを管理する方法について説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 4bb51bef-5dab-4a72-8511-1a5e528f4b95
source-git-commit: d1c11881654580247e8d7c92237cad130f11f749
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 0%

---

# 電子メールのオプトアウト管理 {#email-opt-out}

受信者が電子メール通信を受信しないようにするための機能を提供するには、宛先に送信されるすべての電子メールに、購読中止のリンク **を必ず含める** 必要があります。[プライバシーについて詳しくは、オプトアウトの管理を参照してください。](../privacy/opt-out.md)

これを行うには、次の操作を行います。

* 外部のランディングページ **へのリンクを電子メールに挿入し、** ユーザーが自分のブランドから配信されないようにすることができます。[Nexternal 脱退リンクを追加する方法について説明します。](#opt-out-external-lp)

* 電子メールコンテンツに1クリックで脱退するリンク **を** 追加します。このリンクを使用すると、受信者は選択内容を確認する必要があるランディングページにリダイレクトされることなく、自分のコミュニケーションを速やかに購読解除することができます。 [ワンクリックのオプトインリンクを追加する方法について説明します。](#one-click-opt-out)

さらに、このオプションがチャンネルのサーフェスレベルで有効になっている場合 **[!UICONTROL List-Unsubscribe]** は、旅のオプティマイザーによって送信される対応電子メールには、電子メールのヘッダーに購読中止リンクが追加されます。 [電子メールヘッダーのオプトアウトについて詳しくは、](#unsubscribe-header)

>[!NOTE]
>
>マーケティングタイプの電子メールメッセージには脱退リンクが含まれている必要があります。これは、トランザクションメッセージには必要ありません。 メッセージカテゴリー **[!UICONTROL Marketing]** **[!UICONTROL Transactional]** は、チャネルサーフェス ](../configuration/channel-surfaces.md#email-type) (メッセージプリセット) レベルとメッセージ作成時に定義 [ されます。

## 外部のオプトアウト {#opt-out-external-lp}

### 購読中止リンクの追加 {#add-unsubscribe-link}

最初に、メッセージに購読前のリンクを追加する必要があります。 これを行うには、次の手順を実行します。

1. Unsubscription のランディングページを独自に作成します。

1. 任意のサードパーティシステムでホストします。

1. メッセージを作成して、旅に出します。

1. コンテンツ [ 内のテキストを選択し、状況に応じたツールバーを使用してリンク ](../email/message-tracking.md#insert-links) を挿入します。

   ![](assets/opt-out-insert-link.png)

1. ドロップダウンリストから **[!UICONTROL Link type]** 選択 **[!UICONTROL External Opt-out/Unsubscription]** します。

   ![](assets/opt-out-link-type.png)

1. **[!UICONTROL Link]**&#x200B;フィールドに、サードパーティのランディングページへのリンクをペーストします。

   ![](assets/opt-out-link-url.png)

1. をクリック **[!UICONTROL Save]** します。

### オプトアウト用の API 呼び出しの実装 {#opt-out-api}

受信者がランディングページに表示されている内容を選択したときに、その受信者にオプトアウトされるようにするには、Adobe Developer ](https://developer.adobe.com) {target = &quot;_blank&quot;} を使用して [ 、対応するプロファイルの環境設定を更新する必要があり **** ます。

このようなポストは、次のようになります。

Endpoint: platform.adobe.io/journey/imp/consent/preferences

クエリーパラメーター:

* **params** : 暗号化されたペイロードを含みます。
* **sig** : signature
* **pid** : 暗号化されたプロファイル ID

この3つのパラメーターは、受信者に送信される3パーティのランディングページの URL に含まれます。

![](assets/opt-out-parameters.png)

ヘッダー要件:

* x-api キー
* x gw: ims-org id
* x-サンドボックス名
* 認証 (テクニカルアカウントのユーザートークン)

要求本文:

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

[!DNL Journey Optimizer] では、 [ これらのパラメーターを使用して、Adobe Developer ](https://developer.adobe.com) {target = &quot;_blank&quot;} API 呼び出しによって、対応するプロファイルを選択します。

### 購読中止のリンクが設定されたメッセージを送信します。 {#send-message-unsubscribe-link}

登録解除リンクをランディングページに設定し、API 呼び出しを実装したら、メッセージを送信することができます。

1. リンクを使用したメッセージを、旅 ](../building-journeys/journey.md) で [ 送信します。

1. 受信者が購読中止のリンクをクリックすると、メッセージが受信されると、ジャンプ先のページが表示されます。

   ![](assets/opt-out-lp-example.png)

1. 受信者がフォームを送信した場合 (ここでは、 **ランディングページの「登録解除** ボタンに移動した場合)、プロファイルデータは API 呼び出し ](#opt-out-api) に [ よって更新されます。

1. その後、除外された受信者は、オプトインが成功したことを示す確認メッセージ画面にリダイレクトされます。

   ![](assets/opt-out-confirmation-example.png)

   その結果、このユーザーは、再購読されていない限り、ブランドからの通信を受け付けません。

1. 適切なプロファイルの選択内容が更新されたことを確認するには、「経験のあるプラットフォーム」に移動して、id 名前空間とそれに対応する id 値を選択し、プロファイルにアクセスしてください。 詳細については、操作プラットフォームのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started) {target = &quot;_blank&quot;} を参照して [ ください。

   ![](assets/opt-out-profile-choice.png)

   **[!UICONTROL Attributes]**&#x200B;タブに表示されているの **[!UICONTROL choice]** 値が「変更済み」に **[!UICONTROL no]** なっています。

## ワンクリックオプトアウト {#one-click-opt-out}

電子メールに脱退リンクを追加するには、次の手順を実行します。

1. [リンク ](../email/message-tracking.md#insert-links) を挿入し、リンクの種類としてを選択 **[!UICONTROL One click Opt-out]** します。

   ![](assets/message-tracking-opt-out.png)

1. 「オプトアウト」を適用する方法として、チャネル、id、購読レベルのいずれかを選択します。

   ![](assets/message-tracking-opt-out-level.png)

   * **[!UICONTROL Channel]**&#x200B;オプトアウトは、現在のチャンネルのプロファイルのターゲット (つまり電子メールアドレス) に送信される今後のメッセージに適用されます。 プロファイルに複数のターゲットが関連付けられている場合、脱退はそのチャネルのプロファイル内のすべてのターゲット (つまり電子メールアドレス) に適用されます。
   * **[!UICONTROL Identity]**: オプトアウトは、現在のメッセージに使用されている特定のターゲット (例: 電子メールアドレス) に送信される将来のメッセージに適用されます。
   * **[!UICONTROL Subscription]**&#x200B;オプトアウトは、特定の購読リストに関連付けられた今後のメッセージに適用されます。 このオプションは、現在のメッセージが購読リストに関連付けられている場合にのみ選択できます。

1. ユーザーが購読解除されたときにリダイレクトされるランディングページの URL を入力します。 このページは、有効にしたことを確認する場合にのみ適用されます。

   >[!NOTE]
   >
   >チャンネルの「購読中止 **」オプションをオン** にしている場合は、ユーザーが電子メールのヘッダーにある購読中止のリンクをクリックすると、この URL が使用されます。[詳細情報](#unsubscribe-header)

   ![](assets/message-tracking-opt-out-confirmation.png)

   リンクを個人用に設定することができます。 この節 ](../personalization/personalization-syntax.md) では、 [ 個人用の url について詳しく説明しています。

1. 変更内容を保存します。

メッセージが旅 ](../building-journeys/journey.md) に出て [ きたら、相手が脱退のリンクをクリックすると、そのプロファイルはただちにオプトアウトされます。

## 電子メールのヘッダーにある購読中止リンク {#unsubscribe-header}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_unsubscribe"
>title="電子メールヘッダーへのアンサブスクライブリンクの追加"
>abstract="リストの有効化-講読中止リンクを電子メールヘッダーに追加します。 購読中止の URL を設定するには、電子メールコンテンツにワンクリックのオプトアウトリンクを挿入します。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/consent/opt-out.html#one-click-opt-out" text="ワンクリックオプトアウト"

[チャンネルのサーフェスレベルでリスト購読中止オプション ](../configuration/channel-surfaces.md#list-unsubscribe) が有効になっている場合は、によっ [!DNL Journey Optimizer] て送信される電子メールには、電子メールヘッダーに購読解除リンクが追加されます。

例えば、次のようなアンサブスクライブのリンクが Gmail に表示されます。

![](assets/unsubscribe-header.png)

>[!NOTE]
>
>電子メールヘッダーに購読中止リンクを表示するには、宛先の電子メールクライアントがこの機能をサポートしている必要があります。

購読解除のアドレスは、対応するチャンネルサーフェスに表示されるデフォルト **[!UICONTROL Mailto (unsubscribe)]** のアドレスです。 [詳しく ](../configuration/channel-surfaces.md#list-unsubscribe) は、こちらを参照してください。

カスタマイズされていない登録解除 URL を設定するには、「ワンクリック」リンクを電子メールメッセージのコンテンツに挿入し、任意の URL を入力します。 [詳細情報](#one-click-opt-out)

電子メールクライアントによっては、ヘッダーのサブスクライブ中止リンクをクリックすると、次のような影響を受ける場合があります。

* 購読中止のリクエストは、デフォルトの購読解除アドレスに送信されます。

* 受信者は、メッセージに脱退リンクを追加するときに指定したランディングページの URL に送られます。

   >[!NOTE]
   >
   >ワンクリックのオプトアウトのリンクをメッセージコンテンツに追加していない場合は、ジャンプページは表示されません。

* 対応するプロファイルはただちにオプトアウトされ、この選択はエクスペリエンスプラットフォームで更新されます。 詳細については、操作プラットフォームのマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html#getting-started) {target = &quot;_blank&quot;} を参照して [ ください。
