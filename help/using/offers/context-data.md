---
product: experience platform
solution: Experience Platform
title: コンテキストデータの基本を学ぶ
description: 意思決定管理でコンテキストデータを活用する方法を説明します。
feature: Decision Management
role: Developer, Data Engineer
level: Experienced
source-git-commit: 9b66f4871d8b539bf0201b2974590672205a3243
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# コンテキストデータの基本を学ぶ {#context-data}

決定リクエストの一部として送信されたデータは、コンテキストデータと見なされます。 決定エンジンでコンテキストデータを活用できます。例えば、決定リクエストの作成時に現在の天気を≥80 度にする必要がある決定ルールをデザインできます。

コンテキストデータの定義は、{Decisioning **API リクエストと** 2}Edge Decisioning **API リクエストとで異なります。**&#x200B;どちらのタイプのリクエストでも、コンテキストデータは実施要件ルールやランキング式で使用できますが、コンテキストデータを使用してコンテンツをパーソナライズできるのはEdge Decisioning API リクエストのみです。

開始する前に、次のガードレールと制限事項を確認してください。

* Decisioning とEdge Decisioning の呼び出しの間ではコンテキストの受け渡し方法が異なるので、コンテキストベースの実施要件ルールとランキング式は、Decisioning とEdge Decisioning の呼び出しの間で交換できません。
* `dryrun` パラメーターを使用したテストは、Decisioning API でのみ可能です。 Edge Decisioning API では使用できません。 Decisioning API でこのパラメーターを `true` に設定しても、提案の上限と数には影響しません。

各 API でのコンテキストデータの使用方法について詳しくは、次の節を参照してください。

* [Edge Decisioning リクエストでのコンテキストデータの使用](context-data-edge.md)
* [決定リクエストでのコンテキストデータの使用](context-data-decisioning.md)

