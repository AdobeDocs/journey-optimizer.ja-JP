---
solution: Journey Optimizer
product: journey optimizer
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 273cda84-0261-4c5b-b5f4-0202e8874d05
source-git-commit: b93d2288156713ac7479eef491f6104df1955a18
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 64%

---

# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

このフィールドグループは、journeyStepEvent と journeyStepProfileEvent が共有します。

処理が必要なアクションがステップにある場合、これらのフィールドはイベントペイロードに追加されます。

## actionID {#actionid-field}

実行中のアクションの ID。

型：文字列

## actionName {#actionname-field}

アクションの名前。名前が設定されていない場合、stepName が使用されます。

型：文字列

## actionType {#actionType-field}

アクションのタイプ。

型：文字列

## actionParameterized {#actionparameterized-field}

アクションがパラメータ化されているかどうかを示します。

型：ブール型

## actionExecutionTime {#actionexecutiontime-field}

現在のアクションを実行するのに費やした時間（ミリ秒）。

型：long

`actionExecutionTime` フィールドは、アクションを実行するのに要した合計時間（ミリ秒単位）を表します。これには、リクエストがキュー内で待機していた時間（スロットルが設定され、レート制限に達した場合）と実際の実行時間（外部エンドポイントへのネットワーク待ち時間を含む）の両方が含まれます。

`Timestamp` フィールドは、アクション実行の終了時刻を示します。プロファイルがカスタムアクションノードにエントリしたタイミングを特定するには、`Timestamp` から `actionExecutionTime` を減算します。

例えば、`Timestamp` が「2025-02-04 09:39:03 UTC」で、`actionExecutionTime` が 1,813,227 ミリ秒（～31 分）の場合、プロファイルは「2025-02-04 09:08:32 UTC」頃にノードにエントリしました。


## actionExecutionError {#actionexecutionerror-field}

アクションが呼び出されたときに発生するエラーの種類。

型：文字列

値：

* http
* キャップ
* timeout
* error

## actionExecutionErrorCode {#actionexecutionerrorcode-field}

アクション実行エラーのコード。エラーにコードがあるかどうかを示します（HTTP など）。

型：文字列

## actionExecutionOriginError {#actionexecutionoriginerror-field}

タイムアウトは、次の 2 つの場合に発生する可能性があります。

* アクションの実行を最初に試行したとき。この場合、実行は完了せず、基になるエラーはありません。
* 再試行時。この場合、actionExecOrigError/actionExecOrigErrorCode は、再試行前に試行したときのエラーを示します。

たとえば、メールが送信され、最初の試行時に HTTP 500 エラーが返されます。フェッチを再試行しますが、2 回の試行のデュレーションがタイムアウトを超えます。次に、アクションの実行にタイムアウトのタグが付けられます。アクション部分は次のようになります。

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

型：文字列

## actionExecutionOriginCode {#actionexecutionorigincode-field}

actionExecOrigError のエラーコード。

型：文字列

## actionOriginEndpoint {#actionoriginendpoint}

アクションで使用されるカスタムアクションエンドポイントの URI。

型：文字列

## actionOriginMethod {#actionoriginmethod}

これは、HTTP リクエストで使用されるメソッド（GETまたは POST）を表します。

型：文字列

## actionOriginIsMTLS {#actionoriginismtls}

これは、エンドポイントに対して MTLS が有効になっているかどうかを表します。

型：ブール型

## actionIsProxy {#actionisproxy}

定義済みの IP アドレス範囲を持つ HTTP プロキシが呼び出しに使用されるかどうかを示します。

型：ブール型

## actionExecutionOriginStartTime {#actionexecutionoriginstarttime}

これは、HTTP リクエストが開始されるタイムスタンプを表します。 再試行の場合、これは最後の再試行が開始されるタイムスタンプです。 タイムスタンプは、UTC タイムゾーンで ISO8601 形式を使用します。

このタイムスタンプは、通常、プロファイルがカスタムアクションノードに入ってやや後になることに注意してください。または、スロットルの場合、プロファイルがノードに入ってかなり後になります。

タイプ：timestamp

## actionExecutionOriginTime {#actionexecutionorigintime}

HTTP 呼び出しの応答時間を表します。 再試行の場合、これは最後の再試行の試行にかかる時間です。 HTTP リクエストが開始されてから、サーバーから完全な応答が返されるまでの時間を測定します。 スロットルの場合、キューでの待機に費やされた時間は除外されます。

型：long

## actionIsThrottled {#actionisthrottled}

これは、エンドポイントに対してスロットルが有効になっているかどうかを表します。

型：ブール型

## actionWaitTime {#actionwaittime}

これは、スロットルされたエンドポイントに対して設定されたレート制限に達した場合、呼び出しは設定されたレートでキューに入れられ、処理されます。 このフィールドは、コールが実行されるまでキュー内で待機していた時間をレポートします。 actionIsThrottled が true の場合にのみ指定==ます。

型：long

## actionBusinessType {#actionbusinesstype-field}

アクションのタイプを示します。

値：

* 組み込み
   * ACS メール
   * ACS SMS
   * ACS プッシュ
* 顧客
   * Epsilon
   * ...

型：文字列

## deliveryJobID {#deliveryjobid-field}

バッチジャーニーの配信ジョブ ID を示します。

型：文字列

## batchDeliveryID {#batchdeliveryid-field}

バッチジャーニーの配信 ID を示します。

型：文字列

## fromSegmentTrigger {#fromsegmenttrigger-field}

バッチジャーニーがオーディエンスセグメントからトリガーされるかどうかを示します。

型：ブール型

## actionSchedulerCount {#actionschedulercount-field}

ステップの処理中にスケジューラーサービスに送信されたスケジューラー通知リクエストの数。

型：long
