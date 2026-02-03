---
solution: Journey Optimizer
product: journey optimizer
title: Journey Orchestration - 完全ガイド
description: Adobe Journey Optimizer でジャーニーオーケストレーションを開始するための包括的なガイド
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
keywords: ジャーニー, オーケストレーション, はじめに, オンボーディング, 機能
source-git-commit: d1fd0b60ae60c2642108a1eb308564c9d04f5f9e
workflow-type: ht
source-wordcount: '851'
ht-degree: 100%

---


# Journey Orchestration - 完全ガイド{#journey-orchestration-guide}

Adobe Journey Optimizer でジャーニーを使用すると、オーディエンスの行動やニーズにリアルタイムで適応する、パーソナライズされた複数手順のカスタマージャーニーを作成できます。直感的なドラッグ＆ドロップキャンバスを使用すると、コンテキストデータとオーディエンスターゲティングを活用して、複数のチャネルをまたいでメッセージとアクションを調整し、最大限の影響を得ることができます。

リアルタイムのトリガーを探索する場合や、ジャーニープロパティを管理する場合、カスタムアクションや式などの高度なツールを使用する場合のいずれであっても、このガイドでは、有意義でタイムリーなカスタマーエクスペリエンスを提供するジャーニーを自信を持ってデザインおよび絞り込むための明確なロードマップを提供します。

## ジャーニーとは

[!DNL Journey Optimizer] を使用すると、イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションのユースケースを作成できます。顧客行動やビジネスイベントにリアルタイムで対応する、マルチステップの高度なシナリオをデザインします。

Journey Optimizer ジャーニーデザイナーには、マーケターやジャーニー実務担当者がチャネルをまたいで複数の手順から成る 1:1 ジャーニーを調整するのに必要なすべての機能が用意されています。これには、直感的なドラッグ＆ドロップキャンバスが含まれており、ジャーニーの各手順を調整し、ターゲットオーディエンスを定義し、行動、コンテキストデータ、ビジネスイベントに基づいてターゲットオーディエンスメンバーに表示されるチャネルをまたいでメッセージ、オファーおよびコンテンツを含めることができます。

![パレット、キャンバス、プロパティパネルを含むジャーニーデザイナーインターフェイス](assets/journey38.png)

**作成を開始する準備は整っていますか？**&#x200B;最初のジャーニーを作成してデザインする方法について詳しくは、[このページ](journey-gs.md)を参照してください。


## 主な機能 {#capabilities}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=ja)

**リアルタイムおよびバッチ配信**

イベントの受信をトリガーにしてリアルタイムに&#x200B;**単一配信**&#x200B;を送信したり、Adobe Experience Platform のオーディエンスを使用してメッセージを&#x200B;**一括で**&#x200B;送信したりできます。

[ジャーニーのエントリの詳細情報](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg?lang=ja)

**コンテキストデータ**

イベント、Adobe Experience Platform の情報、サードパーティの API サービスのデータなどの&#x200B;**コンテキストデータ**&#x200B;を活用できます。

[データソースの操作](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg?lang=ja)

**ビルトインアクション**

**ビルトインのチャネルアクション**&#x200B;を使用して、[!DNL Journey Optimizer] でデザインしたメッセージをメール、プッシュ、SMS／MMS などをまたいで送信します。

[ジャーニーでのメッセージの送信](journeys-message.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=ja)

**カスタムアクション**

サードパーティシステムを使用してメッセージを送信したり、外部 API に接続したりする場合は、**カスタムアクション**&#x200B;を作成します。

[カスタムアクションの設定](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg?lang=ja)

**視覚的なジャーニーデザイナー**

**ジャーニーデザイナー**&#x200B;を使用すると、エントリイベントや「オーディエンスを読み取り」アクティビティを簡単にドラッグ＆ドロップして、条件を追加し、パーソナライズされたメッセージを送信するなど、複数のステップから成るユースケースを作成できます。

[ジャーニーデザイナーの探索](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=ja)

**テストと最適化**

公開前にジャーニーをテストし、そのパフォーマンスを監視し、送信時間の最適化などの高度な機能を使用して配信を最適化します。

[ジャーニーのテストと公開](testing-the-journey.md)
:::

::::

## ユースケースと例 {#use-cases}

ジャーニーデザイナー内から、マーケターはイベントが発生した際に、任意のチャネルを通じてリアルタイムでトリガーされる 1:1 メッセージを送信できます。例えば、お客様がサービスを購読する際に、[ウェルカムメールがトリガー](message-to-subscribers-uc.md)され、初めてアプリにログインして環境設定を行うように促すことができます。購入の完了、メールの開封、アプリへのログインなどのアクションを使用して、新規顧客をジャーニーに進めることができます。

