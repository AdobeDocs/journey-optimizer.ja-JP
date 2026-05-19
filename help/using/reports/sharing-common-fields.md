---
solution: Journey Optimizer
product: journey optimizer
title: journeySteps イベントの共通フィールド
description: journeySteps イベントの共通フィールド
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 42aec986-2352-456a-a725-7f1585ae01f8
TQID: https://experienceleague.adobe.com/MWcV6FkgtiFJd9Y7q8CvTXQsL68cD5JcvqjmoEyiYhI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2: id: fa683eda-48de-4558-af32-2673edcd44feid: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 634
ht-degree: 96%

---

# journeySteps イベントの共通フィールド {#sharing-common-fields}

このフィールドグループは、**journeyStepEvent** と **journeyStepProfileEvent** で共有されます。

[!DNL Journey Optimizer] が Adobe Experience Platform に送信する一般的な XDM フィールドです。 共通フィールドは、ジャーニーで処理される各ステップに対して送信されます。 カスタムアクションやカスタムエンリッチメントには、より具体的なフィールドが使用されます。

これらのフィールドの中には、特定の処理パターン（アクション実行、データ取得など）でのみ使用できるものもあります。 イベントのサイズを制限できます。


>[!NOTE]
>
>ジャーニーのプロパティ属性について詳しくは、[この節](../building-journeys/expression/journey-properties.md#journey-properties-fields)を参照してください。


## エントリ {#entrance-field}

ユーザーがジャーニーにエントリしたかどうかを示します。 存在しない場合、値は false とみなします。

型：ブール型

値：true または false

## 再エントリ {#reentrance-field}

ユーザーが同じインスタンスでジャーニーに再度エントリしたかどうかを示します。 存在しない場合、値は false とみなします。

型：ブール型

値：true または false

## instanceEnded {#instance-ended-field}

インスタンスが終了したかどうか（成功または失敗）を示します。

型：ブール型

## eventID {#eventid-field}

ステップ処理など、処理中のイベント ID。 イベントが外部イベントの場合、値は eventId です。 イベントが内部イベントの場合、値は内部 eventId（scheduledNotificationReceived、executedAction など）です。

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
* capped：アクションまたはエンリッチメント実行中にキャップエラーが発生し、ステップが失敗しました。
* timedout：ステップは、アクションまたはエンリッチメント中に発生したタイムアウトエラーで失敗しました。
* instanceTimedout：インスタンスがタイムアウトに到達したので、ステップの処理が停止しました。

## journeyID {#journeyid-field}

ジャーニー ID。

型：文字列

## journeyVersionID {#journeyversionid-field}

ジャーニーバージョンの ID。 この ID は、journeyStepEvent においてジャーニーを参照する ID です。

型：文字列

>[!NOTE]
>
>トラブルシューティングの目的では、ジャーニーのクエリ時に journeyVersionName ではなく journeyVersionID を使用することをお勧めします。

## journeyVersionName {#journeyversionname-field}

ジャーニーバージョンの名前。

型：文字列

>[!NOTE]
>
>トラブルシューティングの目的では、ジャーニーのクエリ時に journeyVersionName ではなく journeyVersionID を使用することをお勧めします。

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

## exitCriteriaID

exitCriteria の ID

型：文字列

## exitCriteriaName

exitCriteria の名前

型：文字列