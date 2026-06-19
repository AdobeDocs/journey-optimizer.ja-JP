---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer オンボーディングハブ
description: Adobe Adobe Journey Optimizerのオンボーディングハブ機能を利用すれば、ステップバイステップの指示や実際のユースケース、動画コンテンツなどを一元管理し、新規顧客を迅速に増やし、初めての顧客体験を提供できます。
feature: Get Started
topic: Content Management
role: User
level: Beginner
hide: true
keywords: adobe journey optimizer, オンボーディング，オンボーディングハブ，ユースケース，動画，チュートリアル，導入の相談，新規ジャーニーの立ち上げ
source-git-commit: 79337a0d2a65fa1e8aa1e5d47bcf39906d9887a7
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 12%

---

# Journey Optimizer オンボーディングハブ {#onboarding-hub}


>[!BEGINSHADEBOX]

**このページでは：** Adobe Journey Optimizerをすばやく使い始めます。簡単な手順に従って、最初のエクスペリエンスを配信したり、実際のユースケースを参照したり、厳選されたビデオコンテンツを楽しんだりできます。

>[!ENDSHADEBOX]

<!-- 
rebuild
-->

[!DNL Adobe Journey Optimizer]を初めて使用する場合 このハブでは、ゼロから最初のライブ顧客体験を実現するのに役立つリソースを収集します。一般的な目標に関するステップバイステップの指示、可能なことを示す実際のユースケース、厳選されたビデオコンテンツ（チュートリアル、ウォークスルー、実践的な実践）などを利用できます。

>[!TIP]
>
>自社の目標に適合する能力を把握できない場合、 目標ファーストの[目標に適したJourney Optimizer機能を見つけます](ajo-use-case-guide.md) ガイド。ステップバイステップの手順については、こちらを参照してください。

## ここから始める：視聴して学ぶ {#start-here}

10分ある場合は、このオリエンテーションビデオから始めます。 インターフェイスを順を追って説明し、役割ごとの主要な機能を強調表示します。

