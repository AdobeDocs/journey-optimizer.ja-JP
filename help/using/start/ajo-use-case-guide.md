---
solution: Journey Optimizer
product: journey optimizer
title: 最適なJourney Optimizer機能の選定
description: 実践的なチュートリアルにより、一般的な実務担当者の目標を適切なAdobe Journey Optimizer機能にマッピングし、達成したい目標に適したツールを見つけて、すばやく開始するための目標ファーストの意思決定ガイド。
feature: Get Started
topic: Content Management
role: User
level: Beginner
keywords: journey optimizer, ユースケース，意思決定ガイド，どの機能，使い始める，実務担当者の目標，チュートリアル
source-git-commit: 727d99f93d3fc19848f00ab423ec320a092b357c
workflow-type: tm+mt
source-wordcount: '1566'
ht-degree: 22%

---

# 最適なJourney Optimizer機能の選定 {#ajo-use-case-guide}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;実行したい処理から開始し、その処理を行うAdobe Journey Optimizer機能に移動します。機能名を最初に知る必要はありません。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer]は多くの機能を提供しており、適切な機能は達成しようとしている内容によって異なります。 このガイドでは、製品の機能ではなく、ビジネス目標について説明します。必要に応じた目標を見つけたら、リンクをクリックして推奨機能から始めます。

