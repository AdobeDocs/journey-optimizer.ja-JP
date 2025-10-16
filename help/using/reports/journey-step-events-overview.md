---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーステップイベントの操作
description: Adobe Journey Optimizerでのジャーニーステップイベントの操作方法 – 概要、重要性、分析と最適化での使用方法を説明します
feature: Journeys, Reporting
topic: Content Management
role: Data Engineer, Data Architect, Admin, User
level: Intermediate, Experienced
keywords: ジャーニー，ステップイベント，分析，レポート，監視，XDM
hide: true
hidefromtoc: true
exl-id: 9f8e7d6c-5b4a-3928-1756-849302a11c2b
source-git-commit: df3abb7da17eb21e5e4120b55bdeb61fec3e202d
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 3%

---

# ジャーニーステップイベントの操作 {#work-with-journey-step-events}

ジャーニーステップイベントは、Adobe Journey Optimizerでのジャーニーの進行に伴うプロファイルの各ステップの詳細情報を取り込む、自動生成されたイベントです。 これらのイベントは、ジャーニーのパフォーマンスを包括的に可視化し、強力な分析機能を有効にします。

## ジャーニーステップイベントとは {#what-are-step-events}

ジャーニーステップイベントは、プロファイルがジャーニーのあるノードから別のノードに移動するたびに、Adobe Journey Optimizerが自動的に作成してAdobe Experience Platformに送信する、システム生成の XDM （エクスペリエンスデータモデル）イベントです。 各イベントは、顧客のジャーニーエクスペリエンスの特定のアクションまたはトランジションに対応します。

ジャーニーステップイベントには、主に次の 2 つのタイプがあります。

- **journeyStepEvent**：ジャーニーステップを通じた個人プロファイルの進行に関連するイベント
- **journeyStepProfileEvent**：追加のプロファイルコンテキスト情報を含むイベント

### ジャーニーステップイベントのトリガー {#event-triggers}

ジャーニーステップイベントは、様々なジャーニーアクティビティに対して自動的に生成されます。

- **エントリイベント**：プロファイルがジャーニーにエントリする場合
- **アクションの実行**：メッセージが送信されたとき、またはカスタムアクションが実行されたとき
- **条件評価**：プロファイルが決定ポイントを通過したとき
- **待機アクティビティ**：プロファイルが待機ノードに入って終了したとき
- **イベントを終了**：プロファイルがジャーニーを完了または終了したとき
- **エラー処理**：ジャーニーの実行中にエラーが発生した場合

>[!NOTE]
>
>ジャーニーステップイベントは、すべてのインスタンスでデフォルトで有効になっています。 ステップイベントのプロビジョニング時に作成されたスキーマやデータセットは、変更も更新もできません。これらのスキーマとデータセットは、読み取り専用モードです。

## ジャーニーステップイベントが重要な理由 {#why-step-events-matter}

ジャーニーステップイベントは、Adobe Journey Optimizerを使用する組織にとって重要な価値を提供します。

### リアルタイムの分析と監視 {#real-time-analytics}

- **ジャーニーパフォーマンストラッキング**: ジャーニー内でのプロファイルのフローをリアルタイムで監視します
- **コンバージョン分析**：ドロップオフポイントと成功したコンバージョンパスについて
- **エラー検出**：問題が発生した場合の特定とトラブルシューティング

### データ統合とインサイト {#data-integration}

- **クロスプラットフォーム分析**：ジャーニーデータを他のAdobe Experience Platform データソースと組み合わせます
- **Customer 360 表示**：ジャーニーインタラクションを含む包括的な顧客プロファイルを作成します
- **アトリビューションモデリング**：ジャーニータッチポイントをダウンストリームのビジネスアウトカムに接続する

### 最適化の機会 {#optimization}

- **A/B テストインサイト**：様々なジャーニーパスのパフォーマンスを分析します
- **Personalizationの機能強化**：ジャーニー行動データを使用して、今後のエクスペリエンスを向上させます
- **運用効率**：ボトルネックを特定し、ジャーニーの設計を最適化

## ジャーニーステップイベントの使用方法 {#how-to-use-step-events}

### ジャーニーステップイベントデータへのアクセス {#accessing-data}

ジャーニーステップイベントデータはAdobe Experience Platformに自動的に保存され、以下の方法でアクセスできます。

1. **データレイクのクエリ**:SQL を使用して、`journey_step_events` データセットをクエリします
2. **Customer Journey Analytics**：高度な分析ツールを使用してジャーニーデータを分析します
3. **リアルタイムレポート**:Journey Optimizerのビルトインレポート機能を使用して、データにアクセスします
4. **API**：カスタムアプリケーションのイベントデータへのプログラムによるアクセス

### 使用可能な主要なデータポイント {#key-data-points}

ジャーニーステップイベントでは、次のような包括的な情報を取り込むことができます。

- **ジャーニー ID**: ジャーニー ID、バージョン、および名前
- **プロファイル情報**：プロファイル ID および関連する ID
- **ステップの詳細**：ノード名、ステップタイプおよび実行ステータス
- **タイムスタンプ**：各ジャーニーステップの正確なタイミング
- **アクションの結果**：成功/失敗のステータスと実行の詳細
- **エラー情報**：問題が発生した場合の詳細なエラーコードと説明

