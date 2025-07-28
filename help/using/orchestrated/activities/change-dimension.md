---
solution: Journey Optimizer
product: journey optimizer
title: ディメンションを変更アクティビティの使用
description: ディメンションの変更アクティビティの使用方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 83e66f10-93dd-4759-840c-2c83abc42a28
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 62%

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

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - <b>[ディメンションを変更](change-dimension.md)</b> - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

マーケターは、オーケストレートキャンペーン内で、あるデータエンティティから関連するデータエンティティにシフトすることで、オーディエンスのターゲティングを強化できます。 これにより、ユーザープロファイルを超えて、購入、予約、その他のインタラクションなどの特定の行動に焦点を当てることができます。

これを実現するには、**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを使用します。オーケストレートキャンペーン中にターゲティングディメンションを調整できます。

<!--
>[!IMPORTANT]
>
>Please note that the **[!UICONTROL Change Dimension]** and **[!UICONTROL Change Data source]** activities should not be added in one row. If you need to use both activities consecutively, make sure you include an **[!UICONTROL Enrichement]** activity in between them. This ensures proper execution and prevents potential conflicts or errors.-->

## ディメンションを変更アクティビティの設定 {#configure}

**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL ディメンションを変更]** アクティビティをオーケストレーションされたキャンペーンに追加します。

   ![](../assets/orchestrated-change-dimension.png)

1. **[!UICONTROL 新しいターゲットディメンション]**&#x200B;を定義します。ディメンションの変更時に、すべてのレコードが保持されます。


## 例 {#example}

このユースケースは、過去 1 か月以内にウィッシュリストを作成したプロファイルへの SMS の送信に焦点を当てています。

**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティから開始し、**[!UICONTROL ウィッシュリスト]**&#x200B;ターゲティングディメンションを使用して関連するすべてのウィッシュリストを特定します。

次に、**[!UICONTROL ディメンションを変更]**&#x200B;アクティビティを追加して、ターゲティングディメンションを&#x200B;**[!UICONTROL ウィッシュリスト]**&#x200B;から&#x200B;**[!UICONTROL 受信者]に切り替えますこの手順**、オーケストレーションされたキャンペーンが、これらのウィッシュリストにリンクされている正しいプロファイルをターゲットにし、SMS を目的のプロファイルに送信できるようにします。

![](../assets/orchestrated-change-dimension-example.png)