このページをクイックルーターとして使用する – 目標をスキャンし、適切な機能に直接ジャンプします。 ガイド付きのステップバイステップの手順とビデオに従いたい場合は、代わりに[&#x200B; オンボーディングハブ &#x200B;](onboarding-hub.md)から始めてください。

特定のシナリオではエンドツーエンドのチュートリアルが利用できない場合は、リンクをクリックすると、現在の最適な出発点に移動して機能を学習し、開始できます。

AIは、これらの機能の多くに組み込まれています。以下の表で&#x200B;**（AI）** タグを探してください。 会話型の[AI アシスタント &#x200B;](ai-features.md#ai-assistant)は、製品に関する質問に答えたり、ジャーニーに関する運用上のインサイトをいつでも確認したりすることもできます。 インテリジェント機能の完全なセットについては、[AIとインテリジェント機能](ai-features.md)を参照してください。

>[!TIP]
>
>Journey Optimizerを初めて利用する場合 [&#x200B; オンボーディングハブ &#x200B;](onboarding-hub.md)で、ステップバイステップの手順、厳選されたユースケース、ビデオをご覧ください。 また、[Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"} （ビデオとガイド付きチュートリアル）をすべて参照し、エキスパートが監修した[&#x200B; ビデオプレイリスト &#x200B;](https://experienceleague.adobe.com/en/playlists?solution=Journey+Optimizer){target="_blank"}に従い、[&#x200B; トレーニングサンドボックス &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/configure-a-training-sandbox/introduction-and-prerequisites){target="_blank"}または[実践的な課題](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/challenges/introduction-and-prerequisites){target="_blank"}で練習することもできます。

## Journey Optimizerの導入 {#setup-admin}

ジャーニーまたはキャンペーンを構築する前に環境を設定する必要がある管理者および技術ユーザー向け。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| 送信前に電子メール、SMSまたはプッシュチャネルを設定する | チャネル設定 | [&#x200B; チャネル設定の基本を学ぶ](../configuration/get-started-configuration.md) |
| メール送信用に新しいIP アドレスをウォームアップする | IP ウォームアッププラン | [IP ウォームアップの基本を学ぶ](../configuration/ip-warmup-gs.md) |
| 役割、権限、アクセス制御の設定 | アクセス制御 | [&#x200B; アクセス制御の基本を学ぶ](../administration/permissions-overview.md) |
| 複数の環境や地域をまたいで作業 | サンドボックス | [サンドボックスの操作](../administration/sandboxes.md) |

## リアルタイムで顧客とエンゲージ {#engage-real-time}

顧客のアクションやイベントに反応するシナリオの場合。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| 新規顧客や購読者を自動的に歓迎する | イベントトリガージャーニー | [&#x200B; ジャーニーの基本を学ぶ](../building-journeys/journey-gs.md) ・ [&#x200B; ジャーニーの構築の概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/introduction-to-building-a-journey){target="_blank"} |
| 放棄されたカートの回復またはセッションの閲覧 | イベントトリガージャーニー | [&#x200B; ジャーニーの基本を学ぶ](../building-journeys/journey-gs.md) ・ [放棄された参照チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma){target="_blank"} |
| web サイトフォーム送信からのジャーニーのトリガー | イベントトリガージャーニー | [&#x200B; ジャーニーの基本を学ぶ](../building-journeys/journey-gs.md) ・ [&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/trigger-journey-on-form-submission/introduction){target="_blank"} |
| アプリ内の動作に反応する（アプリを開く、画面表示） | ジャーニー + アプリ内 | [&#x200B; アプリ内で使い始める](../in-app/get-started-in-app.md) |
| 注文、発送、または予約の確認を送信する | API トリガーキャンペーン | [API トリガーによるキャンペーンの操作](../campaigns/api-triggered-campaigns.md) |
| 非アクティブな顧客や離脱した顧客のリエンゲージメント | ジャーニー+オーディエンス | [&#x200B; プロファイルとオーディエンスの概要](../audience/get-started-profiles.md) ・ [&#x200B; ルールビルダーを使用したオーディエンスの作成](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/profiles-audiences-subscriptions/create-audiences-using-the-rule-builder){target="_blank"} |
| アクティベートする前に、実際のデータでジャーニーをテストする | ジャーニードライラン | [&#x200B; ドライランでジャーニーをテスト &#x200B;](../building-journeys/journey-dry-run.md) |
| 実行中のプロファイルを停止せずにライブジャーニーを一時停止して編集 | ジャーニーの一時停止と再開 | [&#x200B; ジャーニーを一時停止して再開](../building-journeys/journey-pause.md) |
| 自然言語プロンプトからジャーニーを構築または最適化する | Journey Agent **（AI）** | [AI エージェント &#x200B;](ai-features.md#ai-agents) ・ [Journey Agent チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-agent-overview){target="_blank"} |

## オーディエンスへの大規模なリーチ {#reach-at-scale}

スケジュールされた一対多のアウトリーチを定義されたオーディエンスに実行できます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| ニュースレターやプロモーションをセグメントに送信する | 予定キャンペーン | [キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md) |
| A/B テストで製品を発売する | コンテンツ実験&#x200B;**（AI）** | [&#x200B; コンテンツの実験を開始](../content-management/experiment-accelerator-gs.md) ・ [&#x200B; メールキャンペーンのコンテンツの実験を作成](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/experimentation/content-experiments-for-emails){target="_blank"} |
| 停止またはサービスの更新を顧客に通知 | スケジュール済みキャンペーン + オーディエンス | [&#x200B; オーディエンスについて](../audience/about-audiences.md) |
| 分岐ロジックを使用したマルチステップのキャンペーンの設計 | オーケストレーションキャンペーン | [&#x200B; オーケストレーションされたキャンペーンの開始](../orchestrated/gs-orchestrated-campaigns.md) |
| 前回のキャンペーン実行以降に変更されたプロファイルのみをターゲット | オーケストレーションされたキャンペーン – 増分クエリ | [&#x200B; オーケストレーションされたキャンペーンでクエリを作成](../orchestrated/build-query.md) <!-- TODO: verify target — no dedicated "incremental query" page found; build-query.md ("Build your first rule") is the closest existing page --> |
| ローンチ前に、オーディエンスに一致するプロファイル数を確認する | オーディエンスプレビュー | [&#x200B; オーディエンスについて](../audience/about-audiences.md) <!-- TODO: verify target — no "create-compositions.md#preview" page/anchor exists; about-audiences.md used as placeholder --> |
| 多くのチャネルをまたいだメッセージを大規模に調整 | オーケストレーション | [オーケストレーションのオムニチャネルエンゲージメントへの拡大](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/scaling-orchestration-to-omnichannel-engagement/introduction){target="_blank"} |
| 顧客一人ひとりに最適なタイミングでメッセージを配信 | 送信時間の最適化&#x200B;**（AI）** | [送信時間の最適化](../building-journeys/send-time-optimization.md) |

## 顧客一人ひとりに合わせてコンテンツをパーソナライズ {#personalize}

一人ひとりに合わせてオファーとコンテンツを調整できます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| それぞれの顧客に最適なオファーを表示 | 決定 | [&#x200B; オファー決定の基本を学ぶ](../offers/get-started/starting-offer-decisioning.md) ・ [Web オファーチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/use-decisioning-to-personalize-web-offers/introduction){target="_blank"} |
| 数式を使用してオファーをランク付け（郵便番号、収入、天気） | Decisioning — ランキング式 | [&#x200B; ランキング式チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-ranking-formulas-based-on-user-zip-code-and-income/introduction){target="_blank"} ・ [天気データチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction){target="_blank"} |
| 外部製品やCRM データを使用してオファーをパーソナライズ | 決定：AEPデータセットの検索 | [決定でデータセット検索を使用](../experience-decisioning/context-data.md) |
| プロファイルデータを使用したメッセージコンテンツのカスタマイズ | パーソナライゼーション | [&#x200B; コンテンツのパーソナライズ &#x200B;](../personalization/personalize.md) |
| コピー、画像、メッセージのバリエーションを生成 | AI コンテンツ生成&#x200B;**（AI）** | [AI コンテンツ生成](../content-management/gs-generative.md) ・ [&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/content-management/ai-assistant/ai-assistant-for-content-generation-overview){target="_blank"} |
| デザイン画像を編集可能なメールテンプレートに変換する | HTML コンバータ **（AI）**&#x200B;への画像 | [画像を電子メールテンプレートに変換](../content-management/image-to-html.md) |
| オファーを自動的にランク付けしてパーソナライズ | AI ランキング モデル **（AI）** | 決定のための[AI モデル &#x200B;](../experience-decisioning/ranking/ai-models.md) |
| 常時対応可能なコンテキストコンテンツを提供（キャンペーン不要） | コンテンツカード | [&#x200B; コンテンツカードの基本を学ぶ](../content-card/get-started-content-card.md) ・ [&#x200B; コンテンツカードを作成する](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/channels/content-cards/create-content-cards){target="_blank"} |
| APIを介してパーソナライズされたコンテンツを、あらゆるアプリやサーフェスに配信 | コードベースのエクスペリエンス | [&#x200B; コードベースのエクスペリエンスの基本を学ぶ](../code-based/get-started-code-based.md) |
| チームが編集できるメールテンプレートの部分の制御 | コンテンツのロック | [&#x200B; メールテンプレート内のコンテンツをロック &#x200B;](../content-management/content-locking.md) |

## 配信の調整と管理 {#coordinate-govern}

チャネルをまたいで顧客に連絡する方法、タイミング、頻度を制御できます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| チャネルをまたいでメッセージの疲労を防ぐ | フリークエンシーキャップ | [&#x200B; チャネル別に頻度の上限を設定](../conflict-prioritization/channel-capping.md) |
| 競合するメッセージや競合するメッセージの解決 | 競合の優先順位付け | [潜在的な競合の特定](../conflict-prioritization/conflicts.md) ・ [&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/conflict-management/identify-potential-conflicts){target="_blank"} |
| どのジャーニーを優先するかを決める | ジャーニーの判別 | [数式を使用してジャーニーをランク付け](../conflict-prioritization/journey-ranking-formulas.md) |
| サイレントアワーと同意の尊重 | サイレントアワー/プライバシー | [&#x200B; サイレントアワーを設定](../conflict-prioritization/quiet-hours.md) |
| チャネルをまたいで同意ポリシーとデータ使用ラベルを適用したい | 同意とデータガバナンス | [&#x200B; プライバシーの基本を学ぶ](../privacy/get-started-privacy.md) |
| ジャーニーのエラー率が高い、または破棄される場合にアラートを受け取る | ジャーニーアラート | [&#x200B; ジャーニーアラートの設定](../reports/alerts.md) |

## 配信するチャネルの選択 {#choose-channel}

| 送りたいです… | チャネル | ここから開始 |
| --- | --- | --- |
| メールマガジン、プロモーション、トランザクションメッセージ | メール | [電子メールの基本を学ぶ](../email/get-started-email.md) |
| モバイルプッシュ通知（iOSおよびAndroid） | プッシュ | [&#x200B; プッシュ通知の基本を学ぶ](../push/get-started-push.md) |
| SMS、MMS、RCSのテキストメッセージ | SMS/MMS/RCS | [SMS/MMS/RCS](../mobile/get-started-mobile.md)の基本を学ぶ・ [&#x200B; モバイル学習ハブ &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/mobile-learning-hub/overview){target="_blank"} |
| Meta Cloud API経由のWhatsApp メッセージ | WhatsApp | [WhatsApp の基本を学ぶ](../whatsapp/get-started-whatsapp.md) |
| ブラウザー内またはアプリ内のオーバーレイとバナー | アプリ内 | [&#x200B; アプリ内で使い始める](../in-app/get-started-in-app.md) |
| パーソナライズされたweb ページコンテンツ | Web | [Web チャネルの基本を学ぶ](../web/get-started-web.md) |
| API経由のあらゆるサーフェス（キオスク、接続デバイス、ヘッドレスアプリ） | コードベースのエクスペリエンス | [&#x200B; コードベースのエクスペリエンスの基本を学ぶ](../code-based/get-started-code-based.md) |
| ジャーニーからトリガーされた物理的なメールの部分 | ダイレクトメール | [&#x200B; ダイレクトメールの基本を学ぶ](../direct-mail/get-started-direct-mail.md) |

## 測定と最適化 {#measure-optimize}

パフォーマンスの追跡、問題の診断、長期的な結果の改善に役立ちます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| ライブジャーニーまたはキャンペーンのパフォーマンス指標を参照する | ライブレポート | [&#x200B; ライブレポート &#x200B;](../reports/live-report.md) ・ [&#x200B; ライブレポートでジャーニーを監視して分析](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/report-and-monitor/monitor-and-analyze-your-journey-with-live-reports){target="_blank"} |
| キャンペーンやジャーニーのパフォーマンス全体を終了後にレポートできます | グローバルレポート | [レポートの概要](../reports/gs-reports.md) |
| 実験を分析して次のステップのレコメンデーションをゲット | Experimentation Agent **（AI）** | [Experimentation Agent](ai-features.md#experimentation-agent) ・ [&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/experimentation/experimentation-agent-overview){target="_blank"} |
| ジャーニー内のカスタムアクションの正常性と遅延を監視する | カスタムアクションの監視 | [&#x200B; カスタムアクションを使用](../building-journeys/using-custom-actions.md) <!-- TODO: verify target — no dedicated "custom-action-monitoring.md" page found; using-custom-actions.md is the closest existing page --> |
| ジャーニーエラーまたは破棄の率がしきい値を超えた場合にアラートを受け取る | ジャーニーアラート | [&#x200B; ジャーニーアラートの設定](../reports/alerts.md) |

## わからない場合 {#not-sure}

目標がご存知の用語にマッピングされている場合、またはテーブルがどの機能を指しているかわからない場合は、[Journey Optimizerの主要用語](terminology.md) ページから始めて、各機能の背後にある概念を明確にします。

また、[Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"}のエンドツーエンドの演習を使用して、実践的な自信を築くこともできます。
