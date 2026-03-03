---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: パーソナライゼーションエディターでサポートされる関数
description: 意思決定管理（Offer Decisioning）でオファーコンテンツをパーソナライズする際にサポートされるパーソナライゼーションエディター機能について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management
topic: Integrations
role: User
level: Intermediate
version: Journey Orchestration
exl-id: c4df41a2-d740-437c-acc3-957508c4a1c0
source-git-commit: c15bae97ea52243d65aa59fdd4e924dc4e1852d8
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 36%

---

# パーソナライゼーションエディターでサポートされる関数 {#personalization-editor-supported-functions}

意思決定管理では、**表示域を追加** や [ オファーコンテンツ ](add-representations.md) （画像、テキスト、オファー内のリンク）をパーソナライズする際に **パーソナライゼーションエディター** を使用します。

Offer Decisioning バックエンドは、コンテンツをパーソナライズする際に、パーソナライゼーションエディターで使用できる関数の **サブセット** のみをサポートします。 このページには、オファーコンテンツに対してエディターで安全に使用できるすべての関数が一覧表示されます。 各セクションを展開すると、サポートされる演算子、ヘルパー、関数が表示されます。

>[!NOTE]
>
>この関数リストは、**オファーコンテンツのパーソナライズのみ** （表示域）に適用されます。 決定ルールとランキング式は、異なるエディターを使用するので、このサブセットに限定されません。

## サポートされる関数のリスト {#supported-functions-list}

+++ 演算子

* 算術演算：`+` `-` `*` `/` `%`
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
| 小文字 | lowercase |
| 大文字 | uppercase |
| キャメルケース | camelCase |
| タイトルケース | titleCase |
| トリミング | trim |
| 左トリミング | leftTrim |
| 右トリミング | rightTrim |
| 空である | isEmpty |
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
| 類似 | 次に類似 |
| 次で始まる | startsWith |
| 次で始まらない | doesNotStartWith |
| 次で終わる | endsWith |
| 次で終わらない | doesNotEndWith |
| 次を含む | 次を含む |
| 次を含まない | doesNotContain |
| 次に等しい | 次と等しい |
| 次と等しくない | notEqualTo |
| 一致 | 一致する |
| 正規表現グループ | regexGroup |
| 文字列から数値へ | stringToNumber |
| 文字列を日付に | stringToDate |
| 日時に | toDateTime |
| 日時のみに | toDateTimeOnly |
| メールドメインを抽出 | extractEmailDomain |
| 電子メールユーザー名を抽出 | extractEmailUsername |
| 空でない | isNotEmpty |
| インデックス | indexOf |
| 最後のインデックス | lastIndexOf |
| 部分文字列 | substr |
| ブール値に | toBool |
| 文字列を整数に | string_to_integer |
| マスク | マスク |
| 形式の通貨を取得 | formatCurrency |
| 文字の Unicode 値の取得 | charCodeAt |
| 任意のテキストの Qr コードを取得 | qrCode |

+++

+++ 配列、リストおよびセットの関数

| 表示名 | 内部名 |
|--------------|---------------|
| 個別 | distinct |
| 次に含まれる | in |
| 次に含まれない | notIn |
| 交わり | 交わり |
| サブセット | subsetOf |
| スーパーセット | スーパーセットの |
| 次を含む | includes |
| 配列の最初の N 個を並べ替えて取得 | topN |
| 配列の最後の N 個を並べ替えて取得 | bottomN |
| 最初の項目 | ヘッド |
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
| 切り上げ | 切り上げ |
| 切り捨て | roundDown |
| 精度に | toPrecision |
| 絶対 | 絶対パス |
| ランダム | random |
| 16 進数へ | toHexString |
| ロケールに対応する数値を取得 | formatNumber |
| 文字列へ | toString |
| ToInt | toInt |
| To Long | toLong |

+++

+++ 日時関数

| 表示名 | 内部名 |
|--------------|---------------|
| Now | now |
| CurrentZonedDateTime を取得 | getCurrentZonedDateTime |
| 終了日 | toDate |
| 終了時間 | toTime |
| 日時に | toDateTime |
| 日時のみに | toDateTimeOnly |
| 終了日のみ | toDateOnly |
| 終了時間のみ | toTimeOnly |
| タイムゾーンへ | toTimeZone |
| 日付を書式設定 | formatDate |
| 日時をフォーマット | formatDateTime |
| 時間をフォーマット | formatTime |
| 日付を解析 | parseDate |
| 日時を解析 | parseDateTime |
| 解析時間 | parseTime |
| 日数を追加 | addDays |
| 月数を追加 | addMonths |
| 年数を追加 | addYeers |
| 時間数を追加 | addHours |
| 分数を追加 | addMinutes |
| 秒数を追加 | addSeconds |
| 日数を減算 | subtractDays |
| 月を減算 | subtractMonths |
| 年を減算 | subtractYears |
| 時間を減算 | subtractHours |
| 分を減算 | subtractMinutes |
| 秒を減算 | subtractSeconds |
| 日数差 | diffDays |
| 月数の違い | diffMonths |
| 年差 | diffYears |
| 時間差 | diffHours |
| 分単位の違い | diffMinutes |
| 秒単位の違い | diffSeconds |
| 1 日の始まり | startOfDay |
| 1 日の終わり | endOfDay |
| 次より前である | isBefore |
| 次の後である | isAfter |

+++

+++ URL 関数

| 表示名 | 内部名 |
|--------------|---------------|
| エンコード URL | encodeUrl |
| デコード URL | decodeUrl |
| URL クエリパラメーターを取得 | getUrlQueryParam |
| URL プロトコルを取得 | getUrlProtocol |
| URL ホストを取得 | getUrlHost |

+++

>[!NOTE]
>
>オファーコンテンツのパーソナライズ時に上記のリストにない関数を使用すると、実行時に式が失敗したり、予期しない結果が生じたりする可能性があります。 [!DNL Journey Optimizer] のパーソナライゼーションで使用できる関数の完全なセットについては、[ ヘルパー関数リスト ](../../personalization/functions/functions.md) を参照してください。 Offer Decisioningでのコンテンツのパーソナライズでは、このページに記載されているサブセットのみがサポートされます。
