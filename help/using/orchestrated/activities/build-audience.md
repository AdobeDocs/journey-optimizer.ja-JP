---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスを作成アクティビティの使用
description: オーケストレーションされたキャンペーンでオーディエンスを作成アクティビティを使用する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
source-git-commit: 3f4652445bb52850d7480e844c77a4b67dc4db10
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 32%

---

# オーディエンスを作成 {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="オーディエンスを作成アクティビティ"
>abstract="**オーディエンスを作成**&#x200B;アクティビティを使用すると、調整されたキャンペーンにエントリするオーディエンスを定義できます。オーケストレーションされたキャンペーンのコンテキストでメッセージを送信する場合、メッセージオーディエンスはチャネルアクティビティではなく、**オーディエンスを作成** アクティビティで定義されます。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](../send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションを変更 ](change-dimension.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) - [ 分割 ](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

マーケターの場合、直感的なインターフェイスを使用して複雑なオーディエンスセグメントを作成でき、様々な条件や行動に基づいてユーザーをターゲット設定し、キャンペーンを効果的に調整できます。

それには、**[!UICONTROL オーディエンスを作成]** ターゲティングアクティビティを使用します。 このアクティビティは、オーケストレーションされたキャンペーンに参加するオーディエンスを定義します。 オーケストレーションされたキャンペーンの一部としてメッセージを送信する場合、オーディエンスは、オーケストレーションされたキャンペーン内ではなく、**[!UICONTROL オーディエンスを作成]** アクティビティで定義されます。

## オーディエンスを作成アクティビティの設定 {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="オーディエンス"
>abstract="新しい配信をデザインする際にオーディエンスを使用するのと同じ方法で、オーディエンスを選択します。"

**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを追加します。

   ![](../assets/build-audience.png)

1. **[!UICONTROL ラベル]** を定義します。

1. 以下のタブに示す手順に従って、オーディエンスを設定します。

1. 「**[!UICONTROL ターゲティングディメンション]**」を選択します。ターゲティングディメンションは、受信者、契約の受益者、オペレーター、サブスクライバーなど、ターゲットされる母集団を操作ごとに定義します。デフォルトでは、ターゲットが受信者から選択されます。

1. 「**[!UICONTROL 続行]**」をクリックします。

1. クエリモデラーを使用してクエリを定義します。 [ クエリモデラーの詳細については、この節を参照してください ](../orchestrated-rule-builder.md)

1. オーディエンスが空の場合にアウトバウンドトランジションを生成するかどうかを指定します。

## 例{#build-audience-examples}

次に、2 つの **[!UICONTROL オーディエンスを作成]** アクティビティを使用して調整されたキャンペーンの例を示します。 最初は、買い物かごに項目が含まれるプロファイルをターゲットにし、次にメール配信が続きます。 2 番目は、ウィッシュリストを使用したプロファイルをターゲットにし、次に SMS 配信をターゲットにします。

![](../assets/build-audience-2.png)
