---
product: journey optimizer
title: inNextHours
description: inNextHours 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inNextHours, 関数, 式, ジャーニー
exl-id: 079a91b6-49c5-4e68-a240-358ed0cded92
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: ht
source-wordcount: '48'
ht-degree: 100%

---

# inNextHours {#inNextHours}

指定された日付または日時が現在と現在 + デルタ時間の間にある場合、true を返します。

## カテゴリ

日付

## 関数の構文

`inNextHours(<dateTime>,<delta>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| 日時 | 日時 |
| delta | 整数 |

## シグネチャと戻り値のタイプ

`inNextHours(<dateTime>,<integer>)`

ブール値を返します。

## 例

`inNextHours(toDateTime('2023-12-12T01:11:00Z'), 4)`

true を返します。
