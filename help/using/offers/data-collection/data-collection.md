---
title: データ収集
description: 意思決定管理のフィードバックデータ収集の詳細情報
feature: Offers
topic: Integrations
role: User
level: Intermediate
source-git-commit: c9e970bc231fc3d19f0243b71256ea0f5a981af7
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 74%

---

# 意思決定管理データ収集 {#data-collection}

## データ収集について

Adobe Experience Platform では、表示されるオファーやユーザーの操作方法など、オファー決定支援のフィードバックを収集できます。 このデータは、次の目的で使用できます。
* [意思決定管理レポート](../reports/get-started-events.md)の作成
* [フリークエンシーキャップ](../offer-library/add-constraints.md#capping)ルールの使用
* ランキングメソッドとして使用できる [AI モデル](../ranking/create-ranking-strategies.md)の構築。

## イベントのタイプ

データの収集方法は、取り込むイベントタイプに応じて異なります。

### 決定イベント

意思決定管理で特定のプロファイルに対する決定が行われるたびに、その意思決定イベントに関連する情報がすべてのチャネルの Adobe Experience Platform へと&#x200B;**自動的に**&#x200B;送信されます。[詳細情報](../reports/get-started-events.md)

### インプレッションとクリックイベント

意思決定管理のインプレッションおよびクリック数は、次のように定義されます。

* **インプレッション**&#x200B;イベントとは、オファーがユーザーに表示される時のイベントです。

* **クリック**&#x200B;イベントとは、ユーザーがオファーをクリックまたは操作した時のイベントです。

インプレッション数およびクリック数に関するフィードバックは、使用される [!DNL Journey Optimizer] チャネルによってキャプチャされます。

**電子メール** 作成者： [!DNL Journey Optimizer] **自動** インプレッション数およびクリック数を追跡します。

しかし、 **ほとんどのチャネル** Adobe Experience Platformにインプレッション数とクリック数のデータをとして送信する必要がある **エクスペリエンスイベント**. これには以下が含まれます。

* Web ページ の使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} オファーをレンダリング

* モバイルアプリ [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html){target="_blank"} to render offers - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
* キオスク
* サードパーティのアプリケーションを通じて送信されるメッセージ
   <!--Mobile push notifications authored by [!DNL Journey Optimizer] - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer/api-reference/#handlenotificationresponse){target="_blank"}-->

>[!NOTE]
>
>判定 API リクエストを使用してオファーを受け取るチャネルは、エクスペリエンスイベントとしてフィードバックを送信する必要があります。 つまり、オファーのレンダリング方法に関する指示が必要な場合は、フィードバックをエクスペリエンスイベントとして送信する必要があると想定できます。

### カスタムイベント

オファーに関連付けられたカスタムイベントに関するフィードバックは、独自の環境設定に従って Adobe Experience Platform に送信できます。例えば、1 つのオファーに複数のボタン（*興味あり*、*興味なし*&#x200B;など）がある場合、イベントを個別に送信することもありますが、エクスペリエンスイベントとして送信することもできます。<!--Not sure to get that part. How feedback is collected in the first case, i.e. when events are sent in separately? Does it mean the customer just handles it the wau he wants?-->

## フィードバックデータの送信

フィードバックデータを送信するには、イベントを収集するデータセットを作成し、各イベントタイプに対して、Adobe Experience Platform に送信するエクスペリエンスイベントを定義する必要があります。

* エクスペリエンスイベントが収集されるデータセットを作成する方法について詳しくは、[この節](create-dataset.md)を参照してください。

* フィードバックデータで送信するエクスペリエンスイベントを定義する方法について詳しくは、[この節](schema-requirement.md)を参照してください。

