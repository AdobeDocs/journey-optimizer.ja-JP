---
solution: Journey Optimizer
product: Journey Optimizer
title: テスト、検証、承認
description: Journey Optimizerのすべてのテスト機能と承認機能をご確認ください。 ローンチ前に、コンテンツのプレビュー、ジャーニーのシミュレーション、メールの検証、実験の実行、競合の検出、承認ワークフローの設定を行います。
feature: Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: テスト，検証，承認，品質保証，qa, テストプロファイル，パーソナライゼーション，レンダリング，スパムチェック，コンテンツ実験，a/b テスト，競合検出，シードリスト，配達確認，サンプルデータ，承認ワークフロー，メールテスト，検証ワークフロー
redpen-status: CREATED_||_2025-08-11_20-30-59
exl-id: a770412f-2f80-459d-8cce-32212154d154
source-git-commit: f774ce00cea82eca84410bd76f482e53d3c60bf6
workflow-type: tm+mt
source-wordcount: '3103'
ht-degree: 5%

---

# テスト、検証、承認{#section-overview}

この節では、Journey Optimizerのすべてのテスト機能と承認機能について説明します。 テストプロファイルを使用したコンテンツのプレビュー、ジャーニーのロジックの検証、メールのレンダリングとスパムスコアの確認、A/B 実験の実行、競合の検出、承認ワークフローの設定などを行うツールが用意されています。

