---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスを作成アクティビティの使用
description: オーケストレーションされたキャンペーンでオーディエンスを作成アクティビティを使用する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 3959b5fa-0c47-42a5-828f-4d7ca9b7e72d
source-git-commit: e71cbc5b29a31e2f23b408ae8c8b73379a44275d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 53%

---

# オーディエンスを作成 {#build-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience"
>title="オーディエンスを作成アクティビティ"
>abstract="**オーディエンスを作成** アクティビティを使用すると、オーケストレーションされたキャンペーンにエントリするオーディエンスを定義できます。 オーケストレーションされたキャンペーンのコンテキストでメッセージを送信する場合、メッセージオーディエンスはチャネルアクティビティではなく、**オーディエンスを作成** アクティビティで定義されます。"

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - <b>[オーディエンスを作成](build-audience.md)</b> - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++


<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

マーケターは、直感的なインターフェイスを通じて複雑なオーディエンスセグメントを作成し、様々な条件と行動に基づいてユーザーをターゲットにして、キャンペーンをより効果的にカスタマイズできます。

これを行うには、**[!UICONTROL オーディエンスを作成]**&#x200B;ターゲティングアクティビティを使用します。このアクティビティは、オーケストレートキャンペーンに参加するオーディエンスを定義します。 オーケストレートキャンペーンの一部としてメッセージを送信する場合、オーディエンスは、オーケストレートキャンペーン内ではなく、**[!UICONTROL オーディエンスを作成]** アクティビティで定義されます。

## オーディエンスを作成アクティビティの設定 {#build-audience-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_build_audience_audienceselector"
>title="オーディエンス"
>abstract="新しい配信をデザインする際にオーディエンスを使用するのと同じ方法で、オーディエンスを選択します。"

**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティを追加します。

   ![](../assets/build-audience.png)

1. **[!UICONTROL ラベル]**&#x200B;を定義します。

1. 以下のタブに示す手順に従って、オーディエンスを設定します。

1. 「**[!UICONTROL ターゲティングディメンション]**」を選択します。ターゲティングディメンションは、受信者、契約の受益者、オペレーター、サブスクライバーなど、ターゲットされる母集団を操作ごとに定義します。デフォルトでは、ターゲットが受信者から選択されます。

1. 「**[!UICONTROL 続行]**」をクリックします。

1. ルールビルダーを使用してクエリを定義します。 [ ルールビルダーの詳細については、この節を参照してください ](../orchestrated-rule-builder.md)

1. オーディエンスが空の場合に、アウトバウンドトランジションを生成するかどうかを指定します。

## 例{#build-audience-examples}

2 つの **[!UICONTROL オーディエンスを作成]** アクティビティを使用したオーケストレートキャンペーンの例を次に示します。 最初は、買い物かごに商品があるプロファイルをターゲットにし、次にメール配信が続きます。2 番目は、ウィッシュリストがあるプロファイルをターゲットにし、次に SMS 配信が続きます。

![](../assets/build-audience-2.png)
