---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerについて
description: Adobe Journey OptimizerがAdobe Experience Platformと連携して、パーソナライズされたカスタマーエクスペリエンスを提供する方法を説明します
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: a956684ab52f9045b5e1f84cc0b8d0071689873b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 12%

---

# Journey Optimizerについて {#understanding-ajo}

Adobe Journey Optimizer（AJO）と Adobe Experience Platform（AEP）は連携して、データ駆動型の大規模なパーソナライゼーションを実現します。このページでは、これらのシステムがどのように動作するか、主要な機能領域がどのように組み合わさって優れた顧客体験を提供するかについて説明します。

## Journey Optimizerの仕組み {#how-it-works}

Adobe Journey Optimizerは、パーソナライズされたカスタマージャーニーを作成するために、データを収集、分析、適用する継続的なフローとして機能します。

![](assets/ajo-aep-architecture-diagram.png)

### Adobe Experience Platform:The Foundation {#aep-foundation}

Adobe Experience Platformはバックボーンとして機能するので、企業は顧客データを一元化し、パーソナライズされたエクスペリエンスのためにアクティブ化できます。

* **データプラットフォーム** – 顧客データを収集、管理、構造化してシステム間の一貫性を確保するための一元的なハブ
* **データ取得（ソース）** – 事前定義済みのコネクタを使用して、CRM プラットフォーム、web サイト、モバイルアプリ、クラウドストレージからデータをインポートします
* **リアルタイム顧客プロファイル** – 複数のソース（メールのやり取り、店舗での購入、web 行動）からのデータを結合して、統合プロファイルを作成します
* **ガバナンスレイヤー** – 規制に準拠しながら、データアクセス、プライバシーコンプライアンス、セキュリティを管理します

### Adobe Journey Optimizer：オーケストレーションエンジン {#ajo-orchestration}

Adobe Journey Optimizerは、AEPのデータとインサイトを適用して、インテリジェントでパーソナライズされたカスタマーエクスペリエンスを提供します。

* **顧客の理解** - リアルタイム顧客プロファイルを使用すると、ターゲットメッセージング用にオーディエンスをセグメント化できます
* **コンテンツとオファー** - コンテンツを作成、管理およびパーソナライズするツール。個々のユーザーに最適なオファーを選択するリアルタイムロジック
* **ジャーニーとキャンペーン管理** - インタラクションのシーケンス（ジャーニー）を自動化し、1 回限りのターゲットメッセージ（キャンペーン）をスケジュールします
* **配信（接続）** - メール、SMS、プッシュ通知、ダイレクトメールなどのチャネルを通じてメッセージを配信し、データを外部システムに書き出します
* **測定と分析** – 継続的な改善に役立つレポートを使用して、顧客エンゲージメントとキャンペーンのパフォーマンスを追跡します

### 継続的な最適化サイクル {#optimization-cycle}

このエコシステムは、継続的な最適化サイクルとして機能します。データは、パーソナライズされたコンテンツと決定を提供する、お客様の理解を推進します。これらはジャーニーに調整され、チャネルをまたいで配信され、有効性を測定し、時間の経過と共に調整されます。

![](../assets/do-not-localize/get-started-flow.png)

## 主要な機能領域 {#functional-areas}

Journey Optimizerには、シームレスに連携する 7 つの主要な機能領域が含まれています。

| 機能領域 | 目的 | 主要なアクティビティ |
|-----------------|---------|----------------|
| **データ管理** | 顧客データの整理 | スキーマの定義、データセットの作成、様々なシステムからのデータの読み込み |
| **顧客管理** | お客様の理解 | 統合プロファイルの作成、ID の解決、オーディエンスの作成 |
| **コンテンツ管理** | パーソナライズされたメッセージの作成 | メールの設計、アセットの管理、テンプレートとフラグメントの作成、コンテンツのパーソナライズ |
| **意思決定管理** | 最適なオファーをリアルタイムで選択 | オファーライブラリの管理、ルールの定義、制約の適用、ランキングロジックの確立 |
| **ジャーニーの管理** | 自動化された顧客体験の設計 | ビジュアルデザイナーでジャーニーを作成し、トリガーを設定し、条件と待機ステップを追加します |
| **接続** | データソースとチャネルの接続 | ソースコネクタの設定、チャネルの設定、外部プラットフォームへの接続 |
| **管理とプライバシー** | コントロールの設定とコンプライアンス | ユーザーの管理、サンドボックスの設定、チャネルの設定、プライバシーリクエストの処理 |

### これらの領域の連携 {#working-together}

これらの機能領域は、連続したサイクルで動作します。

1. **データ取り込み** - Data Management で構造化されたAEPへのデータフロー
2. **顧客の理解** - リアルタイム顧客プロファイルはデータを統合し、顧客管理はオーディエンスを作成します
3. **コンテンツとオファー戦略** - コンテンツ管理はメッセージを作成し、意思決定管理はオファーロジックを定義します
4. **オーケストレーション** - Customer Management は、ジャーニーデータ、コンテンツ、意思決定を使用して、チャネルをまたいでインタラクションをマッピングします
5. **配信** – 接続により、チャネルを介したメッセージ配信や外部システムとのデータ共有が容易になります
6. **測定** - パフォーマンスデータは、インサイトをフィードして、オーディエンス、コンテンツ、決定およびジャーニーを絞り込みます
7. **ガバナンス** – 管理とプライバシー制御により、全体を通してコンプライアンスを確保します

## アーキテクチャの詳細 {#architecture-details}

技術チーム向けに、Journey OptimizerとAdobe Experience Platformの統合方法を示す詳細なアーキテクチャ図を次に示します。

![Adobe Journey Optimizer アーキテクチャ](assets/ajo-architecture.png)

Experience Platformには、Adobe Real-Time Customer Data Platform、Journey Optimizer、Customer Journey Analytics、Adobe Mix Modelerの 4 つのアプリケーションがネイティブに構築されています。 Journey Optimizerは、これらのアプリケーションとシームレスに連携しますが、独立して機能することもできます。

### 統合ポイント {#integration-points}

Journey Optimizerは、複数のレベルでAdobe Experience Platformと統合されます。

* **データレイヤー** – 同じリアルタイム顧客プロファイル、ID グラフ、データセットを共有します
* **サービスレイヤー** - AEPのガバナンス、プライバシー、クエリサービスを活用します
* **アプリケーションレイヤー** - AEP上でジャーニーオーケストレーション、意思決定管理、コンテンツ管理を提供します

[Adobe Journey Optimizer ブループリント ](https://experienceleague.adobe.com/ja/docs/blueprints-learn/architecture/customer-journeys/journey-optimizer/journey-optimizer-overview){target="_blank"} の詳細情報。

## プライバシーとセキュリティ {#privacy-security}

Adobe Experience Cloud のプライバシーとセキュリティのプラクティスは、Adobe Journey Optimizer に適用されます。これらの対策により、GDPR などのプライバシー規制への準拠が確保され、顧客の信頼を維持しながら、パーソナライズされたエクスペリエンスを提供できるようになります。

[Journey Optimizerのプライバシーの詳細情報](../privacy/get-started-privacy.md)

>[!MORELIKETHIS]
>
>* [Journey Optimizerの概要 ](get-started.md)
>* [ 主要用語 ](terminology.md)
>* [ユーザーインターフェイスガイド](user-interface.md)
>* [ ガードレールと制限 ](guardrails.md)

