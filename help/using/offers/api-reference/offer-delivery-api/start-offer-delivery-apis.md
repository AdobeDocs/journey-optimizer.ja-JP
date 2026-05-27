---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Offer Delivery API の基本を学ぶ
description: パーソナライズされたオファーの配信に使用できる API について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/qo18m5-seH1yCaxQPJ7hmXDSkBPex-PgYKMQRsOBhBw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: c132d929-fa62-4271-803e-b823be07b914id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 488
ht-degree: 100%

---

# Offer Delivery API の基本を学ぶ {#about-decisioning-apis}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../../experience-decisioning/gs-experience-decisioning.md)

**Decisioning** API または **Edge Decisioning** API のいずれかを使用してオファーを配信できます。 さらに、**Batch Decisioning** API を使用すると、特定のオーディエンス内のすべてのプロファイルに 1 回の呼び出しでオファーを配信できます。 オーディエンス内の各プロファイルに対するオファーコンテンツは、Adobe Experience Platform データセットに配置され、カスタムバッチワークフローで使用できます。

このページでは、**Decisioning** API と **Edge Decisioning** API で利用できる特定の機能について説明します。 どちらでも顧客にオファーを配信することができますが、インバウンドのユースケースにはできるだけ **Edge Decisioning** API を使用し、プラットフォームでの待ち時間とスループットを向上できるようにすることをお勧めします。

API の使用方法について詳しくは、次の節を参照してください。

* [Decisioning API](decisioning-api.md)
* [Edge Decisioning API](edge-decisioning-api.md)
* [Batch Decisioning API](batch-decisioning-api.md)

## Edge Decisioning API の機能 {#edge}

**エクスペリエンスイベントと決定リクエストについての一意のリクエスト**

Edge Decisioning API を使用すると、エクスペリエンスイベント自体と決定リクエストを、2 つの異なるリクエストではなく、まとめて 1 つのリクエストで送信できます。

例えば、顧客が web サイトを訪問した場合、リクエストにはエクスペリエンスイベント（顧客のページへの訪問）が含まれ、訪問したページに入力するためのオファーが返されます。

**Adobe Experience Platform へのコンテキストデータの格納**

コンテキストデータは、オファーを返す際にしか分からないデータを指します。 例えば、購入した商品の色、購入時の天気などです。

Edge Decisioning API リクエストでコンテキストデータを渡す場合、データは Adobe Experience Platform プロファイルに保存され、後で再利用できるようになります。

>[!NOTE]
>
>コンテキストデータを保存するには、専用の XDM スキーマを設定する必要があります。

**フリークエンシーキャップカウンターの更新**

一部のオファーでフリークエンシーキャップが有効になっていて、キャップカウントがリセットされる頻度が定義されている場合、カウンターが更新され、3 秒未満で Edge Decisioning API の決定で使用できるようになります。 [オファーに制約を追加する方法を学ぶ](../../offer-library/add-constraints.md)

## Decisioning API の機能 {#decisioning}

以下に示す機能は、Decisioning API でのみ使用できます。 要件を満たすためにこれらのいずれかを利用する必要がある場合は、Decisioning API を使用します。 それ以外の場合は、Edge Decisioning API を使用することをお勧めします。

* **オファーのコンテンツと特性**：専用オプションを使用して、オファーのコンテンツや特性を返さないように選択できます。
* **オファーメタデータ**：オファーのメタデータを返すオプションを有効にします。
* **結合ポリシー**：サンドボックスに関連付けられたものとは異なる結合ポリシーをリクエストで使用します。
* **決定イベントとフリークエンシーキャップ**：発生するフリークエンシーキャップによって決定イベントがカウントされないようにします。
* **提案の重複**：提案の重複を排除しないオプションを有効にします。
