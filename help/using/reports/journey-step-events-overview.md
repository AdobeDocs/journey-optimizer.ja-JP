---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーステップイベントの操作
description: Adobe Journey Optimizer でのジャーニーステップイベントの操作方法と、概要、重要な理由、分析と最適化での使用方法について説明します。
feature: Journeys, Reporting
role: Developer, Admin, User
level: Intermediate, Experienced
keywords: ジャーニー, ステップイベント, 分析, レポート, 監視, XDM
source-git-commit: 17e0528849f2bd4d3cbf279c34c98a8359cad797
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 99%

---

# ジャーニーステップイベントの操作 {#work-with-journey-step-events}

ジャーニーステップイベントは、Adobe Journey Optimizer での[ジャーニー](../building-journeys/journey.md)の進行状況に合わせて[プロファイル](../audience/get-started-profiles.md)が実行する各ステップに関する詳細情報をキャプチャする、自動的に生成されたイベントです。これらのイベントにより、[ジャーニーのパフォーマンス](../building-journeys/report-journey.md)を包括的に表示でき、強力な分析機能が有効になります。

## ジャーニーステップイベントとは {#what-are-step-events}

ジャーニーステップイベントは、システムにより生成される [XDM（エクスペリエンスデータモデル）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}イベントです。ジャーニー内でプロファイルがノード間を移動するたびに、Adobe Journey Optimizer により自動的に作成され、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} に送信されます。各イベントは、顧客のジャーニーエクスペリエンスでの特定の[ジャーニーアクティビティ](../building-journeys/about-journey-activities.md)やトランジションに対応します。

ジャーニーステップイベントには、主に次の 2 つのタイプがあります。

- **journeyStepEvent**：ジャーニーステップを通じた個人プロファイルの進行状況に関連するイベント
- **journeyStepProfileEvent**：追加のプロファイルコンテキスト情報を含むイベント

### ジャーニーステップイベントをトリガーする内容 {#event-triggers}

ジャーニーステップイベントは、次の様々なジャーニーアクティビティに対して自動的に生成されます。

- **エントリイベント**：プロファイルが[ジャーニーにエントリ](../building-journeys/entry-management.md)する場合
- **アクション実行**：[メッセージが送信](../building-journeys/journeys-message.md)される場合や、[カスタムアクション](../building-journeys/using-custom-actions.md)が実行される場合
- **条件評価**：プロファイルが[条件](../building-journeys/condition-activity.md)と決定ポイントを通過する場合
- **待機アクティビティ**：プロファイルが[待機ノード](../building-journeys/wait-activity.md)にエントリおよび終了する場合
- **終了イベント**：プロファイルが[ジャーニーを完了または終了](../building-journeys/end-journey.md)する場合
- **エラー処理**：ジャーニー実行中にエラーが発生する場合

>[!NOTE]
>
>ジャーニーステップイベントは、すべてのインスタンスでデフォルトでアクティブ化されます。ステップイベントのプロビジョニング時に作成された[スキーマやデータセット](sharing-overview.md)は、変更も更新もできません。これらのスキーマとデータセットは読み取り専用モードです。

詳しくは、[ジャーニーステップイベントスキーマ](sharing-field-list.md)を参照してください。

## ジャーニーステップイベントが重要な理由 {#why-step-events-matter}

ジャーニーステップイベントは、Adobe Journey Optimizer を使用する組織に対して次の重要な価値を提供します。

### リアルタイムの分析と監視 {#real-time-analytics}

- **ジャーニーのパフォーマンストラッキング**：[ライブレポート](live-report.md)を使用して、プロファイルがジャーニーを通じてフローする仕組みをリアルタイムで監視します。
- **コンバージョン分析**：[ジャーニー分析](journey-global-report-cja.md)を使用して、離脱ポイントと成功したコンバージョンパスを理解します
- **エラー検出**：[監視とアラート](alerts.md)を通じて発生した問題を特定し、トラブルシューティングします

### データ統合とインサイト {#data-integration}

- **クロスプラットフォーム分析**：ジャーニーデータを他の [Adobe Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)と組み合わせます
- **360 度の顧客表示**：ジャーニーのインタラクションを含む包括的な[顧客プロファイル](../audience/get-started-profiles.md)を作成します。
- **アトリビューションモデリング**：[Customer Journey Analytics](cja-ajo.md) を使用して、ジャーニーのタッチポイントをダウンストリームのビジネス成果に結び付けます

### 最適化の機会 {#optimization}

- **A/B テストのインサイト**：[実験](campaign-global-report-cja-experimentation.md)を使用して、様々なジャーニーパスのパフォーマンスを分析します
- **パーソナライゼーションの機能強化**：ジャーニー行動データを使用して、[動的コンテンツ](../personalization/dynamic-content.md)による今後のエクスペリエンスを向上させます。
- **運用効率**：ボトルネックを特定し、[ジャーニーのデザイン](../building-journeys/using-the-journey-designer.md)を最適化します

## ジャーニーステップイベントの使用方法 {#how-to-use-step-events}

### ジャーニーステップイベントデータへのアクセス {#accessing-data}

ジャーニーステップイベントデータは Adobe Experience Platform に自動的に保存され、次を通じてアクセスできます。

1. **データレイククエリ**：SQL を使用して、[クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja){target="_blank"}で `journey_step_events` データセットのクエリを実行します
2. **Customer Journey Analytics**：[高度な分析ツール](cja-ajo.md)を通じてジャーニーデータを分析します。
3. **リアルタイムのレポート**：Journey Optimizer の[ビルトインレポート機能](gs-reports.md)を通じてデータにアクセスします
4. **API**：カスタムアプリケーションのイベントデータにプログラムでアクセスします

