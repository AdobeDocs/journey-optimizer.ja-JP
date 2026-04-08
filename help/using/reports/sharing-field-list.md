---
solution: Journey Optimizer
product: journey optimizer
title: ステップイベントフィールドのリスト
description: ステップイベントフィールドのリスト
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: c6e38d43a682c10bbb7ceb075a0f4b72d75c62a4
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 83%

---

# ステップイベントフィールドのリスト {#sharing-field-list}

ステップイベントフィールドはカテゴリ別に整理されています。

* デバッグ情報フィールド
* ジャーニーのフィールド
* プロファイルフィールド
* サービスイベントフィールド

identityMap 属性の場合、プライマリ ID はデフォルトで「primary = true」として定義されます。

## debugInfo {#debuginfo-field}

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| requestId | 文字列 | リクエストのフローをトラックするために Journey Optimizer で使用されるリクエスト ID です。 |

## journey {#journey-field}

このフィールドグループは、ジャーニーのスキーマで（journeyStepEvent と関連して）使用します。次のフィールドが含まれています。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | 指定されたジャーニーの識別子 |
| VersionID | 文字列 | ジャーニーバージョンの ID。この ID はジャーニーの ID を表します。 |
| name | 文字列 | ジャーニーの名前 |
| description | 文字列 | ジャーニーの説明 |
| version | 文字列 | バージョン（`major`.`minor` のように表されます） |

## profile {#profile-field}

このフィールドグループは、journeyStepEvent に固有です。このイベントはジャーニーと関連しており、identityMap を持たず、存在する場合はプロファイル ID を示しています。

journeyStepEvent の場合、ID に関連するフィールドも追加する必要があります。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | プロファイル識別子は、ジャーニーで送信／使用されたプロファイルを識別します。例：foo@adobe.com |
| 名前空間 | 文字列 | このフィールドは、ジャーニーで使用されるプロファイルで参照される名前空間を記述します。例：Email、ECID |

## serviceEvents {#servicevents-field}

この Mixin には、プロファイルエクスポートジョブに対応するすべてのフィールドが含まれています。これらのイベントは、**オーディエンスを読み取り**&#x200B;アクティビティごとに生成され、オーディエンスの書き出し操作のライフサイクル（キューに追加、開始、終了、エラー）を追跡します。通常のステップイベントとは異なり、serviceEvents は個々のプロファイルではなく、オーディエンスを読み取りノード自体に関連付けられているので、関連付けられたプロファイル識別子がない場合があります。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | トリガーされたオーディエンスエクスポートジョブの識別子 |
| status | 文字列 | オーディエンスエクスポートジョブのステータス：待機中、開始済み、完了済み |
| exportCountTotal | 整数 | オーディエンスエクスポートジョブの可能な最大値 |
| exportCountRealized | 整数 | ジョブを通じてエクスポートされたオーディエンスの実際の数 |
| exportCountFailed | 整数 | ジョブを通じたエクスポート中に失敗したオーディエンスの数 |
| exportSegmentID | 文字列 | エクスポートするオーディエンスの識別子 |
| eventType | 文字列 | エラーイベントか情報イベントかを示すイベントタイプ：Info、Error |
| eventCode | 文字列 | 対応する eventType の理由を示すエラーコード |

eventTypes について詳しくは、[この節](#discarded-events)を参照してください。

## stepEvents {#stepevents-field}

このカテゴリには、元のステップイベントフィールドが含まれます。詳しくは、この[節](../reports/sharing-legacy-fields.md)を参照してください。


## ジャーニーステップイベントで破棄されたイベントタイプのトラブルシューティング  {#discarded-events}

`eventCode = 'discard'` を使用してレコードのジャーニーステップイベントのクエリを実行すると、複数の eventTypes が発生する場合があります。

最も頻繁に破棄される `eventTypes` の定義、一般的な原因およびトラブルシューティング手順を以下に示します。

* **EXTERNAL_KEY_COMPUTATION_ERROR**：システムでは、イベントデータから顧客の一意の ID（外部キー）を計算できませんでした。

  **一般的な原因**：イベントペイロード内の顧客識別子（メール、顧客 ID など）が欠落しているか、形式が正しくありません。

  **トラブルシューティング**：必要な識別子のイベント設定を確認し、イベントデータが完全で正しい形式であることを確認します。

* **NO_INTERESTED_JOURNEYS_FOR_SEGMENTMEMBERSHIP_EVENT**：セグメントの選定イベントを受信しましたが、このセグメントに応答するジャーニーが設定されていません。

  **一般的な原因**：セグメントをトリガーとして使用するジャーニーがないか、ジャーニーがドラフト／停止状態であるか、セグメント ID が一致しません。

  **トラブルシューティング**：1 つ以上のジャーニーがライブで、セグメントに対して設定されていることを確認し、セグメント ID を検証します。

* **JOURNEY_INSTANCE_ID_NOT_CREATE**：システムでは、顧客のジャーニーインスタンスを作成できませんでした。

  **一般的な原因**：重複イベント、大量のイベント、システムリソースの制限。

  **トラブルシューティング**：重複排除の実装、トラフィックの急増の回避、ジャーニー設計の最適化、永続的な場合は[ サポート ](../start/user-interface.md#support-ticket-guidelines)にお問い合わせください。

* **maxInstanceStackEventsReached**: ジャーニーランタイムは、特定のジャーニーバージョンのプロファイルごとのイベントスタックの内部制限である10 イベントに達しました。

  **共通の原因**: プロファイルのジャーニーインスタンスは、長時間実行している手順（長い待機、低速なエンリッチメント、カスタムアクションの再試行など）でブロックされ、同じプロファイルのイベントが、そのジャーニーでも使用され、10 イベントの制限を超えて積み重ねられます。

  **トラブルシューティング**：頻繁にトリガーを繰り返したり、アップストリームイベントをデバウンスまたは重複排除したり、長いシナリオを複数のジャーニーに分割したりできるパスで、長時間実行されるステップを減らします。 これは安全ガードレールであり、制限は設定できません。スタックがドレインするまで、追加のイベントは破棄されます。 詳しくは、「[ ジャーニーインスタンスがブロックされたために破棄されたイベント ](../building-journeys/troubleshooting-execution.md#max-instance-stack-events-reached)」を参照してください。

* **EVENT_WITH_NO_JOURNEY**：イベントを受信しましたが、応答するアクティブなジャーニーが設定されていません

  **一般的な原因**：イベント名／ID の不一致、ジャーニーが公開されていない、間違ったサンドボックス／組織、テストモード／プロファイルの不一致。

  **トラブルシューティング**：イベントとジャーニーの設定を検証し、ジャーニーステータスを確認し、デバッグツールを使用します。

* 一時停止したジャーニーで発生した破棄の場合：

   * **PAUSED_JOURNEY_VERSION**：ジャーニーのエントリ時に発生した破棄
   * **JOURNEY_IN_PAUSED_STATE**：プロファイルがジャーニー内にある際に発生した破棄

  これらのイベントとトラブルシューティング方法について詳しくは、[ジャーニーの一時停止の節](../building-journeys/journey-pause.md#discards-troubleshoot)を参照してください。

## その他のリソース

* [データセットクエリサンプル - ジャーニーステップイベント](../data/datasets-query-examples.md#journey-step-event)。
* [クエリの例 - イベントベースのクエリ](query-examples.md#event-based-queries)。
* [ビルトインスキーマ辞書](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)

