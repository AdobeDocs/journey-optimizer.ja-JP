---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コンテキストデータの基本を学ぶ
description: 意思決定管理でコンテキストデータを活用する方法について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management
role: Developer
level: Experienced
exl-id: 4e736f9d-0f05-4a79-8ebf-ea22517d78a9
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/aVm2FFqkJWN-k1qngYsp94FgKIZWaLCMUneFd0rVNpA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 100%

---

# コンテキストデータの基本を学ぶ {#context-data}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md)

決定リクエストの一部として送信したデータは、コンテキストデータと見なされます。 決定エンジンでコンテキストデータを活用できます。例えば、決定リクエストが行われた時点で、現在の天気が 80 度以上であることを要求する決定ルールを設計できます。

コンテキストデータの定義は、**Decisioning** API リクエストと **Edge Decisioning** API リクエスト間で異なります。 どちらのタイプのリクエストでも、コンテキストデータは実施要件ルールやランキング式で使用できますが、コンテンツをパーソナライズするためにコンテキストデータを使用できるのは Edge Decisioning API リクエストのみです。

開始する前に、次のガードレールと制限を確認します。

* 決定の呼び出しと Edge 決定の呼び出しの間ではコンテキストの渡し方が異なります。そのため、決定の呼び出しと Edge 決定の呼び出し間で、コンテキストベースの実施要件ルールとランキング式を入れ替えることはできません。
* `dryrun` パラメーターを使用したテストは、Decisioning API でのみ可能です。 Edge Decisioning API ではできません。 Decisioning API でこのパラメーターを `true` に設定しても、提案のキャップと数には影響しません。

各 API でのコンテキストデータの使用方法について詳しくは、次の節を参照してください。

* [Edge 決定リクエストでのコンテキストデータの使用](context-data-edge.md)
* [決定リクエストでのコンテキストデータの使用](context-data-decisioning.md)
