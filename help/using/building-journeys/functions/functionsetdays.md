---
product: journey optimizer
title: setDays
description: setDays 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: setDays, 関数, 式, ジャーニー
exl-id: c2757e41-8206-44f7-9dbb-1fa79c0ba6e6
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 100%

---

# setDays {#setDays}

日時または日時のみの日を設定します。例えば、その月の特定の日まで待つ場合に、その日を強制的に指定できます。

## カテゴリ

日付

## 関数の構文

`setDays(<parameter>)`

## パラメーター

| パラメーター | タイプ |
|--- |--- |
| 日時 | 日時 |
| タイムゾーンを考慮しない日時 | 日時のみ |
| 日 | 整数 |

## シグネチャと戻り値のタイプ

`setDays(<dateTime>,<days>)`

日時を返します。

`setDays(<dateTimeOnly>,<days>)`

タイムゾーンを無視して日時を返します。

## 例

`setDays(toDateTime('2023-12-12T01:11:00Z'), 25)`

2023-12-25T01:11:00Z を返します。

`setDays(toDateTimeOnly(@event{MyEvent.registrationDate}), 1)`
