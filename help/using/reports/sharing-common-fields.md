---
solution: Journey Optimizer
product: journey optimizer
title: journeysteps イベントコモンフィールド
description: journeysteps イベントコモンフィールド
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 42aec986-2352-456a-a725-7f1585ae01f8
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# journeysteps イベントコモンフィールド {#sharing-common-fields}

このフィールドグループは journeyStepEvent および journeyStepProfileEvent によって共有されます。

Adobe エクスペリエンスプラットフォームに送信される [!DNL Journey Optimizer] 一般的な XDM のフィールドを次に示します。 1つのステップで処理される一般的なフィールドが送信されます。 カスタムアクションおよび enrichments については、より具体的なフィールドを使用することができます。

一部のフィールドは特定の処理パターンでのみ使用できます (アクションの実行、データのフェッチなど)。 を指定すると、イベントのサイズが制限されます。

## アピール {#entrance-field}

ユーザーが旅に出たかどうかを示します。 この値が指定されていない場合は、値 false が返されます。

種類: ブール値

値: true/false

## 再入り口 {#reentrance-field}

ユーザーが同じインスタンスを使用して、旅を再度操作したかどうかを示します。 この値が指定されていない場合は、値 false が返されます。

種類: ブール値

値: true/false

## instanceEnded {#instance-ended-field}

インスタンスが終了 (成功または失敗) したかどうかを示します。

種類: ブール値

## Id {#eventid-field}

ステップ処理で使用するイベント id。 イベントが外部イベントの場合、値は eventId になります。 内部イベントの場合は、内部イベント Id (scheduledNotificationReceived、executedAction など) を指定します。

タイプ: string

## nodeID {#nodeid-field}

クライアントノード id (canvas)。

タイプ: string

## stepID {#stepdid-field}

現在処理されているステップの一意の id です。

タイプ: string

## stepName {#stepname-field}

現在処理されているステップの名前を指定します。

タイプ: string

## stepType {#steptype-field}

ステップの種類です。

タイプ: string

指定可能な値:

* 条件
* アクション
* 組む
* 時間

## stepStatus {#stepstatus-field}

ステップの状態で、ステップの状態、処理が終了した時点、ステップのイベントが発生したことを示します。

タイプ: string

状態は以下のようになります。

* 終了: ステップは遷移せず、処理が正常に終了しました。
* エラー: ステップ処理でエラーが発生しました。
* 遷移: ステップは、イベントが別のステップに遷移するのを待機しています。
* 上限: ステップは、アクションの実行中または enrichment 中に発生した、上限エラーに失敗しました。
* timedout: ステップがタイムアウトエラーに失敗しました。操作または enrichment の実行中に発生します。
* instanceTimedout: インスタンスがタイムアウトに達したので、ステップは処理を停止しました。

## journeyID {#journeyid-field}

旅の ID です。

タイプ: string

## journeyVersionID {#journeyversionid-field}

旅のバージョンの ID です。 この id は、journeyStepEvent を参照している場合の、旅への id リファレンスを表しています。

タイプ: string

## journeyVersionName {#journeyversionname-field}

旅のバージョンの名前を指定します。

タイプ: string

## journeyVersion {#journeyversion-field}

旅バージョンのバージョンです。

タイプ: string

## インスタンス {#instanceid-field}

旅インスタンスの内部 ID です。

タイプ: string

## externalKey {#externalkey-field}

外部キーがイベントから抽出され、それが処理されます。

タイプ: string

## parentStepID {#parenstepid-field}

インスタンス内の現在処理されているステップの親のステップ ID です。

タイプ: string

## parentStepName {#parentstepname-field}

現在のステップの親のステップ名。

タイプ: string

## Parentの遷移の Id {#parenttransitionid-field}

処理されたステップのインスタンスになる遷移の Id。

タイプ: string

## Parent遷移 Tionname {#parenttransitionname-field}

処理されたステップのインスタンスになる遷移の名前。

タイプ: string

## inTest {#intest-field}

この旅がテストモードになっているかどうかを示します。

種類: ブール値

## processingTime {#processingtime-field}

インスタンスステップの開始から処理の終わりまでの経過時間の合計 (ミリ秒) です。

タイプ: long

## Instance.instancetype {#instancetype-field}

バッチまたはユニタリの場合は、インスタンスの種類を示します。

タイプ: string

値: batch/ユニタリ

## recurrenceIndex {#recurrenceindex-field}

連続していない場合は、定期的なアイテムのインデックス (最初の実行が recurrenceIndex = 1)

タイプ: long

## isBatchToUnitary {#isbatchtounitary-field}

このユニタリインスタンスがバッチインスタンスからトリガーされたかどうかを示します。

種類: ブール値

## batchExternalKey {#batchexternalkey-field}

Batch イベントの外部キー。

タイプ: string

## batchInstanceID {#batchinstanceid-field}

これは、バッチインスタンス ID です。

タイプ: string

## batchUnitaryBranchID {#batchunitarybranchid-field}

インスタンスがバッチインスタンスからトリガーされている場合は、ユニタリブランチ ID です。

タイプ: string
