---
solution: Journey Optimizer
product: Journey Optimizer
title: AI モデルの基本を学ぶ
description: オファーをランク付けできる AI モデルについて説明します
feature: Ranking, Decision Management
role: User
level: Intermediate
exl-id: 07679823-2288-4528-b09a-12fd76a69482
version: Journey Orchestration
source-git-commit: 3fa90fa707b562ecf2160ec980520bc8bc267a21
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 100%

---

# AI モデルの基本を学ぶ {#ai-models}

[!DNL Journey Optimizer] では、トレーニング済みモデルシステムを使用し、特定のプロファイルに表示するオファーにランクを付けることができます。

この機能を使用すると、ビジネス目標に応じて異なる **AI モデル**&#x200B;を作成できます。決定でこれらの様々な目標ベース戦略を使用すると、様々な AI モデルが目標にどのような影響を及ぼすかを理解するうえで、トレーニング済みモデルシステムが役に立ちます。

<!--For example, you can select an AI model for the email channel and another one for the push channel. For each channel, the trained model system will leverage multiple data points to determine which offer should be presented first for a given decision policy?, rather than taking into account the offers' priority scores or a [ranking formula](create-ranking-formulas.md).

>[!IMPORTANT]
>
>For now, ranking models are not supported in Journey Optimizer authored channels.-->

## AI モデルタイプ {#ai-model-types}

>[!CONTEXTUALHELP]
>id="ajo_exd_ai_model_type"
>title="モデルタイプの選択"
>abstract="作成する AI モデルのタイプを選択します。**自動最適化**&#x200B;では、過去のオファーのパフォーマンスに基づいてオファーが最適化され、**パーソナライズされた最適化**&#x200B;では、オーディエンスとオファーのパフォーマンスに基づいてオファーが最適化およびパーソナライズされます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/create-ranking-strategies#create-ranking-strategy" text="AI モデルの作成"

[!DNL Journey Optimizer] では、2 種類の AI モデルを使用できます。

* **自動最適化モデル**&#x200B;は、ビジネスクライアントが設定したリターン（KPI）を最大化するオファーを提供することを目的としています。これらの KPI は、コンバージョン率、売上高などの形式で設定できます。現時点では、自動最適化は、オファーコンバージョンをターゲットとするオファークリック数の最適化に的を絞っています。自動最適化は、パーソナライズされておらず、オファーの「グローバル」パフォーマンスに基づいて最適化されます。[詳細情報](auto-optimization-model.md)

* **パーソナライズされた最適化モデル**&#x200B;では、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたオファーを提供し、KPI を最大化するためのビジネス指向モデルをトレーニングできます。[詳細情報](personalized-optimization-model.md)

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用する主な手順は次のとおりです。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを作成します。[詳細情報](../data-collection/create-dataset.md)

1. データセットのイベントを活用してオファーをランク付けする AI モデルを作成します。[詳細情報](create-ai-models.md)

1. イベントを自動的にキャプチャするようにオファースキーマを設定します。[詳細情報](../data-collection/schema-requirement.md)

   >[!IMPORTANT]
   >
   >ランキングモデルを収集するには、フィードバックイベントをエクスペリエンスイベントとして送信する必要があります。[詳しくは、決定データ収集を参照してください](../data-collection/data-collection.md)

1. 実施要件を満たすオファーをランク付けする選択戦略に AI モデルを割り当てます。[詳細情報](../selection-strategies.md#select-ranking-method)