>[!VIDEO](https://video.tv.adobe.com/v/3424995?quality=12)

次の学習リソースを活用して、実践的な自信を築きましょう。

* [Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"} – 各役割のステップバイステップのビデオとガイド付きウォークスルー。
* [&#x200B; エキスパートが監修したビデオプレイリスト &#x200B;](https://experienceleague.adobe.com/en/playlists?solution=Journey+Optimizer){target="_blank"} – 順番に視聴する一連の短いビデオ。
* [&#x200B; サンドボックスのトレーニング &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/configure-a-training-sandbox/introduction-and-prerequisites){target="_blank"} – 練習用のサンプルデータを含む安全な環境。
* [実践的な課題](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/challenges/introduction-and-prerequisites){target="_blank"} — ガイド付き演習で学んだことを適用します。

## 初めてのエクスペリエンスの構築 {#build-first}

ここでは、成果に焦点を当てた短い一連のステップを紹介します。どのような要素を構築し、誰のために使用するのか、その方法は何なのかを解説します。 最初のプロジェクトに一致する目標を選択し、詳細なドキュメントへのリンクに従います。

### 新規顧客を歓迎する {#build-welcome}

**次の機能を構築します：**&#x200B;すべての新規購読者に挨拶し、非アクティブな購読者を誘導する自動ウェルカムシリーズ。
**マーケターに最適：** ・ **機能：** イベントトリガージャーニー

1. [統合プロファイルとオーディエンス &#x200B;](../audience/get-started-profiles.md)がサインアップイベントを受け取っていることを確認します。
2. [最初のジャーニー](../building-journeys/journey-gs.md)を作成し、サインアップイベントをエントリとして使用します。
3. ようこそ[電子メール &#x200B;](../email/get-started-email.md)を追加してから、エンゲージしていないプロファイルに対して待機ステップとフォローアップ [&#x200B; プッシュ通知](../push/get-started-push.md)を追加します。
4. [名や表明された関心などのプロファイル属性を使用して、コンテンツ &#x200B;](../personalization/personalize.md)をパーソナライズします。

➡️ [&#x200B; ジャーニーで開始](../building-journeys/journey-gs.md)

### 放棄されたカートの回復 {#build-cart}

**次の項目を作成します：** リアルタイムの復元フローで、残された項目を顧客に思い出してもらいます。
**マーケターに最適：** ・ **機能：** イベントトリガージャーニー

1. 買い物かごの放棄イベントがJourney Optimizerに届いていることを確認します（必要に応じて[&#x200B; データチーム &#x200B;](../data/gs-data.md)と協力してください）。
2. [放棄イベントによってトリガーされたジャーニー](../building-journeys/journey-gs.md)を作成します。
3. パーソナライズされたリマインダーメールを送信します。24時間以内にクリックがない場合は、[&#x200B; プッシュ &#x200B;](../push/get-started-push.md) フォローアップに分岐します。
4. [放棄されたアイテムとロイヤルティステータスで](../personalization/personalize.md)をパーソナライズします。

➡️ [&#x200B; ジャーニーで開始](../building-journeys/journey-gs.md)

### トランザクションメッセージの送信 {#build-transactional}

**外部システムによってトリガーされるオンデマンドの注文、配送、または予約の確認を作成します。**
**マーケターと開発者**&#x200B;に最適・ **機能：** API トリガーキャンペーン

1. [API トリガーのキャンペーン &#x200B;](../campaigns/api-triggered-campaigns.md)の仕組みと期待されるペイロードを確認します。
2. メッセージテンプレートをデザインし、トランザクションの詳細を含めて[&#x200B; パーソナライズ &#x200B;](../personalization/personalize.md)します。
3. 開発者に、注文システムまたはフルフィルメントシステムからキャンペーンエンドポイントを呼び出してもらいます。

➡️ [API トリガーによるキャンペーンの操作](../campaigns/api-triggered-campaigns.md)

### A/B テストによる施策の立ち上げ {#build-campaign}

**最もパフォーマンスの高いコンテンツを自動的に選択するスケジュールされたプロモーションを作成します。**
**マーケターに最適：** ・ **機能：** スケジュール済みキャンペーン + コンテンツ実験

1. [&#x200B; キャンペーンを開始し](../campaigns/get-started-with-campaigns.md)、オーディエンスを定義します。
2. [AI コンテンツ生成](../content-management/gs-generative.md)を使用して、件名とコピーのバリエーションを作成します。
3. [&#x200B; コンテンツ実験](../content-management/experiment-accelerator-gs.md)を設定してサンプルのバリエーションをテストし、勝者を残りの部分に送信します。

➡️ [&#x200B; キャンペーンの開始](../campaigns/get-started-with-campaigns.md)

### 顧客ごとのオファーのパーソナライズ {#build-offers}

**お客様ごとに最適なオファーを表示する決定を作成します。**
**マーケターに最適：** ・ **機能：**&#x200B;決定

1. [&#x200B; オファー決定](../offers/get-started/starting-offer-decisioning.md)を開始し、オファーと実施要件ルールを作成します。
2. 決定を[&#x200B; ジャーニー](../building-journeys/journey-gs.md)またはキャンペーンメッセージに追加します。
3. [AI機能](ai-features.md)のレイヤーを使用して、オファーを自動的にランク付けおよび最適化できます。

➡️ [&#x200B; オファー決定の開始](../offers/get-started/starting-offer-decisioning.md)

## 目標別ユースケース {#use-cases}

上記の例では、最も一般的な出発点を網羅していますが、Journey Optimizerは、積極的な障害通知や顧客とのリエンゲージメントから、リアルタイムで位置情報に即したメッセージ配信まで、さらに多くのシナリオをサポートしています。 各シナリオは、1つ以上の機能を組み合わせたものです。

*あなたの*&#x200B;目標に対する正確な機能を見つけるには、[目標に対する適切なJourney Optimizer機能を見つける](ajo-use-case-guide.md)の完全な目標整理インデックスを使用します。 エンドツーエンドの作業済み例については、[ジャーニーユースケースライブラリ &#x200B;](../building-journeys/jo-use-cases.md)を参照してください。

## ビデオライブラリ {#videos}

厳選されたビデオコンテンツをトピック別に参照できます。 各タブには、Experience Leagueの関連チュートリアルとプレイリストへのリンクが表示されます。

>[!BEGINTABS]

>[!TAB はじめに]

* [Journey Optimizerの概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/introduction){target="_blank"} — コアコンセプトと製品ツアー。
* [Journey Optimizer チュートリアルの概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"} — ガイド付きビデオの完全カタログ。

>[!TAB ジャーニーとキャンペーン ]

* [&#x200B; ジャーニーの構築の概要](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/introduction-to-building-a-journey){target="_blank"} – 最初のイベントトリガージャーニーを構築します。
* [Journey Agentでジャーニーを作成](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-agent-overview){target="_blank"} – 自然言語プロンプトからジャーニーを作成します。

>[!TAB PersonalizationとAI]

* [&#x200B; コンテンツ生成用AI アシスタント &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/content-management/ai-assistant/ai-assistant-for-content-generation-overview){target="_blank"} — コピー、画像、バリエーションを生成します。
* [決定機能を使用してweb オファーをパーソナライズ &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/use-decisioning-to-personalize-web-offers/introduction){target="_blank"} – 顧客ごとにオファーをカスタマイズします。

>[!TAB  レポートと最適化]

* [&#x200B; ライブレポートでジャーニーを監視および分析](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/report-and-monitor/monitor-and-analyze-your-journey-with-live-reports){target="_blank"} — パフォーマンスをリアルタイムで追跡します。
* [&#x200B; メールキャンペーンのコンテンツ実験を作成](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/experimentation/content-experiments-for-emails){target="_blank"} — コンテンツをテストおよび最適化します。

>[!ENDTABS]

## 役割別のオンボーディングチェックリスト {#checklist}

複数の役割に及ぶオンボーディング。 焦点を絞ったスタートパスを確認するには、次の役割を選択します。

* **管理者** — サンドボックス、権限、チャネルを設定します。 [管理者として開始](path/administrator.md)
* **Data Engineer** — スキーマのモデル化とデータの取り込み。 [&#x200B; データエンジニアとして始める](path/data-engineer.md)
* **Developer** — SDKとトリガーイベントを統合します。 [開発者として開始](path/developer.md)
* **マーケター** — ジャーニー、コンテンツ、オーディエンスを構築します。 [&#x200B; マーケターとして開始](path/marketer.md)

これらの役割の連携の詳細については、[役割と責任](quick-start.md)を参照してください。

## 関連リソース {#related-resources}

* [目標に最適なJourney Optimizer機能を見つける](ajo-use-case-guide.md) – 各機能の目標ファーストの決定ガイド。
* [ジャーニーユースケースライブラリ &#x200B;](../building-journeys/jo-use-cases.md) – 実例と実装パターン。
* [主な用語](terminology.md) – 各機能の背後にある概念を明確にします。
* [AIとインテリジェント機能](ai-features.md) — AI アシスタント、送信時間の最適化、コンテンツ生成について詳しく見る。
* [&#x200B; データ管理の基本](../data/gs-data.md) — データの取り込み、統合、アクティベート方法。
