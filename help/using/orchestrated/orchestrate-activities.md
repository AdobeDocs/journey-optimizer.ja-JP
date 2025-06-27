---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerでオーケストレートキャンペーンを作成
description: Adobe Journey Optimizerで調整されたキャンペーンを作成する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: d1d64125-cf00-49c2-a71d-1494ede16f61
source-git-commit: ecb62dfc6a04754cb5d549615047cfb8e5e8f518
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 28%

---

# キャンペーンアクティビティの調整 {#orchestrate}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンの作成 ](gs-campaign-creation.md)<br/><br/>[ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/><b>[ アクティビティのオーケストレーション ](orchestrate-activities.md)</b><br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

[ オーケストレーションされたキャンペーンを作成 ](gs-campaign-creation.md) したら、実行される様々なタスクのオーケストレーションを開始できます。 これを行うために、視覚的なキャンバスが提供され、調整されたキャンペーン図を作成できます。 このダイアグラムに様々なアクティビティを追加し、順番に接続できます。

## アクティビティを追加 {#add}

設定のこの段階では、ダイアグラムに、調整されたキャンペーンの開始を表す「開始」アイコンが付きます。 最初のアクティビティを追加するには、「開始」アイコンに接続されている「**+**」ボタンをクリックします。

ダイアグラムに追加できるアクティビティのリストが表示されます。使用可能なアクティビティは、調整されたキャンペーン図内の位置によって異なります。 例えば、最初のアクティビティを追加する際に、オーディエンスをターゲティング、オーケストレーションされたキャンペーンパスを分割、またはオーケストレーションされたキャンペーンの実行を遅らせる **待機** アクティビティを設定することで、オーケストレーションされたキャンペーンを開始できます。 一方、**オーディエンスを作成** アクティビティの後に、ターゲティングアクティビティでターゲットを絞り込んだり、チャネルアクティビティでオーディエンスに配信を送信したり、フロー制御アクティビティで調整されたキャンペーンプロセスを整理したりできます。

![](assets/orchestrated-start.png){zoomable="yes"}

アクティビティがダイアグラムに追加されると、右側のパネルが表示され、特定の設定を使用して設定できます。 各アクティビティの設定方法について詳しくは、[この節](activities/about-activities.md)を参照してください。

![](assets/orchestrated-configure-activities.png){zoomable="yes"}

このプロセスを繰り返し、オーケストレーションキャンペーンで実行するタスクに応じて、必要な数のアクティビティを追加します。 また、2 つのアクティビティの間に新しいアクティビティを挿入することもできます。これを行うには、アクティビティ間のトランジションで「**+**」ボタンをクリックし、目的のアクティビティを選択して、右側のパネルで設定します。

各アクティビティ間のトランジションの名前をパーソナライズすることもできます。これを行うには、トランジションを選択し、右側のパネルでそのラベルを変更します。

![](assets/canvas-transition.png)

## キャンバスツールバー {#toolbar}

キャンバスツールバーには、アクティビティを簡単に操作し、キャンバス内を移動するためのオプションが用意されています。

![](assets/orchestrated-toolbar.png)

