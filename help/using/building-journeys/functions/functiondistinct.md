---
product: journey optimizer
title: distinct
description: distinct 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: distinct, 関数, 式, ジャーニー
exl-id: f4e2dd34-b634-4a91-af53-60be155a65d0
source-git-commit: 1d30c6ae49fd0cac0559eb42a629b59708157f7d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 100%

---

# distinct {#distinct}

指定されたリストのユニークな値またはオブジェクトを返します。null エントリは無視されます。

>[!NOTE]
>
>ターゲットリストが listObject の場合、この関数はカスタムアクション式でのみ使用できます。

## カテゴリ

リスト

## 関数の構文

`distinct(<parameters>)`

## パラメーター

| パラメーター | タイプ | 説明 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly、listObject のいずれか | 処理するリスト。listObject の場合は、フィールド参照にする必要があります。 |
| keyAttributeName | 文字列 | このパラメーターはオプションで、listObject に対してのみ使用できます。パラメーターを指定しないと、すべての属性の値が同じ場合、オブジェクトは重複していると見なされます。パラメーターを指定していて、指定された属性が同じ値を持つ場合、オブジェクトは重複していると見なされます。 |

## シグネチャと戻り値のタイプ

`distinct(<listInteger>)`

整数のリストを返します。

`distinct(<listDecimal>)`

小数のリストを返します。

`distinct(<listString>)`

文字列のリストを返します。

`distinct(<listDateTimeOnly>)`

タイムゾーンを考慮しない日時のリストを返します。

`distinct(<listDateTime>)`

日時のリストを返します。

`distinct(<listDateOnly>)`

日付のリストを返します。

`distinct(<listBoolean>)`

ブール値のリストを返します。

`distinct(<listDuration>)`

期間のリストを返します。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

オブジェクトのリストを返します。


## 例

`distinct([10,2,10,null])`

`[10, 2]` を返します。
