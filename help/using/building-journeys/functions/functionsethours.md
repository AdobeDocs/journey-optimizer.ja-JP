---
product: journey optimizer
title: setHours
description: 関数の setHours について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ed78c2a9-d83a-4fac-a2e9-7383da131a1f
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# setHours {#setHours}

日時のみを設定することができます。 例えば、ある時間が明日になるまで待機する場合は、時間を指定できます。

## 項目

古い

## 関数のシンタックス

`setHours(<parameter>)`

## パラメーター

| 指定 | 入力 |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮せずの日時 | dateTimeOnly |
| 残存 | 整数 |

## シグネチャと戻り値の型

`setHours(<dateTime>,<hours>)`

Datetime を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに日付時刻を返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

2010-12-12T04 :11: 00z を返します。

`setHours(nowWithDelta(1, "days"), 20)`

8: の明日を返します。この場合は、現在の時間の評価時点での分を示します。 評価が 2:45 AM で発生した場合、返される時刻は 8:45 PM になります。
