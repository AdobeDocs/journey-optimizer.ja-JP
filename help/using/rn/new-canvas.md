---
solution: Journey Optimizer
product: journey optimizer
title: 新しいジャーニーのインターフェイス
feature: Release Notes
topic: Content Management
description: 新しいジャーニーのインターフェイス
hide: true
hidefromtoc: true
exl-id: 03828fca-dde7-4b3b-b890-2c007d1245cc
source-git-commit: 59f41003183e155632124fde294bea575fb0f493
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 1%

---

# 改善されたジャーニーデザイナーへようこそ {#new-canvas}

を開発しました **簡略化されたジャーニーモデル** 社内プロセスの改善を目指します。 この新しいモデルはバックエンドの改善点ですが、アドビのチームは、Journey Optimizerのユーザーから見えて有益な機能を追加する機会を得ました。

* A **ジャーニーキャンバスの再設計** 最新化された UI エクスペリエンス用に作成
* A **ライブレポート** ジャーニーキャンバスで直接使用可能な UI

>[!NOTE]
>
>この機能のロールアウトはプログレッシブになります。 すぐに変更が表示されない場合があります。

## ジャーニーモデルの更新

新しいジャーニーモデルは既存のジャーニーと並行して動作します。つまり、を使用するジャーニーが存在します **2 つの異なるモデル**:

* 「v1」という古い方
* 「v2」という新しいフォルダー

v1 のすべてのジャーニーは v1 にとどまります。 引き続き編集、テストまたは公開できます。 v1 から作成された新しいバージョンも、v1 では保持されます。 次のものがあります **機能上の変更はありません** v1 ジャーニーの周り。

以下のスクリーンショットからわかるように、ノードは円形です。これは、v1 モデルのジャーニーの古い UI です。

![](assets/new-canvas.png)

ただし、**新しいジャーニーの作成** または **既存のものを複製** v2 のジャーニーになります。  アドビでは、ほとんどのお客様が v2 ジャーニーに移行されるまで、v1 ジャーニーを引き続きサポートする予定です。

新しいジャーニーモデルには 1 つの制限があります。制限は次のとおりです **v1 ジャーニーから v2 に（またはその逆に） アクティビティをコピー&amp;ペーストできない**. これを行う場合は、v1 ジャーニーを複製して v2 にしてから、アクティビティをコピーすることをお勧めします。

以下のスクリーンショットには、ジャーニーキャンバス用の新しいデザインの UI が表示されます（v2 モデルでのみ使用可能）。

![](assets/new-canvas2.png)

**ジャーニーデザイナーに追加された新機能（ライブレポートを含む）は、この時点から v2 ジャーニーでのみ使用できます。**

## ジャーニーキャンバスデザインの改善

新しいジャーニーモデルでは、改善された新機能を導入しています **ジャーニーキャンバス UI**&#x200B;は、Adobe Experience Cloud ソリューションおよびアプリエコシステム内にシームレスに適合し、直感的で効率的なユーザーエクスペリエンスを実現します。 v2 スタック内のすべてのジャーニーは、その新しいデザイン上にあります。

![](assets/new-canvas3.gif)

アクティビティは、次の機能を持つ四角いボックスで表されるようになりました。

* アクティビティタイプを表す最初の行。よりコンテキストに基づく情報（例：オーディエンスを読み取り時、選択したオーディエンスの名前を含む）によって、またはカスタムラベル（定義する場合）によって上書きされることもよくあります。
* 2 行目は常にアクティビティタイプを表しています。

![](assets/new-canvas4.png)

この新しい UI では、次の機能を提供することでジャーニーキャンバスが読みやすくなりました **より明確なアクティビティラベルとタイプ**.

また、製品チームはクリック数を減らしながら、キャンバス上でより多くの情報を追加できます。 「詳細情報」の例の 1 つは、ジャーニーキャンバスへのライブレポートの組み込みです。このキャンバスでは、エラーが原因でアクティビティにエントリしたり離脱したりするプロファイルを確認できます。

![](assets/new-canvas5.png)


## ジャーニーキャンバスのライブレポート

ジャーニーキャンバスデザインの改善に加えて、以下を確認できる機能を導入します。 **過去 24 時間のレポート指標** （ライブレポートと呼ばれます）ジャーニーキャンバス内で直接作成します。

![](assets/new-canvas6bis.png)

新しいモデルでのライブジャーニーごとに、以下を確認できます。 **各アクティビティ**、そのアクティビティに入ったプロファイルの数とエラーが原因で終了した数：

![](assets/new-canvas8.png)

<!--`
With every live journey on the new model, you will be able to see two types of "last 24 hours" reporting information:

* On a **new insert**, you will see:
    * The number of profiles that have been exported for audience-triggered journeys. You will see the number of profiles available in the last export job alongside the time when that export has been made.
    * The number of profiles who exited the journey
    * The percentage of errors
    ![](assets/new-canvas7.png)
* **On each activity**, you will see the number of profiles who entered that activity and the number who exited because of an error:
    ![](assets/new-canvas8.png)
-->

ユーザーインターフェイスは、1 分ごとに自動的に更新されます。

<!--
Please note that you may see differences between the number of exported profiles and the number of profiles flowing through the journey. The exported profiles count only provides information about the last export job being made while the number of profiles entering an activity only contains profiles who did it in the last 24 hours. This can especially be visible on recurring daily journeys as there could be a data overlap between two days.
-->
