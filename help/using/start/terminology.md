---
solution: Journey Optimizer
product: journey optimizer
title: 主な用語
description: Adobe Journey Optimizer の基本的な用語と概念
feature: Get Started
role: Admin, Developer, User
level: Beginner
source-git-commit: 4ae9e908d259dbd266417242cf9e65d693227061
workflow-type: ht
source-wordcount: '751'
ht-degree: 100%

---

# 主な用語 {#key-terminology}

このリファレンスガイドでは、Adobe Journey Optimizer を使用する際に発生する重要な用語を定義します。これらの概念を理解することで、プラットフォームを自信を持って操作し、チームと効率的に共同作業を行うことができます。

>[!TIP]
>
>機能とワークフローの説明について詳しくは、このガイド全体にリンクされている特定のドキュメントの節を参照してください。

## コアプラットフォームの用語 {#core-terms}

| 用語 | 定義 |
|------|------------|
| **Adobe Journey Optimizer** | チャネル（メール、SMS、プッシュ通知、web）をまたいで顧客にパーソナライズされたメッセージを作成および配信するためのアプリケーション。これにより、リアルタイム顧客アクションに対応するカスタマージャーニーを設計できます。 |
| **Adobe Experience Platform** | すべての顧客データを 1 か所に収集および整理する Adobe Journey Optimizer の基盤。Journey Optimizer がパーソナライゼーションに使用する統合顧客プロファイルを作成します。[詳細情報](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=ja){target="_blank"} |
| **リアルタイム顧客プロファイル** | オンライン、オフライン、CRM、サードパーティデータなど、複数のチャネルのデータを組み合わせた、各顧客の統合されたリアルタイムビュー。顧客がブランドとやり取りすると、各プロファイルは動的に更新されます。 [詳細情報](../audience/get-started-profiles.md) |
| **サンドボックス** | 実際のお客様とのコミュニケーションに影響を与えずに、テストや実験を行う独立したワークスペース。Adobe Journey Optimizer には、開発環境、テスト環境、実稼動環境用の複数のサンドボックスが用意されています。[詳細情報](../administration/sandboxes.md) |

## ジャーニーとキャンペーンの用語 {#journey-campaign-terms}

| 用語 | 定義 |
|------|------------|
| **ジャーニー** | 時間の経過と共にブランドに関するエクスペリエンスを通じてお客様をガイドする一連のつながりのある手順。各手順は、お客様のアクションや時間のトリガーに基づいて実行されるので、連続したパーソナライズされたインタラクションが実現します。[詳細情報](../building-journeys/journey.md) |
| **キャンペーン** | 特定のオーディエンスに送信される単一の通信または一連の通信。時間の経過と共に展開されるジャーニーとは異なり、キャンペーンは、スケジュールまたはトリガーに従って、メッセージを即時または特定の時間に配信します。[詳細情報](../campaigns/get-started-with-campaigns.md) |
| **イベント** | ジャーニーをトリガーまたは進行させるアクションまたは発生内容。イベントには、顧客アクション（購入の実行、買い物かごの放棄）またはシステムイベント（日時、データの変更）があります。[詳細情報](../event/about-events.md) |
| **チャネル** | 顧客との通信に使用する方法：メール、SMS、プッシュ通知、アプリ内メッセージ、web またはダイレクトメール。 各チャネルには、特定の設定が必要です。[詳細情報](../configuration/get-started-configuration.md) |

## 顧客とオーディエンスの用語 {#customer-audience-terms}

