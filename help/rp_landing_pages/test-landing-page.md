---
solution: Journey Optimizer
product: Journey Optimizer
title: テスト、検証、承認
description: Journey Optimizer のすべてのテスト機能と承認機能について説明します。ローンチ前に、コンテンツのプレビュー、ジャーニーのシミュレート、メールの検証、実験の実行、競合の検出、承認ワークフローの設定を行います。
feature: Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: テスト, 検証, 承認, 品質保証, QA, テストプロファイル, パーソナライゼーション, レンダリング, スパムの確認, コンテンツ実験, A/B テスト, 競合の検出, シードリスト, 本配信前確認, サンプルデータ, 承認ワークフロー, メールテスト, 検証ワークフロー
redpen-status: CREATED_||_2025-08-11_20-30-59
exl-id: a770412f-2f80-459d-8cce-32212154d154
source-git-commit: c3535f39b351d671054031b9cc391bf6d9d83a09
workflow-type: ht
source-wordcount: '2328'
ht-degree: 100%

---

# テスト、検証、承認{#section-overview}

この節では、Journey Optimizer のすべてのテスト機能と承認機能について説明します。テストプロファイルを使用したコンテンツのプレビュー、ジャーニーのロジックの検証、メールのレンダリングとスパムスコアの確認、A/B 実験の実行、競合の検出、承認ワークフローの設定を行うツールが用意されています。

