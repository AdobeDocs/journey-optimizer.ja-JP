---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーの基本を学ぶ
description: ジャーニーの概要 – Adobe Journey Optimizerでパーソナライズされたカスタマーエクスペリエンスを作成するためのジャーニーのタイプ、ワークフロー、機能およびベストプラクティスについて説明します
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
keywords: ジャーニー，検出，開始，単一，オーディエンスを読み取り，オーディエンスの選定，ビジネスイベント，リアルタイム，スケジュール済み，バッチ，イベントトリガー，ワークフロー，オーケストレーション，パーソナライゼーション，複数チャネル
exl-id: 73cfd48b-72e6-4b72-bbdf-700a32a34bda
version: Journey Orchestration
source-git-commit: 522dba0516268a17e72f56c0f28205ba60709d78
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 4%

---


# ジャーニーの基本を学ぶ{#jo-general-principle}

Adobe Journey Optimizerを使用すると、オーディエンスの行動やニーズにリアルタイムで適応する、パーソナライズされた複数のステップから成るカスタマージャーニーを作成できます。 直感的なドラッグ&amp;ドロップキャンバスを使用すると、コンテキストデータとオーディエンスターゲティングを活用して、複数のチャネルにわたってメッセージとアクションを調整し、最大の影響を得ることができます。

このガイドは、ジャーニーの基本を理解し、ユースケースに適したジャーニータイプを選択し、有意義でタイムリーなカスタマーエクスペリエンスを提供するジャーニーを自信を持って設計するのに役立つ明確なロードマップを提供します。

## ジャーニーとは

**ジャーニー** は、顧客の行動、ビジネスイベント、スケジュールされたキャンペーンに応じて、様々なチャネルにわたってパーソナライズされたインタラクションを調整する、自動化された複数手順のカスタマーエクスペリエンスです。

[!DNL Journey Optimizer] を使用すると、次のことができます。

* イベントやデータソースに保存されたコンテキストデータを使用して **リアルタイムオーケストレーション** のユースケースを構築できます。
* 顧客の行動やビジネスイベントに動的に対応する **複数の手順から成る詳細なシナリオ** を設計する
* メール、プッシュ、SMS、アプリ内 **web など、様々な分野で :11** のパーソナライズされたエクスペリエンスを大規模に提供します

![パレット、キャンバス、プロパティパネルを含むジャーニーデザイナーインターフェイス](assets/journey38.png)

➡️ **作成を開始する準備はできていますか？** 最初のジャーニーを作成 [ を 5 分で ](journey-gs.md) きます。

### ジャーニーとキャンペーン：それぞれを使用すべきタイミング {#journeys-vs-campaigns-intro}

Adobe Journey Optimizerがお客様にアプローチするアプローチは 3 つあります。**ジャーニー** （1:1 リアルタイムオーケストレーション）、**キャンペーン** （シンプルなバッチまたは API トリガー配信）、**オーケストレードキャンペーン** （マルチエンティティデータを含むバッチキャンバスワークフロー）。

**クイック決定：**

* **ジャーニー** を使用すると、各顧客が自分のペースで進行する、行動に基づく複数のステップのエクスペリエンスを作成できます
* **アクション/API キャンペーン** を使用して、シンプル、スケジュールまたはトリガーされたメッセージをオーディエンスに配信します
* 複数エンティティのセグメント化と正確な事前送信数を必要とする複雑なバッチワークフローには、**オーケストレートキャンペーン** を使用します

<!-- waiting for DOCAC-13912
➡️ **[View detailed comparison: Journeys vs Campaigns](../start/journeys-vs-campaigns.md)** - Includes decision guide, use cases, and feature availability-->

## ジャーニータイプを選択 {#journey-types}

Adobe Journey Optimizerでは、4 つのジャーニータイプをサポートしており、それぞれが様々なエントリメカニズムとビジネスシナリオに合わせて設計されています。

