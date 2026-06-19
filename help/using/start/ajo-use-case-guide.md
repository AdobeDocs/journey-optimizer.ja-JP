---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerのユースケースの概要| Adobe Journey Optimizer
description: Adobe Journey Optimizerの主なユースケースを紹介し、各シナリオに最適なAJO機能についてガイダンスを提供します。
feature: Get Started
topic: Content Management
role: User
level: Beginner
keywords: journey optimizer, ユースケース，意思決定ガイド，どの機能，使い始める，実務担当者の目標，チュートリアル
source-git-commit: a35c1cd2d99c41cb94c506cebf6c2b2f5e7151cb
workflow-type: tm+mt
source-wordcount: '3153'
ht-degree: 33%

---

# 最適なJourney Optimizer機能の選定 {#ajo-use-case-guide}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;実行したい処理から開始し、その処理を行うAdobe Journey Optimizer機能に移動します。機能名を最初に知る必要はありません。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer]は多くの機能を提供しており、適切な機能は達成しようとしている内容によって異なります。 このガイドでは、製品の機能ではなく、ビジネス目標について説明します。必要に応じた目標を見つけたら、リンクをクリックして推奨機能から始めます。

このページをクイックルーターとして使用する – 目標をスキャンし、適切な機能に直接ジャンプします。 まだ始めたばかりであれば、[Journey Optimizerを使い始める](../../rp_landing_pages/get-started-landing-page.md)で、ご自身の役職に適したエントリ ポイントを見つけます。

