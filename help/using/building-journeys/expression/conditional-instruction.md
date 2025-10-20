---
solution: Journey Optimizer
product: journey optimizer
title: 条件命令（if、then、else）
description: 条件命令について説明します
feature: Journeys
role: Engineer
level: Experienced
keywords: 詳細, 条件, アクション, ジャーニー
exl-id: 5a5b35a7-e3b5-4dc0-8a87-e985956b04a4
version: Journey Orchestration
source-git-commit: 6f7b9bfb65617ee1ace3a2faaebdb24fa068d74f
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 100%

---

# 条件命令（if、then、else） {#conditional-instruction}

高度なエディターでは、条件命令（if、then、else）をサポートしています。これにより、より複雑な式を定義できます。条件命令は、次の要素で構成されています。

* **[!UICONTROL if]**：最初に評価される条件。
* **[!UICONTROL then]**：条件評価の結果が true の場合に評価される式。
* **[!UICONTROL else]**：条件評価の結果が false の場合に評価される式。

>[!NOTE]
>
>すべての式は括弧で囲む必要があります。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` は&#x200B;**ブール値**&#x200B;を返す必要があります。

`<expression2>` と `<expression3>` は、同じタイプまたは互換性のあるタイプを持つ必要があります。サポートされているシグネチャと戻り値のタイプは次のとおりです。

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

**用途**

条件命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。例えば、同じアクションアクティビティ内で、1 つの条件式のみを使用して、1 つのフィールド定義に 2 つの代替オプションを指定できます。

アクションアクティビティの例（条件命令の結果として文字列を想定するフィールドの場合）：

```json
if (startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
