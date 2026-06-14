---
solution: Journey Optimizer
product: journey optimizer
title: API トリガーキャンペーンのオーディエンスの定義
description: API トリガーキャンペーンのオーディエンスの定義方法について説明します。
topic: Content Management
role: Developer
level: Experienced
keywords: キャンペーン, API トリガー, REST, Optimizer, メッセージ
exl-id: 6dda5687-3742-4e88-be7c-c4969b183161
TQID: https://experienceleague.adobe.com/JHnyTJxE0TwHX-izzEQ0VG60L2P2j63anyPQbbdBZ6k
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: a653cc2e-bc85-4353-a306-399e5b247978
subfeature_v2:
  - id: f7479fa1-474b-479d-8c98-f6cee5865a38
  - id: ee67bd4a-25ee-4cdd-9eab-0d7549fde0c6
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: a5c0537a45acbc708ce62bd05a569630230201ac
workflow-type: tm+mt
source-wordcount: 571
ht-degree: 93%

---

# API トリガーキャンペーンのオーディエンスの定義 {#api-audience}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、API トリガーされたキャンペーンが適切な個人にリーチし、リアルタイム配信ステータスを返すように、オーディエンス、ID タイプ、自動プロファイル作成、およびwebhookを定義します。

>[!ENDSHADEBOX]

「**[!UICONTROL オーディエンス]**」タブを使用して、キャンペーンオーディエンスを定義します。

![](assets/campaign-audience.png)

## オーディエンスの選択

**Marketing API トリガーキャンペーンの場合は**、「**[!UICONTROL オーディエンスを選択]**」ボタンをクリックして、使用できる Adobe Experience Platform オーディエンスのリストを表示します。 [詳しくは、オーディエンスを参照してください](../audience/about-audiences.md)。

>[!IMPORTANT]
>
>[オーディエンス構成](../audience/get-started-audience-orchestration.md)からのオーディエンスおよび属性は現在、Healthcare Shield または Privacy and Security Shield では使用できません。

**トランザクション API トリガーキャンペーンの場合は**、API 呼び出しでターゲットプロファイルを定義する必要があります。 1 回の API 呼び出しで最大 20 人のユニーク受信者をサポートできます。 各受信者は一意のユーザー ID を持つ必要があり、重複するユーザー ID は許可されていません。 詳しくは、[Interactive Message Execution API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/messaging#operation/postIMUnitaryMessageExecution){target="_blank"}を参照してください。

## ID タイプの選択

「**[!UICONTROL ID タイプ]**」フィールドで、選択したオーディエンスから個人を識別するために使用するキーのタイプを選択します。 既存の ID タイプを使用することも、Adobe Experience Platform ID サービスを使用して新しい ID タイプを作成することもできます。 標準 ID 名前空間について詳しくは、[このページ](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces#standard){target="_blank"}を参照してください。

1 つのキャンペーンで使用できる ID タイプは 1 つだけです。 様々な ID の中から選択した ID タイプを持たないセグメントに属する個人は、キャンペーンのターゲットにすることができません。 ID タイプと名前空間について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=ja){target="_blank"}を参照してください。

## キャンペーン実行時のプロファイル作成のアクティブ化

場合によっては、システムに存在しないプロファイルにトランザクションメッセージを送信する必要があります。 例えば、不明なユーザーが web サイトでパスワードをリセットしようとした場合などです。 データベースにプロファイルが存在しない場合、Journey Optimizer では、キャンペーンの実行時にプロファイルを自動的に作成して、このプロファイルにメッセージを送信できるようにします。

キャンペーン実行時のプロファイル作成をアクティブ化するには、「**[!UICONTROL 新規プロファイルを作成]**」オプションをオンに切り替えます。 このオプションを無効にした場合、不明なプロファイルの送信は拒否され、API 呼び出しは失敗します。

![](assets/api-triggered-create-profile.png)

>[!IMPORTANT]
>
>このオプションは、大量のトランザクションを送信するユースケースにおいて、既にプラットフォーム上に大量のプロファイルが存在する場合に、**少量のプロファイルを作成**&#x200B;する目的で提供されます。
>
>**AJO インタラクティブメッセージングプロファイルデータセット**&#x200B;の、3 つのアウトバウンドチャネル（メール、SMS、プッシュ）に対応するそれぞれのデフォルト名前空間（メール、電話、ECID）で、不明なプロファイルが作成されます。 ただし、カスタム名前空間を使用している場合、ID は同じカスタム名前空間で作成されます。
>
>[高スループットキャンペーン](../campaigns/api-triggered-high-throughput.md)では実行時にプロファイルを作成できません。このモードは アドビのプロファイルに依存しないからです。 システムではプロファイルが存在するかどうかが確認されません。

## Webhook を有効にする {#webhook}

トランザクション API トリガーキャンペーンの場合は、Webhook を有効にして、メッセージの実行ステータスに関するフィードバックをリアルタイムで受け取ることができます。 これを行うには、「**[!UICONTROL Webhook を有効にする]**」オプションに切り替えて、配信ステータスイベントを設定済みの Webhook に送信します。

![](assets/api-triggered-webhook.png)

Webhook 設定は、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL フィードバック Webhook]** メニューで一元的に管理されます。 管理者はここで Webhook エンドポイントを作成および編集できます。 [フィードバック Webhook の作成方法を学ぶ](../configuration/feedback-webhooks.md)

## 次の手順 {#next}

キャンペーンの設定とコンテンツの準備が整ったら、この実行をスケジュールできます。 [詳細情報](api-triggered-campaign-schedule.md)
