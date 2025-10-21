---
solution: Journey Optimizer
product: journey optimizer
title: ステップイベントフィールドの一覧
description: ステップイベントフィールドの一覧
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: bdf857c010854b7f0f6ce4817012398e74a068d5
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 70%

---

# ステップイベントフィールドの一覧 {#sharing-field-list}

ステップイベントフィールドはカテゴリ別に整理されています。

* デバッグ情報フィールド
* ジャーニーフィールド
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
| namespace | 文字列 | このフィールドは、ジャーニーで使用されるプロファイルで参照される名前空間を記述します。例：Email、ECID |

## serviceEvents {#servicevents-field}

この Mixin には、プロファイルエクスポートジョブに対応するすべてのフィールドが含まれています。 これらのイベントは、**オーディエンスを読み取り** アクティビティごとに生成され、オーディエンスの書き出し操作（待機中、開始済み、完了、エラー）のライフサイクルを追跡します。 通常のステップイベントとは異なり、serviceEvents は個々のプロファイルではなく、オーディエンスを読み取りノード自体に結び付けられます。つまり、プロファイル ID が関連付けられていない可能性があります。

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

このカテゴリには、元のステップイベントフィールドが含まれます。この[節](../reports/sharing-legacy-fields.md)を参照してください。


## ジャーニーステップイベントで破棄されたイベントタイプのトラブルシューティング  {#discarded-events}

`eventCode = 'discard'` を使用してレコードのジャーニーステップイベントのクエリを実行すると、複数の eventTypes が発生する場合があります。

最も頻繁に破棄される `eventTypes` の定義、一般的な原因およびトラブルシューティング手順を以下に示します。

* **EXTERNAL_KEY_COMPUTATION_ERROR**：システムでは、イベントデータから顧客の一意の ID（外部キー）を計算できませんでした。

  **一般的な原因**：イベントペイロードに顧客識別子（メール、顧客 ID など）が見つからないか、形式が正しくありません。

  **トラブルシューティング**：必要な識別子についてイベント設定を確認し、イベントデータが完全で正しい形式であることを確認します。

* **NO_INTERESTED_JOURNEYS_FOR_SEGMENTMEMBERSHIP_EVENT**：セグメントの選定イベントを受信しましたが、このセグメントに応答するジャーニーが設定されていません。

  **一般的な原因**：ジャーニーでセグメントをトリガーとして使用していないこと、ジャーニーがドラフト/停止状態であること、またはセグメント ID が一致していないこと。

  **トラブルシューティング**：少なくとも 1 つのジャーニーがライブであり、セグメントに対して設定されていることを確認し、セグメント ID を検証します。

* **JOURNEY_INSTANCE_ID_NOT_CREATE**：システムでは、顧客のジャーニーインスタンスを作成できませんでした。

  **一般的な原因**：重複イベント、大量のイベント、システムリソースの制約。

  **トラブルシューティング**：重複排除の実装、トラフィックスパイクの回避、ジャーニー設計の最適化を行い、解決しない場合はサポートにお問い合わせください。

* **EVENT_WITH_NO_EVENT**：イベントを受信しましたが、ジャーニーに応答するアクティブなジャーニーが設定されていません

  **一般的な原因**：イベント名/ID の不一致、ジャーニーが公開されていない、間違ったサンドボックス/組織、テストモード/プロファイルの不一致。

  **トラブルシューティング**：イベントとジャーニー設定の検証、ジャーニーのステータスの確認、デバッグツールの使用。

* 一時停止したジャーニーで発生した破棄の場合：

   * **PAUSED_JOURNEY_VERSION**：ジャーニーのエントリ時に発生した破棄
   * **JOURNEY_IN_PAUSED_STATE**：プロファイルがジャーニー内にある際に発生した破棄

  これらのイベントとトラブルシューティング方法について詳しくは、[ジャーニーの一時停止の節](../building-journeys/journey-pause.md#troubleshoot-profile-discards-in-paused-journeys)を参照してください。

## その他のリソース

* [データセットクエリサンプル - ジャーニーステップイベント](../data/datasets-query-examples.md#journey-step-event)。
* [クエリの例 - イベントベースのクエリ](query-examples.md#event-based-queries)。
* [ビルトインスキーマ辞書](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)

