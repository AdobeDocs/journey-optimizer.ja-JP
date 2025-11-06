---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンのレビューとアクティベーション
description: Journey Optimizer でキャンペーンをレビューおよびアクティブ化する方法について学ぶ
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
keywords: キャンペーン, レビュー, 検証, アクティブ化, アクティブ化, Optimizer
exl-id: 86f35987-f0b7-406e-9ae6-0e4a2e651610
source-git-commit: d93b7ce225294257f49caee6ac08cfb575611a93
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---


# API トリガーキャンペーンの実行 {#execute}

キャンペーンがアクティブ化されたら、生成されたサンプル cURL リクエストを取得、それを API で使用してペイロードを作成し、キャンペーンをトリガーする必要があります。

## 必読 {#must-read}

* **キャンペーンの開始日や終了日** - キャンペーンを作成する際に特定の開始日や終了日を設定している場合、そのキャンペーンはこれらの日付以外では実行されず、API 呼び出しは失敗します。

* **呼び出しタイムアウト** - Interactive Message Execution REST API の呼び出しには、60 秒のタイムアウトがあります。ただし、予期しないタイムアウトが発生した場合は、配信の保証に内部再試行が行われます。

## キャンペーンのトリガー {#trigger}

1. キャンペーンを開き、「**[!UICONTROL cURL リクエスト]**」セクションからペイロードリクエストをコピー＆ペーストします。このペイロードには、メッセージで使用されるすべてのパーソナライゼーション（プロファイルとコンテキスト）変数が含まれます。キャンペーンがライブになったら使用できます。

   ![](assets/api-triggered-curl.png)

   >[!IMPORTANT]
   >
   >cURL セクションのエンドポイントは、標準のキャンペーンと[高スループットキャンペーン](../campaigns/api-triggered-high-throughput.md)で異なります。

1. この API への cURL リクエストを使用して、ペイロードを作成し、キャンペーンをトリガーします。詳しくは、[Interactive Message Execution API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution)を参照してください。このドキュメントには、標準および高スループットキャンペーンのすべてのエンドポイントが一覧表示されます。

   API 呼び出しの例について詳しくは、[このページ](https://developer.adobe.com/journey-optimizer-apis/references/messaging-samples/)も参照してください。