### よくあるユースケース {#common-use-cases}

**パフォーマンス監視**

```sql
-- Example: Count profiles entering a journey in the last 24 hours
SELECT count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events 
WHERE _experience.journeyOrchestration.stepEvents.journeyVersionID = '<journey-id>'
AND _experience.journeyOrchestration.stepEvents.nodeType='start'
AND DATE(timestamp) > (now() - interval '24' hour);
```

**エラー分析**

```sql
-- Example: Identify errors by journey node
SELECT _experience.journeyOrchestration.stepEvents.nodeName,
       count(distinct _experience.journeyOrchestration.stepEvents.profileID)
FROM journey_step_events
WHERE _experience.journeyOrchestration.stepEvents.actionExecutionError IS NOT NULL
GROUP BY _experience.journeyOrchestration.stepEvents.nodeName;
```

**ジャーニーfunnel分析**

- ジャーニーステップごとのコンバージョン率の追跡
- プロファイルが最も頻繁にジャーニーから離脱する場所を特定します
- 様々なジャーニーフェーズでの滞在時間の測定

## サンプルとリソース {#samples-resources}

### クエリの例とテンプレート {#query-examples}

一般的なジャーニーステップイベント分析の包括的なクエリ例を確認します。

- **[ジャーニーステップイベントクエリの例](query-examples.md)**：一般的な分析シナリオですぐに使用できる SQL クエリ
- **[データセットクエリサンプル](../data/datasets-query-examples.md#journey-step-event)**：ジャーニーステップイベントデータセットのクエリ例
- **[プロファイルベースのクエリ](query-examples.md#profile-based-queries)**：個々のプロファイルジャーニーとインタラクションを追跡します

### フィールド文書 {#field-documentation}

ジャーニーステップイベントの完全なデータ構造を理解します。

- **[ジャーニーステップイベントフィールドのリスト](sharing-field-list.md)**：使用可能なすべてのフィールドの包括的なリファレンス
- **[共通フィールド](sharing-common-fields.md)**:journeyStepEvent と journeyStepProfileEvent 全体で共有されたフィールド
- **[アクション実行フィールド](sharing-execution-fields.md)**：アクション実行トラッキングに固有のフィールド
- **[ジャーニーフィールド](sharing-journey-fields.md)**:ジャーニー固有のメタデータと識別子

### ベストプラクティスとトラブルシューティング {#best-practices}

**パフォーマンスの最適化**

- クエリパフォーマンスを向上させるには、`journeyVersionID` の代わりに `journeyVersionName` を使用します
- 日付範囲でフィルタリングすると、大きなデータセットに対するクエリの速度が向上します
- ジャーニーの名前空間設定に一致するプロファイル ID の活用

**データ品質**

- データの問題を特定するために [ 破棄されたイベント ](sharing-field-list.md#discarded-events) を定期的に監視する
- イベントスキーマが分析要件に一致することの検証
- カスタムクエリに適切なエラー処理を実装

**Analytics 戦略**

- ジャーニーステップイベントとメッセージフィードバックデータを組み合わせて、完全なアトリビューションを実現
- 時間ベースの分析を使用したジャーニーの速度とボトルネックの把握
- コホート分析を作成して様々なジャーニーバリエーションを比較

### 高度な分析機能 {#advanced-analytics}

**Customer Journey Analyticsの統合**
ジャーニーステップイベントは、Customer Journey Analyticsを使用して次の目的で分析できます。

- 高度なアトリビューションモデリング
- クロスチャネルジャーニービジュアライゼーション
- ジャーニー結果に関する予測分析

**リアルタイム判定**
ジャーニーステップイベントパターンを使用すると、次のことができます。

- トリガーのリアルタイムパーソナライゼーション
- 動的なジャーニーの最適化の実装
- コンテキストに基づく次に最適なアクションのレコメンデーションを有効にする

## その他のリソース {#additional-resources}

### ドキュメントリンク {#documentation-links}

- **[ジャーニーステップ共有の概要](sharing-overview.md)**: ジャーニーデータがAdobe Experience Platformにどのようにフローするかについて
- **[ビルトインスキーマディクショナリ ](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja)**：完全な XDM スキーマリファレンス
- **[Journey Optimizer レポート](report-gs-cja.md)**: Journey Optimizerのレポート機能の概要

### 統合ガイド {#integration-guides}

- **[Adobe Customer Journey Analytics](cja-ajo.md)**: CJAでJourney Optimizer データを分析しています
- **[データ管理](../data/export-datasets.md)**：ジャーニーデータのエクスポートと管理
- **[プライバシーとガバナンス](../privacy/audit-logs.md)**：ジャーニーイベントのデータガバナンスに関する考慮事項

ジャーニーステップイベントは、Adobe Journey Optimizerの advanced journey analytics の基盤となります。 これらのイベントを効果的に理解し活用することで、顧客の行動に関する深いインサイトを得て、ジャーニーのパフォーマンスを最適化し、顧客に合わせてよりパーソナライズされたエクスペリエンスを作成できます。
