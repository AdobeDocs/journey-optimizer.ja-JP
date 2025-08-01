---
solution: Journey Optimizer
product: journey optimizer
title: 結合アクティビティの使用
description: 結合アクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: af3c3a9c-8172-43b0-bba1-4a3d068b9a9e
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 93%

---

# 結合 {#combine}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine"
>title="アクティビティを結合"
>abstract="**結合**&#x200B;アクティビティを使用すると、インバウンド母集団でセグメント化を実行できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。"

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - <b>[結合](combine.md)</b> - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL 結合]**&#x200B;アクティビティは、インバウンド母集団を効果的にセグメント化できる&#x200B;**[!UICONTROL ターゲティング]**&#x200B;アクティビティのタイプです。複数の母集団を結合したり、特定のセグメントを除外したり、複数のターゲット間で共有されるデータのみを保持したりできます。

次のセグメント化オプションを使用できます。

* **[!UICONTROL 和集合]**：複数のアクティビティの結果を 1 つの統合されたターゲットに結合します。

* **[!UICONTROL 積集合]**：すべてのインバウンド母集団に共通する要素のみを保持します。

* **[!UICONTROL 除外]**：指定した基準に基づいて、1 つの集団から要素を削除します。

## 結合アクティビティを設定 {#combine-configuration}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_intersection_merging_options"
>title="「積集合」結合オプション"
>abstract="積集合では、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。「結合の設定」セクションで、結合する前のアクティビティをすべてオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_exclusion_merging_options"
>title="「除外」結合オプション"
>abstract="除外では、特定の条件に従って、ある母集団から要素を除外することができます。「結合の設定」セクションで、結合する前のアクティビティをすべてオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_options"
>title="セグメント化タイプの選択"
>abstract="オーディエンスを結合する方法を選択します。**和集合**&#x200B;では、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。**積集合**&#x200B;では、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。**除外**&#x200B;では、特定の条件に従って、ある母集団から要素を除外することができます。 "

**[!UICONTROL 結合]**&#x200B;アクティビティの設定を開始するには、次の一般的な手順に従います。

![](../assets/orchestrated-union.png)

