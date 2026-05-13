---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: AI モデルの基本を学ぶ
description: オファーをランク付けできる AI モデルについて説明します
badge: label="レガシー" type="Informative"
feature: Ranking, Decision Management
topic: Artificial Intelligence
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/Ya5F8s8gr9dM-surRM-0K4VaM9GSs8jIZNVZ9b7pdIM
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: c132d929-fa62-4271-803e-b823be07b914id: e08599ea-8888-4294-ba74-3ba0a7762a46id: fe338112-e2ce-4876-8989-fc4d497613f1
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 440
ht-degree: 93%

---

# AI モデルの基本を学ぶ {#ai-models}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

[!DNL Journey Optimizer] では、トレーニング済みモデルシステムを使用し、特定のプロファイルに表示するオファーにランクを付けることができます。

この機能を使用すると、ビジネス目標に応じて異なる **AI モデル**&#x200B;を作成できます。 決定でこれらの様々な目標ベース戦略を使用すると、様々な AI モデルが目標にどのような影響を及ぼすかを理解するうえで、トレーニング済みモデルシステムが役に立ちます。

例えば、メールチャネル用にある AI モデルを選択し、プッシュチャネル用に別の AI モデルを選択できます。 各チャネルについて、トレーニング済みモデルシステムは、オファーの優先度スコアや[ランキング式](create-ranking-formulas.md)を考慮するのではなく、複数のデータポイントを活用して、特定のプレースメントに対して最初に提示するオファーを決定します。

>[!IMPORTANT]
>
>現在、Journey Optimizer が作成したチャネルでは、AI モデルはサポートされていません。

➡️ [この機能について詳しくは、ビデオを参照してください](#video)。

## AI モデルタイプ {#ai-model-types}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_ai_model_type"
>title="モデルタイプの選択"
>abstract="作成する AI モデルのタイプを選択します。**自動最適化**&#x200B;では、過去のオファーのパフォーマンスに基づいてオファーが最適化され、**パーソナライズされた最適化**&#x200B;では、オーディエンスとオファーのパフォーマンスに基づいてオファーが最適化およびパーソナライズされます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/create-ranking-strategies#create-ranking-strategy" text="AI モデルの作成"

[!DNL Journey Optimizer] では、2 種類の AI モデルを使用できます。

* **自動最適化モデル**&#x200B;は、ビジネスクライアントが設定したリターン（KPI）を最大化するオファーを提供することを目的としています。 KPIには、コンバージョン率や売上などの指標が含まれます。この時点で、自動最適化は、オファーコンバージョンをターゲットとしたオファークリックの最適化に重点を置いています。 自動最適化は、パーソナライズされておらず、オファーの「グローバル」パフォーマンスに基づいて最適化されます。 [詳細情報](auto-optimization-model.md)

* **パーソナライズされた最適化モデル**&#x200B;では、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたオファーを提供し、KPI を最大化するためのビジネス指向モデルをトレーニングできます。 [詳細情報](personalized-optimization-model.md)

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用する主な手順は次のとおりです。

1. コンバージョンイベントとインプレッションイベントが収集されるデータセットを作成します。 [詳細情報](../data-collection/create-dataset.md)

1. データセットのイベントを活用してオファーをランク付けする AI モデルを作成します。 [詳細情報](create-ranking-strategies.md)

1. イベントを自動的にキャプチャするようにオファースキーマを設定します。 [詳細情報](../data-collection/schema-requirement.md)

   >[!IMPORTANT]
   >
   >AI モデルを収集するには、フィードバックイベントをエクスペリエンスイベントとして送信する必要があります。 [意思決定管理データ収集についての詳細情報](../data-collection/data-collection.md)

1. 実施要件を満たすオファーをランク付けする決定内のプレースメントに AI モデルを割り当てます。 [詳細情報](../offer-activities/configure-offer-selection.md)

## チュートリアルビデオ {#video}

Offer Decisioning 用の AI モデルを作成する方法と、モデルを決定に適用する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3419959?quality=12)
