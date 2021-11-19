---
title: カスタムアクションの使用
description: カスタムアクションの使用方法を説明します
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 2b1b3613-3096-43ec-a860-600dda1d83b2
source-git-commit: daf5c6021a3efc8852b989fb602380c369758ead
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 98%

---

# カスタムアクションの使用 {#section_f2c_hbg_nhb}

アクティビティ設定ペインには、URL 設定パラメーターと、カスタムアクション用に設定された認証パラメーターが表示されます。[詳細情報](../action/about-custom-action-configuration.md)。

>[!NOTE]
>
>カスタムアクションのパラメーターでシンプルなコレクションを渡すことはできません。より複雑なコレクションフィールド（オブジェクトの配列）はサポートされていません。また、パラメーターは想定される形式（例：文字列、10 進数など）になっています。これらの想定される形式に従うように注意する必要があります。

## URL 設定

### 動的パス

URL に動的パスが含まれる場合は、「**[!UICONTROL パス]**」フィールドでパスを指定します。

>[!NOTE]
>
>ジャーニーでは URL の静的な部分を設定できませんが、カスタムアクションのグローバル設定では設定できます。[詳細情報](../action/about-custom-action-configuration.md)。

フィールドとプレーンテキスト文字列を連結するには、高度な式エディターで文字列関数またはプラス記号（+）を使用します。プレーンテキスト文字列を一重引用符（&#39;）または二重引用符（&quot;）で囲みます。[詳細情報](expression/expressionadvanced.md)。

この表は、設定の例を示しています

| フィールド | 値 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| パス | `The id of marketingCampaign + '/messages'` |

連結された URL の形式は次のとおりです。

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;キャンペーン ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### ヘッダー

「**[!UICONTROL URL 設定]**」セクションには、動的ヘッダーフィールドが表示されますが、定数ヘッダーフィールドは表示されません。動的ヘッダーフィールドは、値が変数として設定される HTTP ヘッダーフィールドです。[詳細情報](../action/about-custom-action-configuration.md)。

必要に応じて、動的ヘッダーフィールドの値を指定します。

1. ジャーニーのカスタムアクションを選択します。
1. 設定ペインで、「**[!UICONTROL URL 設定]**」セクションのヘッダーフィールドの横にある鉛筆アイコンをクリックします。

   ![](../assets/journey-dynamicheaderfield.png)

1. フィールドを選択し、「**[!UICONTROL OK]**」をクリックします。

## アクションパラメーター

「**[!UICONTROL アクションパラメーター]**」セクションには、_「変数」_&#x200B;として定義されたメッセージパラメーターが表示されます。これらのパラメーターについては、この情報の取得先（例：イベント、データソース）を定義したり、値を手動で渡したり、高度なユースケースに高度な式エディターを使用したりできます。高度なユースケースとしては、データ操作などの関数の使用が考えられます。詳しくは、 [AdobeJourney Orchestrationドキュメント](expression/expressionadvanced.md).

**関連トピック**

[アクションの設定](../action/about-custom-action-configuration.md)
