---
solution: Journey Optimizer
product: journey optimizer
title: ステップイベントフィールドリスト
description: ステップイベントフィールドリスト
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: e96efa67-ee47-40b9-b680-f5119d8c3481
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# ステップイベントフィールドリスト {#sharing-field-list}

ステップイベントフィールドはカテゴリー別に整理されています。

* 「デバッグ情報」フィールド
* 「旅」フィールド
* プロファイルフィールド
* サービスイベントフィールド

## debugInfo {#debuginfo-field}

| フィールド名 | 入力 | つい |
|---|---|------------|
| Id | 値 | 要求のフローを追跡するために、旅オプティマイザーによって使用される要求 Id です。 |

## 旅 {#journey-field}

このフィールドグループは、journeyStepEvent と関連して、旅スキーマで使用されます。 このファイルには、次のフィールドが含まれています。

| フィールド名 | 入力 | つい |
|---|---|------------|
| コード | 値 | 指定された旅の識別子 |
| VersionID | 値 | 旅のバージョンの Id です。 この id は、旅の id を表します。 |
| 氏名 | 値 | 旅の名前 |
| つい | 値 | 旅について |
| バージョン | 値 | バージョン、として `major` 表示されます。`minor` |

## 薄型 {#profile-field}

このフィールドグループは journeyStepEvent に固有のものです。このイベントは、旅と関連しています。このイベントは、プロファイルに関する情報がある場合は、このイベントが記載されています。

JourneyStepEvent については、id に関連するフィールドも追加する必要があります。

| フィールド名 | 入力 | つい |
|---|---|------------|
| コード | 値 | プロファイル識別子は、旅に送られた、または使用されていたプロファイルを識別します。 例: foo@adobe.com |
| 名前 | 値 | このフィールドには、その過程で使用されるプロファイルによって参照される名前空間が記載されています。 例: 電子メール、その他 d |

## serviceEvents {#servicevents-field}

この mixin には、プロファイルの書き出しジョブに対応したすべてのフィールドが含まれています。

| フィールド名 | 入力 | つい |
|---|---|------------|
| コード | 値 | 開始されたセグメントのエクスポートジョブの識別子 |
| 現状 | 値 | セグメントのエクスポートジョブの状態: queued、開始、終了 |
| エクスポート回数の合計 | 整数 | セグメントのエクスポートジョブの有効な値の最大値 |
| exportCountRealized | 整数 | ジョブを通じて実際に書き出されたセグメントの数 |
| exportCountFailed 失敗しました | 整数 | ジョブを使用した書き出し中に失敗したセグメントの数 |
| exportSegmentID | 値 | 書き出すセグメントの識別子 |
| eventType | 値 | Info イベントによってエラーイベントが発生しているかどうかを示すイベントタイプ: Info、Error |
| eventCode | 値 | イベントに対応するイベントの原因を示すエラーコード |

## stepEvents {#stepevents-field}

このカテゴリーには、オリジナルの step イベントフィールドが含まれています。 この [ 項 ](../reports/sharing-legacy-fields.md) を参照してください。
