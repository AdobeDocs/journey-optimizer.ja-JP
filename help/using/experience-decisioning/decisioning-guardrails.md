---
title: 決定ガードレールと制限
description: 決定ガードレールと制限について説明します。
feature: Decisioning
role: User
level: Intermediate
exl-id: 73548973-ff8d-4d6c-b383-dd3679fa159a
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/oTljriepwffzR-LIAc2kWjTQx9Oj0QMgJpbghkSEsmY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee394c77b226dd35a9c27f4a02e3b8d7a997ccbd
workflow-type: tm+mt
source-wordcount: 314
ht-degree: 71%

---

# 決定ガードレールと制限 {#decisioning-guardrails}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;決定要求、項目、ポリシー、適格性ルール、ランキング式に関する決定に適用されるガードレールと制限を確認して、サポートされているしきい値内に収まる決定設定を設計できます。

>[!ENDSHADEBOX]

決定の最適な使用を確保するには、次のガードレールと制限に注意してください。

[!DNL Journey Optimizer] のガードレールと制限の完全なリストについて詳しくは、[この節](../start/guardrails.md)を参照してください。

## 決定リクエスト {#decision-requests}

| ガードレール | 上限 |
| ------- | ------- |
| エッジセグメント化を利用する決定ポリシーを使用したコードベースのエクスペリエンス API リクエスト | 1500 |
| エッジセグメント化を利用しない決定ポリシーを使用したコードベースのエクスペリエンス API リクエスト | 5,000 |
| Edge Decisioning リクエストあたりのサーフェス URI の最大数 | 30 |

## 決定項目 {#decision-items}

| ガードレール | 上限 |
| ------- | ------- |
| 決定項目合計 | 10K |
| 属性を含む最大アイテム数（1KB）、最大30個の属性 | 1KB |
| 頻度ルール – 決定項目ごとのキャッピングルールの最大数 | 10 |
| 決定項目あたりのAEM コンテンツフラグメントの最大数 | 5 |

## 項目コレクション {#item-collections}

| ガードレール | 上限 |
| ------- | ------- |
| 項目コレクション | 10K |
| コレクションごとの決定項目の合計 | 500 |

## 決定ポリシー {#decision-policy}

| ガードレール | 上限 |
| ------- | ------- |
| 決定ポリシーごとの選択戦略と手動項目の数 | 10 |
| 決定ポリシーごとに返される最大決定項目 | 30 |
| 電子メールごとの最大の決定ポリシー | 10 |

## 実施要件ルール {#eligibility-rules}

| ガードレール | 上限 |
| ------- | ------- |
| 決定ルールとランキング式の合計 | 10K の組み合わせ |
| ルールごとのプロファイル属性の最大数 | 25 |
| ルールごとのコンテキストデータ属性の最大数 | 30 |
| PQL ルールの最大サイズ | 15K（UTF-8） |
| ネストレベルの最大数 | 30 |

## ランキング式 {#ranking-formulas}

| ガードレール | 上限 |
| ------- | ------- |
| ランキング式 PQL の最大サイズ | 8K（UTF-8） |
| プロファイル属性の最大数 | 25 |
| コンテキストデータ属性の最大数 | 30 |
| ネストレベルの最大数 | 30 |

## その他 {#others}

| ガードレール | 上限 |
| ------- | ------- |
| アイテム カタログ スキーマごとのカスタム属性の数 | 100 |
| プレースメントの合計 | 1K |
| AI ランキングモデル | 5 |

## 設定 {#configurations}

決定がサポートする設定の合計数は、20,000 を超えることはできません。

合計設定数は、サンドボックス内に存在する[キャッピングルール](items.md#capping)の合計数です。