| 用語 | 定義 |
|------|------------|
| **オーディエンス** | 「過去 30 日間に購入したお客様」や「ロイヤルティプログラムメンバー」など、共通の特徴や行動を共有するお客様のグループ。オーディエンスは、特定の顧客セグメントをターゲットにするために使用されます。[詳細情報](../audience/about-audiences.md) |
| **オーディエンスの選定** | お客様がオーディエンスに参加または離脱した際に発生する自動プロセス。Journey Optimizer は、ユーザーがオーディエンスにエントリまたは終了した際にアクションをトリガーし、タイムリーで関連性の高い通信を確保できます。[詳細情報](../building-journeys/audience-qualification-events.md) |
| **エンゲージ可能なオーディエンス** | ライセンス契約に基づいて、Adobe Journey Optimizer を通じてアクティブに連絡できる顧客プロファイルの数。これは通常、過去 12 か月以内に関与したプロファイルを指します。 |
| **テストプロファイル** | 実際の顧客に送信する前にメッセージのテストとプレビューに使用される架空のプロファイル。テストプロファイルは、パーソナライゼーション、コンテンツ、ジャーニーロジックの検証に役立ちます。[詳細情報](../audience/creating-test-profiles.md) |

## コンテンツとパーソナライゼーションの用語 {#content-terms}

| 用語 | 定義 |
|------|------------|
| **パーソナライゼーション** | 顧客のプロファイルデータ、環境設定、行動に基づいて、個々の顧客向けにコンテンツをカスタマイズするプロセス。例えば、顧客の名前を挿入したり、閲覧履歴に基づいて製品のレコメンデーションを表示したりします。[詳細情報](../personalization/personalize.md) |
| **コンテンツテンプレート** | ブランドの一貫性を維持し、コンテンツ作成を高速化する、複数のキャンペーンやジャーニーで使用できる再利用可能なメッセージデザイン。[詳細情報](../content-management/content-templates.md) |
| **フラグメント** | 一貫性を確保し、一元化された更新を可能にするために、複数のメッセージをまたいで使用できる再利用可能なコンテンツブロック（ヘッダー、フッター、プロモーションバナーなど）。[詳細情報](../content-management/fragments.md) |
| **ランディングページ** | 顧客が通信のオプトインまたはオプトアウト、サービスの購読、オンラインフォームを通じて情報の提供を行うことができるスタンドアロンの web ページ。[詳細情報](../landing-pages/get-started-lp.md) |

## 決定とオファーの用語 {#decision-terms}

| 用語 | 定義 |
|------|------------|
| **意思決定管理** | リアルタイムのプロファイルデータ、コンテキスト、ビジネスルールに基づいて、各顧客に最適なコンテンツやオファーを自動的に選択する機能。[詳細情報](../offers/get-started/starting-offer-decisioning.md) |
| **オファー** | 顧客に提示できるマーケティングメッセージ、ディスカウントまたはプロモーション。オファーには、オファーを受信できる顧客を決定する実施要件ルールが含まれています。[詳細情報](../offers/offer-library/creating-personalized-offers.md) |
| **決定ポリシー** | 実施要件、優先度、キャッピングルールなどの制約に基づいて、どのオファーをどの顧客に何時に表示するかを決定する一連のルールと戦略。[詳細情報](../experience-decisioning/create-decision.md) |

## データと設定の用語 {#data-config-terms}

| 用語 | 定義 |
|------|------------|
| **スキーマ** | フィールド名、データタイプ、関係など、Adobe Experience Platform でのデータの整理方法を定義する構造。 スキーマは、システムをまたいでデータの一貫性を確保します。[詳細情報](../data/get-started-schemas.md) |
| **データセット** | 特定のスキーマに従うデータのコレクション（通常はテーブル）。 データセットには、お客様データ、インタラクションイベントおよびパーソナライゼーションに使用されるその他の情報が保存されます。[詳細情報](../data/get-started-datasets.md) |

>[!NOTE]
>
>Adobe Experience Platform の用語の包括的な用語集について詳しくは、[Adobe Experience Platform 用語集](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html?lang=ja){target="_blank"}を参照してください。

## 関連トピック {#related-topics}

* [Journey Optimizer の仕組みについて](understanding-ajo.md)
* [ユーザーインターフェイスの基本を学ぶ](user-interface.md)
* [役割と学習パスの選択](quick-start.md)

