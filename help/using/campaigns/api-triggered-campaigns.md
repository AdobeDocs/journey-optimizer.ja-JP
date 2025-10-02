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
source-git-commit: d4765f9084efac1fd241404dff365a66027ce5af
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 100%

---


# API トリガーキャンペーンの操作 {#trigger-campaigns}

>[!CONTEXTUALHELP]
>id="campaigns_overview_api_triggered"
>title="API トリガーキャンペーン"
>abstract="**Transactional API トリガーキャンペーン**<br/> API 呼び出しを使用したリアルタイムメッセージのトリガー&#x200B;<br/><br/>**マーケティングメッセージ**<br/>&#x200B;プロモーションコンテンツ（オプトインが必要、ビジネスルールの対象となる）<br/><br/>**トランザクションメッセージ**<br/>&#x200B;サービス関連コンテンツ（確認、アラート、マーケティングの同意の対象とならない）<br/><br/>**使用できるチャネル**<br/>&#x200B;メール、SMS、プッシュ通知"

## API トリガーキャンペーンについて {#about}

API トリガーキャンペーンを使用すると、適切なタイミングでオーディエンスにリーチするマーケティング通信や、パスワードのリセットなどの個人に対するトランザクション／運用メッセージが可能になります。これらの場合、プロファイル属性だけでなく、REST API ペイロードであるトリガー内のリアルタイムコンテキストデータも使用したパーソナライゼーションが必要になる可能性があります。

それには、まず Journey Optimizer で API トリガーキャンペーンを作成し、次に [Interactive Message Execution REST API](https://developer.adobe.com/journey-optimizer-apis/references/messaging/#tag/execution) を使用して、API 呼び出しを通じてその実行を開始する必要があります。

API トリガー型キャンペーンで使用できるチャネルは、メール、SMS およびプッシュメッセージです。

➡️ [この機能について詳しくは、ビデオを参照してください](#video)。


>[!NOTE]
>
>サポートされているチャネル：[メール](../email/get-started-email.md)、[SMS／MMS／RCS](../sms/get-started-sms.md)、[プッシュ通知](../push/get-started-push.md)。
>
>使用できるチャネルは、ライセンスモデルとアドオンによって異なります。

## API トリガーキャンペーン作成の主な手順 {#steps}

1. [キャンペーンのプロパティの定義](api-triggered-campaign-properties.md)
1. [キャンペーンアクションの設定](api-triggered-campaign-action.md)
1. [キャンペーンコンテンツの編集](api-triggered-campaign-content.md)
1. [キャンペーンオーディエンスの定義](api-triggered-campaign-audience.md)
1. [キャンペーンのスケジュール](api-triggered-campaign-schedule.md)
1. [キャンペーンのレビューとアクティブ化](review-activate-api-triggered-campaign.md)
1. [キャンペーン実行のトリガー](trigger-campaigns.md)

>[!IMPORTANT]
>
>キャンペーンを作成する前に、一般的な[キャンペーンの前提条件](../campaigns/get-started-with-campaigns.md#prerequisites)を確認します。

## チュートリアルビデオ {#video}

Interactive Message Execution REST API を使用して、キャンペーンを作成し、ユーザーインタラクションに基づいて外部システムからキャンペーンをトリガーする方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3425358?quality=12)
