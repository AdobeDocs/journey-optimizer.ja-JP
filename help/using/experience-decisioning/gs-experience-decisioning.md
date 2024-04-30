---
title: Experience Decisioning の基本を学ぶ
description: 詳しくは、Experience Decisioningを参照してください
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 4c57dbf9-b2a4-42da-8aa3-5a1b3a475a32
source-git-commit: 98e3e770530facac6f9c69a72e77fc663ef5ed0c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 100%

---

# Experience Decisioning の基本を学ぶ {#get-started-experience-decisioning}

>[!BEGINSHADEBOX 「このドキュメントガイドの内容は次のとおりです」]

* **[Experience Decisioning の基本を学ぶ](gs-experience-decisioning.md)**
* 決定項目の管理：[項目カタログの設定](catalogs.md) - [決定項目の作成](items.md) - [項目コレクションの管理](collections.md)
* 項目の選択の設定：[決定ルールの作成](rules.md) - [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーの作成](create-decision.md)

>[!ENDSHADEBOX]

## Experience Decisioning とは {#about}

>[!AVAILABILITY]
>
>現在、Experience Decisioning 機能は、ベータ版として一部のユーザーのみが利用できます。ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。
>
>決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。

Experience Decisioning は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。

これらの決定項目は、Journey Optimizer キャンペーン内でアクセス可能になった新しいコードベースのエクスペリエンスチャネルを通じて、幅広いインバウンドサーフェスにシームレスに統合されます。

## Experience Decisioning の主な手順 {#steps}

Experience Decisioning を操作する主な手順は次のとおりです。

1. **カスタム属性の設定**：カスタム属性をカタログのスキーマに設定して、決定項目のカタログを特定の要件に合わせます。

1. ターゲットオーディエンスに表示する&#x200B;**決定項目を作成**&#x200B;します。

1. **コレクションで整理**：コレクションを使用し、属性ベースのルールに基づいて決定項目を分類します。コレクションを選択戦略に組み込んで、考慮する必要がある決定項目のコレクションを特定します。

1. **決定ルールの作成**：決定ルールは、どのユーザーに決定項目を表示できるかを決定するために、決定項目や選択戦略で使用されます。

1. **ランキングメソッドの実装**：ランキングメソッドを作成し、決定戦略内で適用して、決定項目を選択する際の優先順位を決定します。

1. **選択戦略の作成**：コレクション、決定ルール、ランキングメソッドを活用して、プロファイルに表示するのに適した決定項目を特定する選択戦略を作成します。

1. **コードベースのキャンペーンに決定ポリシーを埋め込む**：決定ポリシーは、複数の選択戦略を組み合わせて、対象のオーディエンスに表示する適格な決定項目を決定します。
