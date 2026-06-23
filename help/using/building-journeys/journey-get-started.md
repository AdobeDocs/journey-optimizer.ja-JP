---
solution: Journey Optimizer
product: journey optimizer
title: Journey Orchestration - 完全ガイド
description: ' [!DNL Adobe Journey Optimizer]でのジャーニーオーケストレーションを開始するための包括的なガイド'
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
hide: true
keywords: ジャーニー, オーケストレーション, はじめに, オンボーディング, 機能
exl-id: 96b1d619-986d-493d-a73b-d7c63b92cca8
TQID: https://experienceleague.adobe.com/Ht6fS6uanOs-rXoT4bAnK6eGvm9kOmH-N5B-y8KU6Rc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: ad78185d-8f79-40ad-9bad-cbde74af74eeid: b3538224-471e-4c63-a444-9b19d89ae29cid: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: b15c7c2e-788c-4eb7-86a8-390565b0d2c9id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b5d14f7b40933f110ff666db858e976e5de711db
workflow-type: tm+mt
source-wordcount: 1602
ht-degree: 50%

---

# ジャーニーオーケストレーション – 完全ガイド{#journey-orchestration-guide}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Journey Optimizerのジャーニーオーケストレーションの完全なガイドを入手し、リアルタイムに適応するマルチステップのマルチチャネル カスタマージャーニーを設計、管理、改良する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer]のジャーニーを利用すると、オーディエンスの行動やニーズにリアルタイムで適応する、パーソナライズされたマルチステップのカスタマージャーニーを作成できます。 直感的なドラッグ＆ドロップキャンバスを使用すると、コンテキストデータとオーディエンスターゲティングを活用して、複数のチャネルをまたいでメッセージとアクションを調整し、最大限の影響を得ることができます。

リアルタイムのトリガーを探索する場合や、ジャーニープロパティを管理する場合、カスタムアクションや式などの高度なツールを使用する場合のいずれであっても、このガイドでは、有意義でタイムリーなカスタマーエクスペリエンスを提供するジャーニーを自信を持ってデザインおよび絞り込むための明確なロードマップを提供します。

## ジャーニーとは

[!DNL Journey Optimizer] を使用すると、イベントやデータソースに保存されたコンテキストデータを活用して、リアルタイムオーケストレーションのユースケースを作成できます。 顧客行動やビジネスイベントにリアルタイムで対応する、マルチステップの高度なシナリオをデザインします。

Journey Optimizer ジャーニーデザイナーには、マーケターやジャーニー実務担当者がチャネルをまたいで複数の手順から成る 1:1 ジャーニーを調整するのに必要なすべての機能が用意されています。 これには、直感的なドラッグ＆ドロップキャンバスが含まれており、ジャーニーの各手順を調整し、ターゲットオーディエンスを定義し、行動、コンテキストデータ、ビジネスイベントに基づいてターゲットオーディエンスメンバーに表示されるチャネルをまたいでメッセージ、オファーおよびコンテンツを含めることができます。

![パレット、キャンバス、プロパティパネルを含むジャーニーデザイナーインターフェイス](assets/journey38.png)

**構築を開始する準備ができましたか？** [このページ ](journey-gs.md)で最初のジャーニーを作成およびデザインする方法について説明します。


## 主な機能 {#capabilities}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**リアルタイムおよびバッチ配信**

イベントが受信されたときにトリガーされるリアルタイム **単一配信**、または[!DNL Adobe Experience Platform]人のオーディエンスを使用してバッチ **で**&#x200B;を送信します。

