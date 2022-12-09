---
solution: Journey Optimizer
product: journey optimizer
title: 条件付き命令 (その場合は、その他)
description: 条件付き命令について
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 5a5b35a7-e3b5-4dc0-8a87-e985956b04a4
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# 条件付き命令 (その場合は、その他) {#conditional-instruction}

条件付き命令 (その後、else) は、高度なエディターでサポートされています。 さらに複雑な式を定義することができます。 これは、次の要素で構成されています。

* **[!UICONTROL if]**: 最初に評価する条件を指定します。
* **[!UICONTROL then]**: 条件を評価した結果が true の場合に評価される式を指定します。
* **[!UICONTROL else]**: 条件を評価した結果が false の場合に評価される式を指定します。

>[!NOTE]
>
>カッコはすべてのエクスプレッションを囲む必要があります。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>`ブール **値を** 返す必要があります。

`<expression2>``<expression3>`、同じ型または互換性のある型であることが必要です。サポートされるシグネチャと戻り値は次のとおりです。

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**目的**

条件付き命令を使用すると、condition アクティビティの数を減らすことによって、旅のワークフローを最適化することができます。 例えば、同じアクションアクティビティー内で、1つの条件式のみを使用して2つのフィールド定義を指定することができます。

アクションアクティビティーの例 (条件命令の結果としてストリングが必要なフィールドの場合):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
