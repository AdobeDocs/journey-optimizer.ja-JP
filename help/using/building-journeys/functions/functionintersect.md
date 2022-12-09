---
product: journey optimizer
title: 交わる
description: 関数の intersect について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e236efa9-91a8-4f08-94c6-45f1e060bb2f
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 0%

---

# 交わる{#intersect}

2つの入力リストに含まれる共通の値を返します。 この2つのリストのいずれかが null の場合は、空のリストが返されます。

## 項目

一連

## 関数のシンタックス

`intersect(<parameters>)`

## パラメーター

| 指定 | 入力 |
|-----------|------------------|
| リスト1 | 一連 |
| リスト2 | 一連 |

## シグネチャと戻り値の型

`intersect(listString,listString)`: listString
`intersect(listDecimal,listDecimal)`: listdecimal
`intersect(listInteger,listInteger)`: listinteger
`intersect(listDateTime,listDateTime)`: listdatetime
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`: listdateonly
`intersect(listDuration,listDuration)`: listduration
`intersect(listBoolean,listBoolean)`: listboolean

リストを返します。

## 例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

「スポーツ」、「news」を返します [ 。]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

プロファイル属性と指定されたカテゴリリストとの間で使用される一般的なアイテムを返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドとの間で使用される一般的なアイテムを返します。
