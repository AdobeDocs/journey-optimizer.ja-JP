---
solution: Journey Optimizer
product: journey optimizer
title: ディメンションを変更アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: d59643f18a335fe1e094156a1cfee65b717b9fce
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 28%

---

# ディメンションを変更 {#change-dimension}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_dimension_complement"
>title="補集合の生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。 これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_change_dimension"
>title="ディメンションを変更アクティビティ"
>abstract="このアクティビティを使用すると、オーディエンスの作成時にターゲティングディメンションを変更できます。 データテンプレートと入力ディメンションに応じて軸を移動します。 例えば、「契約」ディメンションから「クライアント」ディメンションに切り替えることができます。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](../send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションを変更 ](change-dimension.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) - [ 分割 ](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

マーケターは、調整されたキャンペーン内で、あるデータエンティティから別のリンクエンティティに切り替えることで、オーディエンスターゲティングを絞り込むことができます。 これにより、ユーザープロファイルのターゲティングから、購入、予約、その他のインタラクションなどの特定のアクションに焦点を当てることへと移行できます。

それには、「**[!UICONTROL ディメンションを変更]** アクティビティを使用します。 これにより、データモデルの構造と入力ディメンションに基づいて、調整されたキャンペーン中にターゲティングディメンションを変更できます。

例えば、ターゲティングディメンションを **プロファイル** から **契約** にシフトすると、選択したオーディエンスに関連付けられた契約所有者に直接メッセージを送信できます。

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## ディメンションを変更アクティビティの設定 {#configure}

**ディメンションを変更**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **ディメンションを変更** アクティビティをオーケストレーションされたキャンペーンに追加します。

   ![](../assets/change-dimension.png)

1. **新しいターゲットディメンション**&#x200B;を定義します。ディメンションの変更時には、すべてのレコードが保持されます。

1. 調整したキャンペーンを実行して、結果を表示します。 ディメンションの変更アクティビティの前後でテーブル内のデータを比較し、調整されたキャンペーンテーブルの構造を比較します。

## 例 {#example}

このユースケースでは、過去 1 か月にウィッシュリストを作成したプロファイルに SMS を送信します。

**ウィッシュリスト** ターゲティングディメンションを使用して **オーディエンスを作成** アクティビティを開始し、関連するすべてのウィッシュリストを選択します。

次に、「**[!UICONTROL ディメンションを変更]**」アクティビティを挿入して、ターゲティングディメンションを **ウィッシュリスト** から **受信者** に切り替えます。 これにより、オーケストレーションされたキャンペーンは、これらのウィッシュリストに関連付けられたプロファイルに SMS を送信できます。

![](../assets/change-dimension-example.png)