* **単一ジャーニー**：リアルタイムのイベントトリガーエクスペリエンス（注文確認、ウェルカムメール）
* **オーディエンスジャーニーを読み取り**：オーディエンスセグメント（ニュースレター、プロモーションキャンペーン）へのスケジュールされたバッチ通信
* **オーディエンスの選定ジャーニー**：オーディエンスメンバーシップの変更に対するリアルタイムの応答（VIPのアップグレード、再エンゲージメント）
* **ビジネスイベントジャーニー**：複数の顧客に影響するビジネス条件（在庫アラート、フラッシュ販売）

<!-- waiting for DOCAC-13912 
➡️ **[Journey types and selection guide](journey-types-selection.md)** - Detailed comparison, decision tree, and feature compatibility matrix -->

## ジャーニーデザイナーを使用したビルド {#journey-designer}

**[ジャーニーデザイナー](using-the-journey-designer.md)** は、顧客体験を作成するための視覚的なキャンバスです。 直感的なドラッグ&amp;ドロップインターフェイスを使用すると、コードを記述しなくても、ジャーニーのすべてのステップを調整できます。

![パレット、キャンバス、プロパティパネルを含むジャーニーデザイナーインターフェイス](assets/journey38.png)

### デザイナーでできること：

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**エントリポイントの定義**

顧客の入力方法（イベント、オーディエンスセグメント、オーディエンスの選定のいずれか）を選択します。

