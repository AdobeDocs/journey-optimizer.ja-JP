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
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
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
