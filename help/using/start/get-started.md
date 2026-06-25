---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer
description: Adobe Journey Optimizerとは何か、主な機能、Adobe Experience Platformに組み込む方法について説明します。
feature: Get Started
topic: Content Management
role: User
level: Beginner
keywords: Journey Optimizer, AJO とは, Adobe Journey Optimizer, 基本を学ぶ, オムニチャネル, パーソナライゼーション, カスタマージャーニー
exl-id: 956178c0-9985-4ff8-a29e-17dd367ce4d4
TQID: https://experienceleague.adobe.com/HYykJIqT1bcoN1oXrG6uvfNuhDNOGLfPtOAf-Y3hzsQ
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: addf009e-030a-4310-8534-776a3e62ed48id: b5520579-b31f-4df7-9281-f0d9f91e2edcid: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ea5309c91db90e54b0c965a34d84b29c57314c62
workflow-type: tm+mt
source-wordcount: 804
ht-degree: 85%

---

# Journey Optimizer の基本を学ぶ {#ajo-gs}

>[!BEGINSHADEBOX]

**このページ：** Adobe Journey Optimizer の概要、そのコア機能、具体的なユースケースについて説明します。これにより、顧客エンゲージメントの目標にどのように適合するかを判断できます。

>[!ENDSHADEBOX]

このページでは、Adobe Journey Optimizer の概要、対象ユーザー、主な機能、Adobe Experience Platform アーキテクチャに適合する仕組みについて説明します。 これは、新規ユーザーに対して推奨される開始点です。

## [!DNL Adobe Journey Optimizer] とは？{#about-ajo}

[!DNL Adobe Journey Optimizer] は、すべてのチャネルとタッチポイントをまたいで、つながりがあり、コンテキストに応じて、パーソナライズされたカスタマーエクスペリエンスを作成および提供するエンタープライズアプリケーションです。 これは [!DNL Adobe Experience Platform] 上にネイティブに作成され、統合されたリアルタイム顧客プロファイル、API ファーストのオープンなフレームワーク、一元化されたオファー決定支援、AI／ML 機能を活用します。 Journey Optimizer により、ブランドがスケジュール済みのマーケティングキャンペーンとリアルタイムのイベントトリガー通信の両方を、単一のアプリケーションから大規模に調整できます。 その結果、顧客の忠誠度とライフタイム値を向上させる、有意義なブランドエクスペリエンスが実現します。

このガイドは、Journey Optimizer を初めて使用するマーケター、運用チーム、管理者に適用されます。

➡️ [Journey Optimizer の概要を確認](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/introduction.html?lang=ja){target="_blank"}（ビデオ）


<!--
 Use [!DNL Adobe Journey Optimizer] to build multi-step customer journeys that initiate a sequence of interactions, offers, and messages across channels in real time. This approach ensures customers are engaged at the optimal moments based on their actions and relevant business signals. Learn how to build journeys in [this section](../building-journeys/journey-gs.md).

You can also create audience-based campaigns to send messages.
-->


## 主な機能 {#key-capabilities}

[!DNL Adobe Journey Optimizer] は、アプリケーション、デバイス、チャネルを問わず、パーソナライズされ、接続されたタイムリーな顧客エクスペリエンスを作成して提供するための、アジャイルで拡張性の高いアプリケーションです。

![Journey Optimizer の 3 つのコア機能領域（リアルタイムの顧客インサイトとエンゲージメント、最新のオムニチャネルオーケストレーションと実行、インテリジェントな意思決定とパーソナライゼーション）を示す図。これらのすべてが Adobe Experience Platform 上に作成されています。](assets/ajo-capabilities.png)

主な機能は次のとおりです。

### リアルタイムの顧客インサイトとエンゲージメント

統合されたプロファイルは、行動データ、トランザクションデータ、財務データ、運用データなど、顧客のタッチポイントを横断するすべてのソースからのライブデータを融合し、顧客の個人的およびコンテキストに応じたエクスペリエンスを最適化します。 [プロファイルとオーディエンスの詳細情報](../audience/get-started-profiles.md)

### 最新のオムニチャネルオーケストレーションと実行

