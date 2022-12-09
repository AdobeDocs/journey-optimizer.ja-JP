---
product: experience platform
solution: Experience Platform
title: AI モデルについて
description: ランク付けが可能な AI モデルについて学習します。
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 4f7f7d1d-a12a-4ff6-b0ff-1a1c3d305a9d
source-git-commit: 12bc2373ac5c391764df3880c5c87666a19e99b2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# AI モデルについて {#ai-models}

[!DNL Journey Optimizer] 特定のプロファイルについて表示するためにランク付けを行う、訓練されたモデルシステムを使用することができます。

この機能を使用すると、ビジネスの目的に合わせて、様々な **AI モデル** を作成することができます。 このような別のゴールに基づいたストラテジを使用すると、訓練されたモデルシステムによって、様々な AI モデルによる目標への影響を理解することができます。

例えば、電子メールチャンネルの AI モデル、およびプッシュチャンネル用の AI モデルを選択することができます。 各チャネルについて、認定されたモデルシステムは複数のデータポイントを活用して、 [ ](create-ranking-formulas.md) 指定された配置に対して最初に提示する必要がある特典を決定します。

## AI モデルタイプ {#ai-model-types}

で [!DNL Journey Optimizer] は、次の2種類の AI モデルを利用できます。

* **自動最適化モデル** は、ビジネスクライアントによって設定される返品 (kpi) を最大化する機能を提供することを目的としています。 このような Kpi は、変換レートや収益などの形式である可能性があります。 この時点で、自動最適化は、オファーによってターゲットとして提供されるクリックを最適化することを中心としています。 自動最適化はパーソナライズされていないので、「グローバル」のパフォーマンスを基準として最適化されています。 [詳細情報](auto-optimization-model.md)

* **パーソナル化モデル** を使用すると、ビジネス目標を定義し、顧客データを活用して、パーソナライズされたキャンペーンを提供して kpi を最大化することができます。 [詳細情報](personalized-optimization-model.md)

   >[!CAUTION]
   >
   >カスタマイズされた最適化モデルは、ユーザーが初めて選択したときに使用できるようになっています。

## AI モデルの作成 {#create-ai-model}

AI モデルを作成して使用するための主な手順は次のとおりです。

1. 変換イベントおよびインプレッションイベントが収集されるデータセットを作成します。 [詳細情報](create-dataset.md)
1. データセットのイベントをランク付けによって利用する AI モデルを作成します。 [詳細情報](create-ranking-strategies.md)
1. イベントを自動的に記録するようにオファースキーマを設定します。 [詳細情報](schema-requirement.md)
1. AI モデルを、ランク付けによって適切なランクの位置に割り当てます。 [詳細情報](../offer-activities/configure-offer-selection.md)
