---
product: experience platform
solution: Experience Platform
title: コンテキストデータの基本を学ぶ
description: 意思決定管理でコンテキストデータを活用する方法について説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management
role: Developer, Data Engineer
level: Experienced
exl-id: 4e736f9d-0f05-4a79-8ebf-ea22517d78a9
source-git-commit: 87f3da0a1d73f9aa26c7420d260778286bacdf0c
workflow-type: ht
source-wordcount: '210'
ht-degree: 100%

---

# コンテキストデータの基本を学ぶ {#context-data}

決定リクエストの一部として送信したデータは、コンテキストデータと見なされます。決定エンジンでコンテキストデータを活用できます。例えば、決定リクエストが行われた時点で、現在の天気が 80 度以上であることを要求する決定ルールを設計できます。

コンテキストデータの定義は、**Decisioning** API リクエストと **Edge Decisioning** API リクエスト間で異なります。どちらのタイプのリクエストでも、コンテキストデータは実施要件ルールやランキング式で使用できますが、コンテンツをパーソナライズするためにコンテキストデータを使用できるのは Edge Decisioning API リクエストのみです。

開始する前に、次のガードレールと制限を確認します。

* 決定の呼び出しと Edge 決定の呼び出しの間ではコンテキストの渡し方が異なります。そのため、決定の呼び出しと Edge 決定の呼び出し間で、コンテキストベースの実施要件ルールとランキング式を入れ替えることはできません。
* `dryrun` パラメーターを使用したテストは、Decisioning API でのみ可能です。Edge Decisioning API ではできません。Decisioning API でこのパラメーターを `true` に設定しても、提案の上限と数には影響しません。

各 API でのコンテキストデータの使用方法について詳しくは、次の節を参照してください。

* [Edge 決定リクエストでのコンテキストデータの使用](context-data-edge.md)
* [決定リクエストでのコンテキストデータの使用](context-data-decisioning.md)
