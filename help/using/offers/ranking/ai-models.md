---
product: experience platform
solution: Experience Platform
title: AI モデルの基本を学ぶ
description: オファーをランク付けできる AI モデルについて説明します
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
source-git-commit: 12b01cb9de84399e5ede987866609acc10b64c5f
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 59%

---

# AI モデルの基本を学ぶ {#ai-models}

[!DNL Journey Optimizer] では、トレーニング済みモデルシステムを使用し、特定のプロファイルに表示するオファーにランクを付けることができます。

この機能を使用すると、ビジネス目標に応じて異なる **AI モデル**&#x200B;を作成できます。決定でこれらの様々な目標ベース戦略を使用すると、様々な AI モデルが目標にどのような影響を及ぼすかを理解するうえで、トレーニング済みモデルシステムが役に立ちます。

例えば、メールチャネル用にある AI モデルを選択し、プッシュチャネル用に別の AI モデルを選択できます。トレーニング済みモデルシステムでは、チャネルごとに複数のデータポイントを活用して、特定のプレースメントに対して最初に提示するオファーを決定します。オファーの優先度スコアや[ランキング式](create-ranking-formulas.md)を考慮するわけではありません。

## AI モデルタイプ {#ai-model-types}

今のところ [!DNL Journey Optimizer]**は AI モデルを 1 つ提供し、 **自動最適化**：過去のオファーのパフォーマンスに基づいてオファーを最適化します。 このタイプの AI モデルの詳細については、 [この節](auto-optimization-model.md).

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用する主な手順は次のとおりです。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを作成します。 [詳細情報](create-dataset.md)
1. データセットのイベントを活用してオファーをランク付けする AI モデルを作成します。 [詳細情報](create-ranking-strategies.md)
1. イベントを自動的にキャプチャするようにオファースキーマを設定します。 [詳細情報](schema-requirement.md)
1. 決定の配置に AI モデルを割り当てて、適格なオファーをランク付けします。 [詳細情報](../offer-activities/configure-offer-selection.md)
