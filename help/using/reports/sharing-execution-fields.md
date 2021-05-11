---
title: journeyStep イベントのアクション実行フィールド
description: journeyStep イベントのアクション実行フィールド
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 14%

---

# journeyStep イベントのアクション実行フィールド {#sharing-execution-fields}

![](../assets/do-not-localize/badge.png)

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

ステップに処理するアクションがある場合、これらのフィールドはイベントペイロードに追加されます。

## actionID

実行中のアクションのID。

型：文字列

## actionName

アクションの名前。 名前が設定されていない場合、stepNameが使用されます。

型：文字列

## actionType

アクションのタイプ。

型：文字列

## actionParameterized

アクションがパラメータ化されているかどうかを示します。

タイプ：ブール型

## actionExecutionTime

現在のアクションを実行するのに費やした時間（ミリ秒）。

タイプ：long

## actionExecutionError

アクションが呼び出されたときに発生するエラーの種類です。

型：文字列

values:
* http
* キャッピング
* timeout
* error

## actionExecutionErrorCode

アクション実行エラーのコード。 HTTPなどのコードがエラーにある場合に表示されます。

型：文字列

## actionExecutionOriginError

タイムアウトは、次の2つの場合に発生する可能性があります。

* 最初の試行時に、アクションが実行されます。 この場合、実行は完了せず、基になるエラーはありません
* 再試行時：この場合、actionExecOrigError/actionExecOrigErrorCodeは、再試行前に試行されたエラーを示します。

例えば、電子メールが送信され、最初の試行時にHTTP 500エラーが返されます。 フェッチは再試行されますが、2回の試行の時間がタイムアウトを超えます。 次に、アクションの実行にタイムアウトのタグが付けられます。 アクションパーツは次のようになります。

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

## actionExecutionOriginCode

actionExecOrigErrorのエラーコードです。

型：文字列

## actionBusinessType

アクションのタイプを示します。

values:

* 組み込み
* ACS電子メール
* ACS SMS
* ACSプッシュ
* 顧客
* エプシロン
* ...

型：文字列

## deliveryJobID

バッチジャーニーの配信ジョブIDを示します。

型：文字列

## batchDeliveryID

バッチジャーニーの配信IDを示します。

型：文字列

## fromSegmentTrigger

ここでは、バッチジャーニーがオーディエンスセグメントからトリガーされるかどうかを説明します。

タイプ：ブール型

## actionSchedulerCount

ステップ処理中にスケジューラーサービスに送信されたスケジューラー通知要求の数。

タイプ：long
