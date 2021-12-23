---
product: adobe campaign
title: setHours
description: setHours 関数について説明します
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ed78c2a9-d83a-4fac-a2e9-7383da131a1f
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: ht
source-wordcount: '101'
ht-degree: 100%

---

# setHours {#setHours}

日時または日時のみの時を設定します。例えば、明日の特定の正時まで待つ場合に、その正時を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setHours(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | 日時のみ |
| 時 | 整数 |

## シグネチャと戻り値のタイプ

`setHours(<dateTime>,<hours>)`

日時を返します。

`setHours(<dateTimeOnly>,<hours>)`

タイムゾーンを無視して日時を返します。

## 例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

2010-12-12T04:11:00Z を返します。

`setHours(nowWithDelta(1, "days"), 20)`

明日の午後 8:XY を返します（XY は現在時刻の分）。評価が午前 2:45 に行われた場合、返される時刻は午後 8:45 になります。
