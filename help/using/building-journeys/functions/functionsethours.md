---
product: adobe campaign
title: setHours
description: setHours 関数の詳細
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ed78c2a9-d83a-4fac-a2e9-7383da131a1f
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

---

# setHours {#setHours}

日付の時間または日時のみを設定します。 例えば、あす特定の時間まで待つ場合は、時間を強制できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | dateTime |
| タイムゾーンを考慮しない日時 | dateTimeOnly |
| 時間 | 整数 |

## 署名と戻り値の型

`setHours(<dateTime>,<hours>)`

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを考慮せずに、日時を返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

戻り値2010-12-12T04:11:00Z

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後 8:XY PM に戻り、XY は現在の時間評価の時点の分です。 評価が午前 2 時 45 分におこなわれた場合、返される時刻は午後 8 時 45 分になります。
