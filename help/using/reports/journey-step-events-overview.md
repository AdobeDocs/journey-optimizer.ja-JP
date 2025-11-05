---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーステップイベントの操作
description: Adobe Journey Optimizerでのジャーニーステップイベントの操作方法 – 概要、重要性、分析と最適化での使用方法を説明します
feature: Journeys, Reporting
role: Developer, Admin, User
level: Intermediate, Experienced
keywords: ジャーニー，ステップイベント，分析，レポート，監視，XDM
source-git-commit: 17e0528849f2bd4d3cbf279c34c98a8359cad797
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 2%

---

# ジャーニーステップイベントの操作 {#work-with-journey-step-events}

ジャーニーステップイベントは、Adobe Journey Optimizerの [&#x200B; ジャーニー &#x200B;](../audience/get-started-profiles.md) を通じて進行する [&#x200B; プロファイル &#x200B;](../building-journeys/journey.md) の各ステップに関する詳細情報を取得する、自動生成されたイベントです。 これらのイベントは、[&#x200B; ジャーニーのパフォーマンス &#x200B;](../building-journeys/report-journey.md) を包括的に可視化し、強力な分析機能を有効にします。

## ジャーニーステップイベントとは {#what-are-step-events}

ジャーニーステップイベントは、プロファイルがジャーニーのあるノードから別のノードに移動するたびに、Adobe Journey Optimizerが自動的に作成して [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"} に送信する、システム生成の [XDM （エクスペリエンスデータモデル） &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} イベントです。 各イベントは、顧客のジャーニーエクスペリエンスの特定の [&#x200B; ジャーニーアクティビティ &#x200B;](../building-journeys/about-journey-activities.md) トランジションに対応します。

ジャーニーステップイベントには、主に次の 2 つのタイプがあります。

- **journeyStepEvent**：ジャーニーステップを通じた個人プロファイルの進行に関連するイベント
- **journeyStepProfileEvent**：追加のプロファイルコンテキスト情報を含むイベント

### ジャーニーステップイベントのトリガー {#event-triggers}

ジャーニーステップイベントは、様々なジャーニーアクティビティに対して自動的に生成されます。

- **エントリイベント**：プロファイルがジャーニーにエントリ [&#x200B; したとき &#x200B;](../building-journeys/entry-management.md)
- **アクションの実行**:[&#x200B; メッセージが送信された &#x200B;](../building-journeys/journeys-message.md) または [&#x200B; カスタムアクション &#x200B;](../building-journeys/using-custom-actions.md) が実行されたとき
- **条件評価**：プロファイルが [&#x200B; 条件 &#x200B;](../building-journeys/condition-activity.md) および決定ポイントを通過した場合
- **待機アクティビティ**：プロファイルがエントリおよび終了したとき [&#x200B; 待機ノード &#x200B;](../building-journeys/wait-activity.md)
- **イベントを終了**：プロファイルがジャーニーを完了または [&#x200B; 終了 &#x200B;](../building-journeys/end-journey.md) したとき
- **エラー処理**：ジャーニーの実行中にエラーが発生した場合

>[!NOTE]
>
>ジャーニーステップイベントは、すべてのインスタンスでデフォルトで有効になっています。 ステップイベントのプロビジョニング中に作成された [&#x200B; スキーマとデータセット &#x200B;](sharing-overview.md) を変更または更新することはできません。 これらのスキーマとデータセットは、読み取り専用モードです。

詳しくは、[&#x200B; ジャーニーステップイベントスキーマ &#x200B;](sharing-field-list.md) を参照してください。

## ジャーニーステップイベントが重要な理由 {#why-step-events-matter}

ジャーニーステップイベントは、Adobe Journey Optimizerを使用する組織にとって重要な価値を提供します。

### リアルタイムの分析と監視 {#real-time-analytics}

- **ジャーニーパフォーマンストラッキング**: [&#x200B; ライブレポート &#x200B;](live-report.md) を使用して、ジャーニー内でのプロファイルのフローをリアルタイムで監視します
- **コンバージョン分析**:[journey analytics を使用したドロップオフポイントと成功したコンバージョンパスについて &#x200B;](journey-global-report-cja.md)
- **エラー検出**：発生した問題を特定してトラブルシューティングする [&#x200B; 監視とアラート &#x200B;](alerts.md)

### データ統合とインサイト {#data-integration}

- **クロスプラットフォーム分析**：ジャーニーデータを他の [Adobe Experience Platform データソースと組み合わせます &#x200B;](../datasource/adobe-experience-platform-data-source.md)
- **Customer 360 表示**：ジャーニーのインタラクションを含む包括的な [&#x200B; 顧客プロファイル &#x200B;](../audience/get-started-profiles.md) を作成します
- **アトリビューションモデリング**:[Customer Journey Analyticsを使用して、ジャーニータッチポイントをダウンストリームのビジネスアウトカムに結び付ける &#x200B;](cja-ajo.md)

### 最適化の機会 {#optimization}

- **A/B テストインサイト**:[&#x200B; 実験 &#x200B;](campaign-global-report-cja-experimentation.md) を使用して、様々なジャーニーパスのパフォーマンスを分析します
- **Personalizationの機能強化**: ジャーニー行動データを使用して、[&#x200B; 動的コンテンツ &#x200B;](../personalization/dynamic-content.md) での今後のエクスペリエンスを向上させます
- **運用効率**：ボトルネックを特定し、最適化 [&#x200B; ジャーニー設計 &#x200B;](../building-journeys/using-the-journey-designer.md)

## ジャーニーステップイベントの使用方法 {#how-to-use-step-events}

### ジャーニーステップイベントデータへのアクセス {#accessing-data}

ジャーニーステップイベントデータはAdobe Experience Platformに自動的に保存され、以下の方法でアクセスできます。

1. **データレイクのクエリ**:SQL を使用して、`journey_step_events` クエリサービス [&#x200B; で &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja){target="_blank"} データセットをクエリします
2. **Customer Journey Analytics**: [&#x200B; 高度な分析ツール &#x200B;](cja-ajo.md) を使用してジャーニーデータを分析します
3. **リアルタイムレポート**:Journey Optimizerのビルトインレポート機能 [&#x200B; を使用してデータにアクセスします &#x200B;](gs-reports.md)
4. **API**：カスタムアプリケーションのイベントデータへのプログラムによるアクセス

詳細情報 [&#x200B; データセットへのアクセス &#x200B;](../data/datasets-query-examples.md)。

### 使用可能な主要なデータポイント {#key-data-points}

ジャーニーステップイベントでは、次のような包括的な情報を取り込むことができます。

- **ジャーニー ID**: [ジャーニー ID、バージョン、および名前 &#x200B;](sharing-journey-fields.md)
- **プロファイル情報**:[&#x200B; プロファイル ID および関連する ID](sharing-identity-fields.md)
- **ステップの詳細**:[&#x200B; ノード名、ステップタイプおよび実行ステータス &#x200B;](sharing-common-fields.md)
- **タイムスタンプ**：各ジャーニーステップの正確なタイミング
- **アクション結果**:[&#x200B; 成功/失敗のステータスと実行の詳細 &#x200B;](sharing-execution-fields.md)
- **エラー情報**：問題が発生した場合の詳細 [&#x200B; エラーコードと説明 &#x200B;](sharing-field-list.md#discarded-events)

すべての [&#x200B; 使用可能なフィールド定義 &#x200B;](sharing-field-list.md) を参照します。

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

詳しくは、[funnel分析のクエリ手法 &#x200B;](query-examples.md#common-queries) を参照してください。

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

- `journeyVersionID` の代わりに `journeyVersionName` を使用して、クエリのパフォーマンスを向上させます（[&#x200B; ジャーニープロパティの詳細 &#x200B;](../building-journeys/expression/journey-properties.md)）。
- 日付範囲でフィルタリングすると、大きなデータセットに対するクエリの速度が向上します
- [&#x200B; ジャーニー名前空間設定 &#x200B;](../building-journeys/entry-management.md) に一致するプロファイル ID の活用

**データ品質**

- データの問題を特定するために [&#x200B; 破棄されたイベント &#x200B;](sharing-field-list.md#discarded-events) を定期的に監視する
- イベントスキーマが分析要件に一致することの検証
- カスタムクエリに適切なエラー処理を実装

**Analytics 戦略**

- ジャーニーステップイベントと [&#x200B; メッセージフィードバックデータ &#x200B;](../data/datasets-query-examples.md#message-feedback-event-dataset) を組み合わせて、完全なアトリビューションを実現します
- 時間ベースの分析を使用したジャーニーの速度とボトルネックの把握

### 高度な分析機能 {#advanced-analytics}

**Customer Journey Analyticsの統合**
ジャーニーステップイベントは、[Customer Journey Analytics](cja-ajo.md) を使用して、次の目的で分析できます。

- 高度なアトリビューションモデリング
- クロスチャネルジャーニービジュアライゼーション
- ジャーニー結果に関する予測分析

Journey Optimizer データ用に [Customer Journey Analyticsを設定 &#x200B;](report-gs-cja.md) する方法を説明します。

## その他のリソース {#additional-resources}

### ドキュメントリンク {#documentation-links}

- **[ジャーニーステップ共有の概要](sharing-overview.md)**: ジャーニーデータがAdobe Experience Platformにどのようにフローするかについて
- **[ビルトインスキーマディクショナリ &#x200B;](https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja){target="_blank"}**：完全な XDM スキーマリファレンス
- **[Journey Optimizer レポート](report-gs-cja.md)**: Journey Optimizerのレポート機能の概要

### 統合ガイド {#integration-guides}

- **[Adobe Customer Journey Analytics](cja-ajo.md)**: CJAでJourney Optimizer データを分析しています
- **[データ管理](../data/export-datasets.md)**：ジャーニーデータのエクスポートと管理
- **[プライバシーとガバナンス](../privacy/audit-logs.md)**：ジャーニーイベントのデータガバナンスに関する考慮事項


**次の手順：**

- [&#x200B; 最初のジャーニーレポートの作成 &#x200B;](sharing-overview.md) から開始します
- 具体的なユースケースについては、[&#x200B; クエリの例 &#x200B;](query-examples.md) を参照してください
- [&#x200B; ジャーニー管理のベストプラクティス &#x200B;](../building-journeys/journey.md) について説明します
