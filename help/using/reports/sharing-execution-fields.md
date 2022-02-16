---
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 273cda84-0261-4c5b-b5f4-0202e8874d05
source-git-commit: 6d744c0289e81ab2229f02c44ead43943b945b89
workflow-type: ht
source-wordcount: '321'
ht-degree: 100%

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

## actionExecutionError {#actionexecutionerror-field}

アクションが呼び出されたときに発生するエラーの種類。

型：文字列

値：
* http
* capping
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
