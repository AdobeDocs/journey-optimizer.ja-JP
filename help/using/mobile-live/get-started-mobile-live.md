---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizerでライブアクティビティを送信する方法を学ぶ
topic: Content Management
role: User
level: Beginner
exl-id: c9766603-df19-4efd-8319-27e9764254b4
source-git-commit: 9cdd115c66c8a26a59bfb45f0f20b6c96ddb5d5d
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 60%

---

# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}

>[!AVAILABILITY]
>
>Journey Optimizer のライブアクティビティは、iOS とのみ互換性があります。

ライブアクティビティは、モバイルアプリ内でリアルタイムの更新とインタラクティブなエクスペリエンスを提供し、ユーザーが進行中のイベントやタスクに関する情報をデバイスの画面に直接表示できるようにします。

この機能は、ユーザーがアプリを開かなくても、進行状況のトラッキング、イベントの更新、インタラクティブコンテンツなどのライブ情報を配信することで、エンゲージメントを強化します。

ライブアクティビティは **API トリガー** キャンペーンを介して **のみ** 開始でき、カスタムペイロードを提供し、独自のペイロードを介してすべてのパーソナライゼーションを実行できます。
対象のライブアクティビティのユースケースに基づいて、適切な **API トリガー**&#x200B;キャンペーンタイプを選択する必要があります。

* オーディエンスベースのキャンペーンには、「**API トリガーマーケティング**」を選択します

  スポーツのスコア、イベントの更新、共有エクスペリエンスなど、同じ更新が複数のユーザーに送信される、オーディエンスやセグメントベースのコミュニケーション向けにデザインされています。

* 個々のキャンペーンには、「**API トリガートランザクション**」を選択します

  注文ステータス、配信トラッキングなど、プロファイルで特定された、対象となる個人ユーザー。

## クイックスタートガイド

ライブアクティビティを設定してアプリケーションに実装するには、以下の手順を実行します。

1. **[Adobe Journey Optimizer を設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDK を統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDK との統合により、ロック画面と Dynamic Island でリアルタイムでの動的な変更が可能になります。

1. **[Journey Optimizerでのライブアクティビティの作成](create-mobile-live.md)**

   Journey Optimizerで API トリガーキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンを追跡](../reports/campaign-global-report-cja-activity.md)**

   組み込みレポートを使用して、ライブ アクティビティの影響の測定を開始します。
