---
solution: Journey Optimizer
product: journey optimizer
title: journeyStep イベントアクション実行フィールド
description: journeyStep イベントアクション実行フィールド
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 273cda84-0261-4c5b-b5f4-0202e8874d05
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# journeyStep イベントアクション実行フィールド {#sharing-execution-fields}

このフィールドグループは journeyStepEvent および journeyStepProfileEvent によって共有されます。

ステップに処理が必要なアクションがある場合は、それらのフィールドがイベントペイロードに追加されます。

## actionID {#actionid-field}

実行中のアクションの ID。

タイプ: string

## actionName {#actionname-field}

アクションの名前を指定します。 名前が設定されていない場合は、stepName が取得されます。

タイプ: string

## actionType {#actionType-field}

アクションのタイプです。

タイプ: string

## actionParameterized 化 {#actionparameterized-field}

アクションがパラメーター化されているかどうかを示します。

種類: ブール値

## actionExecutionTime {#actionexecutiontime-field}

現在のアクションの実行にかかった時間 (ミリ秒) です。

タイプ: long

## actionExecutionError {#actionexecutionerror-field}

アクションが呼び出されたときに発生するエラーのタイプ。

タイプ: string

指定
* http
* 上限
* タイムアウト
* 中

## actionExecutionErrorCode {#actionexecutionerrorcode-field}

アクション実行エラーのコードです。 エラーに HTTP 1 などのコードが含まれている場合に表示されます。

タイプ: string

## Actionexecution原点エラー {#actionexecutionoriginerror-field}

タイムアウトは、次の2つの場合に発生します。

* 最初にアクションが実行されたとき。 この場合、実行は終了せず、根底にあるエラーは発生しません。
* 再試行: この場合は、actionExecOrigError/actionExecOrigErrorCode によって、再試行前に発生したエラーが説明されています。

例えば、電子メールを送信しているときに、最初に HTTP 500 エラーが返されます。 Fetch はリトライされますが、2回の実行回数がタイムアウト時間を超えています。 その後、アクションの実行を timedout としてタグ付けします。 アクションは以下のように表示されます。

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

タイプ: string

## Actionexecutionのコード {#actionexecutionorigincode-field}

ActionExecOrigError のエラーコードです。

タイプ: string

## actionBusinessType {#actionbusinesstype-field}

アクションの種類を指定します。

指定

* builtin
* ACS 電子メール
* ACS SMS
* ACS プッシュ
* ・
* 当社
* ...

タイプ: string

## deliveryJobID {#deliveryjobid-field}

これは、バッチ処理の配送ジョブ Id を示します。

タイプ: string

## batchDeliveryID {#batchdeliveryid-field}

これは、バッチ処理を行う配送 Id を示します。

タイプ: string

## fromSegmentTrigger {#fromsegmenttrigger-field}

これは、バッチ処理が対象となるセグメントからトリガーされるかどうかを示しています。

種類: ブール値

## Actionスケジューラ数 {#actionschedulercount-field}

ステップ処理中に scheduler サービスに送信されたスケジューラ通知要求の数。

タイプ: long