詳しくは、[データセットへのアクセス](../data/datasets-query-examples.md)を参照してください。

### 使用可能な主なデータポイント {#key-data-points}

ジャーニーステップイベントでは、次のような包括的な情報がキャプチャされます。

- **ジャーニー ID**：[ジャーニー ID、バージョン、名前](sharing-journey-fields.md)
- **プロファイル情報**：[プロファイル ID と関連 ID](sharing-identity-fields.md)
- **ステップ詳細**：[ノード名、ステップタイプ、実行ステータス](sharing-common-fields.md)
- **タイムスタンプ**：各ジャーニーステップの正確なタイミング
- **アクション結果**：[成功／失敗のステータスと実行の詳細](sharing-execution-fields.md)
- **エラー情報**：問題発生時の詳細な[エラーコードと説明](sharing-field-list.md#discarded-events)

すべての[使用可能なフィールド定義](sharing-field-list.md)を探索します。

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

**ジャーニーファネル分析**

- 各ジャーニーステップでコンバージョン率を追跡します
- プロファイルが最も頻繁にジャーニーを終了する場所を特定します
- 様々なジャーニーフェーズに費やす時間を測定します

詳しくは、[ファネル分析のクエリ手法](query-examples.md#common-queries)を参照してください。

## サンプルとリソース {#samples-resources}

### クエリの例とテンプレート {#query-examples}

一般的なジャーニーステップイベント分析の包括的なクエリの例を探索します。

- **[ジャーニーステップイベントクエリの例](query-examples.md)**：一般的な分析シナリオですぐに使用できる SQL クエリ
- **[データセットクエリのサンプル](../data/datasets-query-examples.md#journey-step-event)**：ジャーニーステップイベントデータセットのクエリの例
- **[プロファイルベースのクエリ](query-examples.md#profile-based-queries)**：個々のプロファイルのジャーニーとインタラクションを追跡します

### フィールドドキュメント {#field-documentation}

ジャーニーステップイベントの完全なデータ構造を理解します。

- **[ジャーニーステップイベントフィールドリスト](sharing-field-list.md)**：すべての使用可能なフィールドの包括的なリファレンス
- **[共通フィールド](sharing-common-fields.md)**：journeyStepEvent と journeyStepProfileEvent 間で共有されるフィールド
- **[アクション実行フィールド](sharing-execution-fields.md)**：アクション実行トラッキングに固有のフィールド
- **[ジャーニーフィールド](sharing-journey-fields.md)**：ジャーニー固有のメタデータと識別子

### ベストプラクティスとトラブルシューティング {#best-practices}

**パフォーマンスの最適化**

- クエリパフォーマンスを向上させるには、`journeyVersionName` の代わりに `journeyVersionID` を使用します（[ジャーニープロパティの詳細情報](../building-journeys/expression/journey-properties.md)）
- 日付範囲でフィルタリングすると、大規模なデータセットでのクエリ速度が向上します
- [ジャーニー名前空間の設定](../building-journeys/entry-management.md)に一致するプロファイル ID を活用します

**データ品質**

- データの問題を特定するために、[破棄されたイベント](sharing-field-list.md#discarded-events)を定期的に監視します
- イベントスキーマが分析要件と一致しているかどうかを検証します
- カスタムクエリに適切なエラー処理を実装します

**分析戦略**

- ジャーニーステップイベントと[メッセージフィードバックデータ](../data/datasets-query-examples.md#message-feedback-event-dataset)を組み合わせて、完全なアトリビューションを実現します
- 時間ベースの分析を使用して、ジャーニーの速度とボトルネックを理解します

### 高度な分析機能 {#advanced-analytics}

**Customer Journey Analytics の統合**
[Customer Journey Analytics](cja-ajo.md) を使用して、ジャーニーステップイベントを分析することで、次の目的に対応できます。

- 高度なアトリビューションモデリング
- クロスチャネルジャーニーのビジュアライゼーション
- ジャーニーの成果に関する予測分析

Journey Optimizer データに詳しくは、[Customer Journey Analytics の設定](report-gs-cja.md)方法を参照してください。

## その他のリソース {#additional-resources}

### ドキュメントリンク {#documentation-links}

- **[ジャーニーステップ共有の概要](sharing-overview.md)**：ジャーニーデータが Adobe Experience Platform にフローする仕組みについて説明します
- **[ビルトインスキーマディクショナリ](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja){target="_blank"}**：完全な XDM スキーマリファレンス
- **[Journey Optimizer レポート](report-gs-cja.md)**：Journey Optimizer のレポート機能の概要

### 統合ガイド {#integration-guides}

- **[Adobe Customer Journey Analytics](cja-ajo.md)**：CJA での Journey Optimizer データの分析
- **[データ管理](../data/export-datasets.md)**：ジャーニーデータのエクスポートと管理
- **[プライバシーとガバナンス](../privacy/audit-logs.md)**：ジャーニーイベントのデータガバナンスに関する考慮事項


**次の手順：**

- [最初のジャーニーレポートの作成](sharing-overview.md)から開始します
- 特定のユースケースについて詳しくは、[クエリの例](query-examples.md)を参照してください
- 詳しくは、[ジャーニー管理のベストプラクティス](../building-journeys/journey.md)を参照してください
