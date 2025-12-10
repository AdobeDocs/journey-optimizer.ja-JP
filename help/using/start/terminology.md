---
solution: Journey Optimizer
product: journey optimizer
title: 主な用語
description: Adobe Journey Optimizerの基本的な用語と概念
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: 965bb76529f500d6fa4d89fa1d56979afe9d5bb0
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%

---

# 主な用語 {#key-terminology}

このリファレンスガイドでは、Adobe Journey Optimizerを使用する際に出会う重要な用語について説明します。 これらの概念を理解することで、プラットフォームを自信を持ってナビゲートし、チームと効果的に共同作業できるようになります。

>[!TIP]
>
>機能とワークフローについて詳しくは、このガイド全体でリンクされている特定のドキュメントの節を参照してください。

## コアプラットフォームの用語 {#core-terms}

| 用語 | 定義 |
|------|------------|
| **Adobe Journey Optimizer（AJO）** | あらゆるチャネル（メール、SMS、プッシュ通知、web）をまたいで、パーソナライズされたメッセージを作成し、顧客に配信するためのアプリケーション。 これにより、リアルタイムの顧客のアクションに応答するカスタマージャーニーを設計できます。 |
| **Adobe Experience Platform（AEP）** | すべての顧客データを 1 か所で収集および整理するAdobe Journey Optimizerの基盤。 Journey Optimizerがパーソナライゼーションに使用する統合顧客プロファイルを作成します。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} |
| **リアルタイム顧客プロファイル** | オンライン、オフライン、CRM、サードパーティデータなど、複数のチャネルのデータを組み合わせた、各顧客の統合されたリアルタイムビュー。 顧客がブランドとやり取りすると、各プロファイルは動的に更新されます。 [詳細情報](../audience/get-started-profiles.md) |
| **サンドボックス** | ライブカスタマーコミュニケーションに影響を与えずにテストと実験を行うための個別のワークスペース。 Adobe Journey Optimizerには、開発環境、テスト環境、実稼動環境用の複数のサンドボックスが用意されています。 [詳細情報](../administration/sandboxes.md) |

## ジャーニーとキャンペーンの用語 {#journey-campaign-terms}

| 用語 | 定義 |
|------|------------|
| **ジャーニー** | 時間の経過と共にブランドとのエクスペリエンスを顧客に導く一連のつながりのある手順。 各ステップは、顧客の行動や時間のトリガーに基づいて実行され、パーソナライズされたインタラクションを逐次的に実行できるようになります。 [詳細情報](../building-journeys/journey.md) |
| **Campaign** | 特定のオーディエンスに送信される単一の通信または一連の通信。 時間の経過と共に展開されるジャーニーとは異なり、キャンペーンは、メッセージをスケジュールまたはトリガー（即時または特定の時間）に配信します。 [詳細情報](../campaigns/get-started-with-campaigns.md) |
| **イベント** | ジャーニーをトリガーまたは進行させるアクションまたは発生。 イベントには、顧客アクション（購入の実行、買い物かごの放棄）またはシステムイベント（日時、データの変更）があります。 [詳細情報](../event/about-events.md) |
| **チャネル** | 顧客との通信に使用する方法：メール、SMS、プッシュ通知、アプリ内メッセージ、web またはダイレクトメール。 各チャネルには特定の設定が必要です。 [詳細情報](../configuration/get-started-configuration.md) |

## 顧客とオーディエンスの用語 {#customer-audience-terms}

