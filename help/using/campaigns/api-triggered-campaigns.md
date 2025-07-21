---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンの操作
description: Journey Optimizer API を使用してキャンペーンのトリガーを設定する方法を説明します。
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
source-git-commit: 1bdba8c5c1a9238d351b159551f6d3924935b339
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 30%

---


# API トリガーキャンペーンの操作 {#trigger-campaigns}

## API トリガーキャンペーンについて {#about}

API トリガーキャンペーンを使用すると、マーケティングコミュニケーションが適切なタイミングでオーディエンスに到達したり、トランザクションメッセージ/操作メッセージがパスワードリセットなどの個人に到達したりできます。この場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータを使用したパーソナライゼーションが必要になる可能性があります。

これを行うには、まずJourney Optimizerで API トリガーキャンペーンを作成し、次に [ インタラクティブメッセージ実行 REST API](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution) を使用して、API 呼び出しを通じてその実行を開始する必要があります。

API トリガー型キャンペーンで使用できるチャネルは、メール、SMS およびプッシュメッセージです。

➡️ [この機能について詳しくは、ビデオを参照してください](#video)

## API トリガーキャンペーンを作成するための主な手順 {#steps}

1. [キャンペーンのプロパティの定義](api-triggered-campaign-properties.md)
1. [キャンペーンアクションの設定](api-triggered-campaign-action.md)
1. [キャンペーンコンテンツの編集](api-triggered-campaign-content.md)
1. [キャンペーンオーディエンスの定義](api-triggered-campaign-audience.md)
1. [キャンペーンのスケジュール](api-triggered-campaign-schedule.md)
1. [キャンペーンのレビューとアクティブ化](review-activate-api-triggered-campaign.md)
1. [キャンペーン実行のトリガー](trigger-campaigns.md)

## チュートリアルビデオ {#video}

インタラクティブメッセージ実行 REST API を使用して、キャンペーンを作成し、ユーザーインタラクションに基づいて外部システムからキャンペーンをトリガーする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3425358?quality=12)