このランディングページでは、作成している内容（キャンペーンとジャーニー）に基づいて適切なテストアプローチを選択し、推奨されるテストワークフローを順を追って説明し、すべてのテストおよび承認リソースにすばやくアクセスできます。 以下の [&#x200B; テストアプローチを選択 &#x200B;](#choose-your-testing-approach) から開始して、ユースケースに適用するツールを特定します。

## テスト機能の概要

**使用可能なテストの種類：**

* → コンテンツテスト：メッセージを送信する前にメッセージコンテンツをプレビューおよび検証します [&#x200B; キャンペーンをテスト &#x200B;](#testing-campaigns)、[&#x200B; パーソナライゼーションをテスト &#x200B;](#testing-personalization)。
* ジャーニーロジックテスト：ジャーニーパスを通じた顧客の進行状況をシミュレート→ます [&#x200B; ジャーニーのテスト &#x200B;](#testing-journeys)
* 技術テスト：レンダリング、配信品質、認証の→を検証 [&#x200B; 技術検証 &#x200B;](#2-technical-validation)
* パフォーマンステスト：A/B 実験→[&#x200B; コンテンツ実験 &#x200B;](#content-experiments--ab-testing) を使用してコンテンツのバリエーションを比較
* 競合テスト：キャンペーンとジャーニーの重複→検出 [&#x200B; 競合検出 &#x200B;](#conflict-detection)
* 承認テスト：アクティブ化→前の構造化レビューワークフロー [&#x200B; 承認ワークフロー &#x200B;](#approval-workflows-for-journeys-and-campaigns)

**コンテキスト別の主な機能：**

| 機能 | 適用先 | チャネルの制限 | 前提条件 | プライマリ目的 | ドキュメント |
|------------|-----------|---------------------|--------------|-----------------|---------------|
| [テストプロファイル](../using/content-management/test-profiles.md) | キャンペーン、ジャーニー | すべてのチャネル | 作成されたテストプロファイル | パーソナライズされたコンテンツのプレビュー | [ガイド](#testing-campaigns) |
| [サンプル入力データ](../using/test-approve/simulate-sample-input.md) | キャンペーン、ジャーニー | メール，SMS, プッシュ，Web, コードベース，アプリ内，コンテンツカード | CSV/JSON ファイル | 複数のパーソナライゼーションバリアントのテスト | [ガイド](#simulate-content-variations) |
| [&#x200B; テストモード &#x200B;](../using/building-journeys/testing-the-journey.md) | ジャーニーのみ | なし | ドラフトジャーニー、名前空間設定済み | プロファイルの進行をシミュレート | [&#x200B; カード &#x200B;](#test-your-journey) |
| [&#x200B; ドライラン &#x200B;](../using/building-journeys/journey-dry-run.md) | ジャーニーのみ | なし | ジャーニーが作成されました | 実行パスの分析 | [&#x200B; カード &#x200B;](#journey-dry-run) |
| [メールのレンダリング](../using/content-management/rendering.md) | キャンペーン、ジャーニー | メールのみ | Litmus 統合 | クライアント間での表示の検証 | [ワークフロー](#2-technical-validation) |
| [&#x200B; スパムスコア &#x200B;](../using/content-management/spam-report.md) | キャンペーン、ジャーニー | メールのみ | なし | 配信品質の検証 | [ワークフロー](#2-technical-validation) |
| [&#x200B; シードリスト &#x200B;](../using/configuration/seed-lists.md) | キャンペーン、ジャーニー | メールのみ | シードリストが設定済み | 関係者の監視 | [&#x200B; カード &#x200B;](#seed-lists-for-stakeholder-monitoring) |
| [&#x200B; コンテンツ実験 &#x200B;](../using/content-management/get-started-experiment.md) | キャンペーンのみ | すべてのチャネル | なし | A/B およびマルチアームバンディットテスト | [&#x200B; カード &#x200B;](#content-experiments--ab-testing) |
| [&#x200B; 競合の検出 &#x200B;](../using/conflict-prioritization/conflicts.md) | キャンペーン、ジャーニー（限定） | すべてのチャネル | なし | 顧客の過剰なメッセージを防ぐ | [&#x200B; カード &#x200B;](#conflict-detection) |
| [&#x200B; 承認ワークフロー &#x200B;](../using/test-approve/gs-approval.md) | キャンペーン、ジャーニー | すべてのチャネル | 承認ポリシーが作成されました | 構造化されたレビュープロセス | [&#x200B; カード &#x200B;](#approval-workflows-for-journeys-and-campaigns) |
| [Personalization プレイグラウンド &#x200B;](../using/personalization/personalize.md#playground) | すべて | すべてのチャネル | なし | パーソナライゼーション構文の学習とテスト | [&#x200B; カード &#x200B;](#personalization-playground) |

**一般的なテストワークフロー：**

1. 開発前：[&#x200B; パーソナライゼーションプレイグラウンド &#x200B;](#testing-personalization) を使用して構文を学習します
2. 開発中：[&#x200B; テストプロファイル &#x200B;](#testing-campaigns) を使用したプレビュー、[&#x200B; サンプル入力データ &#x200B;](#simulate-content-variations) を使用した検証
3. 起動前：[&#x200B; 技術テスト &#x200B;](#2-technical-validation) （レンダリング、スパム）を実行し、[&#x200B; 競合 &#x200B;](#conflict-detection) を確認し、[&#x200B; 承認 &#x200B;](#approval-workflows-for-journeys-and-campaigns) のために送信
4. ローンチ後：ライブレポートを使用して監視し（[&#x200B; 監視とトラブルシューティング &#x200B;](#monitoring--troubleshooting) を参照）、結果に基づいて繰り返し実行します


## テストと承認が重要な理由

テストおよび承認プロセスは、ブランドの評判を保護し、キャンペーンの成功を確保するための不可欠な品質ゲートとして機能します。 これが重要な理由です。

* **顧客に到達する前にエラーを見つける** – 修正が迅速でリスクのない制御された環境で、リンクの破損、誤ったパーソナライゼーション、レンダリングの問題、ロジックの欠陥を特定します。

* **配信品質の向上** - スパムスコアをテストし、メール認証を検証し、メールクライアント間でのレンダリングを確認して、受信ボックスの配置とエンゲージメント率を最大化します。

* **ブランドの一貫性の確保** – 様々なテストプロファイルを使用してコンテンツをプレビューし、様々な顧客セグメントに対してパーソナライゼーションが正しく表示され、ブランド標準を維持していることを確認します。

* **複雑なジャーニーの検証** – 複数手順のジャーニーフローをシミュレートして、トリガーが正しく発生し、条件が適切に評価され、顧客が適切なメッセージを適切なタイミングで受け取ることを確認します。

* **アカウンタビリティの確立** – 関係者の承認を必要とする正式な承認ワークフローを実装して、明確な所有権を作成し、不正な、または早期のキャンペーン開始を減らします。

* **時間とリソースの節約** – 修正が安価かつ迅速な開発サイクルの早い段階で問題を検出し、コストのかかるローンチ後の修正やカスタマーサービスのエスカレーションを防ぎます。

## 主な用語

**[テストプロファイル](../using/content-management/test-profiles.md)** = パーソナライズされたコンテンツのプレビューに使用される合成顧客プロファイル（実際の顧客ではありません）。 リアルタイム顧客プロファイルサービスでフラグ付け。 テストモードとコンテンツのプレビューで必須です。 [テストプロファイルの作成方法を学ぶ](../using/audience/creating-test-profiles.md)

**[テストモード](../using/building-journeys/testing-the-journey.md)** = ジャーニーパスを介してテストプロファイルを送信するジャーニーシミュレーション機能。 制限事項：ドラフトジャーニーのみ。名前空間が必要です。テストプロファイルのみ。 [&#x200B; テストモードのドキュメントを参照してください &#x200B;](../using/building-journeys/testing-the-journey.md)

**[ドライラン](../using/building-journeys/journey-dry-run.md)** = メッセージの送信や API 呼び出しを行わずにジャーニーをトレースするパス実行分析ツール。 ユースケース：リソースを消費せずにロジックを検証する [&#x200B; ドライランについて学ぶ &#x200B;](../using/building-journeys/journey-dry-run.md)

**[サンプル入力データ](../using/test-approve/simulate-sample-input.md)** = パーソナライゼーションをテストするためのプロファイル属性値を含む CSV または JSON ファイル。 最大 30 のバリアントをサポートします。 テストプロファイルを作成する代わりに使用できます。 [&#x200B; コンテンツのバリエーションをシミュレートする方法 &#x200B;](../using/test-approve/simulate-sample-input.md)

**[シードリスト](../using/configuration/seed-lists.md)** =実際の配信に自動的に含まれる内部関係者のメールアドレス（テスト送信ではありません）。 メールチャネルのみ。 ユースケース：品質の監視とコンプライアンス。 [&#x200B; シードリストの設定 &#x200B;](../using/configuration/seed-lists.md)

**[コンテンツ実験](../using/content-management/get-started-experiment.md)** = A/B テストまたはコンテンツのバリエーションを比較するマルチアームバンディット実験。 キャンペーンのみ。ジャーニーでは使用できません。 [&#x200B; 実験の概要 &#x200B;](../using/content-management/get-started-experiment.md) | [&#x200B; 実験の作成 &#x200B;](../using/content-management/content-experiment.md)

**[配達確認](../using/content-management/proofs.md)** = テストプロファイルデータを使用して、特定のメールアドレスに送信されたテストメール配信。 シードリストとは異なります（配達確認は手動のテスト送信、シードリストは自動的な関係者コピーです）。 [&#x200B; 配達確認の送信 &#x200B;](../using/content-management/proofs.md)

**[競合検出](../using/conflict-prioritization/conflicts.md)** =同じオーディエンスをターゲティングする、重複するキャンペーンおよびジャーニーを識別するツール。 限定的なジャーニーのサポート：単一、オーディエンスの選定、オーディエンスを読み取りタイプのみ。 [&#x200B; 競合管理について説明します &#x200B;](../using/conflict-prioritization/gs-conflict-prioritization.md)

**[承認ワークフロー](../using/test-approve/gs-approval.md)** = アクティベーション前に関係者の承認を必要とする複数手順のレビュープロセス。 承認ポリシーの設定が必要です。 [&#x200B; 承認の設定 &#x200B;](../using/test-approve/gs-approval.md) | [&#x200B; ポリシーの作成 &#x200B;](../using/test-approve/approval-policies.md)

**[レンダリングテスト](../using/content-management/rendering.md)** = メールクライアント（Gmail、Outlook、Apple Mail）およびデバイスをまたいだメール表示の検証。 Litmus 統合が必要です。 [&#x200B; メールのレンダリングをテスト &#x200B;](../using/content-management/rendering.md)

**[Personalization playground](../using/personalization/personalize.md#playground)** = インタラクティブなラーニング環境で、パーソナライゼーションの構文を試し、サンプルデータを使用して式をテストします。 ライブデータセットは必要ありません。 [&#x200B; 遊び場にアクセス &#x200B;](../using/personalization/personalize.md#playground)

## メソッド選択をテストするためのデシジョンツリー

このデシジョンツリーを使用すると、特定のシナリオに適切なテストツールをすばやく特定できます。 コンテキスト（作成している内容、検証が必要な内容、使用しているチャネル）に基づいて各質問に答え、関連する機能およびドキュメントに直接移動します。

+++ **質問 1：テスト対象**

* Campaign →[&#x200B; キャンペーンのテスト &#x200B;](#testing-campaigns)
* ジャーニー→[&#x200B; ジャーニーのテスト &#x200B;](#testing-journeys)
* [Personalization→プレイグラウンド &#x200B;](#testing-personalization) のPersonalization式
+++

+++**質問 2：検証が必要な側面は何ですか？**

* コンテンツとパーソナライゼーション→[&#x200B; テストプロファイル &#x200B;](#testing-campaigns) または [&#x200B; サンプル入力データ &#x200B;](#simulate-content-variations)
* メールの表示→[&#x200B; メールのレンダリングテスト &#x200B;](#2-technical-validation)
* 配信品質→[&#x200B; スパムスコアのチェック &#x200B;](#2-technical-validation)
* ジャーニーのロジックとフロー→[&#x200B; テストモード &#x200B;](#testing-journeys) または [&#x200B; ドライラン &#x200B;](#journey-dry-run)
* パフォーマンス比較→[&#x200B; コンテンツ実験 &#x200B;](#content-experiments--ab-testing) （キャンペーンのみ）
* タイミングの競合→[&#x200B; 競合の検出 &#x200B;](#conflict-detection)
* 関係者レビュー→[&#x200B; 承認ワークフロー &#x200B;](#approval-workflows-for-journeys-and-campaigns)
+++

+++**質問 3：どのチャネルですか？**

* 電子メール →使用可能なすべてのテスト方法（「[&#x200B; キャンペーンのテスト &#x200B;](#testing-campaigns)」を参照）
* SMS、プッシュ→信 [&#x200B; コンテンツテスト &#x200B;](#testing-campaigns)、[&#x200B; サンプル入力データ &#x200B;](#simulate-content-variations)、[&#x200B; 承認ワークフロー &#x200B;](#approval-workflows-for-journeys-and-campaigns)
* Web、アプリ内、コードベースの→[&#x200B; コンテンツテスト &#x200B;](#testing-campaigns)、[&#x200B; サンプル入力データ &#x200B;](#simulate-content-variations)、[&#x200B; 承認ワークフロー &#x200B;](#approval-workflows-for-journeys-and-campaigns)
* 複数のチャネル →各チャネルを個別にテスト
+++

+++**質問 4：ワークフローに含まれるタイミング**

* 学習用→[Personalization プレイグラウンド &#x200B;](#personalization-playground) を作成する前に
* 検証用の→ [&#x200B; テストプロファイル &#x200B;](#testing-campaigns) および [&#x200B; サンプル入力データ &#x200B;](#simulate-content-variations) の構築中
* 起動→前 [&#x200B; レンダリングテスト &#x200B;](#2-technical-validation)、[&#x200B; スパムチェック &#x200B;](#email-spam-report)、[&#x200B; 競合検出 &#x200B;](#conflict-detection)、[&#x200B; 承認 &#x200B;](#approval-workflows-for-journeys-and-campaigns)
* ローンチ後→[&#x200B; ライブレポート &#x200B;](../using/building-journeys/report-journey.md) および [&#x200B; 監視 &#x200B;](#monitoring--troubleshooting)
+++


## テストアプローチを選択

適切なテストアプローチは、何を構築し、何を検証する必要があるかによって異なります。 このガイドを使用すると、シナリオに最も関連性の高いテストツールを特定できます。

### キャンペーンのテスト

**すべてのキャンペーンの場合：**

* [&#x200B; テストプロファイル &#x200B;](../using/content-management/test-profiles.md) または [&#x200B; サンプル入力データ &#x200B;](../using/test-approve/simulate-sample-input.md) を使用したコンテンツのプレビューとテスト
* デバイスとクライアントをまたいだ [&#x200B; メールのレンダリング &#x200B;](../using/content-management/rendering.md) の確認（メールチャネルのみ）
* [&#x200B; スパムスコアチェック &#x200B;](../using/content-management/spam-report.md) を実行する（メールチャネルのみ）
* 他のキャンペーンやジャーニーとの [&#x200B; 競合 &#x200B;](../using/conflict-prioritization/conflicts.md) のレビュー
* 関係者の監視のための [&#x200B; シードリスト &#x200B;](../using/configuration/seed-lists.md) の設定（メールチャネルのみ）
* アクティブ化前に [&#x200B; 承認 &#x200B;](../using/test-approve/gs-approval.md) 用に送信

**A/B テストと最適化の場合：**

* [&#x200B; コンテンツ実験 &#x200B;](../using/content-management/get-started-experiment.md) を作成して、複数の処理をテストし、パフォーマンスを測定する

**API トリガーキャンペーンの場合：**

* [Campaign Simulation API](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"} を使用して、プルーフジョブをプログラムでトリガーします

### ジャーニーのテスト

**すべてのジャーニーの場合：**

* [&#x200B; テストモード &#x200B;](../using/building-journeys/testing-the-journey.md) を使用して、プロファイルの進行をシミュレートします（ドラフトジャーニーのみ、名前空間が必要）または [&#x200B; ドライラン &#x200B;](../using/building-journeys/journey-dry-run.md) を使用して、メッセージを送信せずに実行パスを分析します
* [&#x200B; プレビューと配達確認 &#x200B;](../using/content-management/preview-test.md) を使用した個々のメッセージのテスト
* 他のジャーニーおよびキャンペーンとの [&#x200B; 競合 &#x200B;](../using/conflict-prioritization/conflicts.md) の確認
* 公開前に [&#x200B; 承認 &#x200B;](../using/test-approve/gs-approval.md) 用に送信

**複雑なジャーニーの場合：**

* テストモードとドライランを併用して、分岐ロジックと実行パスを徹底的に検証します
* 様々なエントリ条件とプロファイル属性を系統的にテスト

**メモ：** 競合検出とジャーニーキャッピングは、単一、オーディエンスの選定、オーディエンスを読み取りジャーニーでのみ使用できます。

### パーソナライゼーションのテスト

**コンテンツを作成する前に：**

* [&#x200B; パーソナライゼーションプレイグラウンド &#x200B;](../using/personalization/personalize.md#playground) で実験して、構文を学び、サンプルデータを使用して式をテストします

**コンテンツ作成中：**

* [&#x200B; テストプロファイル &#x200B;](../using/content-management/test-profiles.md) を使用してプレビューし、パーソナライゼーションのレンダリングが正しいことを検証します
* CSV/JSON ファイルの [&#x200B; サンプル入力データ &#x200B;](../using/test-approve/simulate-sample-input.md) を使用して、複数のシナリオをテストします（最大 30 のバリアントをサポート）

## テストのベストプラクティス

テスト作業の有効性を最大限に高めるには、次の推奨プラクティスに従います。

1. **早い段階で頻繁にテストします** - キャンペーンが完全に作成されるまで待たないでください。 開発に合わせて、コンテンツ、パーソナライゼーションおよびロジックを増分的にテストします。

1. **現実的なテストプロファイルの使用** - エッジケースや様々なパーソナライゼーションシナリオなど、ターゲットオーディエンスセグメントを正確に表す [&#x200B; テストプロファイルを作成 &#x200B;](../using/audience/creating-test-profiles.md) します。

1. **デバイスとクライアントをまたいだテスト** – 一般的なメールクライアント（Gmail、Outlook、Apple Mail）およびデバイス（デスクトップ、モバイル、タブレット）で [&#x200B; メールのレンダリング &#x200B;](../using/content-management/rendering.md) を確認し、表示の一貫性を確保します（メールチャネルのみ）。

1. **パーソナライゼーションの徹底的な検証** – 異なる属性値を持つ複数の [&#x200B; テストプロファイル &#x200B;](../using/content-management/test-profiles.md) を使用してテストし、パーソナライゼーショントークンが正しくレンダリングされ、フォールバック値が機能することを確認します。 [&#x200B; パーソナライゼーションプレイグラウンド &#x200B;](../using/personalization/personalize.md#playground) を使用して、パーソナライゼーション式を実験し、サンプルデータを使用したコードのテストを行ってからキャンペーンに適用します。

1. **サンプルデータを使用したコンテンツバリエーションのテスト** - CSV または JSON ファイルの [&#x200B; サンプル入力データ &#x200B;](../using/test-approve/simulate-sample-input.md) を使用して、多数のテストプロファイルを作成することなく、最大 30 個のパーソナライゼーションシナリオをテストし、包括的なカバレッジを確保しながら時間を節約します。 メール、SMS、プッシュ、web、コードベースのエクスペリエンス、アプリ内およびコンテンツカードチャネルをサポートします。

1. **関係者の監視にシードリストを使用** - [&#x200B; シードリスト &#x200B;](../using/configuration/seed-lists.md) を設定して、品質監視とコンプライアンス検証のために、実行時にすべての配信のコピーを受信する内部の関係者を自動的に含めます（メールチャネルのみ）。

1. **ジャーニーパスをシミュレート** – 複数の分岐を持つ複雑なジャーニーの場合は、[&#x200B; テストモード &#x200B;](../using/building-journeys/testing-the-journey.md) を使用して、様々なエントリ条件とプロファイル属性をテストし、可能なすべてのパスを検証します。 名前空間を使用するドラフトジャーニーで使用できます。

1. **配信品質指標の確認** - [&#x200B; スパムスコア &#x200B;](../using/content-management/spam-report.md)、認証ステータスおよびメールヘルス指標を、大きな送信前に確認します（メールチャネルのみ）。

1. **テスト結果の文書化** - テストの結果、見つかった問題、解決策の記録を保持して、今後のテストプロセスを改善し、チームと学習を共有します。

1. **利害関係者を早期に関与させる** - [&#x200B; 正式な承認 &#x200B;](../using/test-approve/gs-approval.md) 前に利害関係者とプレビューやテスト結果を共有して、フィードバックを収集し、期待に合わせます。

## 推奨されるテストワークフロー

徹底的なテストとスムーズな承認を確実に行うために、次の体系的なアプローチに従います。

### &#x200B;1. コンテンツの開発とプレビュー

まず、コンテンツを作成しプレビュー機能を使用して、初期デザインとパーソナライゼーションを検証します。

* [&#x200B; メール &#x200B;](../using/email/create-email.md)、[SMS](../using/sms/create-sms.md)、[&#x200B; プッシュ通知 &#x200B;](../using/push/create-push.md)、またはその他のチャネルコンテンツをデザイン

* **[コンテンツをシミュレート](../using/content-management/preview-test.md)** 機能を使用して、テストプロファイルでプレビューします

* [&#x200B; パーソナライゼーショントークン &#x200B;](../using/personalization/personalization-syntax.md)、動的コンテンツおよびフォールバック値の確認

* **[パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)** でパーソナライゼーション式を実験し、ライブコンテンツに適用する前に、サンプルデータを使用してコードをテストおよび調整します

* CSV/JSON ファイルの **[サンプル入力データ](../using/test-approve/simulate-sample-input.md)** を使用して複数のバリエーションをテストし、様々なプロファイルシナリオでのパーソナライゼーションを検証します

* 異なる画面サイズおよびメールクライアントでの [&#x200B; レンダリング &#x200B;](../using/content-management/rendering.md) の検証

### 2.技術検証

配信品質と機能に影響を与える技術的側面を検証します。

* [&#x200B; スパムスコアチェック &#x200B;](../using/content-management/spam-report.md) を実行して、配信品質の潜在的な問題を特定します

* リンクをテストし、リンクが壊れていないこと、正しく追跡されていないことを確認します

* [&#x200B; メール認証 &#x200B;](../using/configuration/dmarc-record.md) （SPF、DKIM、DMARC）設定を検証

* HTMLのレンダリングを確認し、CSS の互換性の問題を調べる

* モバイルおよびデスクトップデバイスでのテスト [&#x200B; レスポンシブデザイン &#x200B;](../using/email/content-from-scratch.md)

* 他のキャンペーンやジャーニーとの [&#x200B; 競合の可能性 &#x200B;](../using/conflict-prioritization/conflicts.md) をチェックして、顧客メッセージの疲労やタイミングの問題を防ぎます

### &#x200B;3. ジャーニーテスト（ジャーニーのみ）

ジャーニーをテストする場合は、オーケストレーションロジックを検証します。

* **[テストモード](../using/building-journeys/testing-the-journey.md)** を有効化して、ジャーニーを通じたプロファイルの進行状況をシミュレートします

* 様々な [&#x200B; エントリ条件 &#x200B;](../using/building-journeys/entry-management.md) オーディエンス選定のテスト

* [&#x200B; 待機アクティビティ &#x200B;](../using/building-journeys/wait-activity.md)、[&#x200B; 条件 &#x200B;](../using/building-journeys/condition-activity.md) および分岐ロジックが正しく機能していることを確認します

* 複雑なジャーニーに **[ドライラン](../using/building-journeys/journey-dry-run.md)** を使用して、メッセージを送信せずに実行パスを分析します

* [&#x200B; イベント &#x200B;](../using/event/about-events.md) のトリガーが正しいこと、および [&#x200B; カスタムアクション &#x200B;](../using/action/about-custom-action-configuration.md) が期待どおりに実行されていることを確認します

### 4.承認の送信

テストが完了し、問題が解決したら、以下の手順を実行します。

* 組織の [&#x200B; 承認ポリシー &#x200B;](../using/test-approve/approval-policies.md) に従って、キャンペーンまたはジャーニーを承認用に送信します

* [&#x200B; 承認リクエスト &#x200B;](../using/test-approve/request-approval.md) にテスト結果とドキュメントを含める

* [&#x200B; 承認者 &#x200B;](../using/test-approve/review-approve-request.md) からのフィードバックまたは変更リクエストに対応する

* 必要な修正を加え、変更が重大な場合は再テストする

### &#x200B;5. ローンチ前の検証

キャンペーンまたはジャーニーをアクティブ化する前に、以下を行います。

* すべての設定、オーディエンス、[&#x200B; スケジュール &#x200B;](../using/building-journeys/journey-properties.md) の最終レビューを実行します。

* すべての承認が実施され、文書化されていることを確認する

* 送信時間と [&#x200B; タイムゾーン &#x200B;](../using/building-journeys/timezone-management.md) が正しいことを確認します

* [&#x200B; 監視とアラート &#x200B;](../using/reports/alerts.md) を有効にして、起動後のパフォーマンスを追跡する

### 6.監視と反復

立ち上げ後、引き続き監視を実施して、問題を早期に特定します。

* ジャーニーエラー、バウンス率の高さ、エンゲージメントの低さに対する [&#x200B; システムアラート &#x200B;](../using/reports/alerts.md) の設定

* [&#x200B; ライブレポート &#x200B;](../using/building-journeys/report-journey.md) を確認し、期待値に照らしてパフォーマンスを追跡する

* 重大な問題が発生した場合は、ジャーニーを [&#x200B; 一時停止または変更 &#x200B;](../using/building-journeys/journey-pause.md) できるよう備える

* 今後のテストプロセスを改善するために得られた教訓の文書化

## 実行中のテスト：ユースケース

テストの概念が実際のシナリオにどのように適用されるかを確認します。

| 使用例 | 学習内容 | 主なテストの焦点 |
|----------|-------------------|-------------------|
| **[マルチチャネルメッセージの送信](../using/building-journeys/journeys-uc.md)** | オーディエンスの読み取り、反応イベント、メール/プッシュメッセージを組み合わせたジャーニーをテストします。 オーディエンスのターゲティングからメッセージ配信までのフロー全体を検証します。 | マルチチャネルの調整、反応イベント、エンドツーエンドのフロー検証、テストおよび公開手順 |
| **[購読者へのメッセージの送信](../using/building-journeys/message-to-subscribers-uc.md)** | 動的なメールアドレスを使用して、購読リストをターゲットにするテストジャーニー。 正しい購読者ターゲティングのパーソナライゼーション式を検証します。 | Personalization式、動的アドレス指定、サブスクリプションリストのターゲティング |
| **[時間限定メッセージの送信](../using/building-journeys/weekday-email-uc.md)** | 時間ベースの条件を使用してジャーニーをテストし、特定の日にメッセージが送信されるようにします。 待機アクティビティとスケジュールロジックを検証します。 | 時間ベースの条件、待機アクティビティ、スケジュール検証 |
| **[その他のジャーニーのユースケースを見る](../using/building-journeys/jo-use-cases.md)** | エクスペリエンスイベント、マルチチャネルメッセージング、外部システム統合など、実践的な例の包括的なコレクションにアクセスします。 | 様々なシナリオ、詳細なパターン、統合テスト |

## コンテンツのテストと承認

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

コンテンツのプレビュー、テスト、検証

テストプロファイル、メールのレンダリングのテスト、スパムスコア評価などを使用して、パーソナライズされたコンテンツをプレビュー、テスト、検証する方法について説明します。

[コンテンツのプレビューとテストの探索](preview-test-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

ジャーニーおよびキャンペーンの承認ワークフロー

ジャーニーとキャンペーンの品質管理を確保する承認プロセスを設定、管理、実行する方法について説明します。

[承認ワークフローの詳細情報](approve-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

ジャーニーのテスト

特定のプロファイルを使用してテストし、イベント、条件、アクションが期待どおりに動作することを確認することで、公開前にジャーニーを検証できます。 名前空間を使用するドラフトジャーニーで使用できます。

[ジャーニーのテスト](../using/building-journeys/testing-the-journey.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

ジャーニーのドライラン

ドライランを実行して、ジャーニーの実行パスをシミュレートおよび検証し、公開前に潜在的な問題を特定します。

[ジャーニーのドライランの詳細情報](../using/building-journeys/journey-dry-run.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

監視とトラブルシューティング

包括的なトラブルシューティングリソース、システムアラート、エラーコードにアクセスして、ジャーニーの実行とパフォーマンスの問題を解決します。

[監視とトラブルシューティングの表示](troubleshoot-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code.svg)

Personalizationプレイグラウンド

安全な環境でパーソナライゼーション式を試します。 キャンペーンおよびジャーニーに適用する前に、サンプルデータを使用したコードのテストと結果のプレビューを行います。

[Personalization Playground について学ぶ](../using/personalization/personalize.md#playground)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/data.svg)

コンテンツ実験と A/B テスト

複数のコンテンツのバリエーションをテストし、パフォーマンスを測定して最もパフォーマンスの高い処理を特定することで、キャンペーンを最適化します。 キャンペーンでのみ使用できます（A/B およびマルチアームバンディット実験をサポート）。

[コンテンツ実験について](../using/content-management/get-started-experiment.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

関係者による監視のためのシードリスト

品質保証およびコンプライアンスのために顧客に送信される実際のメッセージを監視するために、配信に内部の関係者アドレスを自動的に含めます。 メールチャネルでのみ使用できます。

[シードリストの設定](../using/configuration/seed-lists.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg)

競合の検出

キャンペーンとジャーニーの間の潜在的な重複を特定して、同時通信が多すぎて顧客が圧倒されるのを防ぎます。 キャンペーンおよび単一、オーディエンスの選定、オーディエンスを読み取りの各ジャーニーで使用できます。

[競合の検出](../using/conflict-prioritization/conflicts.md)
:::

::::

## その他のリソース

### 必須のテストおよび検証ガイド

* [&#x200B; コンテンツのバリエーションをシミュレート &#x200B;](../using/test-approve/simulate-sample-input.md) - CSV または JSON ファイルを使用して最大 30 個のパーソナライゼーションシナリオをテストします。 複数のテストプロファイルを作成しない、多言語コンテンツのテストに最適です。 メール、SMS、プッシュ、web、コードベース、アプリ内、コンテンツカードをサポートします。

* [&#x200B; テストプロファイルの作成 &#x200B;](../using/audience/creating-test-profiles.md) - テストプロファイルを作成および管理して、顧客のシナリオをシミュレートします。 テスト用にプロファイルにフラグを付ける方法、属性を設定する方法、テストセグメントを整理する方法について説明します。

* [&#x200B; メールスパムレポート &#x200B;](../using/content-management/spam-report.md) – 送信する前にスパムスコアを確認して、配信品質とインボックスの配置を改善します。 コンテンツの最適化に関する実用的な推奨事項を取得します。

* [ジャーニーに関する FAQ](../using/building-journeys/journey-faq.md) - ジャーニーのテスト、実行、トラブルシューティングに関するよくある質問のクイックリファレンス。

### 依存関係と関係

テスト機能が相互につながったり、より広範なJourney Optimizer ワークフローにつながったりする仕組みを理解します。 このセクションでは、前提条件、アップストリーム/ダウンストリームの依存関係、および一般的な機能の組み合わせをマッピングします。

+++**前提条件（テストの前に必要）**

* テストモードまたはコンテンツプレビューを使用する前に、テストプロファイルを作成する必要があります
* 承認のために送信する前に、承認ポリシーを設定する必要があります
* キャンペーン/ジャーニーに追加する前に、シードリストを作成する必要があります
* メールのレンダリングテストには Litmus 統合が必要です
* テストモードを使用するには、ジャーニーがドラフトステータスである必要があります
* ジャーニーは、テストモードを使用するように名前空間を設定する必要があります

+++

+++**テストが依存するもの（アップストリーム）**

* コンテンツの作成：テストするキャンペーンまたはジャーニーが必要
* テストプロファイル：テストモードとコンテンツのプレビューに必要
* 承認ポリシー：承認ワークフローに必要
* 設定：チャネル設定、メール認証、ドメイン設定

+++

+++**テストに依存するもの（ダウンストリーム）**

* キャンペーン/ジャーニーのアクティブ化：エラーを解決しないとアクティブ化できません
* 公開中：公開前に承認が必要になる場合があります
* ライブ監視：起動後の監視およびレポート作成
* 最適化：テスト結果を使用して今後のキャンペーンを絞り込む

+++

+++**関連する機能**

* テスト +承認ワークフロー=品質保証プロセス
* テスト +競合検出=顧客の過剰なメッセージを防止
* テスト + コンテンツ実験= パフォーマンスの最適化
* テスト + レポート =継続的な改善サイクル
* テストプロファイル + Personalization = コンテンツの検証
* ドライラン + テストモード =包括的なジャーニー検証

+++

+++**一般的な機能の組み合わせ**

* コンテンツテスト：テストプロファイル +サンプル入力データ + Personalization playground
* メール検証：レンダリングテスト + スパムスコア + テストプロファイル +配達確認
* ジャーニーの検証：テストモード + ドライラン + テストプロファイル
* ローンチ前のチェックリスト：すべてのテクニカルテスト +競合検出+承認ワークフロー

+++

### よくある質問

+++**Q：キャンペーンを開始する前にどのようなテストが必要ですか？**

**最小：テストプロファイルとスパムスコアのチェック（メール）を使用したコンテンツプレビュー**
**推奨：** + メールのレンダリング +競合の検出+承認ワークフロー
**ベストプラクティス：** + サンプル入力データのテスト + シードリスト + A/B 実験（最適化する場合）

+++

+++**Q：多くのテストプロファイルを作成せずにパーソナライゼーションをテストするにはどうすればよいですか？**

**プライマリソリューション：** CSV/JSON ファイルで [&#x200B; サンプル入力データ &#x200B;](../using/test-approve/simulate-sample-input.md) を使用します（最大 30 個のバリアントをサポート）
**代替：** 主要なセグメントをカバーする 3 ～ 5 個の代表的な [&#x200B; テストプロファイル &#x200B;](../using/audience/creating-test-profiles.md) を作成します
**学習ツール：** 最初に [&#x200B; パーソナライゼーションプレイグラウンド &#x200B;](../using/personalization/personalize.md#playground) で実験

+++

+++**Q：ジャーニーのテストモードとドライランの違いは何ですか？**

**テストモード：** ジャーニーを通じてテストプロファイルを送信し、実際のアクションをトリガーし、テストメッセージを生成します。 ドラフトジャーニー+名前空間が必要です。
**ドライラン：** 何も送信せずに実行パスをトレースします。 あらゆるジャーニーステータスで機能します。 メッセージは送信されず、アクションは実行されません。
**一緒に使用：** メッセージテストのテストモード + ロジック検証のドライラン =包括的なカバレッジ。

+++

+++**Q：ジャーニーを実稼働/ライブステータスでテストすることはできますか？**

**テストモード：** いいえ – ドラフトジャーニーのみ
**ドライラン：** はい – 任意のジャーニーステータスで機能します
**コンテンツプレビュー：** はい – 個々のメッセージをいつでもプレビューできます
**回避策：** ライブジャーニーをドラフトに複製して完全なテストモードを検証

+++

+++**Q：外部統合が必要なテスト機能はどれですか？**

**メールのレンダリング：** Litmus 統合が必要（個別のライセンス）
**その他：**&#x200B;Journey Optimizerへのビルトイン。追加の統合は必要ありません
**メモ：** テストプロファイルには、リアルタイム顧客プロファイルサービス（付属）が必要です

+++

+++**Q:API トリガーキャンペーンをテストするにはどうすればよいですか？**

**オプション 1:** プログラムによるテストでの [Campaign Simulation API](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"} の使用
**オプション 2:** UI でのテストプロファイルを使用したコンテンツのプレビュー
**オプション 3:** テストメールアドレスへの配達確認の送信
**ベストプラクティス：** 3 つすべてを組み合わせて、包括的な検証を行います

+++


### 関連トピック

* [&#x200B; コンテンツ管理 &#x200B;](content-management-landing-page.md) - テンプレート、フラグメント、メールDesignerを使用して、コンテンツをデザイン、プレビュー、管理する方法について説明します。 一貫したブランディングのためのマスターコンテンツ作成のベストプラクティス。

* [&#x200B; レポートと分析 &#x200B;](reporting-landing-page.md) – 包括的なレポート、ダッシュボード、指標を使用して、キャンペーンとジャーニーのパフォーマンスを分析します。 顧客体験を最適化するための、データに基づく意思決定を行います。

* [ジャーニー設定 &#x200B;](configure-journeys-landing-page.md) - データソース、イベント、カスタムアクションを設定して、高度な Journey Orchestration を有効にします。 ジャーニー作成用の技術基盤を設定します。

* [&#x200B; キャンペーン管理 &#x200B;](../using/campaigns/get-started-with-campaigns.md) – 様々なキャンペーンタイプを調べ、最大の効果を得るためにバッチおよびリアルタイムキャンペーンを作成、スケジュール、最適化する方法を説明します。
