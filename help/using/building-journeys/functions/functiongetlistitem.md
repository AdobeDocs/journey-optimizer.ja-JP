---
product: journey optimizer
title: getListItem
description: gstListItem 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: getListItem, 関数, 式, ジャーニー
exl-id: e995f479-bbaa-45f3-9531-e05680c5a723
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 100%

---

# getListItem {#gestListItem}

指定されたインデックスのリスト項目を返します。

## カテゴリ

リスト

## 関数の構文

`getListItem(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト | listString |
| リスト | listBoolean |
| リスト | listInteger |
| リスト | listDecimal |
| リスト | listDuration |
| リスト | listDateTime |
| リスト | listDateTimeOnly |
| リスト | listDateOnly |
| index | 整数 |

## シグネチャと戻り値のタイプ

`getListItem(<listInteger>,<index>)`

整数を返します。

`getListItem(<listDecimal>,<index>)`

小数を返します。

`getListItem(<listString>,<index>)`

文字列を返します。

`getListItem(<listDateTimeOnly>,<index>)`

タイムゾーンを無視して日時を返します。

`getListItem(<listDateTime>,<index>)`

日時を返します。

`getListItem(<listDateOnly>,<index>)`

日付のリストを返します。

`getListItem(<listBoolean>,<index>)`

ブール値を返します。

`getListItem(<listDuration>,<index>)`

期間を返します。

## 例

`getListItem([10, 2, 3], 1)`

「2」を返します

`getListItem(["A", "B", "C"], 2)`
「C」を返します。

値「20.45.2.3434」を持つイベントフィールド「event.appVersion」の例

`split(@event{event.appVersion}, "\\.")`

`["20", "45", "2", "3434"]` を返します

`getListItem(split(@event{event.appVersion}, "\\."), 0)`

「20」を返します
