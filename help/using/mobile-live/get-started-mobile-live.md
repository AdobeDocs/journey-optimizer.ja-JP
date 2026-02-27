---
solution: Journey Optimizer
product: journey optimizer
title: ライブアクティビティの基本を学ぶ
description: Journey Optimizer でライブアクティビティを送信する方法について説明します
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c9766603-df19-4efd-8319-27e9764254b4
source-git-commit: 6b4e3a6c32d24861f1ea8df54fc2e4fbb19d0ce7
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 100%

---

# ライブアクティビティの基本を学ぶ {#get-started-mobile-live}

>[!AVAILABILITY]
>
>Journey Optimizer のライブアクティビティは、iOS とのみ互換性があります。

ライブアクティビティは、モバイルアプリ内でリアルタイムの更新とインタラクティブなエクスペリエンスを提供するので、ユーザーは進行中のイベントやタスクに関する情報をデバイスの画面上で直接表示できます。

この機能は、ユーザーがアプリを開かなくても、進行状況のトラッキング、イベントの更新、インタラクティブコンテンツなどのライブ情報を配信することで、エンゲージメントを強化します。

ライブアクティビティは、**API トリガー**&#x200B;キャンペーン経由で&#x200B;**のみ**開始できるので、カスタムペイロードを提供し、独自のペイロードを通じてすべてのパーソナライゼーションを実行できます。
対象のライブアクティビティのユースケースに基づいて、適切な **API トリガー**&#x200B;キャンペーンタイプを選択する必要があります。

* オーディエンスベースのキャンペーンには、「**API トリガーマーケティング**」を選択します

  スポーツのスコア、イベントの更新、共有エクスペリエンスなど、同じ更新が複数のユーザーに送信される、オーディエンスやセグメントベースのコミュニケーション向けにデザインされています。

* 個々のキャンペーンには、「**API トリガートランザクション**」を選択します

  注文ステータス、配信トラッキングなど、プロファイルで特定された、対象となる個人ユーザー。

## クイックスタートガイド

アプリケーションでライブアクティビティを設定して実装するには、次の操作を実行します。

1. **[Adobe Journey Optimizer を設定](mobile-live-configuration.md)**

   モバイル設定を作成して環境を設定します。

1. **[Adobe Experience Platform Mobile SDK を統合](mobile-live-configuration-sdk.md)**

   Adobe Experience Platform Mobile SDK との統合により、ロック画面と Dynamic Island でリアルタイムでの動的な変更が可能になります。

1. **[Journey Optimizer でライブアクティビティを作成](create-mobile-live.md)**

   Journey Optimizer で API トリガーキャンペーンを使用して、ライブアクティビティを開始します。

1. **[キャンペーンを追跡](../reports/campaign-global-report-cja-activity.md)**

   ビルトインのレポートを使用して、ライブアクティビティの影響の測定を開始します。
