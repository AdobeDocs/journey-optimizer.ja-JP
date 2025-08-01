---
title: 競合管理と優先順位付け
description: Journey Optimizer の競合と優先順位付けツールを活用する方法について説明します。
role: User
level: Beginner
exl-id: 9dc0cd89-d29a-42d2-a73f-d95f9c39c86e
source-git-commit: 8146221975b7460bf1deaca9363d1624b719b480
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 94%

---

# 競合管理と優先順位付け {#conflict-prioritization}

## 競合管理と優先順位付けツール {#tools}

Journey Optimizer では、過剰な数のインタラクションで顧客が圧倒されるのを避けるために、キャンペーンとジャーニーの量とタイミングを管理することが不可欠です。Journey Optimizer では、競合管理と優先順位付けのためのツールがいくつか提供されています。

これらのツールは、キャンペーンと単一、オーディエンスの選定、オーディエンスを読み取りジャーニーで使用できます。

これらのツールを活用することで、競合や過負荷を回避しながら、適切なメッセージを適切なタイミングで配信し、よりスムーズでターゲットを絞ったマーケティング活動を確実に行うことができます。

### 競合検出ツール

**競合検出ツール**&#x200B;を使用すると、ジャーニーとキャンペーンの潜在的な重複を特定できます。同時に過剰なコミュニケーションが提供されると顧客疲労を引き起こす可能性があるので、これは重要です。Journey Optimizer を使用すると、タイムライン、オーディエンスの重複、チャネル設定などの要素を監視できます。競合を早期に特定することで、キャンペーンを絞り込み、顧客に複数のメッセージが同時に送信されるのを回避できます。

➡️ [ジャーニーとキャンペーンの潜在的な競合の検出方法を学ぶ](conflicts.md)

### 優先度スコア

**優先度スコア**&#x200B;は、顧客が複数のコミュニケーションの対象となる場合に、優先するキャンペーンやジャーニーを制御するのに役立ちます。これは、一度に 1 つのキャンペーンしか表示できない web やモバイルなどのインバウンドチャネルで特に役立ちます。各ジャーニーまたはキャンペーンに優先度スコアを割り当てることで、最も重要なメッセージが最初に配信されるようにすることができます。

➡️ [ジャーニーとキャンペーンに優先度スコアを割り当てる方法を学ぶ](priority-scores.md)

### ルールセット

ルールセットを使用すると、**複数のルールをルールセットにグループ化**&#x200B;し、選択したジャーニーとキャンペーンに適用できます。この結果、精度が向上し、特定の期間内に顧客がエントリできるジャーニーの頻度と数を制限したり、通信のタイプに応じてユーザーがメッセージを受信する頻度を制御したりできます。 [詳しくは、ルールセットの操作方法を参照してください](../conflict-prioritization/rule-sets.md)。

* **ジャーニーのキャップと判別**

  ルールセットを使用すると、一定期間内に顧客がエントリできるジャーニーの頻度と数を制限できます。プロファイルのジャーニーエントリの数を制限するルールや、顧客が同時に登録できるジャーニーの数を制限するルールを設定することもできます。

  さらに、判別設定を使用して、顧客が複数のジャーニーの対象となる場合に、優先度スコアを使用して最適なジャーニーを判断し、エントリする必要があるジャーニーを決定できます。

  ➡️ [ジャーニーのキャップと判別の操作方法を学ぶ](journey-capping.md)

* **チャネルと通信タイプによるフリークエンシーキャップ**

  ルールセットを使用して、通信タイプ別のフリークエンシーキャップ（販売、プロモーションなど）を設定し、類似したメッセージで顧客に過負荷がかかるのを防ぐこともできます。複数のチャネルにわたって頻度を制御し、過度に配信を受けているプロファイルを自動的に除外して、より良い顧客体験を確保できます。

  ➡️ [チャネルと通信タイプに応じたフリークエンシーキャップの設定方法を学ぶ](../conflict-prioritization/channel-capping.md)

## ガードレールと制限

* **キャンペーンと優先度スコア** - キャンペーンでは、優先度スコアは **web**、**アプリ内**、**コードベースの**&#x200B;インバウンドチャネルでのみ使用できます。

* **プロファイルカウンターの更新待ち時間**

  顧客がジャーニーにエントリして、プロファイルカウンターの値が更新されるまで、最大 10 分かかる場合があります。

  プロファイルが短い時間枠で 2 つのジャーニーにエントリすると、2 番目のジャーニーはフリークエンシーキャップに既に達していることを正しく認識できず、プロファイルが両方のジャーニーにエントリできる可能性があります。

* **ジャーニーエントリキャップの名前空間の優先度**

  エントリキャップは、ジャーニーで選択された名前空間がサンドボックスで定義された最も優先度の高い名前空間である場合にのみサポートされます。名前空間の優先度が明示的に設定されていない場合、デフォルトで最も高い優先度はメールです。

* **オーディエンスの選定ジャーニーにおける同時アクティベーション**

  同じオーディエンス選定イベントで複数のオーディエンス選定ジャーニーがアクティブ化されると、エントリキャップのカウントが不正確になります。カウントが上限を下回った場合、ジャーニーは引き続き判別されますが、同時アクティベーションでは最新のカウントを取得することはできません。
