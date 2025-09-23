---
solution: Journey Optimizer
product: journey optimizer
title: ステップイベントフィールドの一覧
description: ステップイベントフィールドの一覧
feature: Journeys, Reporting
topic: Content Management
role: Data Engineer, Data Architect, Admin
level: Experienced
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: 11b2141db8d0e6dd44987d5f7941430fbe3e48f8
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 53%

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

この Mixin には、プロファイルエクスポートジョブに対応するすべてのフィールドが含まれています。

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

eventTypes について詳しくは [ この節 ](#discarded-events) を参照してください。

## stepEvents {#stepevents-field}

このカテゴリには、元のステップイベントフィールドが含まれます。この[節](../reports/sharing-legacy-fields.md)を参照してください。


## ジャーニーステップイベントで破棄されたイベントタイプのトラブルシューティング  {#discarded-events}

`eventCode = 'discard'` を含むレコードに対してジャーニーステップイベントのクエリを実行すると、複数の eventTypes が発生する場合があります。

最も頻繁な破棄 `eventTypes` ードの定義、一般的な原因、トラブルシューティング手順を次に示します。

* EXTERNAL_KEY_COMPUTATION_ERROR: システムは、イベントデータから顧客の一意の識別子（外部キー）を計算できませんでした。
一般的な原因：イベントペイロードに顧客識別子（メール、顧客 ID など）が見つからないか、形式が正しくありません。
トラブルシューティング：必要な識別子についてイベント設定を確認し、イベントデータが完全で正しい形式であることを確認します。
* NO_INTERESTED_SEGMENTMEMBERSHIP_EVENT: セグメントの選定ジャーニーを受信しましたが、このセグメントに応答するジャーニーが設定されていません。
一般的な原因：ジャーニーでセグメントをトリガーとして使用していないこと、ジャーニーがドラフト/停止状態であること、セグメント ID が一致していないこと。
トラブルシューティング：少なくとも 1 つのジャーニーがライブで、セグメントに設定されていることを確認し、セグメント ID を検証します。
* ジャーニーインスタンス ID_NOT_CREATE: ユーザーのジャーニーインスタンスを作成できませんでした。
一般的な原因：重複イベント、大量のイベント、システムリソースの制約。
トラブルシューティング：重複排除の実装、トラフィックスパイクの回避、ジャーニー設計の最適化、永続的な場合はサポートにお問い合わせください。
* EVENT_WITH_NO_event: ジャーニーを受信しましたが、応答するアクティブなジャーニーが設定されていません。
一般的な原因：イベント名/ID の不一致、ジャーニーが公開されていない、間違ったサンドボックス/組織、テストモード/プロファイルの不一致。
トラブルシューティング：イベントとジャーニー設定の検証、ジャーニーステータスの確認、デバッグツールの使用。

一時停止したジャーニーで発生した破棄の場合：

* PAUSED_VERSION_VERSION: ジャーニーのエントリ時に発生したジャーニーを破棄します

* ジャーニー_IN_PAUSED_STATE: プロファイルがジャーニーにあるときに発生した処理を破棄します

これらのイベントの詳細とトラブルシューティング方法については、[ジャーニーの一時停止 ](../building-journeys/journey-pause.md#troubleshoot-profile-discards-in-paused-journeys) の節を参照してください。

## その他のリソース

* [ データセットクエリサンプル - ジャーニーステップイベント ](../data/datasets-query-examples.md#journey-step-event)。
* [ クエリの例 – イベントベースのクエリ ](query-examples.md#event-based-queries)。
* [ ビルトインスキーマディクショナリ ](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)

