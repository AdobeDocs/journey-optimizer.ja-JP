---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: パーソナライゼーションエディターでサポートされる関数
description: 意思決定管理（Offer Decisioning）でオファーコンテンツをパーソナライズする際にサポートされるパーソナライゼーションエディター関数について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
version: Journey Orchestration
exl-id: c4df41a2-d740-437c-acc3-957508c4a1c0
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
product_v2: []
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 635
ht-degree: 37%

---

# パーソナライゼーションエディターでサポートされる関数 {#personalization-editor-supported-functions}

意思決定管理では、**パーソナライゼーションエディター**&#x200B;を使用して、[表示域](add-representations.md)を追加し、**オファーコンテンツ** （オファー内の画像、テキスト、リンク）をパーソナライズします。

Offer Decisioning バックエンドは、コンテンツのパーソナライズ時にパーソナライゼーションエディターで使用できる関数のうち&#x200B;**サブセット**&#x200B;のみをサポートします。 このページには、オファーコンテンツのエディターで安全に使用できるすべての関数が一覧表示されます。 各セクションを展開して、サポートされている演算子、ヘルパー、関数を確認します。

>[!NOTE]
>
>この関数リストは、**オファーのコンテンツのパーソナライズ** （表示域）にのみ適用されます。 決定ルールとランキング式では、異なるエディターを使用し、このサブセットに限定されません。

## サポートされている関数リスト {#supported-functions-list}

+++ 演算子

* 算術：`+` `-` `*` `/` `%`
* 論理：`and` `or` `!`
* 比較：`=` `!=` `>` `>=` `<` `<=`

+++

+++ ヘルパー

* Each
* With
* If
* Unless
* Let
* デフォルトのフォールバック値
* フラグメント
* datasetLookup
* externalDataLookup （Alpha）
* インライン
* Url
* 実行メタデータ
* valueAtPath

+++

+++ 文字列関数

| 表示名 | 内部名 |
|--------------|---------------|
| 小文字 | lowerCase |
| 大文字 | upperCase |
| キャメルケース | camelCase |
| 単語の先頭のみ大文字 | titleCase |
| トリミング | trim |
| 左トリミング | leftTrim |
| 右トリミング | rightTrim |
| が空です | isEmpty |
| 等しい (大文字と小文字を区別しない) | equalsIgnoreCase |
| 等しくない (大文字と小文字を区別しない) | notEqualWithIgnoreCase |
| 置換 | replace |
| すべて置換 | replaceAll |
| 連結 | concat |
| 分割 | split |
| Encode64 | encode64 |
| 長さ | length |
| MD5 | md5 |
| SHA256 | sha256 |
| 次に類似 | いいね！ |
| 次で始まる | startsWith |
| 次で始まらない | doesNotStartWith |
| 次で終わる | endsWith |
| 次で終わらない | doesNotEndWith |
| 次を含む | 含む |
| 次を含まない | doesNotContain |
| 次に等しい | 次と等しい |
| 次と等しくない | notEqualTo |
| 一致 | 一致 |
| 正規表現グループ | regexGroup |
| 文字列から数値へ | stringToNumber |
| 文字列を日付に | stringToDate |
| 日時に | toDateTime |
| 日時のみに | toDateTimeOnly |
| メールドメインの抽出 | extractEmailDomain |
| メールのユーザー名を抽出 | extractEmailUsername |
| 空でない | isNotEmpty |
| インデックス | indexOf |
| 最後のインデックス | lastIndexOf |
| 部分文字列 | substr |
| ブール値に | toBool |
| 文字列を整数に | string_to_integer |
| マスク | マスク |
| 形式の通貨を取得 | formatCurrency |
| 文字のUnicode値を取得 | charCodeAt |
| 任意のテキストのQr コードを取得 | qrCode |

+++

+++ 配列、リスト関数およびセット関数

| 表示名 | 内部名 |
|--------------|---------------|
| 個別 | distinct |
| 次に含まれる | in |
| 次に含まれない | notIn |
| 交わり | 積集合 |
| サブセット | subsetOf |
| スーパーセット | スーパーセットの |
| 次を含む | 含む |
| 配列の最初の N 個を並べ替えて取得 | topN |
| 配列の最後の N 個を並べ替えて取得 | bottomN |
| 最初の項目 | head |
| カウント | count |
| 合計 | sum |
| 平均 | 平均 |
| 最小 | min |
| 最大 | max |

+++

+++ マップ関数

| 表示名 | 内部名 |
|--------------|---------------|
| 取得 | get |
| キー | キー |
| 値 | 値 |

+++

+++ オブジェクト関数

| 表示名 | 内部名 |
|--------------|---------------|
| null である | isNull |
| null でない | isNotNull |

+++

+++ 数学関数

| 表示名 | 内部名 |
|--------------|---------------|
| パーセンテージに | toPercentage |
| 切り上げ | roundUp |
| 切り捨て | roundDown |
| 精度に | toPrecision |
| 絶対 | 絶対 |
| ランダム | random |
| 16進数 | toHexString |
| ロケールへの数値の取得 | formatNumber |
| 文字列へ | toString |
| ToInt | toInt |
| 長い | toLong |

+++

+++ 日付時刻関数

| 表示名 | 内部名 |
|--------------|---------------|
| Now | now |
| CurrentZonedDateTime を取得 | getCurrentZonedDateTime |
| 終了日 | toDate |
| 時間 | toTime |
| 日時に | toDateTime |
| 日時のみに | toDateTimeOnly |
| 日付のみ | toDateOnly |
| 期間のみ | toTimeOnly |
| タイムゾーンへ | toTimeZone |
| 日付を書式設定 | formatDate |
| 日付時刻の書式設定 | formatDateTime |
| 時間の書式設定 | formatTime |
| 解析日 | parseDate |
| パース日時 | parseDateTime |
| パース時間 | parseTime |
| 日数を追加 | addDays |
| 月数を追加 | addMonths |
| 年数を追加 | addYears |
| 時間数を追加 | addHours |
| 分数を追加 | addMinutes |
| 秒数を追加 | addSeconds |
| 日数を減算 | subtractDays |
| 月を減算 | subtractMonths |
| 年数を減算 | subtractYears |
| 時間を減算 | subtractHours |
| 減算（分） | subtractMinutes |
| 秒減算 | subtractSeconds |
| 日数の違い | diffDays |
| 月の違い | diffMonths |
| 年数の違い | diffYears |
| 時間の違い | diffHours |
| 分数の違い | diffMinutes |
| 秒単位の違い | diffSeconds |
| 1日の始まり | startOfDay |
| 終了日 | endOfDay |
| 次より前 | isBefore |
| 次より後 | isAfter |

+++

+++ URL関数

| 表示名 | 内部名 |
|--------------|---------------|
| URLをエンコード | encodeUrl |
| URLをデコード | decodeUrl |
| URL クエリパラメーターを取得 | getUrlQueryParam |
| URL プロトコルを取得 | getUrlProtocol |
| URL ホストを取得 | getUrlHost |

+++

>[!NOTE]
>
>オファーコンテンツをパーソナライズする際に、上記のリストにない関数を使用すると、実行時に式が失敗したり、予期しない結果が発生したりする可能性があります。 [!DNL Journey Optimizer]のパーソナライゼーションで使用できる関数の完全なセットについては、[ ヘルパー関数のリスト ](../../personalization/functions/functions.md)を参照してください。 このページに記載されているサブセットのみが、Offer Decisioningでのコンテンツのパーソナライズでサポートされています。