[ジャーニー designer](using-the-journey-designer.md) には、メール、プッシュ通知、SMS／MMS などのアウトバウンドメッセージと、モバイルアプリ、web サイト、Journey Optimizer 内で直接作成されたコードベースのエクスペリエンスなどのインバウンドチャネルをサポートする[組み込みのチャネルアクション](journeys-message.md)が用意されています。また、サードパーティシステムを使用してメッセージを送信することもできます。Journey Optimizer には、これらのシステムをジャーニーデザイナーから直接ジャーニーに統合できるようにする[カスタムアクション](using-custom-actions.md)が含まれています。


:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg?lang=ja)

**ユースケースを通じて学ぶ**

実際の実装とベストプラクティスを示す、包括的なエンドツーエンドジャーニーのユースケースを探索します。

[すべてのユースケースの確認](jo-use-cases.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg?lang=ja)

**新規サブスクライバーの歓迎**

顧客がサービスに登録する際に、オンボーディング手順をガイドするパーソナライズされたウェルカムジャーニーを送信します。

[詳細情報](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg?lang=ja)

**メール送信時間の最適化**

AI を活用した送信時間の最適化を使用して、各顧客が最も関与する可能性の高いタイミングでメールを配信します。

[詳細情報](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg?lang=ja)

**配信を増やす**

メッセージの量を徐々に増やして、送信の評判をウォームアップし、配信品質の問題を回避します。

[詳細情報](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg?lang=ja)

**平日のターゲット**

顧客がジャーニーにエントリする曜日に基づいて異なるコンテンツを送信します。

[詳細情報](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/question.svg?lang=ja)

**ジャーニーに関する FAQ**

ジャーニーの作成、トラブルシューティング、ベストプラクティスに関するよくある質問への回答を示します。

[よくある質問を見る](journey-faq.md)
:::

::::



## 学習リソース {#learning-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=ja)

**ジャーニーの作成と管理**

パーソナライズされたオムニチャネルキャンペーンを構築するカスタマージャーニーをデザイン、テスト、公開および追跡する手順について説明します。

[ジャーニーの作成の探索](/help/rp_landing_pages/create-journey-landing-page.md) | [ジャーニー管理の詳細情報](/help/rp_landing_pages/manage-journey-landing-page.md) | [ジャーニーワークフローの手順](journey.md#workflow)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg?lang=ja)

**ジャーニーアクティビティ**

トリガー、決定手順、オーディエンス管理、パーソナライズされたメッセージなどのアクティビティをジャーニーで設定および使用する方法について説明します。

[アクティビティの探索](/help/rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=ja)

**式と条件**

強力なツールと構文を使用して、動的なワークフロー、データ操作、高度なジャーニーオーケストレーションのための式の作成を習得します。

[式の詳細情報](/help/rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg?lang=ja)

**トラブルシューティングと監視**

ツール、エラーコード、デバッグと最適化のベストプラクティスを使用して、ジャーニー実行の問題を診断および解決します。

[トラブルシューティングガイド](/help/rp_landing_pages/troubleshoot-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg?lang=ja)

**ジャーニーデザイナーの概要**

ジャーニーキャンバス、パレット、視覚的なインターフェイスを使用してカスタマージャーニーをデザインする方法について説明します。

[デザイナーの詳細情報](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg?lang=ja)

**テストと公開**

ジャーニーを公開する前に徹底的にテストして、期待どおりに機能し、適切なエクスペリエンスが提供されることを確認します。

[ガイドのテスト](testing-the-journey.md)
:::

::::

### ビデオチュートリアル {#video}

ジャーニーのコンポーネントを把握し、キャンバスでのジャーニー構築の基本を理解します。

>[!VIDEO](https://video.tv.adobe.com/v/3430350?captions=jpn&quality=12)

### その他のリソース

* **[エラーコードの参照](error-codes-reference.md)** - ジャーニーエラーコードとトラブルシューティング手順
* **[アラート](../reports/alerts.md)** - ジャーニー監視に関するアラートの設定
* **[トラブルシューティング](troubleshooting.md)** - ジャーニーに関する一般的な問題と解決策
* **[ジャーニーのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** - 実践的なビデオチュートリアルを通じて、ジャーニーの作成について説明します
* **[ジャーニーのガードレールと制限](../start/guardrails.md)** - [!DNL Adobe Journey Optimizer] を使用する際にガードレールと制限を確認します

