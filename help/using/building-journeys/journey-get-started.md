---
solution: Journey Optimizer
product: journey optimizer
title: Journey Orchestration – 完全ガイド
description: ' [!DNL Adobe Journey Optimizer]でのジャーニーオーケストレーションを開始するための包括的なガイド'
feature: Journeys, Get Started, Overview
role: User
level: Beginner, Intermediate
hide: true
keywords: ジャーニー，オーケストレーション，入門，オンボーディング，機能
exl-id: 96b1d619-986d-493d-a73b-d7c63b92cca8
TQID: https://experienceleague.adobe.com/Ht6fS6uanOs-rXoT4bAnK6eGvm9kOmH-N5B-y8KU6Rc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: ad78185d-8f79-40ad-9bad-cbde74af74eeid: b3538224-471e-4c63-a444-9b19d89ae29cid: baecb07f-ce89-4ebb-9cd9-0f7c053f944fid: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: a6c67b0d-bd3e-4d5d-95a8-882e3709d632id: b15c7c2e-788c-4eb7-86a8-390565b0d2c9id: b32bb433-f8c6-4931-8e52-e657230a3bf2id: b3a93754-a8b8-46eb-9421-7eccaeeb3dffid: b9d00d1b-a371-4a75-a52a-3f8ea2029020id: ba62ad25-65cb-4ea9-b7aa-0fa87c4a9fa0id: cfba2953-2ce9-4b00-a00c-71cd338ae63fid: da923278-9c80-47b0-bebd-b68c341e76fbid: fa683eda-48de-4558-af32-2673edcd44fe
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 941
ht-degree: 0%

---

# ジャーニーオーケストレーション – 完全ガイド{#journey-orchestration-guide}

[!DNL Adobe Journey Optimizer]のジャーニーを利用すると、オーディエンスの行動やニーズにリアルタイムで適応する、パーソナライズされたマルチステップのカスタマージャーニーを作成できます。 直感的なドラッグ&amp;ドロップ操作のキャンバスを使用して、複数のチャネルをまたいでメッセージやアクションを編成し、コンテキストデータとオーディエンスのターゲティングを活用して効果を最大化できます。

この記事では、リアルタイムのトリガーを検証する場合であれ、ジャーニーのプロパティを管理する場合であれ、カスタムのアクションや式などの高度なツールを使用する場合であれ、有意義かつタイムリーな顧客体験を提供するジャーニーを自信を持って設計、改善するための明確なロードマップを提供します。

## ジャーニーとは？

[!DNL Journey Optimizer]を使用して、イベントまたはデータソースに保存されているコンテキストデータを使用して、リアルタイムのオーケストレーションのユースケースを構築します。 顧客の行動やビジネスイベントにリアルタイムで対応するマルチステップの高度なシナリオを設計します。

Journey Optimizerのジャーニーデザイナーは、マーケターやジャーニーの実務担当者が、チャネルをまたいでマルチステップの1:1のジャーニーを編成するために必要なあらゆるものを提供します。 さらに、直感的なドラッグ&amp;ドロップ操作のキャンバスを使用して、カスタマージャーニーの各段階を編成し、ターゲットオーディエンスを定義できます。また、行動、コンテキストデータ、ビジネスイベントにもとづいて、ターゲットオーディエンスが閲覧するメッセージ、オファー、コンテンツをチャネルをまたいで含めることができます。

![ パレット、カンバス、およびプロパティパネルを使用したジャーニーデザイナーインターフェイス ](assets/journey38.png)

**構築を開始する準備ができましたか？** [このページ ](journey-gs.md)で最初のジャーニーを作成およびデザインする方法について説明します。


## 主な能力 {#capabilities}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg)

**リアルタイムおよびバッチ配信**

イベントが受信されたときにトリガーされるリアルタイム **単一配信**、または[!DNL Adobe Experience Platform]人のオーディエンスを使用してバッチ **で**&#x200B;を送信します。

[ジャーニー入力について詳しく見る](entry-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/database.svg)

**コンテキストデータ**

イベントからの&#x200B;**コンテキストデータ**、[!DNL Adobe Experience Platform]からの情報、またはサードパーティ API サービスからのデータを活用します。

