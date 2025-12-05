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
source-git-commit: 8cb37cf0fb9dc8048d7da8ddda0c67280477d57f
workflow-type: ht
source-wordcount: '468'
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

## トラブルシューティング {#troubleshooting}

### Azure Cosmos DB 認証エラー（500 内部サーバーエラー） {#cosmosdb-auth-errors}

API トリガーキャンペーンをトリガーする際に **500 内部サーバーエラー**&#x200B;が発生し、システムログに次のようなメッセージを含む Azure Cosmos DB からの **403 禁止**&#x200B;エラーが表示される場合：

_「Azure Cosmos DB サービスがアカウントの既定の ID の AAD 認証トークンを取得できないため、アカウントへのアクセスは現在取り消されています」_

このエラーは通常、Cosmos DB 認証に必要な Azure サービスプリンシパルが無効、削除または誤って設定されている場合に発生します。

+++この問題を解決する方法

1. **Azure サービスプリンシパルを確認** - Azure サービスプリンシパルまたはマネージド ID が有効になっており、Azure Active Directory で無効化または削除されていないことを確認します。

1. **権限を確認** - サービスプリンシパルが Azure Key Vault および Cosmos DB リソースへのアクセスに必要な権限を持っていることを確認します。Azure Cosmos DB で認証するには、サービスプリンシパルに適切な役割が割り当てられている必要があります。

1. **Azure Cosmos DB CMK 設定を確認** - カスタマーマネージドキー（CMK）を使用している場合、AAD トークンの取得を復元する手順について詳しくは、[Azure Cosmos DB CMK トラブルシューティングガイド](https://learn.microsoft.com/ja-jp/azure/cosmos-db/cmk-troubleshooting-guide#azure-active-directory-token-acquisition-error){target="_blank"}を参照してください。

1. **再度有効にしてテスト** - 設定を修正した後、サービスプリンシパルが無効になっていた場合は再度有効にし、トランザクションキャンペーン API 呼び出しを再テストして、認証が成功し、メッセージが配信されることを確認します。

>[!NOTE]
>
>この問題は通常、Cosmos DB 認証に必要な Azure サービスプリンシパルの設定ミスや誤った無効化により発生します。サービスプリンシパルを有効にして適切に設定しておくと、今後このエラーが発生するのを防ぐことができます。

+++