| 用語 | 定義 |
|------|------------|
| **オーディエンス** | 「過去 30 日以内に購入した顧客」や「ロイヤルティプログラムメンバー」など、共通の特徴や行動を共有する顧客のグループ。 オーディエンスは、特定の顧客セグメントをターゲット設定するために使用されます。 [詳細情報](../audience/about-audiences.md) |
| **オーディエンスの選定** | 顧客がオーディエンスに結合したり、オーディエンスから離脱したりするときに発生する自動プロセス。 Journey Optimizerでは、オーディエンスに対してアクションのトリガーを設定できるので、タイムリーで関連性の高いコミュニケーションを確保できます。 [詳細情報](../building-journeys/audience-qualification-events.md) |
| **エンゲージ可能なオーディエンス** | ライセンス契約に基づき、Adobe Journey Optimizerを通じてアクティブに連絡できる顧客プロファイルの数。 これは、通常、過去 12 か月以内にエンゲージされたプロファイルを指します。 |
| **テストプロファイル** | 実際の顧客に送信する前にメッセージのテストとプレビューに使用される架空のプロファイル。 テストプロファイルは、パーソナライゼーション、コンテンツ、ジャーニーロジックの検証に役立ちます。 [詳細情報](../audience/creating-test-profiles.md) |

## コンテンツとPersonalizationの用語 {#content-terms}

| 用語 | 定義 |
|------|------------|
| **パーソナライゼーション** | プロファイルデータ、環境設定、行動を使用して、個々の顧客に合わせてコンテンツを調整するプロセス。 例えば、顧客の名前を挿入したり、閲覧履歴に基づいて製品レコメンデーションを表示したりします。 [詳細情報](../personalization/personalize.md) |
| **コンテンツテンプレート** | 複数のキャンペーンやジャーニーで再利用可能なメッセージデザインを使用して、ブランドの一貫性を維持し、コンテンツの作成を高速化できます。 [詳細情報](../content-management/content-templates.md) |
| **フラグメント** | 複数のメッセージで使用して一貫性を確保し、一元的な更新を可能にする、再利用可能なコンテンツブロック（ヘッダー、フッター、プロモーションバナーなど）。 [詳細情報](../content-management/fragments.md) |
| **ランディングページ** | 顧客が通信のオプトイン/オプトアウト、サービスの購読、またはオンラインフォームを通じた情報の提供を行えるスタンドアロン web ページ。 [詳細情報](../landing-pages/get-started-lp.md) |

## 決定およびオファー条件 {#decision-terms}

| 用語 | 定義 |
|------|------------|
| **意思決定管理** | リアルタイムのプロファイルデータ、コンテキスト、ビジネスルールに基づいて、各顧客に最適なコンテンツやオファーを自動的に選択する機能。 [詳細情報](../offers/get-started/starting-offer-decisioning.md) |
| **オファー** | 顧客に提示できるマーケティングメッセージ、割引またはプロモーション。 オファーには、オファーを受信できる顧客を決定する実施要件ルールが含まれています。 [詳細情報](../offers/offer-library/creating-personalized-offers.md) |
| **決定方針** | 実施要件、優先度、キャッピングルールなどの制約に基づいて、どのオファーをどの顧客に何時に表示するかを決定する一連のルールと戦略。 [詳細情報](../experience-decisioning/create-decision.md) |

## データおよび設定条件 {#data-config-terms}

| 用語 | 定義 |
|------|------------|
| **スキーマ** | フィールド名、データタイプ、関係など、Adobe Experience Platformでのデータの編成方法を定義する構造。 スキーマは、システム間でデータの一貫性を確保します。 [詳細情報](../data/get-started-schemas.md) |
| **データセット** | 特定のスキーマに従うデータのコレクション（通常はテーブル）。 データセットには、顧客データ、インタラクションイベントおよびパーソナライゼーションに使用されるその他の情報が格納されます。 [詳細情報](../data/get-started-datasets.md) |

>[!NOTE]
>
>Adobe Experience Platformの用語の包括的な用語集については、[Adobe Experience Platform用語集 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html?lang=ja){target="_blank"} を参照してください。

## 関連トピック {#related-topics}

* [Journey Optimizerの動作について](understanding-ajo.md)
* [ユーザーインターフェイスの概要](user-interface.md)
* [役割と学習パスを選択](quick-start.md)

