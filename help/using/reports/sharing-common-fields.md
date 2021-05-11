---
title: journeystepsイベント共通フィールド
description: journeystepsイベント共通フィールド
translation-type: tm+mt
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# journeystepsイベント共通フィールド{#sharing-common-fields}

![](../assets/do-not-localize/badge.png)

このミックスインは、jearnyStepEventとjearnyStepProfileEventで共有されます。

[!DNL Journey Optimizer]がAdobe Experience Platformに送る一般的なXDMフィールドです。 共通フィールドは、ジャーニーで処理される各ステップに対して送信されます。 カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

これらのフィールドの一部は、特定の処理パターン（アクションの実行、データの取得など）でのみ使用できます。 イベントのサイズを制限するために、

## 入り口

ユーザーがジャーニーを入力したかどうかを示します。 存在しない場合、値はfalseとみなします。

タイプ：ブール型

値：true/false

## 再入場

ユーザーが同じインスタンスでジャーニーを再入力したかどうかを示します。 存在しない場合、値はfalseとみなします。

タイプ：ブール型

値：true/false

## instanceEnded

インスタンスが終了したかどうかを示します（成功したかどうか）。

タイプ：ブール型

## eventID

処理中のイベントID（ステップ処理用）。 イベントが外部イベントの場合、値はeventIdです。 イベントが内部イベントの場合、値は内部eventId（scheduledNotificationReceived、executedActionなど）です。

型：文字列

## nodeID

（キャンバスからの）クライアントノードID。

型：文字列

## stepID

現在処理中のステップを表す一意のIDです。

型：文字列

## stepName

現在処理中のステップの名前。

型：文字列

## stepType

ステップのタイプ。

型：文字列

可能な値：

* 条件
* アクション
* スケジューラー
* タイマー

## stepStatus

処理が完了した場合(およびステップイベントが起動した場合)のステータスを表すステップのステータス。

型：文字列

ステータスは次のとおりです。

* 終了：ステップにトランジションがなく、その処理は正常に終了しました。
* エラー：ステップ処理でエラーが発生しました。
* トランジション:ステップは、別のステップへのトランジションのイベントを待っています。
* capped:操作またはエンリッチメント中に発生したキャッピングエラーで、ステップが失敗しました。
* timedout:タイムアウトエラーが発生した場合にステップが失敗し、アクションまたはエンリッチメント中に発生しました。
* instanceTimedout:インスタンスがタイムアウトに達したので、ステップの処理が停止しました。

## jurneryID

ジャーニーのID。

型：文字列

## jeurneyVersionID

ジャーニーバージョンのID。 このidは、jearnyStepEventの場合に、ジャーニーへのID参照を表します。

型：文字列

## jeurneyVersionName

ジャーニーバージョンの名前。

型：文字列

## jurneryVersion

ジャーニーのバージョン。

型：文字列

## instanceID

ジャーニーインスタンスの内部ID。

型：文字列

## externalKey

イベントから抽出された外部キーを処理します。

型：文字列

## parentStepID

インスタンス内の現在処理されているステップの親のステップID。

型：文字列

## parentStepName

現在のステップの親のステップ名。

型：文字列

## parentTransitionID

処理済みのステップにインスタンスを導いたトランジションのID。

型：文字列

## parentTransitionName

インスタンスを処理済みのステップに導いたトランジションの名前。

型：文字列

## inTest

このジャーニーがテストモードになっているかどうかを示します。

タイプ：ブール型

## processingTime

インスタンスステップが処理の開始から終了までの合計時間（ミリ秒）です。

タイプ：long

## instanceType

インスタンスタイプ（バッチまたは単一の場合）を示します。

型：文字列

値：バッチ/単一

## recurrenceIndex

ジャーニーがバッチおよび定期的な場合の繰り返しのインデックス（最初の実行はrecurrenceIndex = 1）。

タイプ：long

## isBatchToUnitary

この単一インスタンスがバッチインスタンスからトリガーされたかどうかを示します。

タイプ：ブール型

## batchExternalKey

バッチイベントの外部キー。

型：文字列

## batchInstanceID

これは、バッチインスタンスIDです。

型：文字列

## batchUnitaryBranchID

インスタンスがバッチインスタンスからトリガーされた場合は、単一のブランチID。

型：文字列
