---
product: journey optimizer
title: intersect
description: intersect 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: intersect, 関数, 式, ジャーニー
exl-id: e236efa9-91a8-4f08-94c6-45f1e060bb2f
source-git-commit: cb1fed2460ddbf3b226fe191b9695008970937c1
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 100%

---

# intersect{#intersect}

2 つの入力リストで共通する値を返します。2 つのリストのいずれかが null の場合、空のリストを返します。

## カテゴリ

リスト

## 関数の構文

`intersect(<parameters>)`

## パラメーター

| パラメーター | タイプ |
|-----------|------------------|
| リスト 1 | リスト |
| リスト 2 | リスト |

## シグネチャと戻り値のタイプ

`intersect(listString,listString)`：listString
`intersect(listDecimal,listDecimal)`：listDecimal
`intersect(listInteger,listInteger)`：listInteger
`intersect(listDateTime,listDateTime)`：listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`：listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`：listDateOnly
`intersect(listDuration,listDuration)`：listDuration
`intersect(listBoolean,listBoolean)`：listBoolean

リストを返します。

## 例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

[&quot;sports&quot;, &quot;news&quot;] を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

プロファイル属性と指定されたカテゴリリストの間の共通項目を返します。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @event{myEvent.sport_interests}
)
```

プロファイル属性と指定されたイベントフィールドの間の共通項目を返します。
