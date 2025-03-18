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
source-git-commit: 040c8387c73f9d867840225ddff6cf940cc96ac5
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 100%

---

# リスト登録解除{#list-unsubscribe}

<!--Do not modify - Legal Review Done -->

新しいメールチャネル設定を指定する際に、リストから[サブドメインを選択](email-settings.md#subdomains-and-ip-pools)すると、「**[!UICONTROL リストの登録解除を有効にする]**」オプションが表示されます。

![](assets/preset-list-unsubscribe.png)

## リスト登録解除を有効にする {#enable-list-unsubscribe}

このオプションはデフォルトで有効になっており、次のようなワンクリック登録解除 URL がメールヘッダーに含まれます。

![](assets/preset-list-unsubscribe-header.png)

>[!NOTE]
>
>このオプションを無効にした場合、メールヘッダーにワンクリック登録解除 URL は表示されません。

リスト登録解除ヘッダーには、2 つのオプションがあり、いずれかまたは両方をオフにしない限り、デフォルトでこれらのオプションが有効になります。

![](assets/surface-list-unsubscribe.png){width="80%"}

* **[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスは、登録解除リクエストが自動処理にルーティングされる宛先アドレスです。

  [!DNL Journey Optimizer] の場合、登録解除メールアドレスは、[選択したサブドメイン](#subdomains-and-ip-pools)に基づいてチャネル設定に表示される、デフォルトの&#x200B;**[!UICONTROL 宛先（登録解除）]**&#x200B;アドレスです。<!--With this method, clicking the Unsubscribe link sends a pre-filled email to the unsubscribe address specified in the email header.-->

* **[!UICONTROL ワンクリック登録解除 URL]** は、デフォルトでは、チャネル設定を行ったサブドメインに基づいてワンクリックオプトアウト URL で生成された、リスト登録解除ヘッダーです。<!--With this method, clicking the Unsubscribe link directly unsubscribes the user, requiring only a single action to unsubscribe.-->

対応するドロップダウンリストから&#x200B;**[!UICONTROL 同意レベル]**&#x200B;を選択できます。チャネルまたはプロファイル ID に固有のものにすることができます。この設定に基づいて、ユーザーがメールのヘッダーにあるリスト登録解除 URL を使用して登録解除すると、[!DNL Adobe Journey Optimizer] においてチャネルレベルまたは ID レベルで同意が更新されます。

**[!UICONTROL 宛先（登録解除）]**&#x200B;機能と&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** 機能はオプションです。

デフォルトで生成されたワンクリック登録解除 URL を使用しない場合は、この機能をオフにできます。「**[!UICONTROL リスト登録解除を有効にする]**」オプションがオンに切り替わり、**[!UICONTROL ワンクリック登録解除 URL]** 機能がオフになっているシナリオで、この設定を使用して作成されたメッセージに[ワンクリックオプトアウトリンク](../email/email-opt-out.md#one-click-opt-out)を追加する場合、リスト登録解除ヘッダーは、メールの本文に挿入したワンクリックオプトアウトリンクをピックアップし、それをワンクリック登録解除 URL 値として使用します。

![](assets/preset-list-unsubscribe-opt-out-url.png)

>[!NOTE]
>
>メッセージコンテンツにワンクリックオプトアウトリンクを追加せず、チャネル設定でデフォルトの&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** をオンにしていない場合、メールヘッダーにリスト登録解除ヘッダーの一部として URL が渡されることはありません。

メッセージ内の登録解除機能の管理について詳しくは、[この節](../email/email-opt-out.md#unsubscribe-header)を参照してください。

## 外部での登録解除データ管理 {#custom-managed}

>[!CONTEXTUALHELP]
>id="ajo_email_config_unsubscribe_custom"
>title="登録解除データの管理方法の定義"
>abstract="**アドビが管理**：同意データは、アドビシステム内でユーザーによって管理されます。<br>**顧客管理**：同意データは、外部システムでユーザーによって管理されます。ユーザーが開始しない限り、アドビシステムで同意データの同期は更新されません。"

アドビの外部で同意を管理している場合は、「**[!UICONTROL 顧客管理]**」オプションを選択して、カスタムの登録解除メールアドレスと独自のワンクリック登録解除 URL を入力します。

![](assets/surface-list-unsubscribe-custom.png){width="80%"}

>[!WARNING]
>
>「**[!UICONTROL 顧客管理]**」オプションを使用している場合、アドビでは登録解除データや同意データを保存しません。「**[!UICONTROL 顧客管理]**」オプションを選択した場合、組織は外部システムを使用することを選択し、そのような外部システムで同意データを管理する責任があります。外部システムと [!DNL Journey Optimizer] の間で同意データの自動同期は行われません。[!DNL Journey Optimizer] のユーザー同意データを更新することを目的に、外部システムから行われる同意データの同期は、組織がデータ転送として開始し、同意データを [!DNL Journey Optimizer] にプッシュバックする必要があります。

### 復号化 API の設定 {#configure-decrypt-api}

「**[!UICONTROL 顧客管理]**」オプションを選択した場合、カスタムエンドポイントを入力してキャンペーンやジャーニーで使用すると、受信者が登録解除リンクをクリックした際に、[!DNL Journey Optimizer] によって同意更新イベント<!--sent to the custom endpoint -->にいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

これらのパラメーターは、暗号化された形式でエンドポイントに送信されます。したがって、外部の同意システムは、アドビから送信されたパラメーターを復号化することを目的に、[Adobe Developer](https://developer.adobe.com){target="_blank"} を通じて特定の API を実装する必要があります。

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

+++
