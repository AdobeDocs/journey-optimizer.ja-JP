---
solution: Journey Optimizer
product: Journey Optimizer
title: AI モデルの基本を学ぶ
description: オファーをランク付けできる AI モデルについて説明します
feature: Ranking, Decisioning
topic: Artificial Intelligence
role: User
level: Intermediate
exl-id: 07679823-2288-4528-b09a-12fd76a69482
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/sWJEr5Pm1wl83Q-2HVb-7mqy7hasQ1ffqRDmJsOFomw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 89%

---

# AI モデルの基本を学ぶ {#ai-models}

[!DNL Journey Optimizer] では、トレーニング済みモデルシステムを使用し、特定のプロファイルに表示するオファーにランクを付けることができます。

この機能を使用すると、ビジネス目標に応じて異なる **AI モデル**&#x200B;を作成できます。 決定でこれらの様々な目標ベース戦略を使用すると、様々な AI モデルが目標にどのような影響を及ぼすかを理解するうえで、トレーニング済みモデルシステムが役に立ちます。

<!--
For example, you can select an AI model for the email channel and another one for the push channel. For each channel, the trained model system will leverage multiple data points to determine which offer should be presented first for a given decision policy?, rather than taking into account the offers' priority scores or a [ranking formula](create-ranking-formulas.md).

>[!IMPORTANT]
>
>For now, ranking models are not supported in Journey Optimizer authored channels.
-->

## AI モデルタイプ {#ai-model-types}

>[!CONTEXTUALHELP]
>id="ajo_exd_ai_model_type"
>title="モデルタイプの選択"
>abstract="作成する AI モデルのタイプを選択します。**自動最適化**&#x200B;では、過去のオファーのパフォーマンスに基づいてオファーが最適化され、**パーソナライズされた最適化**&#x200B;では、オーディエンスとオファーのパフォーマンスに基づいてオファーが最適化およびパーソナライズされます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/create-ranking-strategies#create-ranking-strategy" text="AI モデルの作成"

[!DNL Journey Optimizer] では、2 種類の AI モデルを使用できます。

* **自動最適化モデル**&#x200B;は、ビジネスクライアントが設定したリターン（KPI）を最大化するオファーを提供することを目的としています。 KPIには、コンバージョン率や売上などの指標が含まれます。この時点で、自動最適化は、オファーコンバージョンをターゲットとしたオファークリックの最適化に重点を置いています。 自動最適化は、パーソナライズされておらず、オファーの「グローバル」パフォーマンスに基づいて最適化されます。 [詳細情報](auto-optimization-model.md)

* **パーソナライズされた最適化モデル**&#x200B;では、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたオファーを提供し、KPI を最大化するためのビジネス指向モデルをトレーニングできます。 [詳細情報](personalized-optimization-model.md)

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用する主な手順は次のとおりです。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを作成します。 [詳細情報](../data-collection/create-dataset.md)

1. データセットのイベントを活用してオファーをランク付けする AI モデルを作成します。 [詳細情報](create-ai-models.md)

1. イベントを自動的にキャプチャするようにオファースキーマを設定します。 [詳細情報](../data-collection/schema-requirement.md)

   >[!IMPORTANT]
   >
   >ランキングモデルを収集するには、フィードバックイベントをエクスペリエンスイベントとして送信する必要があります。 [詳しくは、決定データ収集を参照してください](../data-collection/data-collection.md)

1. 実施要件を満たすオファーをランク付けする選択戦略に AI モデルを割り当てます。 [詳細情報](../selection-strategies.md#select-ranking-method)

1. AI モデルのトレーニングのステータスとパフォーマンスを監視する。 [詳細情報](ai-model-observability.md)
