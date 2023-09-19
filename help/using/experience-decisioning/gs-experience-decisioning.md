---
title: Experience Decisioning の基本を学ぶ
description: Experience Decisioning の詳細を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 4aea5c1434caa07aad26445c49a3d5c6274502ec
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 6%

---

# Experience Decisioning の基本を学ぶ {#get-started-experience-decisioning}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* **[Experience Decisioning の基本を学ぶ](gs-experience-decisioning.md)**
* 決定項目を管理
   * [項目カタログを設定](catalogs.md)
   * [決定項目の作成](items.md)
   * [項目コレクションを管理](collections.md)
* 項目の選択を設定
   * [決定ルールの作成](rules.md)
   * [ランキングメソッドの作成](ranking.md)
* [選択戦略を作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

## Experience Decisioning とは {#about}

>[!AVAILABILITY]
>
>エクスペリエンス判定機能は、現在、一部のユーザーのみが選択できるベータ版として使用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

エクスペリエンス判定は、「判定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な判定エンジンを提供することで、パーソナライゼーションを簡素化します。 このエンジンでは、ルールとランキング条件を活用して、最も関連性の高い判定項目を選択し、各判定項目に提示します。

これらの判定項目は、Journey Optimizerキャンペーン内でアクセス可能になった新しいコードベースのエクスペリエンスチャネルを通じて、幅広いインバウンドサーフェスにシームレスに統合されます。

**制限事項:**

* 判定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。
* 現時点では、Experience Decisioning では頻度キャップを使用できません。

## エクスペリエンス判定の主な手順 {#steps}

Experience Decisioning を操作する主な手順は次のとおりです。

1. **カスタム属性の設定**：カスタム属性をカタログのスキーマに設定して、決定項目のカタログを特定の要件に合わせます。

1. **決定項目の作成** をターゲットオーディエンスに表示する場合は、を選択します。

1. **コレクションで整理**：コレクションを使用し、属性ベースのルールに基づいて判定項目を分類します。 コレクションを選択戦略に組み込んで、考慮する必要のある判定項目のコレクションを決定します。

1. **決定ルールの作成**：決定ルールは、決定項目や選択戦略で、どのユーザーに決定項目を表示できるかを決定するために使用されます。

1. **ランキングメソッドの実装**：ランキングメソッドを作成し、判定戦略内で適用して、判定項目を選択する際の優先順位を決定します。

1. **選択戦略を作成**：コレクション、決定ルール、ランキングメソッドを活用して、プロファイルへの表示に適した決定項目を識別する選択戦略を構築します。

1. **コードベースのキャンペーンに決定ポリシーを埋め込む**：決定ポリシーは、複数の選択戦略を組み合わせて、対象のオーディエンスに表示する適格な決定項目を決定します。

## 用語集

条件を入力する Brandon。
