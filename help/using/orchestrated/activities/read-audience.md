---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスを読み取りアクティビティの使用
description: オーケストレーションされたキャンペーンでオーディエンスを読み取りアクティビティを使用する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: ef8eba57-cd33-4746-8eb4-5214ef9cbe2f
source-git-commit: 2ad659b391515c193418325c34a9dd56133b90d6
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 19%

---

# オーディエンスを読み取り {#read-audience}


>[!CONTEXTUALHELP]
>id="ajo_orchestration_read_audience"
>title="「オーディエンスを作成」アクティビティ"
>abstract="**オーディエンスを読み取り**&#x200B;アクティビティを使用すると、調整されたキャンペーンにエントリするオーディエンスを選択できます。このオーディエンスは、既存の Adobe Experience Platform オーディエンスか、CSV ファイルから取り込まれたオーディエンスです。調整されたキャンペーンのコンテキストでメッセージを送信する際、メッセージオーディエンスはチャネルアクティビティではなく、**オーディエンスを読み取り**&#x200B;または&#x200B;**オーディエンスを作成**&#x200B;アクティビティで定義されます。"


+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ ルールビルダーの操作 ](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](../build-query.md)<br/><br/>[ 式の編集 ](../edit-expressions.md)<br/><br/>[ リターゲティング ](../retarget.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションの変更 ](change-dimension.md) - [ チャネルアクティビティ ](channels.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) [&#128279;](save-audience.md) [&#128279;](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL オーディエンスを読み取り]** アクティビティを使用すると、以前に保存またはインポートした既存のオーディエンスを取得し、調整されたキャンペーン内で再利用できます。 このアクティビティは、新しいセグメント化プロセスを実行しなくても、事前定義済みのプロファイルセットをターゲティングする場合に特に便利です。

オーディエンスが読み込まれたら、一意の ID フィールドを選択し、ターゲティング、パーソナライゼーションまたはレポートの目的で追加のプロファイル属性でオーディエンスを強化することで、オプションでオーディエンスを絞り込むことができます。

## オーディエンスを読み取りアクティビティの設定 {#read-audience-configuration}

**[!UICONTROL オーディエンスを読み取り]** アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーディエンスを読み取り]** アクティビティをオーケストレーションされたキャンペーンに追加します。

   ![](../assets/read-audience-1.png)

1. アクティビティに **[!UICONTROL ラベル]** を入力します。

1. ![ フォルダー検索アイコン ](../assets/do-not-localize/folder-search.svg) をクリックして、オーケストレーションしたキャンペーンのターゲットにするオーディエンスを選択します。

   ![](../assets/read-audience-2.png)

1. オーディエンス内のプロファイルを一意に識別するために使用する **[!UICONTROL エンティティ]** を選択します。

   ![](../assets/read-audience-3.png)

1. 「**[!UICONTROL プロファイル属性を追加]**」を選択して、選択したオーディエンスに追加のデータを追加します。 結果のオーディエンスには、受信者のリストが含まれ、各受信者は選択したプロファイル属性でエンリッチメントされます。

1. オーディエンスに追加する **[!UICONTROL 属性]** を選択します。

   ![](../assets/read-audience-4.png)

## 例

次の例では、**[!UICONTROL オーディエンスを読み取り]** アクティビティを使用して、ニュースレターを購読しているプロファイルの、以前に作成および保存されたオーディエンスを取得します。 その後、オーディエンスは **ロイヤルティメンバーシップ** 属性でエンリッチメントされ、ロイヤルティプログラムの登録メンバーであるユーザーのターゲティングが可能になります。

![](../assets/read-audience-5.png)
