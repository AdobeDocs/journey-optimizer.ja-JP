---
title: データ収集
description: 決定管理のフィードバックデータ収集の詳細を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
source-git-commit: b06b545d377fcd1ffe6ed218badeb94c1bb85ef2
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 6%

---

# 決定管理データ収集 {#data-collection}

## データ収集について

表示されるオファーやoffer decisioningとの関わり方など、Adobe Experience Platformでユーザーのフィードバックを収集できます。 このデータは、次の目的で使用できます。
* 作成中 [決定管理レポート](../reports/get-started-events.md);
* 使用 [頻度キャップ](../offer-library/add-constraints.md#capping) ルール；
* 建物 [AI モデル](../ranking/create-ranking-strategies.md) ランキングメソッドとして使用できます。

## イベントのタイプ

データの収集方法は、取り込むイベントタイプに応じて異なります。

### 決定イベント

決定管理が決定を下すたびに、その決定イベントに関連する情報は次のようになります。 **自動** すべてのチャネルでAdobe Experience Platformに送信されました。 [詳細情報](../reports/get-started-events.md)

### インプレッションとクリックイベント

決定管理のインプレッションおよびクリック数は、次のように定義されます。

* An **impression** イベントとは、オファーがユーザーに表示されるときです。

* A **クリック** イベントとは、ユーザーがオファーをクリックまたは操作したときのことです。

インプレッション数およびクリック数に関するフィードバックは、 [!DNL Journey Optimizer] 使用されるチャネル。

1. 一方で、一部のチャネル **自動** インプレッション数およびクリック数を追跡します。 次の 3 つです。

   * 作成者のメール [!DNL Journey Optimizer]
   * モバイルプッシュ通知の作成者 [!DNL Journey Optimizer]
   * モバイルアプリ [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html?lang=ja#what-is-adobe-experience-platform-web-sdk%3F){target="_blank"} または Mobile SDK<!--TBC--> オファーをレンダリング <!--need more info + link-->

   >[!NOTE]
   >
   >Adobeがオファーをチャネル上のエンドユーザーに視覚的にレンダリングする場合、Adobeがフィードバックを自動送信すると仮定できます。

1. 一方、一部のチャネルでは、インプレッション数およびクリック数データをAdobe Experience Platform as a **エクスペリエンスイベント**.

   モバイルアプリを除き、 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html?lang=ja#what-is-adobe-experience-platform-web-sdk%3F){target="_blank"} または Mobile SDK<!--TBC-->では、判定 API リクエストを使用してオファーを受け取るすべてのチャネルに、エクスペリエンスイベントとしてフィードバックを送信する必要があります。 これには以下が含まれます。

   * Web ページ
   * キオスク
   * サードパーティのアプリケーションを通じて送信されるメッセージ

   >[!NOTE]
   >
   >オファーのレンダリング方法に関する指示が必要な場合は、フィードバックをエクスペリエンスイベントとして送信する必要があると想定できます。

### カスタムイベント

オファーに関連付けられたカスタムイベントに関するフィードバックは、独自の設定に従ってAdobe Experience Platformに送信できます。 例えば、1 つのオファーに複数のボタン ( *関心あり*, *興味なし*&#x200B;などのイベントを個別に送信する場合もありますが、エクスペリエンスイベントとして送信することもできます。 <!--Not sure to get that part. How feedback is collected in the first case, i.e. when events are sent in separately? Does it mean the customer just handles it the wau he wants?-->

## フィードバックデータの送信

フィードバックデータを送信するには、イベントを収集するデータセットを作成し、各イベントタイプに対して、Adobe Experience Platformに送信するエクスペリエンスイベントを定義する必要があります。

* エクスペリエンスイベントが収集されるデータセットを作成する方法を説明します。 [この節](create-dataset.md).

* フィードバックデータを送信するエクスペリエンスイベントを定義する方法について説明します。 [この節](schema-requirement.md).

