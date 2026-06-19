---
solution: Journey Optimizer
product: journey optimizer
title: オンボーディングプロジェクトガイド | Adobe Journey Optimizer
description: Adobe Adobe Journey Optimizerのオンボーディングプロジェクトを、管理者、データ、開発者、マーケターの役割を問わず計画、管理します。
feature: Get Started
topic: Content Management
role: Admin
level: Intermediate
keywords: journey optimizer, オンボーディング，オンボーディングプロジェクト，ロールアウト，実装計画，管理者，csm，実装パートナー，段階的チェックリスト
source-git-commit: 6a653e1dbb00f68ff689ea3e0dc0b15abda1e21e
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 4%

---

# オンボーディングプロジェクトガイド {#onboarding-hub}

>[!BEGINSHADEBOX]

**このページでは、**&#x200B;管理者、データエンジニア、開発者、マーケターの役割を含む段階的なチェックリストを使用して、Adobe Journey Optimizerの完全なロールアウトを計画および調整します。

>[!ENDSHADEBOX]

このページは、Journey Optimizerの完全なロールアウトを調整する&#x200B;**システム管理者および実装パートナー**&#x200B;向けです。 すべての役割をカバーする段階的なチェックリストと、詳細な役割固有のガイドへのリンクを提供します。

>[!NOTE]
>
>特定の役割を持つ個人の場合は、代わりに[Journey Optimizerの使用を開始する](../../rp_landing_pages/get-started-landing-page.md)に移動してください。

## フェーズ 1 – 環境設定（管理者） {#phase-1}

他のメンバーが作業を開始できるように、まずこれらの基本タスクを完了してください。

* [ ] サンドボックスのプロビジョニング （開発、ステージング、実稼動）
* [ ] Adobe Admin Consoleでのユーザーの役割と権限の設定
* [ ]製品プロファイルとオブジェクト レベルのアクセス制御を設定する
* [ ] サブドメインのデリゲートとIP プールの設定
* [ ] チャネル設定の設定（電子メール、SMS、プッシュ通知、web、アプリ内、ダイレクトメール）
* [ ]抑制リストと同意ポリシーの設定

➡️詳細を見る：[管理者の基本を学ぶ](path/administrator.md)

## フェーズ 2 - データ基盤（データエンジニア） {#phase-2}

プロファイル、オーディエンス、ジャーニートリガーを強化するデータレイヤーを構築します。

* [ ] ID名前空間の定義
* [ ] XDM スキーマの作成（プロファイル、エクスペリエンスイベント、リレーショナル）
* [ ] リアルタイム顧客プロファイルのデータセットの設定と有効化
* [ ] データ取り込みの設定（バッチおよびストリーミング）
* [ ]計算属性の作成
* [ ] ジャーニーイベントとデータソースの設定

➡️詳細を見る：[&#x200B; データエンジニア向けの入門](path/data-engineer.md)

## フェーズ 3 – 技術的な統合（開発者） {#phase-3}

アプリケーションを接続し、リアルタイムのデータにもとづいてジャーニーを実行：

* [ ] プッシュ設定を使用したモバイル SDK （iOS/Android）の統合
* [ ] Web エクスペリエンスとweb プッシュ用のWeb SDKの実装
* [ ] アプリケーションからのイベント送信の実装
* [ ]外部システム統合用のカスタムアクションエンドポイントの構築
* [ ] Adobe Experience Platform Assuranceを使用して検証

➡️詳細を見る：[開発者向け基本を学ぶ](path/developer.md)

## フェーズ 4 – 最初の体験（マーケター） {#phase-4}

最初のジャーニーとキャンペーンを開始して、基盤を機能させましょう。

* [ ]最初のオーディエンスを作成（セグメント定義またはCSV アップロード）
* [ ]電子メールアクションを使用したテストジャーニーの作成
* [ ] コンテンツテンプレートとフラグメントの設定
* [ ] キャンペーンの公開と監視
* [ ]件のレビューのライブレポート

➡️詳細を見る：[&#x200B; マーケター向けの基本を学ぶ](path/marketer.md)

## オンボーディングチェックリスト（印刷可能） {#checklist}

| フェーズ | 所有者 | ステータス |
|-------|-------|--------|
| 環境の設定 | 管理者 | |
| データ基盤 | データエンジニア | |
| 技術的な統合 | 開発者 | |
| 最初の体験 | マーケター | |

## 関連リソース {#related-resources}

* [役割と責任](quick-start.md) — 4つの役割の連携の仕組みと推奨される実装順序。
* [Journey Optimizer チュートリアル &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-learn/tutorials/overview){target="_blank"} – 各役割のステップバイステップのビデオとガイド付きウォークスルー。
* [&#x200B; データ管理の基本](../data/gs-data.md) — データの取り込み、統合、アクティベート方法。
