---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer について
description: Adobe Journey Optimizer が Adobe Experience Platform と連携して、パーソナライズされたカスタマーエクスペリエンスを提供する仕組みについて説明します。
feature: Get Started
topic: Content Management
role: Admin, Developer, User
level: Beginner
keywords: journey optimizer，仕組み、アーキテクチャ、エクスペリエンスプラットフォーム、機能領域
exl-id: 9df179a0-a5f6-4dbd-a9db-a103731b1854
TQID: https://experienceleague.adobe.com/E2ksPVFZBggv1RgEri7jx30G2oSanpmNs77vH9Yuq78
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: fdac7813-bd56-47ae-9f6d-fa94ad1c5dee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5520579-b31f-4df7-9281-f0d9f91e2edcid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 46a5a6dc0a3486633a1a71f8bba8a3cd53aaa618
workflow-type: tm+mt
source-wordcount: 986
ht-degree: 58%

---

# Journey Optimizer について {#understanding-ajo}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Journey OptimizerとAdobe Experience Platformの連携の仕組みを説明します。これにより、パーソナライズされたジャーニーの背後にある、データからエクスペリエンスへのサイクル、機能領域、アーキテクチャを理解できます。

>[!ENDSHADEBOX]

ここでは、Adobe Experience PlatformとJourney Optimizerの連携の仕組み、継続的なデータツーエクスペリエンスのサイクル、主な機能領域、アーキテクチャの詳細、統合ポイントについて説明します。

Adobe Journey Optimizer と Adobe Experience Platform は連携して、データ駆動型の大規模なパーソナライゼーションを実現します。 このページでは、これらのシステムが動作する仕組みと、主要な機能領域を組み合わせて優れたカスタマーエクスペリエンスを実現する仕組みについて説明します。 [主な機能の詳細情報](get-started.md) | [主な用語について](terminology.md)

## Journey Optimizerの仕組み {#how-it-works}

統合されたデータ基盤がなければ、ブランドは複数のチャネル固有のツールに依存せざるを得ません。そのため、各顧客の一貫性のあるビューを維持したり、リアルタイムでのそれぞれの行動に対応することが困難になります。 Journey Optimizerなら、Adobe Experience Platformを基盤として、顧客データ、コンテンツの制作、ジャーニーオーケストレーションをつなぎ合わせ、単一の継続的なシステムを構築できます。 その結果、顧客ロイヤルティと生涯価値を高める有意義なブランド体験を創出できます。

Adobe Journey Optimizer は、データを収集、分析および適用する継続的なフローとして機能し、パーソナライズされたカスタマージャーニーを作成します。

![Adobe Experience Platformが基盤となるデータレイヤーであり、Journey OptimizerがReal-Time CDP、Customer Journey Analytics、Adobe Mix Modelerと共に構築され、Real-Time Customer Profile、データガバナンス、ID解決などのコアサービスをすべて共有している図。](assets/ajo-aep-architecture-diagram.png)

### Adobe Experience Platform:the foundation {#aep-foundation}

Adobe Experience Platform はバックボーンとして機能し、ブランドがお客様データを一元化し、パーソナライズされたエクスペリエンスのためにアクティブ化できるようにします。

* **データプラットフォーム** - お客様データを収集、管理、構造化し、システム間の一貫性を確保する一元的なハブ。 [スキーマとデータセットの詳細情報](../data/get-started-schemas.md)
* **データ取り込み（ソース）** - 事前定義済みのコネクタを使用して、CRM プラットフォーム、web サイト、モバイルアプリ、クラウドストレージからデータをインポートします。 [データソースについて](get-started-sources.md)
* **リアルタイム顧客プロファイル** - 複数のソース（メールのインタラクション、店舗での購入、web 動作）からのデータを結合して、統合プロファイルを作成します。 [プロファイルの詳細情報](../audience/get-started-profiles.md)
* **ガバナンスレイヤー** - 規制に準拠しながら、データアクセス、プライバシーコンプライアンスおよびセキュリティを管理します。 [プライバシードキュメントの表示](../privacy/get-started-privacy.md)

### Adobe Journey Optimizer：オーケストレーションエンジン {#ajo-orchestration}

Adobe Journey Optimizer は、Adobe Experience Platform からのデータとインサイトを適用し、インテリジェントでパーソナライズされたカスタマーエクスペリエンスを提供します。

* **お客様の理解** - リアルタイム顧客プロファイルにより、ターゲットメッセージ用にオーディエンスをセグメント化できます。 [オーディエンスの作成](../audience/about-audiences.md)
* **コンテンツとオファー** – 組み込みのビジュアルデザイナー、再利用可能なテンプレート、一元化されたアセットライブラリにより、プラットフォームを離れることなく、あらゆるチャネル向けにメッセージを作成およびパーソナライズできます。 動的パーソナライゼーションでは、顧客の属性、行動、コンテキストにもとづいてコンテンツを調整します。 その後、リアルタイムの意思決定ロジックによって、各個人に最適なオファーが選択されます。 [ デザインコンテンツ ](../../rp_landing_pages/content-management-landing-page.md) | [ アセットの管理](../integrations/assets.md) | [ オファーの管理](../offers/get-started/starting-offer-decisioning.md)
* **ジャーニーとキャンペーン管理** - インタラクションのシーケンス（ジャーニー）を自動化したり、1 回限りのターゲットメッセージ（キャンペーン）をスケジュールします。 [ジャーニーの作成](../building-journeys/journey-gs.md) | [キャンペーンの作成](../campaigns/get-started-with-campaigns.md)
* **配信（接続）** - メール、SMS、プッシュ通知、ダイレクトメールなどのチャネルを通じてメッセージを配信し、データを外部システムにエクスポートします。 [チャネルの設定](../configuration/get-started-configuration.md)
* **測定と分析** - 継続的な改善のためにレポートで顧客エンゲージメントとキャンペーンのパフォーマンスを追跡します。 [レポートの表示](../reports/campaign-global-report-cja.md)

