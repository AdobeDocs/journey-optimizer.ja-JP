---
solution: Journey Optimizer
product: journey optimizer
title: コレクション管理関数
description: コレクション管理関数のデータタイプについて説明します
feature: Journeys
role: Developer
level: Experienced
keywords: クエリ, コレクション, 関数, ペイロード, ジャーニー
exl-id: 09b38179-9ace-4921-985b-ddd17eb64681
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/sNFI7l-UMGmRV2wRcvYa56tILLoWFxXeG3N5txgrUiw
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 1000
ht-degree: 47%

---

# コレクション管理関数 {#collection-management-functions}


## クエリコレクション関数について

式言語には、クエリコレクションに対する一連の関数も導入されています。 これらの関数について以下で説明します。

次の例では、プッシュ通知トークンのコレクションを含む「LobbyBeacon」という名前のイベントを使用します。 このページの例では、以下に示すイベントペイロード構造を使用しています。

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

>[!NOTE]
>
>以下の例では、このペイロードは `@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens}` を使用して参照されています。ここで、「LobbyBeacon」はイベント名で、残りのパスは上記の構造に対応しています。

## all(`<condition>`) 関数

この **[!UICONTROL all]** 関数では、ブール式を使用して指定のコレクションに対するフィルターを定義できます。

```json
<listExpression>.all(<condition>)
```

**概念的な例：**&#x200B;すべてのアプリユーザーの中から、iOS 13 を使用しているユーザーを取得できます（ブール式「app used == IOS 13」）。 この関数の結果は、ブール式に一致する項目（例：アプリユーザー 1、アプリユーザー 34、アプリユーザー 432）を含んだフィルター済みリストになります。

「データソースの条件」アクティビティでは、**[!UICONTROL all]** 関数の結果が null かどうかを確認できます。 また、この **[!UICONTROL all]** 関数を、**[!UICONTROL count]** 関数などの他の関数と組み合わせることができます。 詳しくは、[「データソースの条件」アクティビティ](../conditions.md#data_source_condition)を参照してください。

**LobbyBeacon ペイロードを使用したコード例：**

以下の例では、このページの上部に表示されるイベントペイロードを使用しています。


>[!CAUTION]
>
>ジャーニーの式／条件でのエクスペリエンスイベントの使用はサポートされていません。 ユースケースでエクスペリエンスイベントを使用する必要がある場合は、別の方法を考慮します。 [詳細情報](../exp-event-lookup.md)

### 例 1

ユーザーが特定のバージョンのアプリケーションをインストールしてあるかどうかを確認します。 このために、バージョンが1.0のモバイルアプリケーションに関連付けられたすべてのプッシュ通知トークンを取得します。 次に、**[!UICONTROL count]**&#x200B;関数を使用して条件を実行し、返されるトークンのリストに少なくとも1つの要素が含まれていることを確認します。

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
>* **all()** 関数のフィルター条件に何も指定していない場合、フィルターはリスト内のすべての要素を返します。 **ただし、コレクションの要素数をカウントするためには、all 関数は不要です。**
>
>* `currentEventField` はイベントコレクションを操作する場合、`currentDataPackField` はデータソースコレクションを操作する場合、`currentActionField` はカスタムアクションの応答コレクションを操作する場合にのみ使用できます。
>
>  `all`、`first`、`last` でコレクションを処理する場合、コレクションの各要素を 1 つずつループします。 `currentEventField`、`currentDataPackField`、`currentActionField` は、ループする要素に対応します。


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

**[!UICONTROL at]**&#x200B;関数を使用すると、インデックスに従ってコレクション内の特定の要素を参照できます。
インデックス 0は、コレクションの最初のインデックスです。

_`<listExpression>`.at(`<index>`)_

### 例

この式は、リストの 2 番目のプッシュ通知トークンを返します。


```json
@event{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果は `token_2` です。

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、プッシュ通知トークンのペイロードの例で示されている、ジャーニーの高度な式エディターで使用される`all()`、`first()`、`last()`および`at()` コレクション管理関数について説明します。

**インテント：**

* `all(<condition>)`のブール条件を使用して、イベントまたはデータソースフィールドのコレクションをフィルタリングします
* コレクション関数と組み合わせた`count()`を使用して、フィルター済みまたはフィルターされていないコレクション要素をカウントします
* `first()`または`last()`を使用して、コレクションの最初または最後に一致する要素を取得します
* `at(<index>)`を使用して、特定のゼロベース インデックスのコレクション要素にアクセスする
* 各コレクションコンテキストに適用されるループ変数（`currentEventField`、`currentDataPackField`、`currentActionField`）について説明します

**用語集：**

* **all （condition）**: コレクションをフィルタリングし、指定されたブール式&#x200B;*（product-specific）*&#x200B;に一致するすべての項目を返します
* **first （condition）**：条件&#x200B;*（product-specific）*&#x200B;に一致するコレクションの最初の（エクスペリエンスイベントの最新）要素を返します
* **last （condition）**：条件&#x200B;*（product-specific）*&#x200B;に一致するコレクション内の最後の（エクスペリエンスイベントの最古の）要素を返します
* **at （index）**: コレクション *（product-specific）*&#x200B;の指定されたゼロベース インデックスの要素を返します
* **currentEventField**: ループ変数は、イベントコレクション *（製品固有）*&#x200B;を繰り返す場合にのみ使用できます
* **currentDataPackField**: ループ変数は、データソースコレクション *（製品固有）*&#x200B;を繰り返す場合にのみ使用できます
* **currentActionField**: ループ変数は、カスタムアクション応答コレクション *（製品固有）*&#x200B;を繰り返す場合にのみ使用できます

**ガードレール：**

* ジャーニー式/条件でのエクスペリエンスイベントの使用はサポートされていません。計算属性などの代替方法を検討してください
* `currentEventField`、`currentDataPackField`および`currentActionField`は、それぞれのコレクション コンテキスト内でのみ使用できます
* コレクション要素をカウントするために`all`関数は必要ありません – `count()`はフィールドパスに直接適用できます
* `all()`が空の条件で呼び出されると、コレクション内のすべての要素が返されます

**用語：**

* 正規名：コレクション管理関数 – Acronym: none — バリアント：コレクション関数、クエリコレクション関数
* 同義語：&quot;all （）&quot; = &quot;collection filter function&quot;; &quot;at （）&quot; = &quot;index accessor&quot;
* 混乱しないでください：`first()` （最新のエクスペリエンスイベント）≠最初に挿入された要素が一般的なリストに含まれています

**FAQ:**

* **Q：空の条件を持つ`all()`と条件を持つ`all()`の違いは何ですか？**  – 空の`all()`はすべての要素を返します。条件ベースの`all()`は、そのブール式に一致する要素のみを返します。
* **Q: `all()`を使用せずにプッシュ通知トークンをカウントするにはどうすればよいですか？** — トークンフィールドパス（例：`count(@event{LobbyBeacon...pushNotificationTokens.token})`）で`count()`を直接呼び出します。
* **Q: データソースコレクションをループする際に、現在の要素を参照するためにどの変数を使用しますか？** — データソースコレクションの`all()`、`first()`、または`last()`内で`currentDataPackField`を使用します。
* **Q: コレクションの2番目の項目を取得するにはどうすればよいですか？** — インデックス 0が最初の要素であるため、`at(1)`を使用します。
* **Q: `last()`さんが最も古いエクスペリエンスイベントを返すのはなぜですか？** — エクスペリエンスイベントは逆時系列で保存されるため、コレクション内の最後の位置は最も古いイベントに対応します。

+++
