---
solution: Journey Optimizer
product: journey optimizer
title: Campaign ライブアクティビティレポート
description: キャンペーンレポートからライブアクティビティデータを使用する方法について説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
hide: true
exl-id: 58034ec4-62dc-406c-99c4-d6b7aa107140
TQID: https://experienceleague.adobe.com/NBJkyh9TCAPxD0u3EpwaZth7-ePjEWdg2roQ7J2-RuY
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 663
ht-degree: 22%

---

# ライブアクティビティキャンペーンレポート {#campaign-global-report-cja-activity}

>[!BEGINSHADEBOX]

ライブアクティビティキャンペーンレポートにアクセスするには、キャンペーンの「**[!UICONTROL レポート]**」ボタンをクリックし、「**[!UICONTROL 全期間のレポートを表示]**」を選択します。 [詳細情報](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## 送信統計 {#sending-statistics-mobile}

![](assets/sending-statistics-mobile-live.png)

**[!UICONTROL 送信統計]** テーブルには、ライブアクティビティキャンペーンに関連する主要指標の詳細な概要が表示されます。 ターゲットオーディエンスのサイズや、正常に配信されたライブアクティビティの数などの重要な情報が表示され、ライブアクティビティの全体的なリーチとパフォーマンスを評価するのに役立ちます。

+++ 詳しくは、送信統計指標を参照してください

* **[!UICONTROL ターゲット]**：除外、抑制、または同意の削除が適用されるまでにオーディエンスに適格だったプロファイルの数。

* **[!UICONTROL 送信]**：ターゲットプロファイルに送信しようとしたライブアクティビティイベントの合計数。

* **[!UICONTROL 配信済み]**：デバイスに正常に配信されたライブアクティビティイベントの数（試行された送信の合計数に対する）。

* **[!UICONTROL 送信エラー]**: エラー（無効なトークンや接続の問題など）が原因で送信できなかったライブアクティビティイベントの合計数。

* **[!UICONTROL 送信除外数]**：Adobe Journey Optimizer により送信から除外されたプロファイルの数（例：オプトアウトステータスや実施要件ルールにより）。

+++

## ライブアクティビティライフサイクル {#lifecycle}

**[!UICONTROL ライブアクティビティのライフサイクル]** テーブルには、ライブアクティビティの時間の経過に関する包括的なビューが表示されます。 アクティビティがいつ開始、更新、終了したかなどの重要なイベントを可視化し、ユーザーエンゲージメントとライブアクティビティキャンペーン全体のライフサイクルをより深く理解できます。

レポートは、トランザクションキャンペーンとマーケティングキャンペーンのどちらを使用しているかによって異なります。

### トランザクションライブアクティビティ

![](assets/activity-lifecycle.png)

トランザクションキャンペーンの場合、ライブアクティビティキャンペーンレポートには、リモート開始、ローカル開始、更新、終了など、すべてのライフサイクルイベントが表示されます。

+++ トランザクションキャンペーンを使用したライブアクティビティライフサイクル指標の詳細

* **[!UICONTROL リモート開始]**: リモートで開始されたライブアクティビティ開始イベントの合計数。通常、サーバーまたはバックエンドシステムによってトリガーされます。

* **[!UICONTROL ローカル開始]**: ユーザーのデバイスでローカルに開始されたライブアクティビティ開始イベントの合計数。多くの場合、ユーザーの操作またはクライアントサイドのトリガーに起因します。

* **[!UICONTROL アップデート数]**：デバイスに送信されたライブアクティビティのアップデートの合計数。 アップデートには、ステータスの変更、新しいコンテンツ、進行状況の通知を含めることができます。

* **[!UICONTROL 終了]**: デバイスに送信されたライブアクティビティ終了イベントの合計数。

* **[!UICONTROL 合計カウント]**：ライブアクティビティのボリュームの完全な測定値を提供する、開始、更新、終了を含むすべてのライブアクティビティライフサイクルイベントの全体的な合計。

+++

### マーケティングライブアクティビティ

![](assets/activity-lifecycle-broadcast.png)

マーケティングキャンペーンでは、ブロードキャストのユースケースにライブアクティビティを使用し、複数のデバイスに同時にアップデートを送信します。

Marketing CampaignsのiOS Live アクティビティの場合、レポートには、開始時に&#x200B;**[!UICONTROL Remote Starts]**&#x200B;件のイベントと&#x200B;**[!UICONTROL Remote starts errors]**&#x200B;件のみが表示されます。 APNがフィードバックを提供せずにすべてのデバイスにアップデートを配信するため、**[!UICONTROL 更新]**&#x200B;および&#x200B;**[!UICONTROL 終了]**&#x200B;のイベントは追跡されません。 **[!UICONTROL 更新]**&#x200B;および&#x200B;**[!UICONTROL 終了]** イベントを表示するには、[Apple プッシュ通知コンソール &#x200B;](https://developer.apple.com/notifications/push-notifications-console/)を使用します。

+++ マーケティングキャンペーンのライブアクティビティライフサイクル指標の詳細

* **[!UICONTROL リモート開始]**: リモートで開始されたライブアクティビティ開始イベントの合計数。通常、サーバーまたはバックエンドシステムによってトリガーされます。

* **[!UICONTROL リモートで開始エラー]**: ライブ アクティビティをリモートで開始しようとしたときに発生したエラーの合計数（無効なトークンや接続性の問題など）。

+++

#### APIを介した更新と終了数の取得 {#retrieving-updates-end-api}

Appleのプッシュ通知コンソールを使用する代わりに、ヘッドレス API呼び出しを使用してアップデートと終了回数を取得できます。

ブロードキャストのユースケースに対して更新または終了API呼び出しを実行する場合、応答には`controlBreakdown` セクションが含まれ、ライブアクティビティ実行に対して実行された更新呼び出しと終了呼び出しの数を示すカウンターが提供されます。 このブロックは、ライフサイクルデータのないレガシー実行には存在しません。 また、必要に応じて、GET エンドポイントを使用して実行ステータスを明示的に取得することもできます。

**更新/応答終了（200 OK）**

```json
{
  "executionId": "HA-exec-abc",
  "campaignId": "campaign-abc-123",
  "campaignVersionId": "v1",
  "audienceId": "audience-segment-id",
  "status": "processing",
  "targetedProfileCount": 150000,
  "createdAt": "2026-02-27T10:00:00Z",
  "executionLifecycle": {
    "lastControlAt": "2026-02-27T10:45:00Z",
    "controlBreakdown": {
      "update": 5,
      "end": 1
    }
  }
}
```

**実行ステータス （GET）**

```
GET /im/executions/audience/{executionId}
```

## エラーの理由 {#error-reasons}

![](assets/error-reasons-activity.png)

「**[!UICONTROL エラーの理由]**」テーブルを使用すると、ライブアクティビティの送信プロセス中に発生した特定のエラーを特定でき、発生した問題を詳細に分析できます。

## 除外された理由 {#excluded-reasons}

![](assets/excluded-activity.png)

**[!UICONTROL 除外された理由]**&#x200B;テーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、ライブアクティビティを受信できない原因となった様々な要因が視覚的に表示されます。
