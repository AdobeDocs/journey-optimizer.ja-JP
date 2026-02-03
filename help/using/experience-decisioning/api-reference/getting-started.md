---
title: Decisioning API の基本を学ぶ
description: Decisioning API の使用を開始して、決定項目をプログラムで管理し、パーソナライズされたオファーを配信する方法について説明します。
feature: API, Decisioning
topic: Integrations
role: Developer
level: Experienced
exl-id: 7a4b5d4e-9c1d-4f3a-b8e9-1d5f6e7a8c3a
version: Journey Orchestration
source-git-commit: e46ab0637a0fa4a2b4b8b6ff3b8ab3eb5d38e0f7
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---

# Decisioning API 開発者ガイド {#decisioning-api-developer-guide}

Decisioning API を使用すると、パーソナライズされたオファーを顧客に配信するために使用されるコンポーネントをプログラムで作成および管理できます。これらの RESTful API では、決定項目、選択戦略、実施要件ルール、その他の決定コンポーネントに対して完全な CRUD（作成、読み取り、更新、削除）操作を提供します。

## 認証 {#authentication}

Decisioning API を使用する前に、API エンドポイントにアクセスするための認証を設定する必要があります。手順について詳しくは、[Journey Optimizer 認証ガイド](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}を参照してください。

## 使用可能な API 操作 {#available-operations}

Decisioning API は、決定コンポーネントの包括的な管理機能を提供します。使用可能な操作のカテゴリは次のとおりです。

* **決定項目** - 顧客に配信するオファーやコンテンツを表す決定項目を作成、読み取り、更新、削除、一覧表示します。

  ➡️ [決定項目の管理方法の詳細情報](decisions-items/create.md)

* **項目コレクション** - 実施要件ルールを使用して管理とターゲティングを簡単にするために、決定項目をコレクションに整理します。

  ➡️ [項目コレクションの管理方法の詳細情報](items-collections/create.md)

* **選択戦略** - 複数の項目が配信で選定される際に、決定項目を選択およびランク付けする方法を定義します。

  ➡️ [選択戦略の管理方法の詳細情報](selection-strategies/create.md)

* **実施要件ルール** - 特定の決定項目を受け取る実施要件を満たすプロファイルを決定する条件を設定します。

  ➡️ [実施要件ルールの管理方法の詳細情報](eligibility-rules/create.md)

* **ランキング式** - 決定項目の表示順序を決定するカスタムランキングロジックを作成します。

  ➡️ [ランキング式の管理方法の詳細情報](ranking-formulas/create.md)

* **プレースメント** - エクスペリエンスで決定項目を表示できる場所またはコンテキストを定義します。

  ➡️ [プレースメントの管理方法の詳細情報](exd-placements/create.md)

## 次の手順 {#next-steps}

Decisioning API の基本を理解したので、次の特定の操作に進むことができます。

* [決定項目の作成](decisions-items/create.md)
* [決定項目のリスト](decisions-items/decision-items-list.md)
* [選択戦略の作成](selection-strategies/create.md)
* [実施要件ルールの作成](eligibility-rules/create.md)

キャンペーンとジャーニーで決定を使用する方法について詳しくは、[決定ドキュメント](../gs-experience-decisioning.md)を参照してください。