[エントリ管理の詳細](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**メッセージの送信**

メール、プッシュ、SMS/MMS、アプリ内、web などの組み込みチャネルアクションを、すべてJourney Optimizerで設計して使用します。

[ジャーニーでのメッセージの送信](journeys-message.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**ロジックおよび条件の追加**

プロファイル属性、オーディエンスメンバーシップまたはリアルタイムイベントに基づいてジャーニーを分岐します。

[条件を使用](condition-activity.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**データの活用**

イベント、Adobe Experience Platform、サードパーティの API サービスなどのコンテキストデータを使用できます。

[データソースの操作](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**外部システムの接続**

カスタムアクションを作成して、メッセージの送信またはワークフローのトリガー用にサードパーティ製システムを統合します。

[カスタムアクションの設定](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**オーケストレーションアクティビティの追加**

待機時間、ジャンプ、プロファイル更新およびオーディエンス管理を使用して、高度なフローを作成します。

[すべてのアクティビティを探索](about-journey-activities.md)
:::

::::

➡️ **実践的な学習：** [ ジャーニーデザイナーのビデオをご覧ください ](#video) または [ エンドツーエンドのユースケースについて詳しく説明 ](jo-use-cases.md)

## ジャーニー作成ワークフロー {#workflow}

ジャーニーを成功させるには、明確で繰り返し可能なプロセスに従います。 ステップバイステップのワークフローを次に示します。

**1. プラン** → **2. デザイン** → **3. テスト** → **4。 公開** → **5. モニタ** → **6 最適化**

### &#x200B;1. ジャーニーの計画 {#plan}

デザイナーを開く前に、目的を明確にします。

* **目標は何ですか？** （例：新規顧客のオンボーディング、非アクティブユーザーの再エンゲージ）
* **観客はだれですか。** （特定のセグメント、イベント駆動型の個人）
* **適合するジャーニータイプはどれですか？** （上記の [ ジャーニータイプ ](#journey-types) を参照）
* **どのチャネルを使用しますか？** （メール、プッシュ、SMS など）

### &#x200B;2. キャンバスでのデザイン {#design}

ジャーニーデザイナーを使用したフローの作成：

* **エントリ条件の設定** - プロファイルの入力方法（イベント、オーディエンス、選定）を定義します
* **オーケストレーションロジックの追加** – 待機時間、条件、決定ポイントを含める
* **メッセージの設定** – 通信を設計したり、既存のテンプレートを活用したりします
* **アクションの設定** – 実行するビルトインまたはカスタムアクションを設定します
* **終了条件の定義** - ジャーニーを完了するタイミングと方法を指定します

[Journey designer →の使用方法を学ぶ](using-the-journey-designer.md)

### 3.運用開始前のテスト {#test}

ジャーニーを常にテストして、顧客が経験する前に問題を特定してください。

* **テストモード** を使用して、テストプロファイルを含むジャーニーをシミュレートします
* **ドライラン** を使用すると、実際のデータに影響を与えたりメッセージを送信したりせずに、ジャーニーの実行をプレビューできます
* すべての条件、メッセージ、アクションが期待どおりに動作することを確認します
* タイミング、データフロー、パーソナライゼーションの確認

[ ジャーニー→のテスト ](testing-the-journey.md) | [ ドライラン→ールについて学ぶ ](journey-dry-run.md)

### &#x200B;4. ジャーニーの公開 {#publish}

テストが完了したら、公開してジャーニーをライブにします。

* 最終的な設定とプロパティの確認
* 実際の顧客向けに有効化するパブリッシュ
* メモ：ライブジャーニーは停止できますが、編集はできません（新しいバージョンを作成する必要があります）

[ジャーニー→を公開する](publish-journey.md)

### &#x200B;5. パフォーマンスの監視 {#monitor}

ジャーニーの実際のパフォーマンスを追跡する：

* ジャーニーレポートと分析の表示
* エントリ、完了およびエラー率の監視
* 重大な問題に対するアラートの設定

[→の監視とレポート ](report-journey.md) | [ アラートの設定→](../reports/alerts.md)

### 6.最適化と反復 {#optimize}

インサイトを使用した改善：

* エンゲージメント指標とコンバージョン率の分析
* 送信時間の最適化のテスト
* 機能強化を含む新しいジャーニーバージョンの作成
* AI を活用したレコメンデーションの使用

[ ジャーニーの最適化→](optimize.md) | [ 送信時間の最適化→](send-time-optimization.md)

➡️ **開始する準備ができましたか？**[ 今すぐ最初のジャーニーを作成→ます ](journey-gs.md)

## 実際のユースケース {#use-cases}

ジャーニーの概念を適用して一般的なマーケティングの課題を解決する方法を示す、実用的な例から学びます。

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**新規購読者へようこそ**

お客様がサービスを登録する際に、オンボーディング手順の完了を促すウェルカムジャーニーをトリガーします。

[ユースケースを表示→](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**送信時間の最適化**

AI を使用すると、各顧客が最も関与する可能性が高いタイミングでメールを配信し、開封率とクリック率を最大化します。

[ユースケースを表示→](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**配信を増やす**

メッセージ量を徐々に増やして送信評判をウォームアップし、配信品質の問題を回避します。

[ユースケースを表示→](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**平日の目標**

関連性を高めるために、顧客がジャーニーにエントリする曜日に基づいて異なるコンテンツを送信します。

[ユースケースを表示→](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**マルチチャネルキャンペーン**

メール、プッシュ、SMS、web チャネルにわたるシームレスなエクスペリエンスを 1 つのジャーニーで調整します。

[ユースケースを表示→](journeys-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**すべてのユースケース**

ステップバイステップの実装を使用して、ジャーニーのユースケースの完全なライブラリを調べます。

[ すべての→を参照 ](jo-use-cases.md) | [ ユースケースライブラリ→](/help/rp_landing_pages/journey-use-cases-landing-page.md)
:::

::::

## ジャーニー機能の詳細 {#capabilities}

ジャーニーの構築に慣れたら、次の強力な機能を探索して、高度な顧客体験を作成します。

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**高度な式**

データ操作と複雑なロジック用の式エディターを使用して、動的条件とパーソナライゼーションを構築します。

[式の詳細情報](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/clock.svg)

**タイムゾーン管理**

自動タイムゾーン調整と最適な送信時間で、グローバルオーディエンスを処理します。

[タイムゾーンの管理](timezone-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**テストモードとドライラン**

運用開始前にテストプロファイルを使用してジャーニーを検証し、実際のデータに影響を与えずに実行をプレビューします。

[ドライランを使用](journey-dry-run.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**サンドボックスにコピー**

サンドボックス間でジャーニーを複製して、テストおよびデプロイメントワークフローを効率化します。

[ジャーニーのコピー](copy-to-sandbox.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**タグと組織**

タグを使用してジャーニーを分類およびフィルタリングし、大規模な管理を強化します。

[タグを使用して整理](tags.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**スループット制御**

メッセージのスループットを制限して送信の評判を管理し、システムが大量に送信されるのを回避します。

[スループットの制御](limit-throughput.md)
:::

::::

[すべてのジャーニー機能を表示します→](/help/rp_landing_pages/manage-journey-landing-page.md)

## ～を見ることで学ぶ {#video}

ジャーニーコンポーネントを視覚的に紹介し、キャンバスでジャーニーを作成するための基本を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)

➡️ **ビデオを増やしますか？**[ ジャーニーのビデオチュートリアルを見る ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}

## よくある質問 {#common-questions}

+++ ジャーニーとキャンペーンの違いは何ですか？

Adobe Journey Optimizerには、次の 3 つのアプローチがあります。

* **ジャーニー**: 1:1 各プロファイルが自分のペースでステップを進めていくリアルタイムオーケストレーション。 条件付きロジック（オンボーディング、買い物かごの放棄など）を使用した、行動駆動型の複数ステップのエクスペリエンスに最適です。

* **キャンペーン（アクションおよび API トリガー）**：オーディエンスに対するシンプルなメッセージ配信。スケジュールに従って、または APIトリガーを使用して、すべてのプロファイルに対して同時に実行されます。 プロモーションキャンペーン、ニュースレター、トランザクションメッセージに最適です。

* **キャンペーンの調整**：リレーショナルデータ（プロファイル +製品/店舗/予約）を使用した、複雑なセグメント化を伴う複数手順のバッチワークフロー。 すべてのプロファイルが、正確な事前送信数と共に処理されます。 季節的なプロモーション、製品発売、マルチエンティティデータを必要とするキャンペーンに最適です。

**主な違い**:ジャーニーはリアルタイムのアクションに対して個別のカスタマーの状態を維持します。アクション/API キャンペーンはシンプルなメッセージをバッチで配信します。

<!-- waiting for DOCAC-13912 - [See detailed comparison](#journeys-vs-campaigns) -->
[オーケストレートキャンペーンについて学ぶ](../orchestrated/gs-orchestrated-campaigns.md)

+++

<!-- Waiting for DOCAC-13912
+++ Which journey type should I use?

Use the [decision guide](#decision-guide) or [comparison table](#journey-types-comparison) to choose between Unitary, Read Audience, Audience Qualification, and Business Event journeys based on your trigger mechanism and use case.

+++
-->

+++ ライブジャーニーを編集できますか？

制限付きの要素（名前、メッセージコンテンツ）を編集できますが、構造の変更には新しいバージョンを作成する必要があります。 [ ジャーニーのバージョンについて学ぶ ](publish-journey.md#journey-versions)

+++

➡️ **その他の質問** [ジャーニーに関する完全な FAQ を表示 ](journey-faq.md) と 40 件以上の詳細な回答

## サポートが必要な場合 {#help}

### 一般的なタスクのクイックリンク

* **[初めてのジャーニーの作成](journey-gs.md)** – 初心者向けステップバイステップガイド
* **[ジャーニーに関する FAQ](journey-faq.md)** – よくある質問への回答
* **[トラブルシューティング](/help/rp_landing_pages/troubleshoot-journey-landing-page.md)** – 問題の診断と修正
* **[エラーコードのリファレンス](error-codes-reference.md)** - エラーメッセージについて
* **[ガードレールと制限事項](../start/guardrails.md)** – 技術的な境界とベストプラクティス

### 問題に関する通知を受け取る

**[ジャーニーアラート](../reports/alerts.md)** を設定すると、ジャーニーでエラーや異常なパターンが発生した場合に、リアルタイムで通知を受け取ることができます。

### その他のリソース

* **[ジャーニー管理ハブ](/help/rp_landing_pages/manage-journey-landing-page.md)** - フィルタリング、最適化およびプロファイル管理のためのツール
* **[ジャーニーアクティビティのリファレンス](/help/rp_landing_pages/about-journey-building-landing-page.md)** – すべてのアクティビティタイプに関する完全なガイド
* **[実行の問題のトラブルシューティング](troubleshooting-execution.md)** - ジャーニー実行の問題のデバッグ
* **[インバウンドアクティビティのトラブルシューティング](troubleshooting-inbound.md)** - エントリと選定の問題の修正

**初めてのジャーニーを作成する準備はできていますか？** [ 今すぐ始める→](journey-gs.md)
