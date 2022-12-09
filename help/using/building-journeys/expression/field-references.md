---
solution: Journey Optimizer
product: journey optimizer
title: フィールドリファレンス
description: 高度な表現についてのフィールド参照について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2348646a-b205-4b50-a08f-6625e92f44d7
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# フィールドリファレンス {#field-references}

フィールド参照は、イベントまたはフィールドグループに関連付けることができます。 意味のある情報は、フィールドの名前とそのパスになります。

フィールドで特殊文字を使用している場合は、二重引用符を使用するか、二重引用符を使用する必要があります。 Quote が必要な場合は、次のようになります。

* このフィールドの先頭には数字が含まれています。
* このフィールドは、「-」文字で始まります。
* このフィールドには、次のような __ __ __ __ 値は含まれません。 _a-z、a-z、0_ - _9_ _、-_

例えば、次のようなフィールドを使用すると _します。 3h_ : _# {openweather weatherData &#39;3h &#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

この式では、イベントフィールドは &quot;@&quot; で、「#」を使用して参照されます。

シンタックスカラーを使用して、フィールドグループ (青) からイベントフィールド (緑) を視覚的に区別します。

## フィールド参照のデフォルト値 {#default-value}

デフォルト値をフィールド名に関連付けることができます。 シンタックスは次のとおりです。

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>フィールドの種類とデフォルト値は同じである必要があります。 例えば、@ {LobbyBeacon のようになります。このデフォルト値は整数なので、有効な値は string である必要があるので、emailid id、defaultValue: 2} は無効になります。 _experience

例

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

デフォルト値として任意の種類の式を追加することができます。 唯一の制約は、式が予期されるデータ型を返す必要があることです。 関数を使用するときは、関数を () にカプセル化する必要があります。

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## コレクション内のフィールドへの参照

コレクション内で定義されたエレメントは、特定の関数 `all` `first` `last` を使用して参照されます。 詳しくは、このページ ](../expression/collection-management-functions.md) を [ 参照してください。

一

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## マップで定義されているフィールドへの参照

### `entry` 関数

Map 内のエレメントを取得するには、指定されたキーを使用して入力関数を使用します。 例えば、これは、選択された名前空間に応じてイベントのキーを定義するときに使用されます。 詳しくは、このページ ](../../event/about-creating.md#select-the-namespace) を参照してください [ 。

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

この正規表現では、イベントの「&quot;イベントコードマップ&quot;」フィールドの「Email」キーに対応するエントリを取得しています。 「Email」エントリはコレクションなので、最初のエレメントの「id」を「first ()」を使用して取得します。 詳しくは、このページ ](../expression/collection-management-functions.md) を参照してください [ 。

### `firstEntryKey` 関数

マップの1番目のエントリキーを取得するには、この関数を使用 `firstEntryKey` します。

次の例では、特定のリストのサブスクライバーの最初の電子メールアドレスを取得する方法を示します。

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

この例では、購読リストにはという名前が付け `daily-email` られています。 電子メールアドレスは、購読リストマップにリンクされたマップ内の `subscribers` キーとして定義されます。

### `keys` 関数

マップのすべてのキーを取得するには、この関数を使用 `keys` します。

この例では、特定のプロファイルについて、特定のリストのサブスクライバーに関連付けられたすべての電子メールアドレスを取得する方法を示します。

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## データソースのパラメーター値 (データソースの動的な値)

パラメーターを呼び出す必要がある外部データソースからフィールドを選択した場合は、右側にタブが表示され、このパラメーターを指定することができます。 このページ ](../expression/expressionadvanced.md) を参照してください [ 。

複雑な使用例については、データソースのパラメーターをメイン式に含める必要がある場合は、キーワード _params_ を使用してその値を定義することができます。 パラメーターは、別のデータソースにも含まれていても、他のパラメーターを含む有効な式であってもかまいません。

>[!NOTE]
>
>式の中でパラメーター値を定義すると、右側のタブが非表示になります。

次のシンタックスを使用します。

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: データソースの1番目のパラメーターの正確な名前。
* **`<params-1-value>`**: 1 番目のパラメーターの値を指定します。 有効な式を指定することもできます。

一

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
