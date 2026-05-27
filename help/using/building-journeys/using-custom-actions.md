---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションの使用
description: カスタムアクションの使用方法を説明します
feature: Journeys, Actions, Custom Actions
topic: Content Management
role: User, Developer
level: Intermediate
keywords: アクション, カスタム, API, ジャーニー, 設定, サービス
exl-id: 2b1b3613-3096-43ec-a860-600dda1d83b2
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/Sw-hR0cfAG8Lk8YbhJKj53UqG-er2bC3-7Ijih0PF44
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: c2beecbb-b93e-4ae3-baa9-72adcdc06781id: fa683eda-48de-4558-af32-2673edcd44feid: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: e0eb8757-182f-49f3-94a4-1587d16f5094id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 448
ht-degree: 100%

---

# カスタムアクションの使用 {#use-custom-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom"
>title="カスタムアクション"
>abstract="カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。 アクションは、JSON 形式のペイロードを使用した REST API を介して呼び出すことができる、任意のプロバイダーの任意のサービスで設定できます。"

カスタムアクションを使用して、サードパーティシステムへの接続を有効にし、メッセージや API 呼び出しを送信します。 アクションは、JSON 形式のペイロードを使用した REST API を介して呼び出すことができる、任意のプロバイダーの任意のサービスで設定できます。

カスタムアクションについて詳しくは、[この節](../action/action.md)を参照してください。

カスタムアクションを作成して設定する方法について詳しくは、[このページ](../action/about-custom-action-configuration.md)を参照してください。

パーソナライゼーションに対してカスタムアクションから API 呼び出し応答を使用する方法について詳しくは、[このページ](../action/action-response.md)を参照してください。

## 同意とデータガバナンス {#privacy}

Journey Optimizer では、カスタムアクションにデータガバナンスポリシーと同意ポリシーを適用して、特定のフィールドがサードパーティシステムにエクスポートされないようにしたり、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外したりできます。 詳しくは、次のページを参照してください。

* [データガバナンス](../action/action-privacy.md)。
* [同意](../action/consent.md)。

## URL 設定

**カスタムアクション**&#x200B;アクティビティの設定ペインには、URL 設定パラメーターと、カスタムアクション用に設定された認証パラメーターが表示されます。 ジャーニーでは URL の静的な部分を設定できませんが、カスタムアクションのグローバル設定では設定できます。 [学習を増やす](../action/about-custom-action-configuration.md)。

### 動的パス

URL に動的パスが含まれる場合は、「**[!UICONTROL パス]**」フィールドでパスを指定します。

フィールドとプレーンテキスト文字列を連結するには、高度な式エディターで文字列関数またはプラス記号（+）を使用します。 プレーンテキスト文字列を一重引用符（&#39;）または二重引用符（&quot;）で囲みます。 [学習を増やす](expression/expressionadvanced.md)。

この表は、設定の例を示しています

| フィールド | 値 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| パス | `The _id + '/messages'` |

連結された URL の形式は次のとおりです。

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;ID>`/messages`

![動的パラメーターマッピングを含むカスタムアクション URL 設定](assets/journey-custom-action-url.png)

### ヘッダーとクエリパラメーター {#headers}

「**[!UICONTROL URL の設定]**」セクションには、動的ヘッダーフィールドとクエリパラメーターフィールドが表示されますが、定数フィールドは表示されません。 動的ヘッダーおよびクエリパラメーターのフィールドは、アクション設定画面で変数として定義されます。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)

動的ヘッダーおよびクエリパラメーターのフィールドの値を指定するには、フィールド内または鉛筆アイコンをクリックして目的のフィールドを選択します。

![カスタムアクションでの動的ヘッダーフィールド設定](assets/journey-dynamicheaderfield.png)

## アクションパラメーター

「**[!UICONTROL アクションパラメーター]**」セクションには、_「変数」_&#x200B;として定義されたメッセージパラメーターが表示されます。 これらのパラメーターについては、この情報の取得先（例：イベント、データソース）を定義したり、値を手動で渡したり、高度なユースケースに高度な式エディターを使用したりできます。 高度なユースケースとしては、データ操作などの関数の使用が考えられます。 この[ページ](expression/expressionadvanced.md)を参照してください。

