---
title: カスタムアクションの使用
description: カスタムアクションの使用方法を説明します
feature: Actions
topic: Content Management
role: User
level: Intermediate
exl-id: 2b1b3613-3096-43ec-a860-600dda1d83b2
source-git-commit: 951799a9986e4fd293f282ecf82496e5e7f2da9e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 100%

---

# カスタムアクションの使用 {#use-custom-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_custom"
>title="カスタムアクション"
>abstract="カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。アクションは、JSON 形式のペイロードを持つ REST API を介して呼び出すことのできる任意のプロバイダーからの任意のサービスで設定できます。"

カスタムアクションを使用すると、メッセージや API 呼び出しを送信するサードパーティシステムの接続を設定できます。アクションは、JSON 形式のペイロードを持つ REST API を介して呼び出すことのできる任意のプロバイダーからの任意のサービスで設定できます。

## 同意とデータガバナンス {#privacy}

Journey Optimizer では、カスタムアクションにデータガバナンスポリシーと同意ポリシーを適用して、特定のフィールドがサードパーティシステムにエクスポートされないようにしたり、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外したりできます。詳しくは、次のページを参照してください。

* [データガバナンス](../action/action-privacy.md)。
* [同意](../action/consent.md)。

## URL 設定

**カスタムアクション**&#x200B;アクティビティの設定ペインには、URL 設定パラメーターと、カスタムアクション用に設定された認証パラメーターが表示されます。ジャーニーでは URL の静的な部分を設定できませんが、カスタムアクションのグローバル設定では設定できます。[詳細情報](../action/about-custom-action-configuration.md)。

### 動的パス

URL に動的パスが含まれる場合は、「**[!UICONTROL パス]**」フィールドでパスを指定します。

フィールドとプレーンテキスト文字列を連結するには、高度な式エディターで文字列関数またはプラス記号（+）を使用します。プレーンテキスト文字列を一重引用符（&#39;）または二重引用符（&quot;）で囲みます。[詳細情報](expression/expressionadvanced.md)。

この表は、設定の例を示しています

| フィールド | 値 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| パス | `The id of marketingCampaign + '/messages'` |

連結された URL の形式は次のとおりです。

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;キャンペーン ID\>`/messages`

![](assets/journey-custom-action-url.png)

### ヘッダー

「**[!UICONTROL URL 設定]**」セクションには、動的ヘッダーフィールドが表示されますが、定数ヘッダーフィールドは表示されません。動的ヘッダーフィールドは、値が変数として設定される HTTP ヘッダーフィールドです。[詳細情報](../action/about-custom-action-configuration.md)。

必要に応じて、動的ヘッダーフィールドの値を指定します。

1. ジャーニーのカスタムアクションを選択します。
1. 設定ペインで、「**[!UICONTROL URL 設定]**」セクションのヘッダーフィールドの横にある鉛筆アイコンをクリックします。

   ![](assets/journey-dynamicheaderfield.png)

1. フィールドを選択し、「**[!UICONTROL OK]**」をクリックします。

## アクションパラメーター

「**[!UICONTROL アクションパラメーター]**」セクションには、_「変数」_&#x200B;として定義されたメッセージパラメーターが表示されます。これらのパラメーターについては、この情報の取得先（例：イベント、データソース）を定義したり、値を手動で渡したり、高度なユースケースに高度な式エディターを使用したりできます。高度なユースケースとしては、データ操作などの関数の使用が考えられます。この[ページ](expression/expressionadvanced.md)を参照してください。

**関連トピック**

[アクションの設定](../action/about-custom-action-configuration.md)
