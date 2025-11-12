---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizerでライブアクティビティを送信する方法を学ぶ
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ce6bfca78d097588b5958c10c721b29b7013b3e2
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 2%

---


# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}

>[!BEGINSHADEBOX]

* **[ライブアクティビティの概要](get-started-mobile-live.md)**
* [ライブアクティビティ設定](mobile-live-configuration.md)
* [Adobe Experience Platform Mobile SDKとライブアクティビティの統合](mobile-live-configuration-sdk.md)
* [ライブアクティビティの作成](create-mobile-live.md)
* [よくある質問](mobile-live-faq.md)
* [ライブアクティビティキャンペーンレポート](../reports/campaign-global-report-cja-activity.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>Journey Optimizerのライブアクティビティは、iOSとのみ互換性があります。

ライブアクティビティは、モバイルアプリ内でリアルタイムの更新とインタラクティブなエクスペリエンスを提供し、ユーザーが進行中のイベントやタスクに関する情報をデバイスの画面に直接表示できるようにします。

この機能は、ユーザーがアプリを開くことなく、進行状況の追跡、イベントの更新、インタラクティブコンテンツなどのライブ情報を配信することで、エンゲージメントを強化します。

ライブアクティビティは **API トリガー** キャンペーンを介して **のみ** 開始でき、カスタムペイロードを提供し、独自のペイロードを介してすべてのパーソナライゼーションを実行できます。
目的のライブアクティビティのユースケースに基づいて、適切な **API トリガー** キャンペーンタイプを選択する必要があります。

* オーディエンスベースのキャンペーン用に「**API トリガーマーケティング**」を選択します

  スポーツスコア、イベントの更新、共有エクスペリエンスなど、同じ更新が複数のユーザーに送信されるオーディエンスまたはセグメントベースのコミュニケーション向けに設計されています。

* 個々のキャンペーン用に「**API トリガートランザクション**」を選択します

  プロファイル（注文ステータス、配信トラッキングなど）で識別される意図された個人ユーザー。

## クイックスタートガイド

アプリケーションにライブアクティビティを設定して実装するには、以下の手順を実行します。

1. **[Adobe Journey Optimizerの設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDKの統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDKとの統合により、ロック画面と Dynamic Island でリアルタイムの動的な更新が可能になります。

1. **[Journey Optimizerでのライブアクティビティの作成](create-mobile-live.md)**

   Journey Optimizerで API トリガーキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンのトラッキング](../reports/campaign-global-report-cja-activity.md)**

   組み込みレポートを使用して、ライブ アクティビティの影響の測定を開始します。




