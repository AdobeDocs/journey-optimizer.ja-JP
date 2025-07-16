---
title: データ収集
description: 意思決定管理のフィードバックデータ収集の詳細情報
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Data Engineer, Developer
level: Experienced
exl-id: 278cb255-439c-4ce8-ab59-07df79774b98
source-git-commit: 87f3da0a1d73f9aa26c7420d260778286bacdf0c
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

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

[!DNL Journey Optimizer] で作成した&#x200B;**メール**&#x200B;では、**自動**&#x200B;でインプレッション数およびクリック数をトラッキングします。

ただし、**ほとんどのチャネル**&#x200B;では、インプレッション数およびクリック数のデータを&#x200B;**エクスペリエンスイベント**&#x200B;として Adobe Experience Platform に送信する必要があります。これには以下が含まれます。

* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} を使用してオファーをレンダリングする web ページ

* [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=ja){target="_blank"} を使用してオファーをレンダリングするモバイルアプリ - [詳細情報](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
* キオスク
* サードパーティのアプリケーションを通じて送信されるメッセージ
  <!--Mobile push notifications authored by [!DNL Journey Optimizer] - [Learn more](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer/api-reference/#handlenotificationresponse){target="_blank"}-->

>[!NOTE]
>
>Decisioning API リクエストを使用してオファーを受け取るチャネルでは、エクスペリエンスイベントとしてフィードバックを送信する必要があります。つまり、レンダリング方法の説明が必要なオファーは、フィードバックをエクスペリエンスイベントとして送信する必要があると想定できます。

### カスタムイベント

オファーに関連付けられたカスタムイベントに関するフィードバックは、独自の環境設定に従って Adobe Experience Platform に送信できます。例えば、1 つのオファーに複数のボタン（*興味あり*、*興味なし*&#x200B;など）がある場合、イベントを個別に送信することも、エクスペリエンスイベントとして送信することもできます。

## フィードバックデータの送信

フィードバックデータを送信するには、イベントを収集するデータセットを作成し、各イベントタイプに対して、Adobe Experience Platform に送信するエクスペリエンスイベントを定義する必要があります。

* エクスペリエンスイベントが収集されるデータセットを作成する方法について詳しくは、[この節](create-dataset.md)を参照してください。

* フィードバックデータで送信するエクスペリエンスイベントを定義する方法について詳しくは、[この節](schema-requirement.md)を参照してください。
