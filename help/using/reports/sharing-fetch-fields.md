---
solution: Journey Optimizer
product: journey optimizer
title: journeyStep イベントのデータ取得フィールド
description: journeyStep イベントのデータ取得フィールド
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 948fe843-47cf-4b20-976a-48069eb9cf5c
TQID: https://experienceleague.adobe.com/obaiLWD6yq0dZ5ZhE69q-iLHzI99ll7XJnMNlOpJp1A
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a9f73820-6899-47c2-a597-3fec28ab756aid: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
subfeature_v2: id: d145add9-d5b9-481b-aa8a-e15e6bb7f813id: a7289281-9ae4-47b1-b8cf-4028b98af776id: b5afe8bf-bda6-41b5-ba06-922638872d63
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 377
ht-degree: 100%

---

# journeyStep イベントのデータ取得フィールド {#sharing-fetch-fields}

このフィールドグループは、journeyStepEvent と journeyStepProfileEvent が共有します。

ステップの処理中に、フィールドグループで N 個のデータを取得できます。

## fetchTotalTime {#fetchtotaltime-field}

ステップ処理中のデータ取得に費やした合計時間（ミリ秒単位）です。

型：long

## fetchTypeInError {#fetchtypeinerror-field}

エラーの取得先を Adobe Experience Platform 上とするか、カスタムデータソース上とするかを定義します。

型：string

値：

* aep
* custom

## fetchError {#fetcherror-field}

データ取得の処理時に発生するエラーの種類です。

型：string

値：

* http
* キャップ
* timedout
* error

## fetchErrorCode {#fetcherrorcode-field}

取得エラーコード。 エラーにコードがあるかどうかを示します（HTTP など）。 例えば、actionExecError が http の場合、コード 404 は HTTP 404 エラーを表します。

型：文字列

## fetchOriginError {#fetchoriginerror-field}

タイムアウトは、次の 2 つの場合に発生する可能性があります。

* 初回試行時に、アクションが実行されます。 この場合、実行は完了せず、基になるエラーはありません。
* 再試行時。この場合、actionExecOrigError/actionExecOrigErrorCode は、再試行前に試行したときのエラーを示します。

例えば、統合プロファイルサービスからデータを取得中、最初の試行時に HTTP 500 エラーが返されます。 フェッチを再試行しますが、2 回の試行のデュレーションがタイムアウトを超えます。 次に、アクションの実行にタイムアウトのタグが付けられます。 アクション部分は次のようになります。

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

型：string

## fetchOriginErrorCode {#fetchoriginerrorcode-field}

システム [!DNL Journey Optimizer] から提供されたエラーコードを問い合わせています。 例えば、404、500などのエラーコード。

型：文字列

## fetchCount {#fetchcount-field}

データの取得回数（ソースのタイプを問わない）。

型：long

## fetchPlatformTotalTime {#fetchplatformtotaltime-field}

Adobe Experience Platform からデータを取得するのに要した合計時間（ミリ秒）。 備考：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時点から計算されます。

型：long

## fetchPlatformCount {#fetchplatformcount-field}

Adobe Experience Platform からデータが取得された回数。

型：long

## fetchCustomTotalTime {#fetchcustomtotaltime-field}

カスタムデータの取得にかかる時間（ミリ秒）。 備考：この時間は、エンジンがエンリッチメントイベントをエンリッチメントサービスに送信し、応答を受信した時点から計算されます

型：long

## fetchCustomCount {#fetchcustomcount-field}

外部システムからカスタムデータを取得した回数。

型：long