1. **[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティなどの複数のアクティビティを追加して、2 つ以上の異なる実行分岐を形成します。
1. **[!UICONTROL 結合]**&#x200B;アクティビティを任意の前の分岐に追加します。
1. [和集合](#union)、[積集合](#intersection)または[除外](#exclusion)のセグメント化タイプを選択します。
1. 「**[!UICONTROL 続行]**」をクリックします。
1. 「**[!UICONTROL 結合の設定]**」セクションで、結合する前のアクティビティをすべてオンにします。

## 和集合 {#combine-union}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_reconciliation"
>title="紐付けオプション"
>abstract="「**紐付けタイプ**」を選択して、重複の処理方法を定義します。デフォルトでは、「**キー**」オプションがアクティブ化されます。つまり、アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。「**列の選択**」オプションを使用して、データの紐付けが適用される列のリストを定義します。"

**[!UICONTROL 結合]**&#x200B;アクティビティ内では、「**[!UICONTROL 紐付けタイプ]**」を選択して&#x200B;**[!UICONTROL 和集合]**&#x200B;を設定し、重複レコードの管理方法を決定できます。

* **[!UICONTROL キーのみ]**（デフォルト）：複数のインバウンドトランジションが同じキーを共有する場合は、単一のレコードを保持します。このオプションは、インバウンド母集団が同質である場合にのみ適用できます。

* **[!UICONTROL 列の選択]**：データの紐付けに使用する列を指定できます。「**[!UICONTROL 属性を追加]**」を選択します。

次の例では、**[!UICONTROL 結合]**&#x200B;アクティビティを&#x200B;**[!UICONTROL 和集合]**&#x200B;と使用して、**ロイヤルティメンバー**&#x200B;と&#x200B;**購入者**&#x200B;の 2 つのクエリの結果を、両方のセグメントのすべてのプロファイルを含む単一の大きなオーディエンスに結合します。

![](../assets/orchestrated-union-example.png)

## 積集合 {#combine-intersection}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_intersection_reconciliation_options"
>title="積集合の紐付けオプション"
>abstract="「**紐付けタイプ**」を選択して、重複の処理方法を定義します。デフォルトでは、「**キー**」オプションがアクティブ化されます。つまり、アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。「**列の選択**」オプションを使用して、データの紐付けが適用される列のリストを定義します。"

**[!UICONTROL 結合]**&#x200B;アクティビティでは、「**[!UICONTROL 積集合]**」を設定できます。このためには、以下の追加の手順に従う必要があります。

1. 「**[!UICONTROL 紐付けタイプ]**」を選択して、重複の処理方法を定義します。

   * **[!UICONTROL キーのみ]**（デフォルト）：複数のインバウンドトランジションが同じキーを共有する場合は、単一のレコードを保持します。このオプションは、インバウンド母集団が同質である場合にのみ適用できます。

   * **[!UICONTROL 列の選択]**：データの紐付けに使用する列を指定できます。「**[!UICONTROL 属性を追加]**」を選択します。

1. 残りの母集団を処理する場合は、**[!UICONTROL 補集合を生成]**&#x200B;を有効にします。補集合には、積集合を除くすべてのインバウンドアクティビティ結果の和集合が含まれます。追加のアウトバウンドトランジションがアクティビティに追加されます。

次の例は、2 つのクエリアクティビティ間の&#x200B;**[!UICONTROL 積集合]**&#x200B;の使用を示しています。これは、**ロイヤルティメンバー**&#x200B;であり、過去 1 か月以内に購入を行ったプロファイルを識別するのに使用されます。

![](../assets/orchestrated-intersection-example.png)


## 除外 {#combine-exclusion}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_exclusion_options"
>title="除外ルール"
>abstract="必要に応じて、インバウンドテーブルを操作できます。別のディメンションからターゲットを除外するには、このターゲットが同じターゲティングディメンションをメインターゲットとして返します。 それには、「除外ルール」セクションの「ルールを追加」をクリックし、ディメンションの変更条件を指定します。データの紐付けは、属性または結合を使用して実行されます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_sets"
>title="結合するセットを選択"
>abstract="「**結合の設定**」セクションで、インバウンドトランジションから「**プライマリセット**」を選択します。 これは、要素の除外元のセットです。 これ以外のセットは、プライマリセットから除外する前の要素に一致します。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_exclusion"
>title="除外ルール"
>abstract="必要に応じて、インバウンドテーブルを操作できます。別のディメンションからターゲットを除外するには、このターゲットが同じターゲティングディメンションをメインターゲットとして返します。 それには、「除外ルール」セクションの「ルールを追加」をクリックし、ディメンションの変更条件を指定します。データの紐付けは、属性または結合を使用して実行されます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine_complement"
>title="結合で補集合を生成"
>abstract="「補集合を生成」オプションの切替スイッチをオンにして、追加のトランジションで残りの母集団を処理します。"

**[!UICONTROL 結合]**&#x200B;アクティビティでは、「**[!UICONTROL 除外]**」を設定できます。このためには、以下の追加の手順に従う必要があります。

1. 「**[!UICONTROL 結合するセット]**」セクションで、主要な母集団を表す「**[!UICONTROL プライマリセット]**」を選択します。他のセットで見つかったレコードは、このプライマリセットから除外されます。

1. 必要に応じて、インバウンドテーブルを調整して、様々なディメンションのターゲットを揃えることができます。別のディメンションからターゲットを除外するには、まずこのターゲットをメインの母集団と同じターゲティングディメンションに移動する必要があります。これを行うには、「**[!UICONTROL ルールを追加]**」をクリックし、ディメンションを変更する条件を定義します。その後、属性または結合を使用して紐付けが行われます。

1. 残りの母集団を処理する場合は、**[!UICONTROL 補集合を生成]**&#x200B;を有効にします。補集合には、積集合を除くすべてのインバウンドアクティビティ結果の和集合が含まれます。追加のアウトバウンドトランジションがアクティビティに追加されます。

次の&#x200B;**[!UICONTROL 除外]**&#x200B;の例は、製品を購入したプロファイルをフィルタリングするように設定された 2 つのクエリを示しています。ロイヤルティメンバーシップを持たないプロファイルは、最初のセットから除外されます。

![](../assets/orchestrated-exclusion-example.png)

