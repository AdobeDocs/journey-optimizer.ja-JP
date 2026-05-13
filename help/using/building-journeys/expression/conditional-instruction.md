---
solution: Journey Optimizer
product: journey optimizer
title: 条件命令（if、then、else）
description: 条件命令について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 詳細, 条件, アクション, ジャーニー
exl-id: 5a5b35a7-e3b5-4dc0-8a87-e985956b04a4
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/SObpEvgu0D-pcoLVaKM7iRffLTSP1stp1zcg4Ygs-vQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: cce82f05-fc3c-4af7-85ff-8bba603861a7id: d8353d85-5da7-453d-bd68-40ad33fa0ab7
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 168
ht-degree: 100%

---

# 条件命令（if、then、else） {#conditional-instruction}

高度なエディターでは、条件命令（if、then、else）をサポートしています。 これにより、より複雑な式を定義できます。 条件命令は、次の要素で構成されています。

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

`<expression2>` と `<expression3>` は、同じタイプまたは互換性のあるタイプを持つ必要があります。 サポートされているシグネチャと戻り値のタイプは次のとおりです。

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

条件命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。 例えば、同じアクションアクティビティ内で、1 つの条件式のみを使用して、1 つのフィールド定義に 2 つの代替オプションを指定できます。

アクションアクティビティの例（条件命令の結果として文字列を想定するフィールドの場合）：

```json
if (startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
