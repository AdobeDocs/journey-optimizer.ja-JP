---
solution: Journey Optimizer
product: journey optimizer
title: ユーザーインターフェイス
description: Adobe Journey Optimizer インターフェイスの操作方法を説明します
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
exl-id: 681532f8-1149-465e-92c8-2b5366abc3aa
source-git-commit: b48a8fa89605ac18c6db85751bf71d2ccec08f63
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 34%

---

# インターフェイスの操作 {#user-interface}

Adobe Journey Optimizerにアクセスするには、Adobe IDを使用して [0&rbrace;Adobe Experience Cloud&rbrace; にログインし、「](https://experience.adobe.com)」を選択します。[!DNL Journey Optimizer]

>[!NOTE]
>
>* お使いの環境で使用できるコンポーネントと機能は、[&#x200B; 権限 &#x200B;](../administration/permissions.md) および [&#x200B; ライセンスパッケージ &#x200B;](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"} によって異なります。
>* このドキュメントは頻繁に更新されます。 一部のスクリーンショットは、お使いのインターフェイスと少し異なる場合があります。

## クイックツアー {#quick-tour}

Journey Optimizer インターフェイスは、次の 4 つの主な領域で構成されます。

![](assets/ajo-home.png)

1. **左側のナビゲーション** – 関数別に整理されたすべての機能にアクセスします
2. **上部バー** - ユニバーサル検索、ヘルプ、通知、設定
3. **ホームページ** – 最近のアイテムと役立つリソースへのクイックアクセス
4. **メインワークスペース** - コンテンツを作成および管理する場所

## 左側のナビゲーション {#left-nav}

左側のナビゲーションでは、Journey Optimizer機能を機能的なカテゴリに分類しています。 使用できるメニュー項目は、権限とライセンスによって異なります。

### 主要セクション {#main-sections}

**ホーム** – 最近作成したアイテムと役立つリソースにすばやくアクセスできる出発点

**ジャーニー管理** - カスタマーエクスペリエンスを作成および管理します
* **キャンペーン** – 特定のオーディエンスに対して 1 回限りのメッセージまたはスケジュールされたメッセージを作成します。 [&#x200B; キャンペーンの概要 &#x200B;](../campaigns/get-started-with-campaigns.md)
* **ジャーニー** - マルチステップのクロスチャネルのカスタマーエクスペリエンスを構築します。 [初めてのジャーニーの作成](../building-journeys/journey-gs.md)
* **レポート** – 統合されたCustomer Journey Analytics レポートを使用してパフォーマンスを分析します。 [&#x200B; レポートドキュメントの表示 &#x200B;](../reports/campaign-global-report-cja.md)

**意思決定管理** - パーソナライズされたオファーを管理します。 [&#x200B; 意思決定管理について &#x200B;](../offers/get-started/starting-offer-decisioning.md)
* **オファー** - パーソナライズされたオファーの作成と管理
* **コンポーネント** - オファーのプレースメント、ルールおよびタグを設定します

**コンテンツ管理** - コンテンツの作成と整理
* **Assets** – 画像およびメディアの一元的リポジトリーです。 [アセットの管理](../integrations/assets.md)
* **コンテンツテンプレート** - キャンペーンおよびジャーニー用の再利用可能なメッセージテンプレート。 [&#x200B; テンプレートの作成 &#x200B;](../content-management/content-templates.md)
* **フラグメント** – 複数のメッセージで使用できるコンテンツブロック。 [&#x200B; フラグメントの操作 &#x200B;](../content-management/fragments.md)
* **ランディングページ** – 購読および環境設定用の web フォーム [ランディングページの設計](../landing-pages/get-started-lp.md)
* **ユースケースプレイブック** – 一般的なマーケティングシナリオの事前定義済みワークフロー。 [&#x200B; プレイブックを検索 &#x200B;](ai-features.md#playbooks)

**データ管理** - データ基盤を管理します。 [&#x200B; スキーマとデータセットについて &#x200B;](../data/get-started-schemas.md)
* **スキーマ** - データ構造の定義
* **データセット** - データ収集を保存および管理します
* **クエリ** - クエリの書き込みと実行
* **監視** - データ取り込みの追跡

**接続** – 他のシステムとの統合
* **ソース** – 外部システムからデータを取り込みます。 [&#x200B; ソースの設定 &#x200B;](get-started-sources.md)
* **宛先** - クラウドストレージにデータを書き出します。 [&#x200B; 宛先の設定 &#x200B;](../data/export-datasets.md)

**顧客** - オーディエンスとプロファイルの管理
* **オーディエンス** – 顧客セグメントを作成および管理します。 [&#x200B; オーディエンスの操作 &#x200B;](../audience/about-audiences.md)
* **購読リスト** - オプトインリストを管理します。 [購読の管理](../landing-pages/subscription-list.md)
* **プロファイル** – 統合された顧客プロファイルを表示します。 [&#x200B; プロファイルを探索 &#x200B;](../audience/get-started-profiles.md)
* **ID** - ID 解決を管理します。 [ID について学ぶ &#x200B;](../audience/get-started-identity.md)

**プライバシー** - プライバシーとコンプライアンスを制御します。 [プライバシーの概要](../privacy/get-started-privacy.md)
* **ポリシー** - データガバナンスポリシーの定義
* **リクエスト** - プライバシーリクエストを処理します（GDPR、CCPA）
* **監査** - アクティビティログを確認します。 [&#x200B; 監査ログの表示 &#x200B;](../privacy/audit-logs.md)
* **データのライフサイクル** - データ保持の設定

**管理** - システム設定を指定します。 [アクセス制御の概要](../administration/permissions-overview.md)
* **設定** - イベント、データソース、アクションを設定します。 [チャネルの設定](../configuration/get-started-configuration.md)
* **ビジネスルール** - メッセージの頻度とジャーニーのエントリを制御します。 [&#x200B; ビジネス・ルールの設定 &#x200B;](../conflict-prioritization/rule-sets.md)
* **アラート** - システムアラートを表示および管理します。 [&#x200B; アラートの監視 &#x200B;](../reports/alerts.md)
* **サンドボックス** – 環境を管理し、サンドボックス間でオブジェクトをコピーします。 [&#x200B; サンドボックスの操作 &#x200B;](../administration/sandboxes.md)
* **チャネル** - チャネル設定と配信品質を設定します。 [&#x200B; チャネル設定のセットアップ &#x200B;](../configuration/channel-surfaces.md) | [&#x200B; 設定の概要 &#x200B;](../configuration/get-started-configuration.md)
* **タグ** - コンテンツを整理および分類します。 [&#x200B; 統合タグの操作 &#x200B;](search-filter-categorize.md#tags)

## 上部バーの機能 {#top-bar}

### ユニバーサル検索 {#search}

検索アイコンを使用すると、Journey Optimizer全体のジャーニー、キャンペーン、アセット、その他のオブジェクトをすばやく見つけることができます。 キーワードを入力すると、プラットフォームのすべての領域から関連性の高い結果が表示されます。

### ヘルプとサポート {#help}

**ヘルプ** アイコンをクリックして、次の操作を行います。
* ヘルプ記事とビデオを検索
* 現在のページのコンテキストヘルプへのアクセス
* Adobe サポートに連絡する
* フィードバックを共有

![&#x200B; コンテキストヘルプの例 &#x200B;](assets/do-not-localize/Context-help.gif)

### 通知 {#notifications}

製品内通知およびメール通知を有効にして、次の情報を常に把握できるようにします。
* **アラート** - システム障害とパフォーマンスの問題
* **承認** - レビューが必要なリクエスト
* **新しいリリース** – 製品アップデートと新機能

通知を設定するには：

1. プロファイルアイコンをクリックし、「**[!UICONTROL 環境設定]**」を選択します
2. **[!UICONTROL 通知]**&#x200B;の下にある **[!UICONTROL Journey Optimizer]** を見つけます。
3. 受信する通知タイプを有効にする

![&#x200B; 通知設定 &#x200B;](../rn/assets/do-not-localize/pulse-notif.png){width="60%" align="center"}

### 言語設定 {#language}

インターフェイスで使用できる言語は、英語、フランス語、ドイツ語、イタリア語、スペイン語、ポルトガル語（ブラジル）、日本語、韓国語、繁体字中国語、簡体字中国語です。

言語を変更するには：

1. プロファイルメニューで **環境設定** をクリックします
2. 優先言語を選択
3. オプションで、フォールバックとして第 2 言語を選択します
4. **保存**&#x200B;をクリックします。

## ホームページ {#home-page}

ホームページには次の機能があります。

* **最近** – 最近作成したイベント、ジャーニー、キャンペーンおよびその他のオブジェクトへのショートカット
* **ユースケース** – すぐに使い始めるのに役立つ事前定義済みのシナリオ（テストプロファイルの作成、誕生日メッセージの送信など）。
* **リソース** - ドキュメント、チュートリアル、サポートへのリンク

### 製品内のユースケース {#use-cases}

クイックスタートワークフローは、一般的なタスクを実行するのに役立ちます。

* **テストプロファイルの作成** - CSV テンプレートを使用してテストプロファイルを生成します
* **誕生日メッセージの送信** – 誕生日メールを自動的に送信します（近日公開）
* **新規顧客のオンボーディング** – 新規顧客向けウェルカムシリーズ（近日公開予定）
* **インポートしたリストへのプッシュの送信** - CSV データからのクイックプッシュ通知（近日公開予定）

各ユースケースの詳細を確認するには **[!UICONTROL 詳細を表示]** をクリックし、開始するには **[!UICONTROL 開始]** をクリックします。

## AI アシスタント {#ai-assistant}

AI アシスタントは、即座にヘルプと操作のインサイトを提供します。 上部バーの「AI アシスタント」アイコンをクリックして、次の操作を行います。
* 製品機能に関する回答を得る
* ジャーニーに関する運用インサイトを受け取る
* 概念とベストプラクティスの操作

[AI アシスタントの詳細](ai-features.md#ai-assistant)

## 関連トピック {#related-topics}

* [役割別に学習パスを選択](quick-start.md)
* [コンテンツの検索、フィルタリング、分類](search-filter-categorize.md)
* [Journey Optimizerの動作について](understanding-ajo.md)
* [アクセシビリティ機能](accessibility.md)


<!--CONTEXTUAL HELP TO DISPATCH IN DOCS ONCE FEATURE LIVE-->



<!--ORCHESTRATED CAMPAIGNS - Overview page-->


<!--OVERVIEW TAB ORCHESTRATED CAMPAIGNS SKU only-->


>[!CONTEXTUALHELP]
>id="ajo_oc_campaign_ovv_1"
>title="キャンペーンオーケストレーション"
>abstract="リレーショナルデータセットを分割、組み合わせ、強化、操作して、オーディエンスを定義する"



>[!CONTEXTUALHELP]
>id="ajo_oc_campaign_ovv_2"
>title="マルチエンティティデータの活用"
>abstract="調整されたキャンペーンでリレーショナルデータセットを活用して、セグメント化とパーソナライゼーションのためのデータを強化する方法を学ぶ"



>[!CONTEXTUALHELP]
>id="ajo_oc_campaign_ovv_3"
>title="アドホックセグメント化と正確なカウント"
>abstract="正確なカウント数を使用してセグメントを段階的に作成する"



>[!CONTEXTUALHELP]
>id="ajo_oc_campaign_ovv_4"
>title="使用可能なチャネル"
>abstract="メール, SMS, プッシュ通知, ダイレクトメール"

<!--OVERVIEW TAB ORCHESTRATED CAMPAIGNS + JOURNEYS SKU -->


>[!CONTEXTUALHELP]
>id="ajo_oc_jo_camppaign_ovv_1"
>title="キャンペーンを作成して送信するためのガイド付き UI"
>abstract="チャネルでの 1 つ以上のアクションの設定、オーディエンスの選択、コンテンツの設定、スケジュールの定義を行うと、送信の準備が整います"


>[!CONTEXTUALHELP]
>id="ajo_oc_jo_camppaign_ovv_2"
>title="使用可能なチャネル"
>abstract="メール，SMS, プッシュ通知，アプリ内，web, コードベースのエクスペリエンス"


<!--OVERVIEW TAB ORCHESTRATED CAMPAIGNS - API triggered tab -->


>[!CONTEXTUALHELP]
>id="ajo_oc_api_camppaign_ovv_1"
>title="トランザクション API トリガーキャンペーン"
>abstract="API 呼び出しを通じてリアルタイムメッセージをトリガー"

>[!CONTEXTUALHELP]
>id="ajo_oc_api_camppaign_ovv_2"
>title="マーケティングメッセージ"
>abstract="プロモーションコンテンツ（オプトインが必要。ビジネスルールの対象です）"

>[!CONTEXTUALHELP]
>id="ajo_oc_api_camppaign_ovv_3"
>title="トランザクションメッセージ"
>abstract="サービス関連コンテンツ（確認、アラート。マーケティングの同意の対象ではありません）"

>[!CONTEXTUALHELP]
>id="ajo_oc_api_camppaign_ovv_4"
>title="使用可能なチャネル"
>abstract="メール, SMS, プッシュ通知"

<!--APPROVAL POLICIES-->


>[!CONTEXTUALHELP]
>id="ajo_campaigns_edit_disabled"
>title="無効化を編集"
>abstract="無効な（キャンペーン）を編集"

>[!CONTEXTUALHELP]
>id="ajo_journey_edit_disabled"
>title="無効化を編集"
>abstract="無効な（ジャーニー）を編集"

>[!CONTEXTUALHELP]
>id="ajo_approval_policy_approval_status"
>title="承認ステータス"
>abstract="承認ステータス"

>[!CONTEXTUALHELP]
>id="ajo_campaigns_approve"
>title="承認"
>abstract="承認（キャンペーン）"

>[!CONTEXTUALHELP]
>id="ajo_journey_approve"
>title="承認"
>abstract="承認（ジャーニー）"

>[!CONTEXTUALHELP]
>id="ajo_journey_simulation"
>title="ジャーニーのシミュレート"
>abstract="ジャーニーシミュレーションを使用すると、ジャーニーを検証し、アクティブ化する前にジャーニーのパフォーマンスを確認できます。トレーニング済みモデルのデータを使用して、ジャーニー全体にわたる数値を提供し、実際のシナリオでのジャーニーの動作を確認します。"

<!-- WEBHOOKS -->

>[!CONTEXTUALHELP]
>id="ajo_channels_feedback_webhook_settings"
>title="Webhook を有効にする"
>abstract="Webhook を有効にすると、メッセージの実行ステータスに関するリアルタイムのフィードバックを受信できます。このオプションをアクティブ化する前に、**管理**／**チャネル**／**フィードバック Webhook** メニューで webhook が設定されていることを確認します。"

>[!CONTEXTUALHELP]
>id="ajo_channels_feedback_webhook_settings_create"
>title="フィードバック Webhook"
>abstract="フィードバック webhook を使用すると、トランザクション API トリガーキャンペーンで送信されたメッセージの実行ステータスに関するリアルタイムのフィードバックを受信できます。組織 + サンドボックスの組み合わせごとに、1 つの webhook 設定のみが許可されます。"

>[!CONTEXTUALHELP]
>id="ajo_channels_feedback_webhook_settings_configuration"
>title="基本設定"
>abstract="このセクションでは、webhook を特定するためのわかりやすい名前を入力し、この webhook がフィードバックを受信するチャネル（メールや SMS）を選択します。Webhook URL フィールドに、フィードバックイベントを配信する必要がある HTTPS エンドポイントを指定します。"

>[!CONTEXTUALHELP]
>id="ajo_channels_feedback_webhook_settings_authentication"
>title="認証"
>abstract="エンドポイントで JWT 認証が必要な場合は、リストから「**JWT 認証**」を選択し、必要な詳細を指定します。"

>[!CONTEXTUALHELP]
>id="ajo_channels_feedback_webhook_settings_header_parameters"
>title="ヘッダーパラメーター"
>abstract="このセクションでは、各 webhook リクエストと共に送信される追加のカスタムヘッダーを設定できます。"
