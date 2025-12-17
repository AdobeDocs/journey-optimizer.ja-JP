---
title: Decisioning API の基本を学ぶ
description: Decisioning API の使用を開始して、決定項目をプログラムで管理し、パーソナライズされたオファーを配信する方法を説明します。
feature: API, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 7a4b5d4e-9c1d-4f3a-b8e9-1d5f6e7a8c3a
version: Journey Orchestration
source-git-commit: e46ab0637a0fa4a2b4b8b6ff3b8ab3eb5d38e0f7
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 5%

---

# Decisioning API デベロッパーガイド {#decisioning-api-developer-guide}

Decisioning API を使用すると、パーソナライズされたオファーを顧客に配信するために使用されるコンポーネントをプログラムによって作成および管理できます。 これらの RESTful API では、決定項目、選択戦略、実施要件ルール、その他の決定コンポーネントに対して完全な CRUD （作成、読み取り、更新、削除）操作を提供します。

## 認証 {#authentication}

Decisioning API を使用する前に、API エンドポイントにアクセスするための認証を設定する必要があります。 詳細な手順については、[Journey Optimizer認証ガイド &#x200B;](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"} を参照してください。

## 使用可能な API 操作 {#available-operations}

Decisioning API は、決定コンポーネントのための包括的な管理機能を提供します。 次のカテゴリの操作を使用できます。

* **決定項目** – 顧客に配信するオファーまたはコンテンツを表す決定項目を作成、読み取り、更新、削除およびリスト化します。

  ➡️ [&#x200B; 決定項目の管理方法を学ぶ &#x200B;](decisions-items/create.md)

* **項目コレクション** – 実施要件ルールを使用して管理とターゲティングを容易にするために、決定項目をコレクションに整理します。

  ➡️ [&#x200B; 項目コレクションの管理方法を学ぶ &#x200B;](items-collections/create.md)

* **選択戦略** – 複数の項目が配信に適している場合に、決定項目を選択およびランク付けする方法を定義します。

  ➡️ [&#x200B; 選択戦略の管理方法を学ぶ &#x200B;](selection-strategies/create.md)

* **実施要件ルール** – 特定の決定項目を受け取る資格があるプロファイルを決定する条件を設定します。

  ➡️[&#x200B; 実施要件ルールの管理方法を学ぶ &#x200B;](eligibility-rules/create.md)

* **ランキング式** - カスタムランキングロジックを作成して、決定項目の表示順序を決定します。

  ➡️ [&#x200B; ランキング式の管理方法を学ぶ &#x200B;](ranking-formulas/create.md)

* **プレースメント** - エクスペリエンスで決定項目を表示できる場所またはコンテキストを定義します。

  ➡️[&#x200B; プレースメントの管理方法を学ぶ &#x200B;](exd-placements/create.md)

## 次の手順 {#next-steps}

これで Decisioning API の基本を理解したので、次の特定の操作に進むことができます。

* [決定項目の作成](decisions-items/create.md)
* [決定項目のリスト](decisions-items/decision-items-list.md)
* [選択戦略の作成](selection-strategies/create.md)
* [実施要件ルールの作成](eligibility-rules/create.md)

キャンペーンとジャーニーで意思決定を使用する方法について詳しくは、[&#x200B; 意思決定に関するドキュメント &#x200B;](../gs-experience-decisioning.md) を参照してください。