1:1 の顧客エンゲージメントとマーケティングアウトリーチのために、カスタマージャーニーを調和させ、最適化できる単一のキャンバスです。これによってブランドは、カスタマーライフサイクルを通じてより多くの価値を提供できるようになります。 [!DNL Adobe Journey Optimizer] で設計されたカスタマージャーニーは、イベントベースの動的なものにすることができます。これにより、ブランドは状況にリアルタイムに反応し、これらのやり取りをスケジュールされたキャンペーンと結び付け、顧客に送信するコミュニケーション、タイミング、チャネルに関して適切な決定を下すことができます。 ドラッグ＆ドロップによるビジュアルデザイナー、再利用可能なテンプレート、コンテンツフラグメント、パーソナライゼーションエディターなどの組み込みのコンテンツ制作ツールにより、チームはすべてのチャネル向けメッセージを同じワークフロー内で直接作成、パーソナライズ、管理できます。 [最初のジャーニーの作成](../building-journeys/journey-gs.md) | [コンテンツのデザイン](../../rp_landing_pages/content-management-landing-page.md)

### インテリジェントな意思決定とパーソナライゼーション

ブランドは、一元的な決定を適用し、人工知能と機械学習を組み込んで、顧客体験全体で予測インサイトを設定できます。これにより、意思決定の自動化や、規模に合わせたエクスペリエンスの最適化が容易になります。 決定では、[!DNL Adobe Journey Optimizer] を通じ、複数のチャネルをまたぐ大規模な一元的なオファーを支援します。 [オファー決定支援の探索](../offers/get-started/starting-offer-decisioning.md) | [AI 機能の確認](ai-features.md)


## よくあるユースケース {#use-cases}

Journey Optimizerは、リアルタイムのトリガージャーニーやカート放棄による復旧から、スケジュール型のキャンペーン、意思決定、業務上の通知に至るまで、幅広いシナリオをサポートします。

目標に合った機能を見つけるには、[Journey Optimizerのユースケースの概要](ajo-use-case-guide.md)を参照してください。 エンドツーエンドの作業済み例については、[ ジャーニーのユースケースライブラリ ](../building-journeys/jo-use-cases.md)を参照してください。


## 可用性とライセンス {#availability}

このドキュメントは、Journey Optimizer の最新リリースを対象とし、特に明記されていない限り、B2C Edition と B2B Edition の両方のユーザーに適用されます。 環境で使用できるコンポーネントと機能は、[権限](../administration/permissions.md)と[ライセンスパッケージ](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"}によって異なります。 ご不明な点について詳しくは、アドビカスタマーサクセスマネージャーまたはアドビ担当者までお問い合わせください。

[!DNL Journey Optimizer]には、[!DNL Adobe CX Enterprise]の一般的なプライバシーガイドラインと手順が適用されます。 [ プライバシー](https://www.adobe.com/jp/privacy/experience-cloud.html){target="_blank"}の詳細を確認します。 [!DNL Adobe CX Enterprise] 


## アーキテクチャ {#architecture}

Journey Optimizer は、Adobe Experience Platform 上にネイティブに作成され、そのデータ基盤、ID グラフ、ガバナンスサービスを共有します。これらのシステムの連携の仕組みについて詳しくは、[Journey Optimizer について](understanding-ajo.md)を参照してください。


## 関連リソース {#related-resources}

* [開始するための主な手順](quick-start.md) - 管理者、マーケター、データエンジニア向けの役割ベースのクイックスタートガイド。
* [データ管理の基本を学ぶ](../data/gs-data.md) - Journey Optimizer でデータを取り込み、統合し、アクティブ化する方法について説明します。
* [ジャーニーのデザインとメッセージの送信](../building-journeys/journey-gs.md) - 最初のカスタマージャーニーを作成し、チャネルアクションを設定します。
* [ライブレポート](../reports/live-report.md) - キャンペーンとジャーニーのパフォーマンスをリアルタイムで監視します。
* [Journey Optimizer の概要チュートリアル ](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/introduction-to-journey-optimizer/introduction){target="_blank"} - Journey Optimizer のコア概念のガイド付きビデオチュートリアル。
* [Journey Optimizer セキュリティの概要](https://www.adobe.com/content/dam/cc/en/security/pdfs/AJO_SecurityOverview.pdf)（PDF）- セキュリティアーキテクチャ、データ保護、コンプライアンスの詳細。
* [Journey Optimizer 製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer.html){target="_blank"} - 公式ライセンス用語と各エディションの機能の分類。

## 次の行き先 {#where-next}

| 私は… | 次に移動… |
|------------|--------|
| Journey OptimizerとAdobe Experience Platformの連携について説明します | [Journey Optimizerについて](understanding-ajo.md) |
| 特定の役割に関する基本を学ぶ | [役割と責任](quick-start.md) |
| ユースケースの探索 | [Journey Optimizer ユースケースの概要](ajo-use-case-guide.md) |
| 関連用語 | [用語](terminology.md) |