### 継続的な最適化サイクル {#optimization-cycle}

このエコシステムは、継続的な最適化サイクルとして機能します。 データは、パーソナライズされたコンテンツと決定を提供する、お客様の理解を推進します。 これらはジャーニーに調整され、チャネルをまたいで配信され、有効性を測定し、時間の経過と共に調整されます。

![Journey Optimizerの継続的な最適化サイクルを示す図：データ取り込みは、コンテンツとオファーの意思決定に役立つ顧客プロファイルを提供します。このプロファイルは、ジャーニーにオーケストレーションされ、チャネルをまたいで配信され、パフォーマンスを測定し、時間の経過とともに調整されます。](../assets/do-not-localize/get-started-flow.png)

## 主な活動分野 {#functional-areas}

Journey Optimizer には、シームレスに連携するいくつかの主要な機能領域が含まれています。

| 機能領域 | 目的 | 主なアクティビティ |
|-----------------|---------|----------------|
| **データ管理** | 顧客データの整理 | スキーマの定義、データセットの作成、様々なシステムからのデータのインポートを行います。 [詳細情報](../data/get-started-schemas.md) |
| **顧客管理** | お客様の理解 | 統合プロファイルの作成、ID の解決、オーディエンスの作成を行います。 [詳細情報](../audience/get-started-profiles.md) |
| **コンテンツ管理** | パーソナライズされたメッセージの作成 | メールのデザイン、アセットの管理、テンプレートとフラグメントの作成、コンテンツのパーソナライズを行います。 [詳細情報](../../rp_landing_pages/content-management-landing-page.md) |
| **意思決定管理** | リアルタイムでの最適なオファーの選択 | オファーライブラリの管理、ルールの定義、制約の適用、ランキングロジックの確立を行います。 [詳細情報](../offers/get-started/starting-offer-decisioning.md) |
| **ジャーニー管理** | 自動化されたカスタマーエクスペリエンスのデザイン | ビジュアルデザイナーでのジャーニーの作成、トリガーの設定、条件の追加、待機ステップの追加を行います。 [詳細情報](../building-journeys/journey-gs.md) |
| **接続** | データソースとチャネルの接続 | ソースコネクタの設定、チャネルの設定、外部プラットフォームへの接続を行います。 [詳細情報](../configuration/get-started-configuration.md) |
| **管理とプライバシー** | 設定とコンプライアンスの制御 | ユーザーの管理、サンドボックスの設定、チャネルの設定、プライバシーリクエストの処理を行います。 [詳細情報](../administration/permissions.md) |

### 連携の仕組み {#working-together}

これらの機能領域は、継続的なサイクルで動作します。

1. **データ取り込み** - データは、データ管理によって構造化され、Adobe Experience Platform にフローされます
2. **お客様の理解** - リアルタイム顧客プロファイルにより、データが統合され、顧客管理により、オーディエンスが作成されます
3. **コンテンツとオファー戦略** - コンテンツ管理では、メッセージを作成し、意思決定管理では、オファーロジックを定義します
4. **オーケストレーション** - ジャーニー管理では、お客様データ、コンテンツ、決定を使用してチャネル間でインタラクションをマッピングします
5. **配信** - 接続により、チャネル経由でのメッセージ配信や外部システムとのデータの共有が容易になります
6. **測定** - パフォーマンスデータでは、インサイトがフィードバックされ、オーディエンス、コンテンツ、決定、ジャーニーが絞り込まれます
7. **ガバナンス** - 管理とプライバシーの制御により、全体を通じてコンプライアンスが確保されます

## アーキテクチャの詳細 {#architecture-details}

Journey Optimizerは、Real-Time CDP、Customer Journey Analytics、Adobe Mix Modelerに加え、Adobe Experience Platform上にネイティブに構築された4つのアプリケーションのひとつです。 Adobe AEPのコアサービスであるReal-Time Customer Profile、ID グラフ、データガバナンス、クエリサービスを共有することで、別々の統合を必要とせずに、統合された顧客データ基盤を利用できます。 Journey Optimizerは、スタンドアロンアプリケーションとして動作したり、他のAEP ネイティブアプリケーションと相互運用したりできます。

統合パターン、前提条件、システムデータフローなど、技術的なアーキテクチャについて詳しくは、[Adobe Journey Optimizer ブループリント ](https://experienceleague.adobe.com/en/docs/blueprints-learn/architecture/architecture-diagrams/customer-journeys/journey-optimizer/journey-optimizer-overview){target="_blank"}を参照してください。 実装に関する考慮事項については、[ ガードレールと制限事項を確認](guardrails.md)してください。

## プライバシーとセキュリティ {#privacy-security}

Adobe Experience Cloud のプライバシーとセキュリティのプラクティスは、Adobe Journey Optimizer に適用されます。 これらの対策により、GDPR などのプライバシー規制への準拠が確保され、お客様の信頼を維持しながら、パーソナライズされたエクスペリエンスを提供できます。 [Journey Optimizer でのプライバシーの詳細情報](../privacy/get-started-privacy.md)