![ 複数選択モードアイコン ](assets/do-not-localize/canvas-multiple.svg) 複数のアクティビティを選択して一度にすべてを削除するか、コピーして貼り付けます。 [ アクティビティのコピーと貼り付けの方法を学ぶ ](#copy)

![ 回転アイコン ](assets/do-not-localize/canvas-rotate.svg) キャンバスを垂直方向に切り替えます。

![ 画面に合わせるアイコン ](assets/do-not-localize/canvas-fit.svg) キャンバスのズームレベルを画面に合わせます。

![ ズームアウトアイコン ](assets/do-not-localize/canvas-zoomout.svg)![ ズームインアイコン ](assets/do-not-localize/canvas-zoomin.svg) ズームアウトまたはキャンバス。

![Campaign 設定アイコン ](assets/do-not-localize/canvas-map.svg) キャンバスのスナップショットを開いて、位置を示します。

## アクティビティの管理 {#manage}

アクティビティを追加する場合、プロパティパネルでアクションボタンを使用して複数の操作を実行できます。

![](assets/activity-action.png)

![ 削除アイコン ](assets/do-not-localize/activity-delete.svg) キャンバスからアクティビティを削除します。

![ 無効アイコン ](assets/do-not-localize/activity-disable.svg)![ 有効アイコン ](assets/do-not-localize/activity-enable.svg) アクティビティを無効/有効にします。 オーケストレーションされたキャンペーンを実行すると、同じパス上の無効なアクティビティと後続のアクティビティは実行されず、オーケストレーションされたキャンペーンは停止します。

![ 一時停止アイコン ](assets/do-not-localize/activity-pause.svg)![ 再開アイコン ](assets/do-not-localize/activity-resume.svg) アクティビティを一時停止/再開します。 調整したキャンペーンを実行すると、一時停止したアクティビティで一時停止します。 対応するタスクと、同じパス内でそのタスクに続くすべてのタスクが実行されません。

![ コピーアイコン ](assets/do-not-localize/activity-copy.svg) アクティビティをコピーします。 [ アクティビティのコピーと貼り付けの方法を学ぶ ](#copy)

![ ログとタスクのアイコン ](assets/do-not-localize/activity-logs.svg) アクティビティのログとタスクにアクセスします。

「**結合**」や「**重複排除**」などの&#x200B;**ターゲティング**&#x200B;アクティビティを使用すると、残りの母集団を処理し、追加のアウトバウンドトランジションに含めることができます。例えば、「**分割**」アクティビティを使用している場合、補集合は、以前に定義されたどのサブセットにも一致しない母集団で構成されます。 この機能を使用するには、「**[!UICONTROL 補集合を生成]**」オプションを有効化します。

## アクティビティの移動またはコピー {#move-copy}

### アクティビティのコピーとペースト {#copy}

アクティビティをコピーして、調整した任意のキャンペーンキャンバスに貼り付けることができます。 宛先キャンペーンは、別のブラウザータブに配置できます。

* 1 つのアクティビティをコピーするには、アクティビティのプロパティペインで「![ コピーアイコン ](assets/do-not-localize/activity-copy.svg)」ボタンをクリックします。
* 複数のアクティビティをコピーするには、キャンバスツールバーの ![ 複数選択モード ](assets/do-not-localize/canvas-multiple.svg) アイコンをクリックします。

| 1 つのアクティビティをコピー | 複数のアクティビティのコピー |
|  ---  |  ---  |
|  |
| ![](assets/orchestrated-copy-1.png){width="200" align="center" zoomable="yes"} | ![](assets/orchestrated-copy-2.png){width="200" align="center" zoomable="yes"} |

アクティビティを貼り付けるには、トランジションの「**+**」ボタンをクリックし、「x アクティビティを貼り付け」を選択します。

![](assets/orchestrated-copy-3.png){zoomable="yes"}{width="50%"}

<!--## Example {#example}

Here is an orchestrated campaign example designed to send an email to all customers (other than VIP customers) with an email who are interested in coffee machines.

![](assets/workflow-example.png){zoomable="yes"}{zoomable="yes"}

To achieve this, activities below have been added:

* A **[!UICONTROL Fork]** activity that divides the orchestrated campaign into three paths (one for each set of customer),
* **[!UICONTROL Build audience]** activities to target the three sets of customers:

    * Customers with an email,
    * Customers belonging to the pre-existing "Interrested in Coffee Machine(s)" audience,
    * Customers belonging to the pre-existing "VIP ro reward" audience.

* A **[!UICONTROL Combine]** activity that groups together customers with an email and those interested in coffee machines,
* A **[!UICONTROL Combine]** activity that excludes VIP customers,
* An **[!UICONTROL Email delivery]** activity that sends an email to the resulting customers. 

Once you have completed the orchestrated campaign, add en **[!UICONTROL End]** activity at the end of the diagram. This activity allow you to visually mark the end of a workflow and has no functional impact.

After successfully designing the orchestrated campaign diagram, you can execute the orchestrated campaign and track the progress of its various tasks. [Learn how to start an orchestrated campaign and monitor its execution](start-monitor-campaigns.md)-->
