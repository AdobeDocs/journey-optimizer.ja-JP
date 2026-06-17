---
source-git-commit: 4aebdb06094628cfe7393c7f7b41e5fe0ee9df13
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 43%

---
Wiki ツールの権限が付与されていません。 チケット自体の詳細情報を使用して進めます。この情報には、主要な仕様が含まれています（デフォルトは500 TPS、パフォーマンスアドオン経由の1000/1500 TPS階層、プッシュ専用、バースト/期間限定の増加をサポート）。

&#x200B;---

ソリューション：Journey Optimizer
製品：journey optimizer
タイトル：API トリガーキャンペーンの操作
説明：Journey Optimizer APIを使用してキャンペーンをトリガーする方法を説明します。
機能：キャンペーン，API
トピック：コンテンツ管理
役割：開発者
レベル：経験豊富
キーワード：キャンペーン，API トリガー，REST, Optimizer, メッセージ
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
TQID: https://experienceleague.adobe.com/DNNZWQjgdcranVpuJV9WCKW8RRENVJ6iZnIt1k-Easc
product_v2:
- id: cb954087-f4fc-4456-afb9-e939cabcdc79
internal-label: Journey Optimizer
feature_v2:
- id: a653cc2e-bc85-4353-a306-399e5b247978
internal-label: Journey Optimizer campaigns
subfeature_v2:
- id: f7479fa1-474b-479d-8c98-f6cee5865a38
internal-label: API トリガーキャンペーン
- id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
internal-label: Campaign management
role_v2:
- id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
internal-label: Developer
topic_v2:
- id: e0eb8757-182f-49f3-94a4-1587d16f5094
internal-label: Personalization

更新されたMarkdown ファイルの詳細は次のとおりです。

&#x200B;---

```
solution: Journey Optimizer
product: journey optimizer
title: Work with API triggered campaigns
description: Learn how to trigger campaigns using Journey Optimizer APIs.
feature: Campaigns, API
topic: Content Management
role: Developer
level: Experienced
keywords: campaigns, API-triggered, REST, optimizer, messages
exl-id: 0ef03d33-da11-43fa-8e10-8e4b80c90acb
TQID: https://experienceleague.adobe.com/DNNZWQjgdcranVpuJV9WCKW8RRENVJ6iZnIt1k-Easc
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a653cc2e-bc85-4353-a306-399e5b247978
    internal-label: Journey Optimizer campaigns
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
    internal-label: API triggered campaigns
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
    internal-label: Campaign management
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
```

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

## プッシュ通知のスループット {#push-throughput}

デフォルトでは、API トリガーキャンペーンは、プッシュ通知配信で最大&#x200B;**500 トランザクション/秒（TPS）**&#x200B;をサポートします。 大量の運用上のメッセージ要件を持つ組織は、**パフォーマンスアドオン**&#x200B;を通じてこの制限を増やすことができます。

パフォーマンスアドオンには、プッシュ通知のスループットが高い2つの階層があります。

| 階層 | スループット |
|------|-----------|
| スタンダード | 500 TPS （すべてのお客様に含まれます） |
| パフォーマンスアドオン – レベル 1 | 1,000 TPS |
| パフォーマンスアドオン – レベル 2 | 1,500 TPS |

スループットの向上は、製品の発売や大規模なキャンペーンなど、一時的に大量のシナリオをサポートするために、**期間限定**&#x200B;および契約上の永続的な増加の両方として利用できます。

>[!NOTE]
>
>スループット階層の増加は、API トリガーキャンペーンの&#x200B;**プッシュ通知チャネルのみ**&#x200B;に適用されます。 電子メールとSMS チャネルはこのアドオンの対象外です。
>
>Adobeのアカウントチームに連絡して、自社のスループット層を高めましょう。

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

>[!VIDEO](https://video.tv.adobe.com/v/3452726?captions=jpn&quality=12)

&#x200B;---

キーの追加は、「バージョン情報」と「キーステップ」の間に配置された新しい&#x200B;**プッシュ通知スループット** セクション （`## Push notification throughput {#push-throughput}`）です。これは次のドキュメントです。
- すべての顧客に対するデフォルトの500 TPSが含まれています
- 2つのPerformance Add-on階層（1,000および1,500 TPS）
- 永続的な増加と期間限定の増加の両方のサポート
- 範囲はプッシュチャネルのみに制限されています
- Adobeのアカウントチームにお客様を誘導するメモ