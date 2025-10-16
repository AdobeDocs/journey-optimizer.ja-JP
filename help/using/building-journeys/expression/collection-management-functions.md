---
solution: Journey Optimizer
product: journey optimizer
title: コレクション管理機能
description: コレクション管理関数のデータタイプについて説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: クエリ, コレクション, 関数, ペイロード, ジャーニー
exl-id: 09b38179-9ace-4921-985b-ddd17eb64681
version: Journey Orchestration
source-git-commit: 7ac246c0aa6776d3ec67223c4b07536b8ed0c881
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# コレクション管理機能 {#collection-management-functions}


## クエリコレクション関数について

式言語には、クエリコレクションに対する一連の関数も導入されています。これらの関数について以下で説明します。

次の例では、コレクションを含むイベントペイロードを使用します。

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

## all(`<condition>`) 関数

この **[!UICONTROL all]** 関数では、ブール式を使用して指定のコレクションに対するフィルターを定義できます。

```json
<listExpression>.all(<condition>)
```

例えば、すべてのアプリユーザーの中から、iOS 13 を使用しているユーザーを取得できます（ブール式「app used == IOS 13」）。この関数の結果は、ブール式に一致する項目（例：アプリユーザー 1、アプリユーザー 34、アプリユーザー 432）を含んだフィルター済みリストになります。

「データソースの条件」アクティビティでは、**[!UICONTROL all]** 関数の結果が null かどうかを確認できます。また、この **[!UICONTROL all]** 関数を、**[!UICONTROL count]** 関数などの他の関数と組み合わせることができます。詳しくは、[「データソースの条件」アクティビティ](../condition-activity.md#data_source_condition)を参照してください。


>[!CAUTION]
>
>ジャーニーの式／条件でのエクスペリエンスイベントの使用はサポートされていません。ユースケースでエクスペリエンスイベントを使用する必要がある場合は、別の方法を考慮します。[詳細情報](../exp-event-lookup.md)

### 例 1

ユーザーが特定のバージョンのアプリケーションをインストールしてあるかどうかを確認します。この目的のために、バージョンが 1.0 のモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンを取得します。その後、**[!UICONTROL count]** 関数で条件分けをして、返されたトークンリストに少なくとも 1 つの要素が含まれているかどうかを確認します。

```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果は true です。

### 例 2

ここでは、**[!UICONTROL count]** 関数を使用して、コレクションにプッシュ通知トークンがあるかどうかを確認します。

```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```


結果は true です。


```json
count(@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

式の結果は **3** です。


>[!NOTE]
>
>* **all()** 関数のフィルター条件に何も指定していない場合、フィルターはリスト内のすべての要素を返します。**ただし、コレクションの要素数をカウントするためには、all 関数は不要です。**
>
>* `currentEventField` はイベントコレクションを操作する場合、`currentDataPackField` はデータソースコレクションを操作する場合、`currentActionField` はカスタムアクションの応答コレクションを操作する場合にのみ使用できます。
>
>  `all`、`first`、`last` でコレクションを処理する場合、コレクションの各要素を 1 つずつループします。`currentEventField`、`currentDataPackField`、`currentActionField` は、ループする要素に対応します。


## first(`<condition>`) 関数と last(`<condition>`) 関数

**[!UICONTROL first]** 関数と **[!UICONTROL last]** 関数では、コレクションのフィルターを定義できる一方、フィルター条件を満たすリストの最初または最後の要素を返すこともできます。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

### 例 1

この式は、バージョンが 1.0 のモバイルアプリケーションに関連付けられた最初のプッシュ通知トークンを返します。


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token}
```

結果は `token_1` です。

### 例 2

この式は、バージョンが 1.0 のモバイルアプリケーションに関連付けられた最後のプッシュ通知トークンを返します。


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last(currentEventField.application.version == "1.0").token}
```

結果は `token_2` です。

## at(`<index>`) 関数

**[!UICONTROL at]** 関数を使用すると、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス 0 はコレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

### 例

この式は、リストの 2 番目のプッシュ通知トークンを返します。


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は `token_2` です。