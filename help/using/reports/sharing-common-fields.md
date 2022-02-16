---
title: journeySteps イベントの共通フィールド
description: journeySteps イベントの共通フィールド
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 42aec986-2352-456a-a725-7f1585ae01f8
source-git-commit: 6d744c0289e81ab2229f02c44ead43943b945b89
workflow-type: ht
source-wordcount: '582'
ht-degree: 100%

---

# journeySteps イベントの共通フィールド {#sharing-common-fields}

このフィールドグループは、journeyStepEvent と journeyStepProfileEvent が共有します。

[!DNL Journey Optimizer] が Adobe Experience Platform に送信する一般的な XDM フィールドです。共通フィールドは、ジャーニーで処理される各ステップに対して送信されます。カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

イベントのサイズを制限するため、これらのフィールドの一部は、特定の処理パターン（アクションの実行、データの取得など）でのみ使用できます。

## エントリ {#entrance-field}

ユーザーがジャーニーにエントリしたかどうかを示します。存在しない場合、値は false とみなします。

型：ブール型

値：true/false

## 再エントリ {#reentrance-field}

ユーザーが同じインスタンスでジャーニーに再度エントリしたかどうかを示します。存在しない場合、値は false とみなします。

型：ブール型

値：true/false

## instanceEnded {#instance-ended-field}

インスタンスが終了したかどうか（成功または失敗）を示します。

型：ブール型

## eventID {#eventid-field}

ステップ処理など、処理中のイベント ID。イベントが外部イベントの場合、値は eventId です。イベントが内部イベントの場合、値は内部 eventId（scheduledNotificationReceived、executedActionなど）です。

型：文字列

## nodeID {#nodeid-field}

（キャンバスから得られる）クライアントノード ID。

型：文字列

## stepID {#stepdid-field}

現在処理中のステップを表す一意の ID です。

型：文字列

## stepName {#stepname-field}

現在処理中のステップの名前。

型：文字列

## stepType {#steptype-field}

ステップのタイプ。

型：文字列

使用可能な値：

* 条件
* アクション
* スケジューラー
* タイマー

## stepStatus {#stepstatus-field}

処理が完了（およびステップイベントが実行された）ときの、ステップのステータス。

型：文字列

ステータスには次の種類があります。

* ended：ステップにトランジションがなく、正常に処理が終了しました。
* error：ステップ処理でエラーが発生しました。
* transitions：ステップは、別のステップへトランジションするイベントの待機中です。
* capped：操作またはエンリッチメント中にキャッピングエラーが発生し、ステップが失敗しました。
* timedout：ステップは、アクションまたはエンリッチメント中に発生したタイムアウトエラーで失敗しました。
* instanceTimedout：インスタンスがタイムアウトに到達したので、ステップの処理が停止しました。

## journeyID {#journeyid-field}

ジャーニー ID。

型：文字列

## journeyVersionID {#journeyversionid-field}

ジャーニーバージョンの ID。この ID は、journeyStepEvent においてジャーニーを参照する ID です。

型：文字列

## journeyVersionName {#journeyversionname-field}

ジャーニーバージョンの名前。

型：文字列

## journeyVersion {#journeyversion-field}

ジャーニーのバージョン。

型：文字列

## instanceID {#instanceid-field}

ジャーニーインスタンスの内部 ID。

型：文字列

## externalKey {#externalkey-field}

イベントから抽出された外部キーを処理します。

型：文字列

## parentStepID {#parenstepid-field}

インスタンス内で現在処理されているステップの親ステップ ID。

型：文字列

## parentStepName {#parentstepname-field}

現在のステップの親ステップ名。

型：文字列

## parentTransitionID {#parenttransitionid-field}

処理済みのステップにインスタンスを導いたトランジションの ID。

型：文字列

## parentTransitionName {#parenttransitionname-field}

インスタンスを処理済みのステップに導いたトランジションの名前。

型：文字列

## inTest {#intest-field}

このジャーニーがテストモードになっているかどうかを示します。

型：ブール型

## processingTime {#processingtime-field}

インスタンスステップのエントリから処理の終了までの合計時間（ミリ秒）です。

型：long

## instanceType {#instancetype-field}

インスタンスの種類（バッチまたは単一の場合）を示します。

型：文字列

値：バッチ／単一

## recurrenceIndex {#recurrenceindex-field}

ジャーニーがバッチおよび定期的な場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

型：long

## isBatchToUnitary {#isbatchtounitary-field}

この単一インスタンスがバッチインスタンスからトリガーされたかどうかを示します。

型：ブール型

## batchExternalKey {#batchexternalkey-field}

バッチイベントの外部キー。

型：文字列

## batchInstanceID {#batchinstanceid-field}

これは、バッチインスタンス ID です。

型：文字列

## batchUnitaryBranchID {#batchunitarybranchid-field}

インスタンスがバッチインスタンスからトリガーされた場合は、単一の分岐 ID。

型：文字列
