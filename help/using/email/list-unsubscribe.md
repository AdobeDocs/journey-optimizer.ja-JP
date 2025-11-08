---
solution: Journey Optimizer
product: journey optimizer
title: リスト登録解除の設定
description: チャネル設定を指定する際に、メールのヘッダーにワンクリック登録解除 URL を含める方法について説明します
feature: Email, Surface
topic: Administration
role: Admin
level: Experienced
keywords: 設定, メール, 設定
exl-id: c6c77975-ec9c-44c8-a8d8-50ca6231fea6
source-git-commit: b8d56578aae90383092978446cb3614a4a033f80
workflow-type: tm+mt
source-wordcount: '1693'
ht-degree: 100%

---

# リスト登録解除{#list-unsubscribe}

<!--Do not modify - Legal Review Done -->

[!DNL Adobe Journey Optimizer] で、新しいメールチャネル設定を指定する際に、リストから[サブドメインを選択](email-settings.md#ip-pools)すると、「**[!UICONTROL リスト登録解除を有効にする]**」オプションが表示されます。これは、デフォルトで有効です。

![](assets/preset-list-unsubscribe.png)

ワンクリックリスト登録解除 URL は、メールの送信者情報の横に表示される登録解除リンクまたはボタンであり、受信者は 1 回のクリックでメーリングリストから即座にオプトアウトできます。

例えば、ワンクリック登録解除 URL は、Gmail で次のようなリンクが表示されます。

![](assets/preset-list-unsubscribe-header.png)

>[!IMPORTANT]
>
>メールヘッダーにワンクリック登録解除 URL を表示するには、受信者のメールクライアントがこの機能をサポートしている必要があります。

メールクライアントとメール設定の登録解除設定に応じて、メールヘッダーの登録解除リンクをクリックすると、次のような影響を受ける可能性があります。

* **宛先（登録解除）**&#x200B;機能を有効にすると、登録解除リクエストは、設定したサブドメインに基づいてデフォルトの登録解除アドレスに送信されます。
* **ワンクリック登録解除 URL** 機能が有効になっている場合や、メール本文コンテンツに登録解除 URL を挿入した場合、受信者が、（設定したサブドメインに基づく）ワンクリック登録解除 URL をクリックすると、チャネルレベルまたは ID レベル（同意の設定方法によって異なる）で直接オプトアウトされます。

>[!NOTE]
>
>登録解除設定を管理する方法について詳しくは、以下の[この節](#enable-list-unsubscribe)を参照してください。

どちらの場合も、受信者がオプトアウトリンクをクリックすると、登録解除リクエストがそれに応じて処理されます。対応するプロファイルはすぐにオプトアウトされ、この選択は [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/user-guide.html?lang=ja#getting-started){target="_blank"} で更新されます。

>[!NOTE]
>
>場合によっては、ダウンストリームのデータ処理により、登録解除イベントがプロファイルレベルで反映されるまでに時間がかかることがあります。システムの更新に多少時間がかかる場合があります。

## リスト登録解除を有効にする {#enable-list-unsubscribe}

>[!CONTEXTUALHELP]
>id="ajo_admin_preset_unsubscribe"
>title="メールへの登録解除 URL の追加"
>abstract="このオプションを有効にすると、メールヘッダーに登録解除 URL が自動的に追加されます。また、メールのコンテンツにワンクリックオプトアウトリンクを挿入することで、メッセージに登録解除 URL を設定することもできます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/email/email-opt-out#one-click-opt-out" text="メールコンテンツからのワンクリックオプトアウトの設定"

「**[!UICONTROL リスト登録解除を有効にする]**」オプションが有効になっている場合、受信者のメールクライアントでサポートされている場合は、メールヘッダーに、受信者がメーリングリストから登録解除に使用できる宛先と URL の両方がデフォルトで含まれます。

>[!NOTE]
>
>このオプションを無効にした場合、メールヘッダーにワンクリック登録解除 URL は表示されません。

リスト登録解除ヘッダーには、2 つのオプションがあり、いずれかまたは両方をオフにしない限り、デフォルトでこれらのオプションが有効になります。

![](assets/surface-list-unsubscribe.png){width="80%"}

* **[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスは、自動処理で登録解除リクエストがルーティングされる宛先アドレスです。[!DNL Journey Optimizer] の場合、登録解除のメールアドレスは、[選択したサブドメイン](email-settings.md#subdomains)に基づいてチャネル設定に表示される、デフォルトの&#x200B;**[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスです。<!--With this method, clicking the Unsubscribe link sends a pre-filled email to the unsubscribe address specified in the email header.-->

* **[!UICONTROL ワンクリック登録解除 URL]** は、デフォルトでは、[選択したサブドメイン](email-settings.md#subdomains)に基づいてワンクリックオプトアウト URL で生成された、リスト登録解除ヘッダーです。<!--With this method, clicking the Unsubscribe link directly unsubscribes the user, requiring only a single action to unsubscribe.-->

対応するドロップダウンリストから&#x200B;**[!UICONTROL 同意レベル]**&#x200B;を選択できます。チャネルまたはプロファイル ID に固有のものにすることができます。この設定に基づいて、ユーザーがメールのヘッダーにあるリスト登録解除 URL を使用して登録解除すると、[!DNL Adobe Journey Optimizer] においてチャネルレベルまたは ID レベルで同意が更新されます。

## ガードレールとレコメンデーション {#list-unsubscribe-guardrails}

ワンクリックリスト登録解除 URL 機能を使用すると、受信者は簡単に通信をオプトアウトできます。ただし、すべてのメールクライアントがメールヘッダーのこのリンクをサポートしているわけではないので、アドビでは、メールの本文に[ワンクリックオプトアウトリンク](email-opt-out.md#one-click-opt-out)または[登録解除リンク](email-opt-out.md#add-unsubscribe-link)も追加することをお勧めします。

**[!UICONTROL 宛先（登録解除）]**&#x200B;機能と&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** 機能はオプションです。

* [メール設定](email-settings.md)で「**[!UICONTROL リスト登録解除を有効にする]**」オプションをオンにしている場合は、**宛先（登録解除）**&#x200B;と&#x200B;**ワンクリック登録解除 URL** の両方の方法を有効にすることをお勧めします。すべてのメールクライアントが HTTP メソッドをサポートしているわけではありません。代替手段を選択できる宛先リスト登録解除機能を使用すると、送信者の評判をより適切に保護でき、すべての受信者が登録解除機能を使用できます。

* デフォルトで生成されたワンクリック登録解除 URL を使用しない場合は、この機能をオフにできます。

   * 「**[!UICONTROL リスト登録解除を有効にする]**」オプションがオンに切り替わり、**[!UICONTROL ワンクリック登録解除 URL]** 機能がオフになっているシナリオで、この設定を使用して作成されたメッセージに[ワンクリックオプトアウトリンク](../email/email-opt-out.md#one-click-opt-out)を追加する場合、リスト登録解除ヘッダーは、メールの本文に挿入したワンクリックオプトアウトリンクをピックアップし、それをワンクリック登録解除 URL 値として使用します。

     ![](assets/preset-list-unsubscribe-opt-out-url.png)

   * メッセージコンテンツにワンクリックオプトアウトリンクを追加せず、チャネル設定でデフォルトの&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** をオンにしていない場合、メールヘッダーにリスト登録解除ヘッダーの一部として URL が渡されることはありません。

  >[!NOTE]
  >
  >メッセージ内の登録解除機能の管理について詳しくは、[この節](../email/email-opt-out.md#unsubscribe-header)を参照してください。

[!DNL Journey Optimizer] では、同意は Experience Platform [同意スキーマ](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/profile/consents.html?lang=ja){target="_blank"}で処理されます。デフォルトでは同意フィールドの値は空で、通信内容の受信に同意したものとして扱われます。このデフォルト値を[ここ](https://experienceleague.adobe.com/docs/experience-platform/xdm/data-types/consents.html?lang=ja#choice-values){target="_blank"}に一覧表示されている値の 1 つにオンボーディングする際に変更したり、[同意ポリシー](../action/consent.md)を使用してデフォルトのロジックを上書きしたりできます。

現在、[!DNL Journey Optimizer] は、リスト登録解除機能によってトリガーされる登録解除イベントに特定のタグを追加しません。リスト登録解除クリックを他の登録解除アクションと区別する必要がある場合は、外部でカスタムタグ付けを実装するか、トラッキング用に外部ランディングページを活用する必要があります。

## 外部での登録解除データ管理 {#custom-managed}

>[!CONTEXTUALHELP]
>id="ajo_email_config_unsubscribe_custom"
>title="登録解除データの管理方法の定義"
>abstract="**アドビが管理**：同意データは、アドビシステム内でユーザーによって管理されます。<br>**顧客管理**：同意データは、外部システムでユーザーによって管理されます。ユーザーが開始しない限り、アドビシステムで同意データの同期は更新されません。"

>[!CONTEXTUALHELP]
>id="ajo_email_config_unsubscribe_custom_url"
>title="独自のワンクリック登録解除 URL の入力"
>abstract="**ワンクリック登録解除 URL** では、POST リクエストメソッドを使用する必要があります。"

アドビの外部で同意を管理している場合は、「**[!UICONTROL 顧客管理]**」オプションを選択して、カスタムの登録解除メールアドレスと独自のワンクリック登録解除 URL を入力します。

![](assets/surface-list-unsubscribe-custom.png){width="80%"}

**[!UICONTROL ワンクリック登録解除 URL]** は、POST URL にする必要があります。

>[!WARNING]
>
>「**[!UICONTROL 顧客管理]**」オプションを使用している場合、アドビでは登録解除データや同意データを保存しません。「**[!UICONTROL 顧客管理]**」オプションを選択した場合、組織は外部システムを使用することを選択し、そのような外部システムで同意データを管理する責任があります。外部システムと [!DNL Journey Optimizer] の間で同意データの自動同期は行われません。[!DNL Journey Optimizer] のユーザー同意データを更新することを目的に、外部システムから行われる同意データの同期は、組織がデータ転送として開始し、同意データを [!DNL Journey Optimizer] にプッシュバックする必要があります。

### エンドポイントへのカスタム属性の追加 {#custom-attributes}

「**[!UICONTROL 顧客管理]**」オプションを選択した場合、カスタムエンドポイントを入力してキャンペーンやジャーニーで使用すると、受信者が登録解除リンクをクリックした際に、[!DNL Journey Optimizer] によって、同意更新イベント<!--sent to the custom endpoint -->にいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

エンドポイント <!-- (**[!UICONTROL Mailto (unsubscribe)]** and **[!UICONTROL One-click Unsubscribe URL]**)--> をさらにパーソナライズするには、カスタム属性を定義できます。これらは同意イベントにも追加されます。

>[!AVAILABILITY]
>
>**[!UICONTROL 宛先（登録解除）]**&#x200B;オプションでは、この機能は限定提供（LA）で利用できます。アクセス権を取得するには、アドビ担当者にお問い合わせください。この場合、[以下の](#configure-decrypt-api)「**カスタム属性（限定提供）を使用した宛先（登録解除）**」セクションに記載されている、新しいクエリパラメーターを使用する必要があります。

エンドポイントのカスタム属性を定義するには、「**[!UICONTROL URL トラッキングパラメーター]**」セクションを使用します。対応するセクションで定義するすべての URL トラッキングパラメーターは、デフォルトのパラメーターに加えて、カスタムエンドポイントの末尾に追加されます。[カスタム URL トラッキングの設定方法の詳細情報](url-tracking.md)

### 復号化 API の設定 {#configure-decrypt-api}

受信者がカスタム登録解除リンクをクリックすると、同意更新イベントに追加されたパラメーターが暗号化された状態でエンドポイントに送信されます。したがって、外部の同意システムは、アドビから送信されたパラメーターを復号化することを目的に、[Adobe Developer](https://developer.adobe.com){target="_blank"} を通じて特定の API を実装する必要があります。

これらのパラメーターを取得する GET 呼び出しは、使用しているリスト登録解除オプション（**[!UICONTROL ワンクリック登録解除 URL]** または&#x200B;**[!UICONTROL 宛先（登録解除）]**）によって異なります。

<!--To configure the API to send back the information to [!DNL Adobe Journey Optimizer] when a recipient has unsubscribed using the List unsubscribe option with custom endpoints, follow the steps below.-->

+++ ワンクリック登録解除 URL

「**[!UICONTROL ワンクリック登録解除 URL]**」オプションを使用して、登録解除リンクをクリックすると、ユーザーは直接登録解除されます。

GET 呼び出しは次のとおりです。

エンドポイント：https://platform.adobe.io/journey/imp/consent/decrypt

クエリパラメーター：

* **params**：暗号化されたペイロードが格納されています
* **pid**：暗号化されたプロファイル ID

これら 2 つのパラメーターは、カスタムエンドポイントに送信される同意更新イベントに含まれます。

ヘッダー要件：

* x-api-key
* x-gw-ims-org-id
* 認証（技術アカウントからのユーザートークン）

サンプルパラメーターと同意応答を次に示します。

| クエリパラメーター | サンプルペイロード |
|---------|----------|
| pid | {<br>&quot;pid&quot;  : &quot;5142733041546020095851529937068211571&quot;,<br>&quot;pns&quot;  : &quot;CRMID&quot;,<br>&quot;e&quot;    : &quot;john@google.com&quot;,<br>&quot;ens&quot;  : &quot;Email&quot;,<br>} |
| params | {<br>&quot;m&quot;  : &quot;messageExecutionId&quot;,<br>&quot;ci&quot;  : &quot;campaignId&quot;,<br>&quot;jv&quot; : &quot;journeyVersionId&quot;,<br>&quot;ja&quot; : &quot;journeyActionId&quot;,<br>&quot;s&quot;  : &quot;sandboxId&quot;,<br>&quot;us&quot; : &quot;unsubscribeScope&quot;<br>} |

同意応答：

```
{
    "profileNameSpace": " CRMID ",
    "profileId": "5142733041546020095851529937068211571",
    "emailAddress": "john@google.com",
    "emailNameSpace": "Email",
    "sandboxId": "sandboxId",
    "optOutLevel": "channel",
    "channelType": "email",
    "timestamp": "2024-11-26T14:25:09.316930Z"
    "utm": [
         {
            "utm_source": "AJO",
            "utm_medium": "Email"
        }
    ]
}
```

+++

+++ 宛先（登録解除）

「**[!UICONTROL 宛先（登録解除）]**」オプションを使用して、登録解除リンクをクリックすると、事前に入力されたメールが、指定された登録解除アドレスに送信されます。

GET 呼び出しは次のとおりです。

エンドポイント：https://platform.adobe.io/journey/imp/consent/decrypt

クエリパラメーター：

* **emailParams**：**params**（暗号化されたペイロード）と **pid**（暗号化されたプロファイル ID）パラメーターを含む文字列。

**params** および **pid** パラメーターは、カスタムエンドポイントに送信される同意更新イベントに含まれます。

ヘッダー要件：

* x-api-key
* x-gw-ims-org-id
* 認証（技術アカウントからのユーザートークン）

サンプルパラメーターと同意応答を次に示します。

| クエリパラメーター | サンプルペイロード |
|---------|----------|
| emailParams | {<br>&quot;p&quot;  : &quot;profileId&quot;,<br>&quot;pn&quot;  : &quot;profileNamespace&quot;,<br>&quot;en&quot;  : &quot;emailNamespace&quot;,<br>&quot;ci&quot;  : &quot;campaignId&quot;,<br>&quot;jv&quot; : &quot;journeyVersionId&quot;,<br>&quot;ja&quot; : &quot;journeyActionId&quot;,<br>&quot;si&quot;  : &quot;sandboxId&quot;,<br>&quot;us&quot;: &quot;unsubscribeScope&quot;<br>} |

同意応答：

```
{
    "profileNameSpace": " CRMID ",
    "profileId": "5142733041546020095851529937068211571",
    "emailAddress": "john@google.com",
    "emailNameSpace": "Email",
    "sandboxId": "sandboxId",
    "optOutLevel": "channel",
    "channelType": "email",
    "timestamp": "2024-11-26T14:25:09.316930Z"
}
```

+++

+++ カスタム属性を使用した宛先（登録解除）（限定提供）

「**[!UICONTROL 宛先（登録解除）]**」オプションを使用して、登録解除リンクをクリックすると、事前に入力されたメールが、指定された登録解除アドレスに送信されます。

2025年10月以降、**[!UICONTROL 宛先（登録解除）]**&#x200B;エンドポイントの&#x200B;**[!UICONTROL 顧客管理]**&#x200B;オプションを使用している場合は、同意イベントに追加するカスタム属性を定義できます。この場合、以下に説明するクエリパラメーターを使用する必要があります。

>[!AVAILABILITY]
>
>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。

GET 呼び出しは次のとおりです。

エンドポイント：https://platform.adobe.io/journey/imp/consent/decrypt

クエリパラメーター：

* **emailParamsSub**：宛先アドレスで受信したメールの件名から抽出された文字列。

   * 例：*unsubscribev1.abc*

   * 解析値：*v1.abc*

* **emailParamsBody**：メールの本文（存在する場合）から *unsubscribev1.xyz* 形式で抽出された文字列。

   * 解析値：*v1.xyz*

API の例：https://platform.adobe.io/journey/imp/consent/decrypt?emailParamsSub=v1.abc&amp;emailParamsBody=v1.xyz

>[!CAUTION]
>
>以前の実装（例：https://platform.adobe.io/journey/imp/consent/decrypt?emailParams=&lt;v1.xxx>）を使用していた場合は、**emailParams** ではなく、新しい **emailParamsSub** および **emailParamsBody** パラメーターを使用する必要があります。詳しくは、アドビ担当者にお問い合わせください。

**emailParamsSub** および **emailParamsBody** パラメーターは、カスタムエンドポイントに送信される同意更新イベントに含まれます。

ヘッダー要件：

* x-api-key
* x-gw-ims-org-id
* 認証（技術アカウントからのユーザートークン）

同意応答：

```
{
    "profileNameSpace": " CRMID ",
    "profileId": "5142733041546020095851529937068211571",
    "emailAddress": "john@google.com",
    "emailNameSpace": "Email",
    "sandboxId": "sandboxId",
    "optOutLevel": "channel",
    "channelType": "email",
    "timestamp": "2024-11-26T14:25:09.316930Z"
    "utm": [
        {
            "utm_source": "AJO",
            "utm_medium": "Email"
        }
    ]
}
```

+++
