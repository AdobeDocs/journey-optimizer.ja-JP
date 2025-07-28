---
solution: Journey Optimizer
product: journey optimizer
title: オーディエンスを保存アクティビティの使用
description: オーケストレーションされたキャンペーンでオーディエンスを保存アクティビティを使用する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 7b5b03ba-fbb1-4916-8c72-10778752d8e4
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 27%

---

# オーディエンスを保存 {#save-audience}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_save_audience"
>title="オーディエンスを保存アクティビティ"
>abstract="**オーディエンスを保存** アクティビティは、既存のオーディエンスを更新したり、オーケストレーション済みキャンペーンで以前に生成された母集団から新しいオーディエンスを作成したりできる **ターゲティング** アクティビティです。 作成したら、これらのオーディエンスは、アプリケーションオーディエンスのリストに追加され、**オーディエンス**&#x200B;メニューからアクセスできます。"


+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - <b>[オーディエンスを保存](save-audience.md)</b> - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++


<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL オーディエンスを保存]** アクティビティは、オーケストレーションされたキャンペーンで以前に生成された母集団に基づいて、新しいオーディエンスの作成または既存のオーディエンスの更新を行うために使用される **[!UICONTROL ターゲティング]** アクティビティです。 保存すると、オーディエンスがアプリケーションオーディエンスのリストに追加され、**[!UICONTROL オーディエンス]** メニューからアクセスできるようになります。

一般的に、同じキャンペーンワークフロー内で作成されたオーディエンスセグメントをキャプチャし、今後のキャンペーンで再利用できるようにするために使用されます。 通常は、最終的なターゲット母集団を保存するために、**[!UICONTROL オーディエンスを作成]** または **[!UICONTROL 結合]** などの他のターゲティングアクティビティに接続されます。

## オーディエンスを保存アクティビティの設定 {#save-audience-configuration}

**[!UICONTROL オーディエンスを保存]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL オーディエンスを保存]** アクティビティをオーケストレーションされたキャンペーンに追加します。

1. 保存したオーディエンスを識別する&#x200B;**[!UICONTROL オーディエンスラベル]**&#x200B;を入力します。

1. キャンペーンターゲティングディメンションから **[!UICONTROL プロファイルマッピングフィールド&#x200B;]** を選択します。

   ➡️[ このページで説明している手順に従って、Campaign ターゲティングディメンションを作成します ](../target-dimension.md)

   ![](../assets/save-audience-1.png)

1. 保存したオーディエンスを追加の ID フィールドに関連付ける場合は、「**[!UICONTROL オーディエンスマッピングを追加]**」をクリックします。

   ![](../assets/save-audience-2.png)

1. オーケストレーションされたキャンペーンを保存して公開し、設定を完了します。 これにより、オーディエンスが生成および保存されます。

保存したオーディエンスのコンテンツは、オーディエンスの詳細ビューに表示されます。このビューには、**[!UICONTROL オーディエンス]** メニューからアクセスしたり、**[!UICONTROL オーディエンスを読み取り]** アクティビティなどでオーディエンスのターゲティング時に選択したりできます。

![](../assets/save-audience-4.png)


## 例 {#save-audience-example}

次の例では、ターゲティングを使用してシンプルなオーディエンスの作成方法を示しています。クエリは、オーケストレートキャンペーン内でこの母集団をフィルタリングすることにより、過去 30 日間に旅行を予約したすべての受信者を識別します。 **ターゲティングディメンション** として **受信者 – CRMID** を選択すると、オーディエンスは、受信者全体ではなく、個々の予約イベントをターゲットにします。 次に、**[!UICONTROL オーディエンスを保存]**&#x200B;アクティビティでこれらのプロファイルを取得し、最近の購入者の再利用可能なオーディエンスを作成します。

![](../assets/save-audience-3.png)
