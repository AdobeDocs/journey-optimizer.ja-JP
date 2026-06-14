---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーステップイベントの操作
description: Adobe Journey Optimizer でのジャーニーステップイベントの操作方法と、概要、重要な理由、分析と最適化での使用方法について説明します。
feature: Journeys, Reporting
role: Developer, Admin, User
level: Intermediate, Experienced
keywords: ジャーニー, ステップイベント, 分析, レポート, モニタリング, XDM
exl-id: 2e7c5ea5-d8c5-416d-ab88-d2bc02043558
TQID: https://experienceleague.adobe.com/PSXSN-31GNlM0zBKcCvdKPciHt5zhQPPCffFrUoIxUs
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a9f73820-6899-47c2-a597-3fec28ab756aid: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
subfeature_v2: id: d145add9-d5b9-481b-aa8a-e15e6bb7f813id: a7289281-9ae4-47b1-b8cf-4028b98af776id: b5afe8bf-bda6-41b5-ba06-922638872d63
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 7f28f19b11ead867b0851943fdd997dcc3af170b
workflow-type: tm+mt
source-wordcount: 967
ht-degree: 95%

---

# ジャーニーステップイベントの操作 {#work-with-journey-step-events}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey Optimizerのジャーニーステップイベントの概要、重要な理由、およびAdobe Experience Platformを通じた分析、モニタリング、最適化に使用する方法について説明します。

>[!ENDSHADEBOX]

ジャーニーステップイベントは、Adobe Journey Optimizer での[ジャーニー](../building-journeys/journey.md)の進行状況に合わせて[プロファイル](../audience/get-started-profiles.md)が実行する各ステップに関する詳細情報をキャプチャする、自動的に生成されたイベントです。 これらのイベントにより、[ジャーニーのパフォーマンス](../building-journeys/report-journey.md)を包括的に表示でき、強力な分析機能が有効になります。

## ジャーニーステップイベントとは {#what-are-step-events}

ジャーニーステップイベントは、システムにより生成される [XDM（エクスペリエンスデータモデル）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}イベントです。ジャーニー内でプロファイルがノード間を移動するたびに、Adobe Journey Optimizer により自動的に作成され、[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} に送信されます。 各イベントは、顧客のジャーニーエクスペリエンスでの特定の[ジャーニーアクティビティ](../building-journeys/about-journey-activities.md)やトランジションに対応します。

ジャーニーステップイベントには、主に次の 2 つのタイプがあります。

- **journeyStepEvent**：ジャーニーステップを通じた個人プロファイルの進行状況に関連するイベント
- **journeyStepProfileEvent**：追加のプロファイルコンテキスト情報を含むイベント

### ジャーニーステップイベントをトリガーする内容 {#event-triggers}

ジャーニーステップイベントは、次の様々なジャーニーアクティビティに対して自動的に生成されます。

- **エントリイベント**：プロファイルが[ジャーニーにエントリ](../building-journeys/entry-management.md)する場合
- **アクション実行**：[メッセージが送信](../building-journeys/journey-action.md)される場合や、[カスタムアクション](../building-journeys/using-custom-actions.md)が実行される場合
- **条件評価**：プロファイルが[条件](../building-journeys/conditions.md)と決定ポイントを通過する場合
- **待機アクティビティ**：プロファイルが[待機ノード](../building-journeys/wait-activity.md)にエントリおよび終了する場合
- **終了イベント**：プロファイルが[ジャーニーを完了または終了](../building-journeys/end-journey.md)する場合
- **エラー処理**：ジャーニー実行中にエラーが発生する場合

>[!NOTE]
>
>ジャーニーステップイベントは、すべてのインスタンスでデフォルトでアクティブ化されます。 ステップイベントのプロビジョニング時に作成された[スキーマやデータセット](sharing-overview.md)は、変更も更新もできません。 これらのスキーマとデータセットは読み取り専用モードです。

詳しくは、[ジャーニーステップイベントスキーマ](sharing-field-list.md)を参照してください。

## ジャーニーステップイベントが重要な理由 {#why-step-events-matter}

ジャーニーステップイベントは、Adobe Journey Optimizer を使用する組織に対して次の重要な価値を提供します。

### リアルタイムの分析とモニタリング {#real-time-analytics}

- **ジャーニーのパフォーマンストラッキング**：[ライブレポート](live-report.md)を使用して、プロファイルがジャーニーを通じてフローする仕組みをリアルタイムで監視します。
- **コンバージョン分析**：[ジャーニー分析](journey-global-report-cja.md)を使用して、離脱ポイントと成功したコンバージョンパスを理解します
- **エラー検出**：[モニタリングとアラート](alerts.md)を通じて発生した問題を特定し、トラブルシューティングします

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

**パフォーマンスモニタリング**

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

**Customer Journey Analyticsとの連携**
ジャーニーステップイベントは、[Customer Journey Analytics](cja-ajo.md)を使用して分析できます。

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