[ジャーニーのエントリの詳細情報](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**コンテキストデータ**

イベントからの&#x200B;**コンテキストデータ**、[!DNL Adobe Experience Platform]からの情報、またはサードパーティ API サービスからのデータを活用します。

[データソースの操作](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**ビルトインアクション**

**組み込みのチャネルアクション**&#x200B;を使用して、電子メール、プッシュ通知、SMS/RCS/MMSなどで[!DNL Journey Optimizer]にデザインされたメッセージを送信します。

[ジャーニーでのメッセージの送信](journey-action.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**カスタムアクション**

サードパーティシステムを使用してメッセージを送信したり、外部 API に接続したりする場合は、**カスタムアクション**&#x200B;を作成します。

[カスタムアクションの設定](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**視覚的なジャーニーデザイナー**

**ジャーニーデザイナー**&#x200B;を使用すると、エントリイベントや「オーディエンスを読み取り」アクティビティを簡単にドラッグ＆ドロップして、条件を追加し、パーソナライズされたメッセージを送信するなど、複数のステップから成るユースケースを作成できます。

[ジャーニーデザイナーの探索](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**再利用可能なジャーニーフラグメント**

適格性チェックやチャネルルーティングロジックなど、ジャーニーノードのセットを一度作成すれば、**ジャーニーフラグメント**&#x200B;を使用して、ジャーニーをまたいで再利用できます。

[ジャーニーフラグメントの詳細](journey-fragments.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**テストと最適化**

公開前にジャーニーをテストし、そのパフォーマンスを監視し、送信時間の最適化などの高度な機能を使用して配信を最適化します。

[ジャーニーのテストと公開](testing-the-journey.md)
:::

::::

## ユースケースと例 {#use-cases}

ジャーニーデザイナー内から、マーケターはイベントが発生した際に、任意のチャネルを通じてリアルタイムでトリガーされる 1:1 メッセージを送信できます。 例えば、お客様がサービスを購読する際に、[ウェルカムメールがトリガー](message-to-subscribers-uc.md)され、初めてアプリにログインして環境設定を行うように促すことができます。 購入の完了、メールの開封、アプリへのログインなどのアクションを使用して、新規顧客をジャーニーに進めることができます。

[ ジャーニーデザイナー](using-the-journey-designer.md)は、電子メール、プッシュ通知、SMS/RCS/MMSなどのアウトバウンドメッセージと、Journey Optimizer内で直接構築されたモバイルアプリ、web サイト、コードベースのエクスペリエンスなどのインバウンドチャネルをサポートする[組み込みのチャネルアクション ](journey-action.md)を提供します。 また、サードパーティシステムを使用してメッセージを送信することもできます。Journey Optimizer には、これらのシステムをジャーニーデザイナーから直接ジャーニーに統合できるようにする[カスタムアクション](using-custom-actions.md)が含まれています。


:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**ユースケースを通じて学ぶ**

実際の実装とベストプラクティスを示す、包括的なエンドツーエンドジャーニーのユースケースを探索します。

[すべてのユースケースの確認](jo-use-cases.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**新規サブスクライバーの歓迎**

顧客がサービスに登録する際に、オンボーディング手順をガイドするパーソナライズされたウェルカムジャーニーを送信します。

[詳細情報](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**メール送信時間の最適化**

AI を活用した送信時間の最適化を使用して、各顧客が最も関与する可能性の高いタイミングでメールを配信します。

[詳細情報](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**配信を増やす**

メッセージの量を徐々に増やして、送信の評判をウォームアップし、配信品質の問題を回避します。

[詳細情報](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**平日のターゲット**

顧客がジャーニーにエントリする曜日に基づいて異なるコンテンツを送信します。

[詳細情報](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/question.svg)

**ジャーニーに関する FAQ**

ジャーニーの作成、トラブルシューティング、ベストプラクティスに関するよくある質問への回答を示します。

[よくある質問を見る](journey-faq.md)
:::

::::



## 学習リソース {#learning-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

**ジャーニーの作成と管理**

パーソナライズされたオムニチャネルキャンペーンを構築するカスタマージャーニーをデザイン、テスト、公開および追跡する手順について説明します。

[ジャーニーの作成の探索](../../rp_landing_pages/create-journey-landing-page.md) | [ジャーニー管理の詳細情報](../../rp_landing_pages/manage-journey-landing-page.md) | [ジャーニーワークフローの手順](journey.md#workflow)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**ジャーニーアクティビティ**

トリガー、決定手順、オーディエンス管理、パーソナライズされたメッセージなどのアクティビティをジャーニーで設定および使用する方法について説明します。

[アクティビティの探索](../../rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**式と条件**

強力なツールと構文を使用して、動的なワークフロー、データ操作、高度なジャーニーオーケストレーションのための式の作成を習得します。

[式の詳細情報](../../rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg)

**トラブルシューティングと監視**

ツール、エラーコード、デバッグと最適化のベストプラクティスを使用して、ジャーニー実行の問題を診断および解決します。

[トラブルシューティングガイド](../../rp_landing_pages/troubleshoot-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**ジャーニーデザイナーの概要**

ジャーニーキャンバス、パレット、視覚的なインターフェイスを使用してカスタマージャーニーをデザインする方法について説明します。

[デザイナーの詳細情報](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**テストと公開**

ジャーニーを公開する前に徹底的にテストして、期待どおりに機能し、適切なエクスペリエンスが提供されることを確認します。

[ガイドのテスト](testing-the-journey.md)
:::

::::

### ビデオチュートリアル {#video}

ジャーニーのコンポーネントを把握し、キャンバスでのジャーニー構築の基本を理解します。

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)

### その他のリソース

* **[エラーコードの参照](error-codes-reference.md)** - ジャーニーエラーコードとトラブルシューティング手順
* **[アラート](../reports/alerts.md)** - ジャーニー監視に関するアラートの設定
* **[トラブルシューティング](troubleshooting.md)** - ジャーニーに関する一般的な問題と解決策
* **[ジャーニーのチュートリアル](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** - 実践的なビデオチュートリアルを通じて、ジャーニーの作成について説明します
* **[ジャーニーのガードレールと制限](../start/guardrails.md)** - [!DNL Adobe Journey Optimizer] を使用する際にガードレールと制限を確認します

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;これは、Adobe Journey Optimizerのジャーニーオーケストレーションの包括的な基本ガイドです。主な機能（リアルタイム配信とバッチ配信、コンテキストデータ、組み込みのカスタムアクション、ビジュアルデザイナー、ジャーニーフラグメント、テスト）、一般的なユースケース、すべての主要な学習リソースへのリンクを取り上げます。

**インテント：**
* 最初のジャーニーを構築する前に、Journey Optimizer ジャーニーデザイナーで使用できる主な機能を理解します
* ジャーニーの作成、管理、テスト、またはトラブルシューティングに適したリソースに移動します
* ジャーニーデザイナーを使用して、任意のチャネルで1:1件のリアルタイムメッセージをトリガーする方法について説明します
* ジャーニーフラグメントによって、ジャーニー全体で共通のノードロジックを再利用する方法を説明します
* ウェルカムシリーズ、カート放棄、送信時間の最適化など、ジャーニーの一般的なユースケースに関するビデオチュートリアルとステップバイステップガイドにアクセスできます

**用語集：**
* **ジャーニーデザイナー**: Adobe Journey Optimizerのドラッグ&amp;ドロップ操作によるビジュアルキャンバスを使用して、マルチステップのカスタマージャーニー&#x200B;*（製品固有）*&#x200B;を構築および編成しました
* **ジャーニーフラグメント**：一度作成された再利用可能なジャーニーノードのセット（例：適格性チェック、チャネルルーティングロジック）で、複数のジャーニー&#x200B;*（製品固有）*&#x200B;に挿入されます
* **単一配信**：特定のイベントが発生したときに、単一のプロファイルに対してトリガーされるリアルタイム メッセージ *（製品固有）*
* **バッチ配信**: Adobe Experience Platform オーディエンスのすべてのプロファイルに一度またはスケジュール *（製品固有）*&#x200B;に送信されたメッセージ
* **送信時間最適化（STO）**: エンゲージメントを最大化するために、各プロファイルにメッセージを送信する最適な時間を予測するAIを活用した機能&#x200B;*（製品固有）*
* **カスタムアクション**: メッセージの送信またはデータの取得のためにAPI経由でサードパーティシステムに接続するジャーニーアクティビティ *（製品固有）*

**ガードレール：**
* ジャーニーのガードレールと制限事項については、ガードレール ページで個別に説明します。大規模な設計を行う前に、必ず確認してください
* カスタムアクションをジャーニーで使用するには、テクニカルユーザーが事前に設定する必要があります
* ジャーニーフラグメントは、ジャーニーに挿入する前にアクティブにする必要があります

**用語：**
* 正規名：ジャーニー – 頭字語：なし – バリエーション：カスタマージャーニー、オーケストレーションフロー、マルチステップジャーニー
* 同義語：「ジャーニーデザイナー」 = 「ジャーニーキャンバス」 = 「ジャーニービルダー」
* 混同しないでください：「組み込みのチャネルアクション」≠「カスタムアクション」 – 組み込みのアクションはネイティブのAJO チャネルを使用します。カスタムアクションは外部サードパーティ APIを呼び出します

**FAQ:**
* **Q: ジャーニーでのリアルタイム（単一）配信とバッチ配信の違いは何ですか？** — イベントが発生したときに、リアルタイムで1つのプロファイルに対してメッセージをトリガーします。 バッチ配信では、オーディエンスを読み取りアクティビティを使用して、オーディエンス内のすべてのプロファイルを一度に処理するか、スケジュールに従って処理します。
* **Q：複数のジャーニーで共通のロジック（適格性チェックなど）を再利用できますか？**  – はい。ノードをジャーニーフラグメントとして保存し、サンドボックス全体の任意のジャーニーにアクティブフラグメントを挿入します。
* **Q：最初のジャーニーを作成するには、どこへ行けばよいですか？** — 「最初のジャーニーを作成」ページのステップバイステップガイドに従います。このページでは、エントリポイントの選択、キャンバスのデザイン、テスト、およびパブリケーションについて説明します。
* **Q: ジャーニーからサードパーティシステムを介してメッセージを送信するにはどうすればよいですか？** — カスタムアクションを設定して外部APIを呼び出し、それをジャーニーキャンバスのアクションアクティビティとして追加します。
* **Q：一般的なジャーニーに関する質問に対する回答はどこで見つけることができますか？** — コンセプト、構築、テスト、実行、モニタリング、ベストプラクティスに関するFAQ ページにアクセスして、ジャーニーのFAQを確認してください。

+++
