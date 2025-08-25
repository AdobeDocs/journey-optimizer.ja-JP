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
source-git-commit: 6b9044117dcdd7554dea0c5f791a6dcfb0218010
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# 改善されたジャーニー designer へようこそ {#new-canvas}

Journey Optimizerは、ユーザーエクスペリエンスと内部プロセスの向上を目的とした **シンプルなジャーニーモデル** を提供するようになりました。 4 月のリリース以降、次の機能を利用できます。

* 最新化された UI エクスペリエンス用に作成された **再設計されたジャーニーキャンバス**
* ジャーニーキャンバスで直接使用可能な **ライブレポート** UI

>[!NOTE]
>
>この機能のロールアウトはプログレッシブになります。 すぐに変更が表示されない場合があります。

## ジャーニーモデルの更新

新しいジャーニーモデルは既存のジャーニーモデルと並行して動作します。つまり、**2 つの異なるモデル** を使用するジャーニーが存在します。

* レガシーモデル
* 新しいモデル

レガシーモデル内のすべてのジャーニーが保持されます。 引き続き編集、テストまたは公開できます。 レガシーモデルのジャーニーから作成された新しいバージョンも、そのまま残ります。 これらのジャーニーには **機能の変更なし** はありません。

以下のスクリーンショットに示すように、ノードは円形です。これは、従来のモデルでのジャーニーの古い UI です。

![](assets/new-canvas.png)

ただし、**新しいジャーニーを作成** または **既存のジャーニーを複製** すると、そのジャーニーは新しいモデルに配置されます。 従来のモデルのジャーニーは、大部分のお客様が新しいモデルに移行されるまで、引き続きサポートされます。

新しいジャーニーモデルには制限が 1 つあります **従来のモデルから新しいモデルにアクティビティをコピーして貼り付けることはできません。その逆も同様です**。 これを行う場合は、従来のジャーニーを複製して新しいモデルに切り替え、アクティビティをコピーすることをお勧めします。

以下のスクリーンショットには、ジャーニーキャンバス用の新しいデザインの UI が表示されます（新しいモデルでのみ使用可能）。

![](assets/new-canvas2.png)

**ジャーニーデザイナーに追加された新機能（ライブレポートを含む）は、この時点から新しいモデル上のジャーニーでのみ使用できます。**

## ジャーニーキャンバスデザインの改善

新しいジャーニーモデルでは、Adobe Experience Cloud ソリューションおよびアプリエコシステム内にシームレスに収まり、直感的で効率的なユーザーエクスペリエンスを実現する、新しく改善された **ジャーニーキャンバス UI** を導入します。 新しいモデルでのジャーニーは、すべて新しいデザインを使用することになります。

![](assets/new-canvas3.gif)

アクティビティは、次の機能を持つ四角いボックスで表されるようになりました。

* アクティビティタイプを表す最初の行。多くの場合、よりコンテキストに沿った情報（オーディエンスを読み取り時には、選択したオーディエンスの名前を含みます）や、カスタムラベル（定義した場合）で上書きされます。
* 2 行目は常にアクティビティタイプを表しています。

![](assets/new-canvas4.png)

この新しい UI では、**より明確なアクティビティラベルとタイプ** が提供されるようになり、ジャーニーキャンバスが読みやすくなりました。

また、製品チームはクリック数を減らしながら、キャンバス上でより多くの情報を追加できます。 「詳細情報」の例の 1 つは、ジャーニーキャンバスへのライブレポートの組み込みです。このキャンバスでは、エラーが原因でアクティビティにエントリしたり離脱したりするプロファイルを確認できます。

![](assets/new-canvas5.png)

## ジャーニーキャンバスのライブレポート

ジャーニーキャンバスのレイアウトの改善に加えて、ライブレポートと呼ばれる **過去 24 時間** のリアルタイムレポート指標をジャーニーキャンバス内で直接表示できる新機能が導入されています。

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
