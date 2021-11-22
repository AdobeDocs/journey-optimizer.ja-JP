---
title: ステップイベントフィールドリスト
description: ステップイベントフィールドリスト
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: f0c5b42984b76fee005fe0c0e10312d47f9d10e8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 26%

---

# ステップイベントフィールドリスト {#sharing-field-list}

ステップイベントのフィールドはカテゴリ別に整理されます。

* デバッグ情報フィールド
* ジャーニーのフィールド
* プロファイルフィールド
* サービスイベントフィールド

## debugInfo

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| requestId | 文字列 | リクエストのフローを追跡するためにJourney Orchestrationで使用されるリクエスト ID。 |

## ジャーニー

このフィールドグループは、ジャーニーのスキーマで（journeyStepEvent と関連して）使用します。次のフィールドが含まれます。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | 指定されたジャーニーの識別子 |
| VersionID | 文字列 | ジャーニーバージョンの ID。この ID は、ジャーニーの ID を表します |
| name | 文字列 | ジャーニーの名前 |
| description | 文字列 | ジャーニーの説明 |
| バージョン | 文字列 | バージョン： `major`.`minor` |

## profile

このフィールドグループは journeyStepEvent に固有です。このイベントはジャーニーに関連しており、identityMap を持たず、プロファイル id を記述しています（存在する場合）。

journeyStepEvent の場合、ID に関連するフィールドも追加する必要があります。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | プロファイル識別子は、ジャーニーで送信/使用されるプロファイルを識別します。 例：foo@adobe.com. |
| 名前空間 | 文字列 | このフィールドは、ジャーニーで使用されるプロファイルで参照される名前空間を説明します。 例：電子メール、ECID |

## serviceEvents

この mixin には、プロファイル書き出しジョブに対応するすべてのフィールドが含まれます。

| フィールド名 | タイプ | 説明 |
|---|---|------------|
| ID | 文字列 | トリガーされたセグメント書き出しジョブの識別子 |
| status | 文字列 | セグメント書き出しジョブのステータス：待機中，開始，完了 |
| exportCountTotal | 整数 | セグメント書き出しジョブの最大可能値 |
| exportCountRealized | 整数 | ジョブを通じてエクスポートされたセグメントの実際の数 |
| exportCountFailed | 整数 | ジョブを介した書き出し中に失敗したセグメントの数 |
| exportSegmentID | 文字列 | 書き出すセグメントの識別子 |
| eventType | 文字列 | 情報イベントのエラーイベントかどうかを示すイベントタイプ。情報、エラー |
| eventCode | 文字列 | 対応する eventType の理由を示すエラーコード |

## stepEvents

このカテゴリには、元のステップイベントフィールドが含まれます。 [この節](../reports/sharing-legacy-fields.md)を参照してください。