このランディングページでは、作成している内容（キャンペーンとジャーニー）に基づいて適切なテストアプローチを選択し、推奨されるテストワークフローを順を追って説明し、すべてのテストおよび承認リソースにすばやくアクセスできます。以下の[テストアプローチの選択](#choose-your-testing-approach)から開始して、ユースケースに適用されるツールを特定します。主なテスト用語の定義について詳しくは、[主な用語](#key-terminology)を参照してください。

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

特定のプロファイルを使用してテストし、イベント、条件、アクションが期待どおりに機能することを確認することで、公開前にジャーニーを検証します。名前空間を使用するドラフトジャーニーで使用できます。

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

パーソナライゼーションプレイグラウンド

安全な環境でパーソナライゼーション式を実験します。キャンペーンおよびジャーニーに適用する前に、サンプルデータを使用したコードのテストと結果のプレビューを行います。

[パーソナライゼーションプレイグラウンドの詳細情報](../using/personalization/personalize.md#playground)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

コンテンツ実験と A/B テスト

複数のコンテンツバリエーションをテストし、パフォーマンスを測定して最もパフォーマンスの高い処理を特定することで、キャンペーンを最適化します。キャンペーンにのみ使用できます（A/B テストとマルチアームバンディット実験をサポートします）。

[コンテンツ実験の詳細情報](../using/content-management/get-started-experiment.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

関係者による監視のためのシードリスト

品質保証とコンプライアンスのために顧客に送信された実際のメッセージを監視するために、配信に内部関係者のアドレスを自動的に含めます。メールチャネルにのみ使用できます。

[シードリストの設定](../using/configuration/seed-lists.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg)

競合の検出

キャンペーンとジャーニー間の潜在的な重複を特定して、同時通信が多すぎて顧客に負担がかかるのを防ぎます。キャンペーンと単一、オーディエンスの選定、オーディエンスを読み取りジャーニーで使用できます。

[競合の検出](../using/conflict-prioritization/conflicts.md)
:::

::::

## テストと承認が重要な理由

テストと承認のプロセスは、ブランドの評判を保護し、キャンペーンの成功を確保するための不可欠な品質ゲートとして機能します。重要な理由を以下に示します。

* **顧客に到達する前にエラーを検出** - 制御された環境で、リンクの破損、正しくないパーソナライゼーション、レンダリングの問題、ロジックの欠陥を特定し、すばやくリスクなく修正できます。

* **配信品質を向上** - スパムスコアのテスト、メール認証の検証、メールクライアント間のレンダリングの確認を行うことで、インボックスへの配置とエンゲージメント率を最大化します。

* **ブランドの一貫性を確保** - 様々なテストプロファイルを使用してコンテンツをプレビューし、様々な顧客セグメントに対してパーソナライゼーションが正しく表示され、ブランド標準が維持されていることを確認します。

* **複雑なジャーニーを検証** - マルチステップのジャーニーフローをシミュレートし、トリガーが正しく発生し、条件が適切に評価され、顧客が適切なメッセージを適切なタイミングで受信することを確認します。

* **説明責任を確立** - 関係者の承認を必要とする正式な承認ワークフローを実装することで、明確な所有権を作成し、未承認または時期尚早なキャンペーンの開始を削減します。

* **時間とリソースを節約** - 開発サイクルの早い段階で問題を検出し、修正がより安価で迅速に行えるので、ローンチ後の修正やカスタマーサービスのエスカレーションにかかるコストを回避できます。

<!--## Testing capabilities overview

**Testing types available:**

* Content testing: Preview and validate message content before sending → [Choose your testing approach](#choose-your-testing-approach)
* Journey logic testing: Simulate customer progression through journey paths → [Choose your testing approach](#choose-your-testing-approach)
* Technical testing: Validate rendering, deliverability, and authentication → [Technical validation](#2-technical-validation)
* Performance testing: Compare content variations using A/B experiments → [Content Experiments & A/B Testing](#test--approve-content)
* Conflict testing: Detect campaign and journey overlaps → [Conflict Detection](#test--approve-content)
* Approval testing: Structured review workflows before activation → [Approval Workflows](#test--approve-content)

**Key capabilities by context:**

| Capability | Applies to | Channel restrictions | Prerequisites | Primary purpose |
|------------|-----------|---------------------|--------------|-----------------|
| [Test profiles](../using/content-management/test-profiles.md) | Campaigns, Journeys | All channels | Test profiles created | Preview personalized content |
| [Sample input data](../using/test-approve/simulate-sample-input.md) | Campaigns, Journeys | Email, SMS, Push, Web, Code-based, In-app, Content cards | CSV/JSON file | Test multiple personalization variants |
| [Test mode](../using/building-journeys/testing-the-journey.md) | Journeys only | N/A | Draft journey, namespace configured | Simulate profile progression |
| [Dry run](../using/building-journeys/journey-dry-run.md) | Journeys only | N/A | Journey created | Analyze execution paths |
| [Email rendering](../using/content-management/rendering.md) | Campaigns, Journeys | Email only | Litmus integration | Verify display across clients |
| [Spam score](../using/content-management/spam-report.md) | Campaigns, Journeys | Email only | None | Deliverability validation |
| [Seed lists](../using/configuration/seed-lists.md) | Campaigns, Journeys | Email only | Seed list configured | Stakeholder monitoring |
| [Content experiments](../using/content-management/get-started-experiment.md) | Campaigns only | All channels | None | A/B and multi-armed bandit testing |
| [Conflict detection](../using/conflict-prioritization/conflicts.md) | Campaigns, Journeys (limited) | All channels | None | Prevent customer over-messaging |
| [Approval workflows](../using/test-approve/gs-approval.md) | Campaigns, Journeys | All channels | Approval policy created | Structured review process |
| [Personalization playground](../using/personalization/personalize.md#playground) | All | All channels | None | Learn and test personalization syntax |

**Common testing workflows:**

1. Pre-development: Use [personalization playground](#test--approve-content) to learn syntax
2. During development: Preview with [test profiles](#choose-your-testing-approach), validate with [sample input data](#choose-your-testing-approach)
3. Pre-launch: Run [technical tests](#2-technical-validation) (rendering, spam), check [conflicts](#test--approve-content), submit for [approval](#test--approve-content)
4. Post-launch: Monitor with live reports (see [Monitoring & Troubleshooting](#test--approve-content)), iterate based on results

-->

<!--
## Decision tree for testing method selection

Use this decision tree to quickly identify the right testing tools for your specific scenario. Answer each question based on your context (what you're building, what you need to validate, and which channel you're using) to navigate directly to the relevant capabilities and documentation.

+++ **Question 1: What are you testing?**

* Campaign → [Choose your testing approach](#choose-your-testing-approach)
* Journey → [Choose your testing approach](#choose-your-testing-approach)
* Personalization expressions → [Personalization playground](#test--approve-content)
+++

+++**Question 2: What aspect needs validation?**

* Content and personalization → [Test profiles](#choose-your-testing-approach) or [sample input data](#choose-your-testing-approach)
* Email display → [Email rendering tests](#2-technical-validation)
* Deliverability → [Spam score checks](#2-technical-validation)
* Journey logic and flow → [Test mode](#choose-your-testing-approach) or [dry run](#test--approve-content)
* Performance comparison → [Content experiment](#test--approve-content) (campaigns only)
* Timing conflicts → [Conflict detection](#test--approve-content)
* Stakeholder review → [Approval workflow](#test--approve-content)
+++

+++**Question 3: What channel?**

* Email → All testing methods available (see [Choose your testing approach](#choose-your-testing-approach))
* SMS, Push → [Content testing](#choose-your-testing-approach), [sample input data](#choose-your-testing-approach), [approval workflows](#test--approve-content)
* Web, In-app, Code-based → [Content testing](#choose-your-testing-approach), [sample input data](#choose-your-testing-approach), [approval workflows](#test--approve-content)
* Multiple channels → Test each channel separately
+++

+++**Question 4: When in the workflow?**

* Before building → [Personalization playground](#test--approve-content) for learning
* During building → [Test profiles](#choose-your-testing-approach) and [sample input data](#choose-your-testing-approach) for validation
* Before launch → [Rendering tests](#2-technical-validation), [spam checks](#2-technical-validation), [conflict detection](#test--approve-content), [approvals](#test--approve-content)
* After launch → [Live reports](../using/building-journeys/report-journey.md) and [monitoring](#test--approve-content)
+++

-->

## テストアプローチの選択

適切なテストアプローチは、作成している内容と検証する必要がある内容によって異なります。このガイドを使用すると、シナリオに最も関連性の高いテストツールを特定できます。

>[!BEGINTABS]

>[!TAB キャンペーンのテスト]

**すべてのキャンペーンの場合：**

* [テストプロファイル](../using/content-management/test-profiles.md)または[サンプル入力データ](../using/test-approve/simulate-sample-input.md)を使用してコンテンツをプレビューおよびテストします
* デバイスおよびクライアントをまたいだ[メールレンダリング](../using/content-management/rendering.md)を確認します（メールチャネルのみ）
* [スパムスコアの確認](../using/content-management/spam-report.md)を実行します（メールチャネルのみ）
* 他のキャンペーンやジャーニーとの[競合](../using/conflict-prioritization/conflicts.md)をレビューします
* 関係者の監視用に[シードリスト](../using/configuration/seed-lists.md)を設定します（メールチャネルのみ）
* アクティブ化前に[承認](../using/test-approve/gs-approval.md)用に送信します

**A/B テストと最適化の場合：**

* 複数の処理をテストし、パフォーマンスを測定する[コンテンツ実験](../using/content-management/get-started-experiment.md)を作成します

**API トリガーキャンペーンの場合：**

* [Campaign Simulation API](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target-&quot;_blank&quot;}を使用して、本配信前確認ジョブをプログラムでトリガーします

>[!TAB ジャーニーのテスト]

**すべてのジャーニーの場合：**

* [テストモード](../using/building-journeys/testing-the-journey.md)を使用して、プロファイルの進行状況をシミュレートするか（ドラフトジャーニーのみ、名前空間が必要）、[ドライラン](../using/building-journeys/journey-dry-run.md)を使用して、メッセージを送信せずに実行パスを分析します
* [プレビューと本配信前確認](../using/content-management/preview-test.md)を使用して個々のメッセージをテストします
* 他のジャーニーやキャンペーンとの[競合](../using/conflict-prioritization/conflicts.md)を確認します
* 公開前に[承認](../using/test-approve/gs-approval.md)用に送信します

**複雑なジャーニーの場合：**

* テストモードとドライランを連携して使用して、分岐ロジックと実行パスを徹底的に検証します
* 様々なエントリ条件とプロファイル属性を体系的にテストします

**メモ：**&#x200B;競合の検出とジャーニーキャッピングは、単一、オーディエンスの選定、オーディエンスを読み取りジャーニーでのみ使用できます。

>[!TAB パーソナライゼーションのテスト]

**コンテンツ作成前：**

* [パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)で実験して、構文を学び、サンプルデータを使用して式をテストします

**コンテンツ作成中：**

* [テストプロファイル](../using/content-management/test-profiles.md)を使用してプレビューし、パーソナライゼーションが正しくレンダリングされることを確認します
* CSV／JSON ファイルからの[サンプル入力データ](../using/test-approve/simulate-sample-input.md)を使用して、複数のシナリオをテストします（最大 30 のバリアントをサポート）

>[!ENDTABS]

## テストのベストプラクティス

テストの効果を最大化するために、次の推奨プラクティスに従ってください。

1. **早期で頻繁にテスト** - キャンペーンが完全に作成されるまで待たないでください。開発に合わせて、コンテンツ、パーソナライゼーションおよびロジックを増分的にテストします。

1. **現実的なテストプロファイルを使用** - エッジケースや様々なパーソナライゼーションシナリオを含め、ターゲットオーディエンスセグメントを正確に表す[テストプロファイルを作成](../using/audience/creating-test-profiles.md)します。

1. **デバイスとクライアントをまたいでテスト** - 一般的なメールクライアント（Gmail、Outlook、Apple メール）とデバイス（デスクトップ、モバイル、タブレット）で[メールのレンダリング](../using/content-management/rendering.md)を確認して、表示に一貫性があることを確認します（メールチャネルのみ）。

1. **パーソナライゼーションを徹底的に検証** - 属性値が異なる複数の[テストプロファイル](../using/content-management/test-profiles.md)を使用してテストし、パーソナライゼーショントークンが正しくレンダリングされ、フォールバック値が機能することを確認します。[パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)を使用して、キャンペーンに適用する前に、パーソナライゼーション式を実験し、サンプルデータを使用してコードをテストします。

1. **サンプルデータを使用してコンテンツバリエーションをテスト** - CSV または JSON ファイルからの[サンプル入力データ](../using/test-approve/simulate-sample-input.md)を使用して、多数のテストプロファイルを作成することなく最大 30 のパーソナライゼーションシナリオをテストすることで、包括的なカバレッジを確保しながら時間を節約できます。メール、SMS、プッシュ通知、web、コードベースのエクスペリエンス、アプリ内、コンテンツカードの各チャネルをサポートしています。

1. **関係者の監視にシードリストを使用** - [シードリスト](../using/configuration/seed-lists.md)を設定して、実行時にすべての配信のコピーを受信する内部の関係者を自動的に追加し、品質監視とコンプライアンス検証を行います（メールチャネルのみ）。

1. **ジャーニーパスをシミュレート** - 複数の分岐を持つ複雑なジャーニーの場合は、[テストモード](../using/building-journeys/testing-the-journey.md)を使用して、様々なエントリ条件とプロファイル属性をテストし、可能なすべてのパスを検証します。名前空間を使用するドラフトジャーニーで使用できます。

1. **配信品質指標を確認** - 大量の送信を行う前に、[スパムスコア](../using/content-management/spam-report.md)、認証ステータス、メールの健全性指標をレビューします（メールチャネルのみ）。

1. **テスト結果を文書化** - テスト結果、見つかった問題、解決策の記録を保持して、今後のテストプロセスを改善し、チームと学習内容を共有します。

1. **関係者を早期に関与** - [正式な承認](../using/test-approve/gs-approval.md)前にプレビューとテスト結果を関係者と共有し、フィードバックを収集して、期待値を一致させます。

## 推奨テストワークフロー

キャンペーンとジャーニーをローンチ前に検証するには、次の 4 つのフェーズのアプローチに従ってください。

| フェーズ | テストする内容 | 主要なアクション |
|-------|-------------|-------------|
| **1. コンテンツの検証** | パーソナライゼーション、デザイン、レンダリング | [テストプロファイルを使用してプレビュー](../using/content-management/preview-test.md)し、CSV／JSON を使用して[複数のバリエーション](../using/test-approve/simulate-sample-input.md)をテストし、デバイスをまたいで[レンダリング](../using/content-management/rendering.md)を確認します |
| **2. 技術確認** | 配信品質、リンク、競合 | [スパムスコアの確認](../using/content-management/spam-report.md)を実行し、リンクを検証し、他のキャンペーンとの[競合](../using/conflict-prioritization/conflicts.md)を確認します |
| **3. ジャーニーロジック**（ジャーニーのみ） | エントリ条件、フロー、分岐 | [テストモード](../using/building-journeys/testing-the-journey.md)を使用して進行状況をシミュレートし、複雑なパスに対して[ドライラン](../using/building-journeys/journey-dry-run.md)を実行します |
| **4. ローンチ前** | 設定、承認、監視 | [承認](../using/test-approve/gs-approval.md)のために送信し、スケジュールとオーディエンスを確認し、[アラート](../using/reports/alerts.md)を有効にします |

**プロのヒント：**&#x200B;コンテンツを作成する前に[パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)から開始して式をテストし、ローンチ前に常に[競合の検出](../using/conflict-prioritization/conflicts.md)を確認して、過剰なメッセージを防ぎます。

## アクションのテスト：ユースケース

テストの概念が実際のシナリオに適用される仕組みを確認します。

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../using/building-journeys/journeys-uc.md">
<img alt="マルチチャネルメッセージの送信" src="../using/assets/do-not-localize/start-journey.jpeg">
</a>
<div>
<a href="../using/building-journeys/journeys-uc.md"><strong>マルチチャネルメッセージの送信</strong></a>
</div>
<p>
オーディエンスを読み取り、反応イベント、メール／プッシュメッセージを組み合わせたジャーニーをテストします。オーディエンスターゲティングからメッセージ配信までのフロー全体を検証します。マルチチャネルの調整、反応イベント、エンドツーエンドのフロー検証、テスト／公開手順に焦点を当てます。
</p>
</td>
<td>
<a href="../using/building-journeys/message-to-subscribers-uc.md">
<img alt="サブスクライバーへのメッセージの送信" src="../using/assets/do-not-localize/start-quick.png">
</a>
<div>
<a href="../using/building-journeys/message-to-subscribers-uc.md"><strong>サブスクライバーへのメッセージの送信</strong></a>
</div>
<p>
動的なメールアドレスを使用して、購読リストをターゲットにするジャーニーをテストします。正しいサブスクライバーターゲティング用にパーソナライゼーション式を検証します。パーソナライゼーション式、動的なアドレス指定、購読リストのターゲティングに焦点を当てます。
</p>
</td>
<td>
<a href="../using/building-journeys/weekday-email-uc.md">
<img alt="時間制限のあるメッセージの送信" src="../using/assets/do-not-localize/calendar.jpeg">
</a>
<div>
<a href="../using/building-journeys/weekday-email-uc.md"><strong>時間制限のあるメッセージの送信</strong></a>
</div>
<p>
特定の日にメッセージが送信されることを確保するために、時間ベースの条件を使用してジャーニーをテストします。 待機アクティビティとスケジュールロジックを検証します。 時間ベースの条件、待機アクティビティ、スケジュールの検証に焦点を当てます。
</p>
</td>
</tr></table>

<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="../using/building-journeys/jo-use-cases.md">
<img alt="その他のジャーニーユースケースを探索" src="../using/assets/do-not-localize/icon-quick-start.svg">
</a>
<div>
<a href="../using/building-journeys/jo-use-cases.md"><strong>その他のジャーニーユースケースを探索</strong></a>
</div>
<p>
エクスペリエンスイベント、マルチチャネルメッセージ、外部システム統合を対象とした実用的な例の包括的なコレクションにアクセスします。様々なシナリオ、高度なパターン、統合テストのアプローチについて説明します。
</p>
</td>
</tr></table>

## 主な用語

Journey Optimizer のテスト機能と承認機能をより深く理解するには、次の基本的なテストの概念を理解します。各用語は、詳細なドキュメントにリンクしています。

**[テストプロファイル](../using/content-management/test-profiles.md)** - パーソナライズされたコンテンツをプレビューするために使用される合成顧客プロファイル（実際の顧客ではありません）。リアルタイム顧客プロファイルサービスでフラグが付けられました。テストモードとコンテンツのプレビューに必須です。[テストプロファイルの作成方法を学ぶ](../using/audience/creating-test-profiles.md)

**[テストモード](../using/building-journeys/testing-the-journey.md)** - ジャーニーパスを通じてテストプロファイルを送信するジャーニーシミュレーション機能。制限事項：ドラフトジャーニーのみ、名前空間が必須、テストプロファイルのみ。[詳しくは、テストモードのドキュメントを参照してください](../using/building-journeys/testing-the-journey.md)

**[ドライラン](../using/building-journeys/journey-dry-run.md)** - メッセージの送信や API 呼び出しを行わずにパスを追跡するジャーニー実行分析ツール。ユースケース：リソースを消費せずにロジックを検証します。[ドライランの詳細情報](../using/building-journeys/journey-dry-run.md)

**[サンプル入力データ](../using/test-approve/simulate-sample-input.md)** - パーソナライゼーションをテストするためのプロファイル属性値を含む CSV または JSON ファイル。最大 30 のバリアントをサポートしています。テストプロファイルを作成する代わりに使用できます。[コンテンツバリエーションのシミュレート方法](../using/test-approve/simulate-sample-input.md)

**[シードリスト](../using/configuration/seed-lists.md)** - 内部関係者のメールアドレスが実際の配信（テスト送信ではない）に自動的に含まれます。 メールチャネルのみ。ユースケース：品質監視とコンプライアンス。[シードリストの設定](../using/configuration/seed-lists.md)

**[コンテンツ実験](../using/content-management/get-started-experiment.md)** - コンテンツのバリエーションを比較する A/B テストまたはマルチアームバンディット実験。キャンペーンのみ。ジャーニーでは使用できません。[実験の基本を学ぶ](../using/content-management/get-started-experiment.md) | [実験の作成](../using/content-management/content-experiment.md)

**[本配信前確認](../using/content-management/proofs.md)** - テストプロファイルデータを使用して、特定のメールアドレスに送信されるメールの配信をテストします。シードリストとは異なります（本配信前確認は手動のテスト送信、シードリストは関係者への自動的なコピーです）。[本配信前確認の送信](../using/content-management/proofs.md)

**[競合の検出](../using/conflict-prioritization/conflicts.md)** - 同じオーディエンスをターゲットにする重複するキャンペーンとジャーニーを特定するツール。限定的なジャーニーのサポート：単一、オーディエンスの選定、オーディエンスを読み取りタイプのみ。[競合管理の詳細情報](../using/conflict-prioritization/gs-conflict-prioritization.md)

**[承認ワークフロー](../using/test-approve/gs-approval.md)** - アクティブ化の前に関係者の承認を必要とするマルチステップのレビュープロセス。承認ポリシーの設定が必要です。[承認の設定](../using/test-approve/gs-approval.md) | [ポリシーの作成](../using/test-approve/approval-policies.md)

**[レンダリングテスト](../using/content-management/rendering.md)** - メールクライアント（Gmail、Outlook、Apple メール）およびデバイスをまたいだメール表示の検証。Litmus 統合が必要です。[メールのレンダリングのテスト](../using/content-management/rendering.md)

**[パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)** - パーソナライゼーション構文を使用して実験し、サンプルデータを使用して式をテストするインタラクティブな学習環境。ライブデータセットは必要ありません。[プレイグラウンドへのアクセス](../using/personalization/personalize.md#playground)

## その他のリソース

>[!BEGINTABS]

>[!TAB 基本的なガイド]

* [コンテンツバリエーションのシミュレート](../using/test-approve/simulate-sample-input.md) - CSV または JSON ファイルを使用して最大 30 のパーソナライゼーションシナリオをテストします。複数のテストプロファイルを作成しない多言語コンテンツのテストに最適です。メール、SMS、プッシュ、web、コードベース、アプリ内、コンテンツカードをサポートしています。

* [テストプロファイルの作成](../using/audience/creating-test-profiles.md) - 顧客シナリオをシミュレートするためのテストプロファイルを作成および管理します。テスト用のプロファイルにフラグを付ける方法、属性を設定する方法、テストセグメントを整理する方法について説明します。

* [メールスパムレポート](../using/content-management/spam-report.md) - 送信前にスパムスコアを確認して、配信品質とインボックスへの配置を改善します。コンテンツの最適化に関する実用的なレコメンデーションを取得します。

* [ジャーニーに関する FAQ](../using/building-journeys/journey-faq.md) - ジャーニーのテスト、実行、トラブルシューティングに関するよくある質問のクイックリファレンス。

>[!TAB 依存関係と関係]

テスト機能が相互に接続される仕組みと、より広範な Journey Optimizer ワークフローに接続される仕組みについて説明します。この節では、前提条件、アップストリーム／ダウンストリームの依存関係、一般的な機能の組み合わせをマッピングします。

+++**前提条件（テスト前に必須）**

* テストモードまたはコンテンツプレビューを使用する前に、テストプロファイルを作成する必要があります
* 承認のために送信する前に、承認ポリシーを設定する必要があります
* キャンペーン／ジャーニーに追加する前に、シードリストを作成する必要があります
* メールレンダリングテストには Litmus 統合が必須です
* テストモードを使用するには、ジャーニーがドラフトステータスである必要があります
* テストモードを使用するには、ジャーニーに名前空間が設定されている必要があります

+++

+++**テストが依存する内容（アップストリーム）**

* コンテンツの作成：テストするには、キャンペーンまたはジャーニーが必要です
* テストプロファイル：テストモードとコンテンツのプレビューに必須です
* 承認ポリシー：承認ワークフローに必須です
* 設定：チャネル設定、メール認証、ドメイン設定

+++

+++**テストに依存する内容（ダウンストリーム）**

* キャンペーン／ジャーニーのアクティブ化：エラーを解決しないとアクティブ化できません
* 公開：公開前に承認が必須になる場合があります
* ライブ監視：ローンチ後の監視とレポート
* 最適化：テスト結果を使用して今後のキャンペーンを絞り込みます

+++

+++**関連機能**

* テスト + 承認ワークフロー - 品質保証プロセス
* テスト + 競合の検出 - 顧客の過剰なメッセージを防ぎます
* テスト + コンテンツ実験 - パフォーマンスの最適化
* テスト + レポート - 継続的な改善サイクル
* テストプロファイル + パーソナライゼーション - コンテンツの検証
* ドライラン + テストモード - 包括的なジャーニー検証

+++

+++**一般的な機能の組み合わせ**

* コンテンツテスト：テストプロファイル + サンプル入力データ + パーソナライゼーションプレイグラウンド
* メール検証：レンダリングテスト + スパムスコア + テストプロファイル + 本配信前確認
* ジャーニー検証：テストモード + ドライラン + テストプロファイル
* ローンチ前のチェックリスト：すべての技術テスト + 競合の検出 + 承認ワークフロー

+++

>[!TAB よくある質問]

+++**Q：キャンペーンを開始する前に必要なテストは何ですか？**

**最小：**テストプロファイルを使用したコンテンツプレビュー + スパムスコアの確認（メール）
**推奨：**+ メールレンダリング + 競合の検出 + 承認ワークフロー
**ベストプラクティス：**+ サンプル入力データのテスト + シードリスト + A/B テスト（最適化する場合）

+++

+++**Q：多くのテストプロファイルを作成せずにパーソナライゼーションをテストするにはどうすればよいですか？**

**主な解決策：** CSV／JSON ファイルで[サンプル入力データ](../using/test-approve/simulate-sample-input.md)を使用します（最大 30 のバリアントをサポート）
**代替策：**&#x200B;主要なセグメントを対象とする 3～5 の代表的な[テストプロファイル](../using/audience/creating-test-profiles.md)を作成します
**学習ツール：**&#x200B;最初に[パーソナライゼーションプレイグラウンド](../using/personalization/personalize.md#playground)で実験します

+++

+++**Q：ジャーニーのテストモードとドライランの違いは何ですか？**

**テストモード：**ジャーニーを通じてテストプロファイルを送信し、実際のアクションをトリガーし、テストメッセージを生成します。ドラフトジャーニー + 名前空間が必要です。
**ドライラン：**何も送信せずに実行パスを追跡します。任意のジャーニーステータスで機能します。メッセージは送信されず、アクションは実行されません。
**連携して使用：**&#x200B;メッセージテストのテストモード + ロジック検証のドライラン - 包括的なカバレッジ。

+++

+++**Q：ジャーニーを実稼動／ライブステータスでテストできますか？**

**テストモード：**不可 - ドラフトジャーニーのみ実行できます
**ドライラン：**可 - 任意のジャーニーステータスで機能します
**コンテンツプレビュー：**可 - 個々のメッセージをいつでもプレビューできます
**回避策：**&#x200B;ライブジャーニーをドラフトに複製して完全なテストモードを検証します

+++

+++**Q：外部統合が必要なテスト機能はどれですか？**

**メールのレンダリング：**Litmus 統合が必須です（個別ライセンス）
**その他すべて：**Journey Optimizer に搭載されています。追加の統合は必要ありません
**メモ：**&#x200B;テストプロファイルには、リアルタイム顧客プロファイルサービス（付属）が必須です

+++

+++**Q：API トリガーキャンペーンをテストするにはどうすればよいですか？**

**オプション 1：**[Campaign Simulation API](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target-&quot;_blank&quot;} を使用してプログラムによるテストを行います
**オプション 2：**UI でテストプロファイルを使用してコンテンツをプレビューします
**オプション 3：**テストメールアドレスに本配信前確認を送信します
**ベストプラクティス：**&#x200B;包括的な検証のためにこれら 3 つを組み合わせます

+++

>[!ENDTABS]
