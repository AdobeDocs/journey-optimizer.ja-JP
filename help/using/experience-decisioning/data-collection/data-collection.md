---
title: データ収集
description: 意思決定管理のフィードバックデータ収集の詳細情報
feature: Decision Management, Datasets
topic: Integrations
role: User, Data Engineer, Developer
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: e5c457494d5d79d1a7951b9172c39c91007e2651
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 83%

---

# 意思決定管理データ収集 {#data-collection}

## データ収集について

Adobe Experience Platform では、表示されるオファーやユーザーの操作方法など、オファー決定支援のフィードバックを収集できます。 このデータは、次の目的で使用できます。

* [ 決定レポート ](../cja-reporting.md) の作成
* キャッピング [ ルール ](../items.md#capping) 使用
* ランキングメソッドとして使用できる AI モデルの構築 <!--add link-->

## イベントのタイプ

データの収集方法は、取り込むイベントタイプに応じて異なります。

### 決定イベント

Decisioning で特定のプロファイルが決定されるたびに、その意思決定イベントに関連する情報が **自動** Adobe Experience Platformに送信されます。<!--TBC + link-->

### インプレッションとクリックイベント

意思決定管理のインプレッションおよびクリック数は、次のように定義されます。

* **インプレッション**&#x200B;イベントとは、オファーがユーザーに表示される時のイベントです。

* **クリック**&#x200B;イベントとは、ユーザーがオファーをクリックまたは操作した時のイベントです。

インプレッション数およびクリック数に関するフィードバックは、使用される [!DNL Journey Optimizer] チャネルによってキャプチャされます。

[!DNL Journey Optimizer] で作成した&#x200B;**メール**&#x200B;では、**自動**&#x200B;でインプレッション数およびクリック数をトラッキングします。

ただし、**ほとんどのチャネル**&#x200B;では、インプレッション数およびクリック数のデータを&#x200B;**エクスペリエンスイベント**&#x200B;として Adobe Experience Platform に送信する必要があります。これには以下が含まれます。

* [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja){target="_blank"} を使用してオファーをレンダリングする Web ページ

* [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/platform-learn/data-collection/mobile-sdk/overview.html?lang=ja){target="_blank"} を使用したモバイルアプリでオファーをレンダリング - [ 詳細情報 ](https://developer.adobe.com/client-sdks/documentation/adobe-journey-optimizer-decisioning/#ab-sj-tracking-servers){target="_blank"}
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
