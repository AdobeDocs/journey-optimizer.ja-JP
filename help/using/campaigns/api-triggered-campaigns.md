---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンの操作
description: Journey Optimizer API を使用してキャンペーンをトリガーする方法について説明します。
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
TQID: https://experienceleague.adobe.com/DNNZWQjgdcranVpuJV9WCKW8RRENVJ6iZnIt1k-Easc
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a653cc2e-bc85-4353-a306-399e5b247978
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a5c0537a45acbc708ce62bd05a569630230201ac
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 88%

---

# API トリガーキャンペーンの操作 {#trigger-campaigns}

>[!BEGINSHADEBOX]

**このページ：** REST API呼び出しを通じてAPI トリガーキャンペーンを作成および起動し、プロファイルおよびコンテキストデータを使用してリアルタイムのマーケティングおよびトランザクションメッセージを送信できるようにします。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="campaigns_overview_api_triggered"
>title="API トリガーキャンペーン"
>abstract="**Transactional API トリガーキャンペーン**<br/> API 呼び出しを使用したリアルタイムメッセージのトリガー&#x200B;<br/><br/>**マーケティングメッセージ**<br/>&#x200B;プロモーションコンテンツ（オプトインが必要、ビジネスルールの対象となる）<br/><br/>**トランザクションメッセージ**<br/>&#x200B;サービス関連コンテンツ（確認、アラート、マーケティングの同意の対象とならない）<br/><br/>**使用できるチャネル**<br/>&#x200B;メール、SMS、プッシュ通知"

## API トリガーキャンペーンについて {#about}

API トリガーキャンペーンを使用すると、適切なタイミングでオーディエンスにリーチするマーケティング通信や、パスワードのリセットなどの個人に対するトランザクション／運用メッセージを送信できるようになります。これらの場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用したパーソナライゼーションが必要になる可能性があります。

それには、まず Journey Optimizer で API トリガーキャンペーンを作成し、次に [Interactive Message Execution REST API](https://developer.adobe.com/journey-optimizer-apis/references/messaging#tag/execution) を使用して、API 呼び出しを通じてその実行を開始する必要があります。

➡️ [この機能をビデオで確認](#video)

>[!NOTE]
>
>サポートされるチャネルについて詳しくは、[ジャーニーとキャンペーンのチャネル](../channels/gs-channels.md#channels)の節にある表を参照してください。
>
>使用できるチャネルは、ライセンスモデルとアドオンによって異なります。

## API トリガーキャンペーン作成の主な手順 {#steps}

キャンペーンを開始する前に、[この節](get-started-with-campaigns.md#prerequisites)に記載されている次の前提条件を確認してください。 これらの前提条件が満たされたら、キャンペーンの作成を開始できます。

1. [キャンペーンのプロパティの定義](api-triggered-campaign-properties.md)
1. [キャンペーンアクションの設定](api-triggered-campaign-action.md)
1. [キャンペーンコンテンツの編集](api-triggered-campaign-content.md)
1. [キャンペーンオーディエンスの定義](api-triggered-campaign-audience.md)
1. [キャンペーンのスケジュール](api-triggered-campaign-schedule.md)
1. [キャンペーンのレビューとアクティブ化](review-activate-api-triggered-campaign.md)
1. [キャンペーン実行のトリガー](trigger-campaigns.md)

[完全なキャンペーン作成ワークフローについて詳しくは、タイプ固有のガイドを参照してください →](get-started-with-campaigns.md#workflow)

## チュートリアルビデオ {#video}

Interactive Message Execution REST API を使用して、キャンペーンを作成し、ユーザーインタラクションに基づいて外部システムからキャンペーンをトリガーする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3425358?quality=12)
