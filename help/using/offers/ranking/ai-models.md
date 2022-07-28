---
product: experience platform
solution: Experience Platform
title: AI モデルの基本を学ぶ
description: オファーをランク付けできる AI モデルについて説明します
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
source-git-commit: 3188bc97b8103d2a01101a23d8c242a3e2924f76
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 80%

---

# AI モデルの基本を学ぶ {#ai-models}

[!DNL Journey Optimizer] では、トレーニング済みモデルシステムを使用し、特定のプロファイルに表示するオファーにランクを付けることができます。

この機能を使用すると、ビジネス目標に応じて異なる **AI モデル**&#x200B;を作成できます。決定でこれらの様々な目標ベース戦略を使用すると、様々な AI モデルが目標にどのような影響を及ぼすかを理解するうえで、トレーニング済みモデルシステムが役に立ちます。

例えば、メールチャネル用にある AI モデルを選択し、プッシュチャネル用に別の AI モデルを選択できます。トレーニング済みモデルシステムでは、チャネルごとに複数のデータポイントを活用して、特定のプレースメントに対して最初に提示するオファーを決定します。オファーの優先度スコアや[ランキング式](create-ranking-formulas.md)を考慮するわけではありません。

## AI モデルタイプ {#ai-model-types}

では、2 種類の AI モデルを使用できます [!DNL Journey Optimizer]:

* **自動最適化モデル** は、ビジネスクライアントによって設定される KPI（リターン）を最大化するオファーを提供することを目的としています。 これらの KPI は、コンバージョン率、売上高などの形式で設定できます。現時点では、自動最適化は、オファーコンバージョンをターゲットとするオファークリック数の最適化に的を絞っています。自動最適化は、パーソナライズされておらず、オファーの「グローバル」パフォーマンスに基づいて最適化されます。[詳細情報](auto-optimization-model.md)

* **パーソナライゼーションモデル** では、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたオファーを提供し、KPI を最大化するためのビジネス指向モデルをトレーニングできます。 [詳細情報](personalized-optimization-model.md)

>[!CAUTION]
>
>現在、パーソナライズされた最適化モデルの使用は、一部のユーザーのみが早期にアクセスできます。

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用する主な手順は次のとおりです。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを作成します。[詳細情報](create-dataset.md)
1. データセットのイベントを活用してオファーをランク付けする AI モデルを作成します。[詳細情報](create-ranking-strategies.md)
1. イベントを自動的にキャプチャするようにオファースキーマを設定します。[詳細情報](schema-requirement.md)
1. 実施要件を満たすオファーをランク付けする決定内のプレースメントに AI モデルを割り当てます。[詳細情報](../offer-activities/configure-offer-selection.md)
