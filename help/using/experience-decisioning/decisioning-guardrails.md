---
title: 意思決定のガードレールと制限
description: 意思決定のガードレールと制限について詳しく説明します。
feature: Decisioning
role: User
level: Intermediate
source-git-commit: b6c31528784c0c8576e3200e7611a6b6cd43d7a7
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 15%

---


# 意思決定のガードレールと制限 {#decisioning-guardrails}

意思決定の最適な使用を確保するには、次のガードレールと制限に注意してください。

[!DNL Journey Optimizer] のガードレールと制限の完全なリストについては、[ この節 ](../start/guardrails.md) を参照してください。

## 決定リクエスト

| ガードレール | 上限 |
| ------- | ------- |
| Edgeのセグメント化を利用した、意思決定ポリシーを伴うコードベースのエクスペリエンス API リクエスト | 1500 |
| Edgeのセグメント化を利用しない決定ポリシーを使用したコードベースのエクスペリエンス API リクエスト | 5,000 |

## 項目のコレクション

| ガードレール | 上限 |
| ------- | ------- |
| 項目コレクション | 10K |
| 品目コレクションごとの合計オファー品目 | 500 |

## 決定ポリシー

| ガードレール | 上限 |
| ------- | ------- |
| 決定ポリシーごとの選択戦略と手動項目の数 | 10 |
| 決定ポリシーごとに返されるオファー項目の最大数 | 30 |

## 実施要件ルール

| ガードレール | 上限 |
| ------- | ------- |
| 決定ルールとランキング式の合計 | 10,000 組み合わせ |
| ルールあたりのプロファイル属性の最大数 | 25 |
| ルールあたりのコンテキストデータ属性の最大数 | 30 |
| Pql ルールの最大サイズ | 15K （UTF-8） |
| ネストレベルの最大数 | 30 |

## ランキング式

| ガードレール | 上限 |
| ------- | ------- |
| ランキング式PQLの最大サイズ | 8K （UTF-8） |
| プロファイル属性の最大数 | 25 |
| コンテキストデータ属性の最大数 | 30 |
| ネストレベルの最大数 | 30 |

## その他

| ガードレール | 上限 |
| ------- | ------- |
| オファーカタログスキーマあたりのカスタム属性の数 | 100 |
| オファー項目総数 | 10K |
| Total Placements | 1K |
| AI ランキングモデル | 5 |
| 頻度ルール – オファーあたりのキャッピングルールの最大数 | 10 |
