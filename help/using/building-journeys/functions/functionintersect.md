---
product: adobe campaign
title: 交わる
description: 関数の交差について学ぶ
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e236efa9-91a8-4f08-94c6-45f1e060bb2f
source-git-commit: 2022b2c81738ae6d3e66280265948c5b88a117c8
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# 交わる{#intersect}

2 つの入力リスト内の共通値を返します。 2 つのリストのいずれかが null の場合、は空のリストを返します。

## カテゴリ

リスト

## 関数の構文

`intersect(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト 1 | リスト |
| リスト 2 | リスト |

## 署名と戻り値の型

`intersect(listString,listString)`:listString
`intersect(listDecimal,listDecimal)`:listDecimal
`intersect(listInteger,listInteger)`:listInteger
`intersect(listDateTime,listDateTime)`:listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`:listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`:listDateOnly
`intersect(listDuration,listDuration)`:listDuration
`intersect(listBoolean,listBoolean)`:listBoolean

リストを返します。

## 例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

戻り値 [&quot;sports&quot;, &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

プロファイル属性とカテゴリの指定されたリストとの間の共通項目を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドの間の共通項目を返します。
