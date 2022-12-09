---
product: journey optimizer
title: getListItem
description: 関数の gstListItem について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e995f479-bbaa-45f3-9531-e05680c5a723
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---

# getListItem {#gestListItem}

指定されたインデックスのリストの項目を返します。

## 項目

一連

## 関数のシンタックス

`getListItem(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| 一連 | listString |
| 一連 | listBoolean |
| 一連 | listInteger |
| 一連 | リスト10進数 |
| 一連 | listDuration |
| 一連 | listDateTime |
| 一連 | listDateTimeOnly |
| 一連 | listDateOnly |
| 検索 | 整数 |

## シグネチャと戻り値の型

`getListItem(<listInteger>,<index>)`

整数値を返します。

`getListItem(<listDecimal>,<index>)`

10進数を返します。

`getListItem(<listString>,<index>)`

ストリングを返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを考慮せずに日付時刻を返します。

`getListItem(<listDateTime>,<index>)`

Datetime を返します。

`getListItem(<listDateOnly>,<index>)`

日付のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値を返します。

`getListItem(<listDuration>,<index>)`

期間を返します。

## 一

`getListItem([10, 2, 3], 1)`

「2」を返します。

`getListItem(["A", "B", "C"], 2)`「C」を返します。

次の例に示すように、イベントフィールド「イベント. appVersion」に値: &quot;20.45.2.3434&quot; を指定します。

`split(@{event.appVersion}, "\\.")`

制御 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

「20」を返します。
