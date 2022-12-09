---
solution: Journey Optimizer
product: journey optimizer
title: journeyStep イベントのデータ取得フィールド
description: journeyStep イベントのデータ取得フィールド
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 948fe843-47cf-4b20-976a-48069eb9cf5c
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---

# journeyStep イベントのデータ取得フィールド {#sharing-fetch-fields}

このフィールドグループは journeyStepEvent および journeyStepProfileEvent によって共有されます。

ステップの処理中に、フィールドグループに対して N 個のデータフェッチが実行されます。

## fetchTotalTime {#fetchtotaltime-field}

ステップ処理中に、millis でのデータのフェッチに費やされた時間の合計です。

タイプ: long

## fetchTypeInError {#fetchtypeinerror-field}

エラーが発生した fetch が、Adobe エクスペリエンスプラットフォームとカスタムデータソースのどちらであるかを定義します。

タイプ: string

指定
* aep
* custom

## fetchError {#fetcherror-field}

データ fetch が処理されるときに発生するエラーのタイプ。

タイプ: string

指定
* http
* 上限
* timedout
* 中

## fetchErrorCode {#fetcherrorcode-field}

Fetch エラーのコードです。 エラーに HTTP 1 などのコードが含まれている場合に表示されます。 例えば、actionExecError が http の場合は、HTTP 404 エラーがコード404によって表されます。

タイプ: string

## Fetch原点エラー {#fetchoriginerror-field}

タイムアウトは、次の2つの場合に発生します。

* 最初にアクションが実行されます。 この場合、実行は終了せず、根底にあるエラーは発生しません。
* 再試行: この場合は、actionExecOrigError/actionExecOrigErrorCode によって、再試行前に発生したエラーが説明されています。

例えば、統合されたプロファイルサービスからデータを取得し、最初の試みで HTTP 500 エラーが返されます。 Fetch はリトライされますが、2回の実行回数がタイムアウト時間を超えています。 その後、アクションの実行を timedout としてタグ付けします。 アクションは以下のように表示されます。

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

タイプ: string

## fetchOriginErrorCode {#fetchoriginerrorcode-field}

システム [!DNL Journey Optimizer] によって提供されるエラーコードはクエリー中です。 例えば、404、500などを指定することができます。

タイプ: string

## fetchCount {#fetchcount-field}

ソースのタイプに関係なく、データのフェッチ回数。

タイプ: long

## fetchPlatformTotalTime {#fetchplatformtotaltime-field}

Adobe エクスペリエンスプラットフォームからデータを取得するためにかかった時間の合計を millis で返します。 注釈: この時間は、エンジンによって enrichment イベントが enrichment サービスに送信され、応答を受け取るまでの間に計算されます。

タイプ: long

## fetchPlatformCount {#fetchplatformcount-field}

Adobe エクスペリエンスプラットフォームからデータを取得する回数を指定します。

タイプ: long

## fetchCustomTotalTime {#fetchcustomtotaltime-field}

Millis のカスタムデータを取得する時間の長さです。 注釈: この時間は、エンジンが enrichment イベントを enrichment サービスに送信し、応答を受信した時点から計算されます。

タイプ: long

## fetchCustomCount {#fetchcustomcount-field}

外部システムから取得されたカスタムデータの数。

タイプ: long
