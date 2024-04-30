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
source-git-commit: b6b3f710d08fb7f0949e75521ce126fa43d6cdc5
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 1%

---

# 改善されたジャーニーデザイナーへようこそ {#new-canvas}

Journey Optimizerでは、を提供するようになりました **簡略化されたジャーニーモデル** これは、ユーザーエクスペリエンスと内部プロセスの向上を目的としています。 4 月のリリース以降、次の機能を利用できます。

* A **ジャーニーキャンバスの再設計** 最新化された UI エクスペリエンス用に作成
* A **ライブレポート** ジャーニーキャンバスで直接使用可能な UI

>[!NOTE]
>
>この機能のロールアウトはプログレッシブになります。 すぐに変更が表示されない場合があります。

## ジャーニーモデルの更新

新しいジャーニーモデルは既存のジャーニーと並行して動作します。つまり、を使用するジャーニーが存在します **2 つの異なるモデル**:

* レガシーモデル
* 新しいモデル

レガシーモデル内のすべてのジャーニーが保持されます。 引き続き編集、テストまたは公開できます。 レガシーモデルのジャーニーから作成された新しいバージョンも、そのまま残ります。 次のものがあります **機能上の変更はありません** これらのジャーニーの周囲。

以下のスクリーンショットに示すように、ノードは円形です。これは、従来のモデルでのジャーニーの古い UI です。

![](assets/new-canvas.png)

ただし、次のような場合： **新しいジャーニーの作成** または **既存のものを複製**、新しいモデルになります。 従来のモデルのジャーニーは、大部分のお客様が新しいモデルに移行されるまで、引き続きサポートされます。

新しいジャーニーモデルには 1 つの制限があります。制限は次のとおりです **レガシーモデルから新しいモデルにアクティビティをコピーして貼り付けることはできません。逆も同様です**. これを行う場合は、従来のジャーニーを複製して新しいモデルに切り替え、アクティビティをコピーすることをお勧めします。

以下のスクリーンショットには、ジャーニーキャンバス用の新しいデザインの UI が表示されます（新しいモデルでのみ使用可能）。

![](assets/new-canvas2.png)

**ジャーニーデザイナーに追加された新機能（ライブレポートを含む）は、この時点から新しいモデル上のジャーニーでのみ使用できます。**

## ジャーニーキャンバスデザインの改善

新しいジャーニーモデルでは、改善された新機能を導入しています **ジャーニーキャンバス UI**&#x200B;は、Adobe Experience Cloud ソリューションおよびアプリエコシステム内にシームレスに適合し、直感的で効率的なユーザーエクスペリエンスを実現します。 新しいモデルでのジャーニーは、すべて新しいデザインを使用することになります。

![](assets/new-canvas3.gif)

アクティビティは、次の機能を持つ四角いボックスで表されるようになりました。

* アクティビティタイプを表す最初の行。多くの場合、よりコンテキストに沿った情報（オーディエンスを読み取り時には、選択したオーディエンスの名前を含みます）や、カスタムラベル（定義した場合）で上書きされます。
* 2 行目は常にアクティビティタイプを表しています。

![](assets/new-canvas4.png)

この新しい UI では、次の機能を提供することでジャーニーキャンバスが読みやすくなりました **より明確なアクティビティラベルとタイプ**.

また、製品チームはクリック数を減らしながら、キャンバス上でより多くの情報を追加できます。 「詳細情報」の例の 1 つは、ジャーニーキャンバスへのライブレポートの組み込みです。このキャンバスでは、エラーが原因でアクティビティにエントリしたり離脱したりするプロファイルを確認できます。

![](assets/new-canvas5.png)


## ジャーニーキャンバスのライブレポート

改善されたジャーニーキャンバスレイアウトに加えて、ユーザーがからリアルタイムレポート指標を表示できる新機能が導入されています。 **過去 24 時間**&#x200B;はライブレポートと呼ばれ、ジャーニーキャンバス内で直接作成されます。

新しいモデルを使用するすべてのライブジャーニー内のアクティビティごとに、次の項目にアクセスできます。

* このアクティビティに入るプロファイルの数。
* エラーが原因でこのアクティビティを終了するプロファイルの数。

![](assets/new-canvas6bis.png)

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
<!--
Please note that you may see differences between the number of exported profiles and the number of profiles flowing through the journey. The exported profiles count only provides information about the last export job being made while the number of profiles entering an activity only contains profiles who did it in the last 24 hours. This can especially be visible on recurring daily journeys as there could be a data overlap between two days.
-->