[データソースの操作](../datasource/about-data-sources.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**組み込みアクション**

**組み込みのチャネルアクション**&#x200B;を使用して、電子メール、プッシュ通知、SMS/MMSなどで[!DNL Journey Optimizer]にデザインされたメッセージを送信します。

[ジャーニー内のメッセージの送信](journey-action.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

**カスタムアクション**

メッセージの送信や外部APIへの接続にサードパーティシステムを使用している場合は、**カスタムアクション**&#x200B;を作成します。

[カスタムアクションの設定](../action/about-custom-action-configuration.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**ビジュアルジャーニーデザイナー**

**ジャーニーデザイナー**&#x200B;を使用して、マルチステップのユースケースを構築します。エントリイベントまたはオーディエンスアクティビティの読み取りを簡単にドラッグ&amp;ドロップし、条件を追加し、パーソナライズされたメッセージを送信します。

[ジャーニーデザイナーの詳細](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**テストと最適化**

配信時間の最適化などの高度な機能を利用して、公開前にジャーニーをテストし、パフォーマンスを監視して、配信を最適化できます。

[ジャーニーのテストと公開](testing-the-journey.md)
:::

::::

## ユースケースと例 {#use-cases}

マーケターは、ジャーニーデザイナー内から、イベントが発生したときに、任意のチャネルを通じて1:1件のトリガーされたメッセージをリアルタイムで送信できます。 例えば、お客様がサービスに登録すると、[ ウェルカムメール ](message-to-subscribers-uc.md)をトリガーして、初めてアプリにログインして環境設定を行うよう促すことができます。 購入を完了し、電子メールを開き、アプリにログインするなどのアクションを活用することで、新規顧客のジャーニーを誘導できます。

[ ジャーニーデザイナー](using-the-journey-designer.md)は、電子メール、プッシュ通知、SMS/MMSなどのアウトバウンドメッセージと、Journey Optimizer内で直接構築されたモバイルアプリ、web サイト、コードベースのエクスペリエンスなどのインバウンドチャネルをサポートする[組み込みのチャネルアクション ](journey-action.md)を提供します。 サードパーティシステムを使用してメッセージを送信することもできます。Journey Optimizerには[ カスタムアクション ](using-custom-actions.md)が含まれており、これらのシステムをジャーニーデザイナーから直接ジャーニーに統合できます。


:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**ユースケースを通じて学習**

実際の実装とベストプラクティスを示す、包括的なエンドツーエンドのジャーニーユースケースをご確認ください。

[その他のユースケース](jo-use-cases.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg)

**新規登録者を歓迎**

顧客がサービスに登録した際に、パーソナライズされたウェルカムジャーニーを送信し、オンボーディング手順を導きます。

[Adobe Targetの製品概要](message-to-subscribers-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/calendar-alt.svg)

**メール送信時間の最適化**

AIを活用した送信時間の最適化により、各顧客がエンゲージする可能性が最も高いタイミングでメールを配信します。

[Adobe Targetの製品概要](send-time-optimization.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/chart-line.svg)

**配信を増やす**

徐々にメッセージ量を増やすことで、送信のレピュテーションが高まり、配信品質の問題を回避できます。

[Adobe Targetの製品概要](ramp-up-deliveries-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bullseye.svg)

**平日ごとの目標**

顧客がジャーニーにエントリする曜日に基づいて、異なるコンテンツを送信します。

[Adobe Targetの製品概要](weekday-email-uc.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/question.svg)

**ジャーニーに関するFAQ**

ジャーニーの構築、トラブルシューティング、ベストプラクティスに関するよくある質問への回答を示します。

[FAQを表示](journey-faq.md)
:::

::::



## 学習リソース {#learning-resources}

:::: landing-cards-container

:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg)

**ジャーニーの作成と管理**

パーソナライズされたオムニチャネル施策を構築するためのカスタマージャーニーの設計、テスト、公開、追跡に関するステップバイステップのガイダンスを解説します。

[ ジャーニー作成の探索](../../rp_landing_pages/create-journey-landing-page.md) | [ ジャーニー管理の学習](../../rp_landing_pages/manage-journey-landing-page.md) | [ジャーニーワークフローの手順](journey.md#workflow)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/puzzle-piece.svg)

**ジャーニーアクティビティ**

トリガー、意思決定ステップ、オーディエンス管理、パーソナライズされたメッセージをジャーニーで設定し、活用する方法をご確認ください。

[アクティビティを見る](../../rp_landing_pages/about-journey-building-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg)

**式と条件**

強力なツールと構文を使用して、動的なワークフロー、データ操作、高度なジャーニーオーケストレーションを実現するマスター式の作成をサポートします。

[エクスプレッションについて詳しく見る](../../rp_landing_pages/building-advanced-conditions-journeys-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/bell.svg)

**トラブルシューティングと監視**

ツール、エラーコード、デバッグと最適化のベストプラクティスを使用して、ジャーニー実行の問題を診断し、解決します。

[トラブルシューティングガイド](../../rp_landing_pages/troubleshoot-journey-landing-page.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/book.svg)

**ジャーニーデザイナーの概要**

ビジュアルインターフェイスを使用して、ジャーニーキャンバス、パレット、カスタマージャーニーの設計方法を理解します。

[デザイナーを学ぶ](using-the-journey-designer.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/shield-halved.svg)

**テストと公開**

ジャーニーを公開する前に、ジャーニーを詳細にテストし、期待通りに機能することを確認し、適切なエクスペリエンスを提供します。

[テストガイド](testing-the-journey.md)
:::

::::

### ビデオチュートリアル {#video}

ジャーニーのコンポーネントを確認し、キャンバスでジャーニーを構築するための基本的な方法を理解します。

>[!VIDEO](https://video.tv.adobe.com/v/3424996?quality=12)

### 関連資料

* **[エラーコード参照](error-codes-reference.md)** - ジャーニーエラーコードとトラブルシューティング手順
* **[アラート](../reports/alerts.md)** - ジャーニー監視のアラートを設定します
* **[トラブルシューティング](troubleshooting.md)** – 一般的なジャーニーの問題と解決策
* **[ジャーニーチュートリアル ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/journeys/journey-designer-overview){target="_blank"}** – 実践的なビデオチュートリアルを通じてジャーニー構築を学ぶ
* **[ジャーニーのガードレールと制限事項](../start/guardrails.md)** - [!DNL Adobe Journey Optimizer]を使用する際のガードレールと制限事項を確認する