>[!NOTE]
>
>ステップバイステップの実装サンプルについては、[ジャーニーユースケースライブラリ &#x200B;](../building-journeys/jo-use-cases.md)を参照してください。

特定のシナリオではエンドツーエンドのチュートリアルが利用できない場合は、リンクをクリックすると、現在の最適な出発点に移動して機能を学習し、開始できます。

AIは、これらの機能の多くに組み込まれています。以下の表で&#x200B;**（AI）** タグを探してください。 会話型の[AI アシスタント &#x200B;](ai-features.md#ai-assistant)は、製品に関する質問に答えたり、ジャーニーに関する運用上のインサイトをいつでも確認したりすることもできます。 インテリジェント機能の完全なセットについては、[AIとインテリジェント機能](ai-features.md)を参照してください。

>[!TIP]
>
>Journey Optimizerを初めて利用する場合 [Journey Optimizerの基本を学び](../../rp_landing_pages/get-started-landing-page.md)から始めて、お客様の役職に適したパスを選び、[Journey Optimizerとは](get-started.md)をお読みください。 実践的な自信を築くには、[Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"}を参照し、エキスパートが監修した[&#x200B; ビデオプレイリスト &#x200B;](https://experienceleague.adobe.com/en/playlists?solution=Journey+Optimizer){target="_blank"}に従い、[&#x200B; トレーニングサンドボックス &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/configure-a-training-sandbox/introduction-and-prerequisites){target="_blank"}または[実践的な課題](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/challenges/introduction-and-prerequisites){target="_blank"}で練習します。

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

>[!BEGINSHADEBOX]

**ビルドする前に、**&#x200B;必ず（1）サインアップトリガーを取得するように設定された[&#x200B; ジャーニーエントリイベント &#x200B;](../event/about-events.md)と、（2）サンドボックス用に設定された[電子メールまたはプッシュチャネルサーフェス &#x200B;](../configuration/channel-surfaces.md)と、（3）公開前にジャーニーを検証するために利用可能な少なくとも1つの[&#x200B; テストプロファイル &#x200B;](../audience/creating-test-profiles.md)を確認してください。

>[!ENDSHADEBOX]

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| 放棄されたカートの回復またはセッションの閲覧 | イベントトリガージャーニー | [&#x200B; ジャーニーの基本を学ぶ](../building-journeys/journey-gs.md) ・ [放棄された参照チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/use-cases/personalization-insights-engagement/use-cases-luma){target="_blank"} |

>[!BEGINSHADEBOX]

**構築する前に：**&#x200B;必要なのは、（1） webまたはモバイル SDKから買い物かごまたはブラウズアクションをキャプチャする[行動イベント &#x200B;](../event/about-events.md)、（2） [待機アクティビティ &#x200B;](../building-journeys/wait-activity.md)戦略が決定された（通常は最初のナッジの1～4時間前）、（3）フォローアップメッセージの準備ができているチャネルサーフェスです。 注意：ジャーニーには、購入期間が終了する前に購入を完了するプロファイルを終了する条件を含める必要があります。

>[!ENDSHADEBOX]

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| web サイトフォーム送信からのジャーニーのトリガー | イベントトリガージャーニー | [&#x200B; ジャーニーの基本を学ぶ](../building-journeys/journey-gs.md) ・ [&#x200B; チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/trigger-journey-on-form-submission/introduction){target="_blank"} |
| アプリ内の動作に反応する（アプリを開く、画面表示） | ジャーニー + アプリ内 | [&#x200B; アプリ内で使い始める](../in-app/get-started-in-app.md) |
| 注文、発送、または予約の確認を送信する | API トリガーキャンペーン | [API トリガーによるキャンペーンの操作](../campaigns/api-triggered-campaigns.md) |
| 非アクティブな顧客や離脱した顧客のリエンゲージメント | ジャーニー+オーディエンス | [&#x200B; プロファイルとオーディエンスの概要](../audience/get-started-profiles.md) ・ [&#x200B; ルールビルダーを使用したオーディエンスの作成](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/profiles-audiences-subscriptions/create-audiences-using-the-rule-builder){target="_blank"} |

>[!BEGINSHADEBOX]

**構築する前に、**&#x200B;必要です（1）非アクティブなプロファイルを特定する[Adobe Experience Platform](../audience/about-audiences.md)で定義されたオーディエンス（60日以内に購入またはログインしない場合など）、（2）リエンゲージメントチャネル（電子メール、プッシュ、SMS）に関する決定、（3）最近メッセージされたプロファイルへの連絡を避けるための抑制ルールまたは[頻度キャップ &#x200B;](../conflict-prioritization/channel-capping.md)。 このシナリオでは、イベントではなく、**オーディエンスを読み取り** ジャーニーエントリを使用します。

>[!ENDSHADEBOX]

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| アクティベートする前に、実際のデータでジャーニーをテストする | ジャーニードライラン | [&#x200B; ドライランでジャーニーをテスト &#x200B;](../building-journeys/journey-dry-run.md) |
| 実行中のプロファイルを停止せずにライブジャーニーを一時停止して編集 | ジャーニーの一時停止と再開 | [&#x200B; ジャーニーを一時停止して再開](../building-journeys/journey-pause.md) |
| 自然言語プロンプトからジャーニーを構築または最適化する | Journey Agent **（AI）** | [AI エージェント &#x200B;](ai-features.md#ai-agents) ・ [Journey Agent チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-agent-overview){target="_blank"} |

## オーディエンスへの大規模なリーチ {#reach-at-scale}

スケジュールされた一対多のアウトリーチを定義されたオーディエンスに実行できます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| ニュースレターやプロモーションをセグメントに送信する | 予定キャンペーン | [キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md) |

>[!BEGINSHADEBOX]

**作成する前に、**&#x200B;必要なのは（1） Adobe Experience Platformで[公開されたオーディエンスセグメント &#x200B;](../audience/about-audiences.md)、（2）検証済みの送信ドメインを含む[&#x200B; メールチャネルサーフェス &#x200B;](../configuration/channel-surfaces.md)、（3）既に公開されている再利用を計画している[&#x200B; コンテンツフラグメントまたはテンプレート &#x200B;](../content-management/fragments.md)です。 スケジュールされたキャンペーンは、1回限りの送信または分岐ロジックのない定期的な送信の場合、ジャーニーではなく、ここに適した選択肢です。

>[!ENDSHADEBOX]

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| A/B テストで製品を発売する | コンテンツ実験&#x200B;**（AI）** | [&#x200B; コンテンツの実験を開始](../content-management/experiment-accelerator-gs.md) ・ [&#x200B; メールキャンペーンのコンテンツの実験を作成](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/experimentation/content-experiments-for-emails){target="_blank"} |
| 停止またはサービスの更新を顧客に通知 | スケジュール済みキャンペーン + オーディエンス | [&#x200B; オーディエンスについて](../audience/about-audiences.md) |
| 分岐ロジックを使用したマルチステップのキャンペーンの設計 | オーケストレーションキャンペーン | [&#x200B; オーケストレーションされたキャンペーンの開始](../orchestrated/gs-orchestrated-campaigns.md) |
| 前回のキャンペーン実行以降に変更されたプロファイルのみをターゲット | オーケストレーションされたキャンペーン – 増分クエリ | [&#x200B; オーケストレーションされたキャンペーンでクエリを作成](../orchestrated/build-query.md) <!-- TODO: verify target — no dedicated "incremental query" page found; build-query.md ("Build your first rule") is the closest existing page --> |
| ローンチ前に、オーディエンスに一致するプロファイル数を確認する | オーディエンスプレビュー | [&#x200B; オーディエンスについて](../audience/about-audiences.md) <!-- TODO: verify target — no "create-compositions.md#preview" page/anchor exists; about-audiences.md used as placeholder --> |
| 多くのチャネルをまたいだメッセージを大規模に調整 | オーケストレーション | [&#x200B; オーケストレーションされたキャンペーンの開始](../orchestrated/gs-orchestrated-campaigns.md) ・ [&#x200B; オーケストレーションをオムニチャネルエンゲージメントに拡張](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/scaling-orchestration-to-omnichannel-engagement/introduction){target="_blank"} |
| 顧客一人ひとりに最適なタイミングでメッセージを配信 | 送信時間の最適化&#x200B;**（AI）** | [送信時間の最適化](../building-journeys/send-time-optimization.md) |

## 顧客一人ひとりに合わせてコンテンツをパーソナライズ {#personalize}

一人ひとりに合わせてオファーとコンテンツを調整できます。

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| それぞれの顧客に最適なオファーを表示 | 決定 | [&#x200B; オファー決定の基本を学ぶ](../offers/get-started/starting-offer-decisioning.md) ・ [Web オファーチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/use-decisioning-to-personalize-web-offers/introduction){target="_blank"} |

>[!BEGINSHADEBOX]

**ビルドする前に、**&#x200B;決定を行うには、特定のセットアップ シーケンスが必要です。 （1）実施要件ルールと属性を持つ[&#128279;](../experience-decisioning/items.md)作成された決定項目（オファー）、（2）設定された[選択戦略](../experience-decisioning/selection-strategies.md)またはランキング式、（3）オファーが表示されるサーフェスに添付された[決定ポリシー](../experience-decisioning/create-decision.md)が必要です。 この順序をスキップすることは、初回決定設定で結果が返されない最も一般的な理由です。

>[!ENDSHADEBOX]

| 私は… | 推奨される機能 | ここから開始 |
| --- | --- | --- |
| 数式を使用してオファーをランク付け（郵便番号、収入、天気） | Decisioning — ランキング式 | [&#x200B; ランキング式](../experience-decisioning/ranking/ranking-formulas.md) ・ [&#x200B; ランキング式チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-ranking-formulas-based-on-user-zip-code-and-income/introduction){target="_blank"} ・ [天気データチュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction){target="_blank"} |
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

## スターターフロー {#starter-flows}

以下の各スターターフローは、成果志向の短い一連のステップです。何を構築し、誰のために構築するのか、それをどのように実現するのか、といったことを明確にします。 最初のプロジェクトに一致する目標を選択し、詳細なドキュメントへのリンクに従います。

### 新規顧客を歓迎する {#flow-welcome}

**次の機能を構築します：**&#x200B;すべての新規購読者に挨拶し、非アクティブな購読者を誘導する自動ウェルカムシリーズ。
**マーケターに最適：** ・ **機能：** イベントトリガージャーニー

1. [統合プロファイルとオーディエンス &#x200B;](../audience/get-started-profiles.md)がサインアップイベントを受け取っていることを確認します。
1. [最初のジャーニー](../building-journeys/journey-gs.md)を作成し、サインアップイベントをエントリとして使用します。
1. ようこそ[電子メール &#x200B;](../email/get-started-email.md)を追加してから、エンゲージしていないプロファイルに対して待機ステップとフォローアップ [&#x200B; プッシュ通知](../push/get-started-push.md)を追加します。
1. [名や表明された関心などのプロファイル属性を使用して、コンテンツ &#x200B;](../personalization/personalize.md)をパーソナライズします。

➡️ [&#x200B; ジャーニーで開始](../building-journeys/journey-gs.md)

### 放棄されたカートの回復 {#flow-cart}

**次の項目を作成します：** リアルタイムの復元フローで、残された項目を顧客に思い出してもらいます。
**マーケターに最適：** ・ **機能：** イベントトリガージャーニー

1. 買い物かごの放棄イベントがJourney Optimizerに届いていることを確認します（必要に応じて[&#x200B; データチーム &#x200B;](../data/gs-data.md)と協力してください）。
1. [放棄イベントによってトリガーされたジャーニー](../building-journeys/journey-gs.md)を作成します。
1. パーソナライズされたリマインダーメールを送信します。24時間以内にクリックがない場合は、[&#x200B; プッシュ &#x200B;](../push/get-started-push.md) フォローアップに分岐します。
1. [放棄されたアイテムとロイヤルティステータスで](../personalization/personalize.md)をパーソナライズします。

➡️ [&#x200B; ジャーニーで開始](../building-journeys/journey-gs.md)

### トランザクションメッセージの送信 {#flow-transactional}

**外部システムによってトリガーされるオンデマンドの注文、配送、または予約の確認を作成します。**
**マーケターと開発者**&#x200B;に最適・ **機能：**&#x200B;外部システムによってトリガーされるキャンペーン

1. 外部システムによってトリガーされた[&#x200B; キャンペーンの仕組みと、期待されるペイロードを確認します。](../campaigns/api-triggered-campaigns.md)
1. メッセージテンプレートをデザインし、トランザクションの詳細を含めて[&#x200B; パーソナライズ &#x200B;](../personalization/personalize.md)します。
1. 開発者に、注文システムまたはフルフィルメントシステムからキャンペーンエンドポイントを呼び出してもらいます。

➡️ [外部システムによってトリガーされたキャンペーンの操作](../campaigns/api-triggered-campaigns.md)

### コンテンツテストによるキャンペーンの立ち上げ {#flow-campaign}

**最もパフォーマンスの高いコンテンツを自動的に選択するスケジュールされたプロモーションを作成します。**
**マーケターに最適：** ・ **機能：** スケジュール済みキャンペーン + コンテンツ実験

1. [&#x200B; キャンペーンを開始し](../campaigns/get-started-with-campaigns.md)、オーディエンスを定義します。
1. [&#x200B; コンテンツ生成](../content-management/gs-generative.md)を使用して、件名のドラフトとバリエーションのコピーを作成します。
1. [&#x200B; コンテンツ実験](../content-management/experiment-accelerator-gs.md)を設定してサンプルのバリエーションをテストし、勝者を残りの部分に送信します。

➡️ [&#x200B; キャンペーンの開始](../campaigns/get-started-with-campaigns.md)

### 顧客ごとのオファーのパーソナライズ {#flow-offers}

**お客様ごとに最適なオファーを表示する決定を作成します。**
**マーケターに最適：** ・ **機能：**&#x200B;決定

1. [&#x200B; オファー決定](../offers/get-started/starting-offer-decisioning.md)を開始し、オファーと実施要件ルールを作成します。
1. 決定を[&#x200B; ジャーニー](../building-journeys/journey-gs.md)またはキャンペーンメッセージに追加します。
1. [&#x200B; インテリジェント機能](ai-features.md)のレイヤーを使用して、オファーを自動的にランク付けおよび最適化できます。

➡️ [&#x200B; オファー決定の開始](../offers/get-started/starting-offer-decisioning.md)

## シナリオ例 {#example-scenarios}

これらの例は、Journey Optimizer の機能が様々な役割、業界、チャネルをまたいで連携する仕組みを示しています。

### 遅延した出荷の復元 {#scenario-delayed-shipment}

**役割：**&#x200B;マーケター | **コア機能：**&#x200B;[統合プロファイル + オーディエンスの除外](../audience/get-started-profiles.md)

衣料品店では通常、先週製品を購入したすべての顧客に、購入後の調査を送信できます。 悪天候のため商品の出荷が遅れている場合は、 衣料品店は、商品をまだ受け取っていない顧客を調べ、スケジュールされた顧客満足度の送信からそれらの顧客を除外することができます。その代わりに、顧客の購入履歴に基づいて、遅延を謝罪し、割引コードと商品レコメンデーション情報を提供する、パーソナライズされたメールを送信できます。

[キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md)

### リアルタイムの店舗内エンゲージメント {#scenario-instore}

**役割：**&#x200B;マーケター | **コア機能：**&#x200B;[ジオフェンストリガー + プッシュ](../push/get-started-push.md)

同じ小売業者は、顧客のサイズの在庫が復活した、セーターに関するプッシュ通知を送信することで、店舗の駐車場に到着した常連客をリアルタイムで惹きつけることができます。

[プッシュ通知の基本を学ぶ](../push/get-started-push.md)

### 買い物かご放棄の回復 {#scenario-cart}

**役割：**&#x200B;マーケター | **コア機能：**&#x200B;[イベントトリガーのマルチステップジャーニー](../building-journeys/journey-gs.md)

顧客がオンライン買い物かごに商品を追加したものの購入を完了せずに離脱した場合、Journey Optimizer はそのイベントをリアルタイムで検出し、自動的にリカバリージャーニーを開始します。 顧客には、残された商品についてリマインドするパーソナライズされたメールが送信されます。 24 時間以内にクリックスルーしない場合、閲覧履歴とロイヤルティステータスに基づいてパーソナライズされたフォローアップのプッシュ通知が送信されます。

[最初のジャーニーの作成](../building-journeys/journey-gs.md)

### ストリーミングサービスウェルカムシリーズ {#scenario-welcome}

**役割：**&#x200B;マーケター | **コア機能：**&#x200B;[イベントトリガーのウェルカムジャーニー](../building-journeys/journey-gs.md)

顧客がストリーミングサービスに登録すると、Journey Optimizer は登録イベントを検出し、すぐにマルチステップのウェルカムジャーニーを開始します。 顧客には、アプリを初めて開くように促すウェルカムメールが送信されます。 48 時間以内にログインアクティビティが検出されない場合、新規登録時に表明された興味に基づいてパーソナライズされたコンテンツレコメンデーションを含むフォローアップのプッシュ通知が送信されます。これにより、受動的な登録者を初日からアクティブでエンゲージメントの高いユーザーに変えることができます。

[最初のジャーニーの作成](../building-journeys/journey-gs.md)

### 道順を含む予約リマインダー {#scenario-reservation}

**役割：**&#x200B;マーケター | **コア機能：**&#x200B;[スケジュール済み + 場所に応じたメッセージ](../campaigns/get-started-with-campaigns.md)

あるホスピタリティブランドは、予約時間の 1 時間前に各ゲストにタイムリーなリマインダーを送信します。 この通知には、ゲストの名前、予約時間、位置に基づいた会場までの道順が含まれます。これらの情報は、マーケティングチームの手作業なしに、顧客プロファイルと予約データから自動的に組み立てられます。

[キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md)

### サービス停止時のプロアクティブな通知 {#scenario-outage}

**役割：**&#x200B;運用 | **コア機能：**&#x200B;[大規模な自動オーディエンス選択](../audience/about-audiences.md)

サービスの中断が発生すると、Journey Optimizer はアカウントデータと使用状況パターンに基づいて影響を受ける顧客を自動的に特定します。 このような顧客には、問題が発生したことを伝え、次のステップを説明するプロアクティブな通知が送信されます。これにより、潜在的に否定的なエクスペリエンスが、透明性と信頼に満ちた瞬間へと変わり、大規模に提供されます。

[最初のジャーニーの作成](../building-journeys/journey-gs.md)

### インテリジェントなプロモーションキャンペーン {#scenario-ai-campaign}

**役割：** マーケター| **コア機能：** [&#x200B; コンテンツ生成+実験](ai-features.md)

新製品ローンチを計画中の小売ブランドは、Journey Optimizer の AI アシスタントを使用し、自然言語によるプロンプトとアップロード済みのブランドガイドラインに従って、数分で複数の件名と本文のバリエーションを生成します。 組み込みのコンテンツ実験機能により、初期オーディエンスサンプルの中から最もパフォーマンスの高いバリアントが自動的に特定されます。 勝利メッセージは残りの受信者にデプロイされ、追加のコピーライティング作業なしでエンゲージメントが最大化されます。

[&#x200B; インテリジェント機能の詳細](ai-features.md) | [&#x200B; コンテンツ実験の詳細](../content-management/experiment-accelerator-gs.md)

### モバイルアプリ経由のメンテナンスアラート {#scenario-maintenance}

**役割：**&#x200B;運用 | **コア機能：**&#x200B;[マーケティング以外のジャーニーオーケストレーション](../building-journeys/journey-gs.md)

運用チームやカスタマーサポートなどのマーケター以外は、[!DNL Adobe Journey Optimizer] を使用して、運用に関する通知を管理したり、オンボーディングプロセスを監視したりできます。 例えば、訪問者がエクスペリエンスの一部としてモバイルアプリをダウンロードするアミューズメントパークでは、メンテナンススタッフが Journey Optimizer を使用して、メンテナンスにより現在閉鎖されている乗り物を訪問者に通知できます。

[最初のジャーニーの作成](../building-journeys/journey-gs.md)

## ビデオライブラリ {#videos}

厳選されたビデオコンテンツをトピック別に参照できます。 各タブには、Experience Leagueの関連チュートリアルとプレイリストへのリンクが表示されます。

>[!BEGINTABS]

>[!TAB はじめに]

* [Journey Optimizerの概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/introduction){target="_blank"} — コアコンセプトと製品ツアー。
* [Journey Optimizer チュートリアルの概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"} — ガイド付きビデオの完全カタログ。

>[!TAB ジャーニーとキャンペーン ]

* [&#x200B; ジャーニーの構築の概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/introduction-to-building-a-journey){target="_blank"} – 最初のイベントトリガージャーニーを構築します。
* [Journey Agentでジャーニーを作成](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-agent-overview){target="_blank"} – 自然言語プロンプトからジャーニーを作成します。

>[!TAB Personalizationとインテリジェンス ]

* [&#x200B; コンテンツ生成用AI アシスタント &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/content-management/ai-assistant/ai-assistant-for-content-generation-overview){target="_blank"} — コピー、画像、バリエーションを生成します。
* [決定機能を使用してweb オファーをパーソナライズ &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/use-decisioning-to-personalize-web-offers/introduction){target="_blank"} – 顧客ごとにオファーをカスタマイズします。

>[!TAB  レポートと最適化]

* [&#x200B; ライブレポートでジャーニーを監視および分析](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/report-and-monitor/monitor-and-analyze-your-journey-with-live-reports){target="_blank"} — パフォーマンスをリアルタイムで追跡します。
* [&#x200B; メールキャンペーンのコンテンツ実験を作成](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/experimentation/content-experiments-for-emails){target="_blank"} — コンテンツをテストおよび最適化します。

>[!ENDTABS]

## ジャーニー、キャンペーン、オーケストレーションされたキャンペーンの選択 {#choosing}

| シナリオ | 用途 |
|----------|-----|
| 顧客行動にもとづくマルチステップで、それぞれの顧客が自分のペースで移動します | ジャーニー |
| オーディエンスへのシンプルなスケジュール済みまたはAPI トリガーのメッセージ | Campaign |
| 複数のエンティティをセグメンテーションする複雑なバッチワークフロー | オーケストレーションキャンペーン |

## わからない場合 {#not-sure}

目標がご存知の用語にマッピングされている場合、またはテーブルがどの機能を指しているかわからない場合は、[Journey Optimizerの主要用語](terminology.md) ページから始めて、各機能の背後にある概念を明確にします。

また、[Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"}のエンドツーエンドの演習を使用して、実践的な自信を築くこともできます。
