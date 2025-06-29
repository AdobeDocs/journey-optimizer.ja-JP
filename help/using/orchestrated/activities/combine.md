---
solution: Journey Optimizer
product: journey optimizer
title: 結合アクティビティの使用
description: 結合アクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: af3c3a9c-8172-43b0-bba1-4a3d068b9a9e
source-git-commit: 38b65200435e0b997e79aefbb66549b9168188fd
workflow-type: tm+mt
source-wordcount: '1121'
ht-degree: 90%

---

# 結合 {#combine}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_combine"
>title="アクティビティを結合"
>abstract="**結合**&#x200B;アクティビティを使用すると、インバウンド母集団でセグメント化を実行できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](../gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](../configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](../gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](../send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) | [ クエリの操作Modeler](../orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリ ](../build-query.md)<br/><br/>[ 編集式を作成 ](../edit-expressions.md) | [ アクティビティの基本を学ぶ ](about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](and-join.md) - [ オーディエンスを作成 ](build-audience.md) - [ ディメンションを変更 ](change-dimension.md) - [ 結合 ](combine.md) - [ 重複排除 ](deduplication.md) - [ エンリッチメント ](enrichment.md) - [ 分岐 ](fork.md) - [ 紐付け ](reconciliation.md) - [ 分割 ](split.md) [&#128279;](wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

**[!UICONTROL エンリッチメント]**&#x200B;アクティビティは、**[!UICONTROL ターゲティング]**&#x200B;アクティビティです。このアクティビティを使用すると、インバウンド母集団に対してセグメント化を実行できます。したがって、いくつもの母集団を組み合わせて、一部を除外したり、複数のターゲットに共通するデータのみを保持したりできます。使用可能なセグメント化のタイプを次に示します。

<!--
The **Combine** activity can be placed after any other activity, but not at the beginning of the workflow. Any activity can be placed after the **Combine**.
-->

* **[!UICONTROL 和集合]**&#x200B;では、複数のアクティビティの結果を 1 つのターゲットに再グループ化できます。
* **[!UICONTROL 積集合]**&#x200B;では、アクティビティ内の異なるインバウンド母集団に共通の要素のみを保持できます。
* **[!UICONTROL 除外]**&#x200B;では、特定の条件に従って、ある母集団から要素を除外することができます。

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

![](../assets/workflow-combine.png)

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

**[!UICONTROL 結合]**&#x200B;アクティビティでは、「**[!UICONTROL 和集合]**」を設定できます。このためには、「**[!UICONTROL 紐付けタイプ]**」を選択して、重複の処理方法を定義する必要があります。

* **[!UICONTROL キーのみ]**：これはデフォルトのモードです。アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。このオプションは、インバウンド母集団が同質である場合にのみ使用できます。
* **[!UICONTROL 列の選択]**：データの紐付けが適用される列のリストを定義する際に選択するオプションです。最初に（ソースデータを含む）プライマリセットを選択し、次に結合に使用する列を選択する必要があります。

## 積集合 {#combine-intersection}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_intersection_reconciliation_options"
>title="積集合の紐付けオプション"
>abstract="「**紐付けタイプ**」を選択して、重複の処理方法を定義します。デフォルトでは、「**キー**」オプションがアクティブ化されます。つまり、アクティビティは、異なるインバウンドトランジションの要素が同じキーを持つ場合、1 つの要素のみを保持します。「**列の選択**」オプションを使用して、データの紐付けが適用される列のリストを定義します。"

**[!UICONTROL 結合]**&#x200B;アクティビティでは、「**[!UICONTROL 積集合]**」を設定できます。このためには、以下の追加の手順に従う必要があります。

1. 「**[!UICONTROL 紐付けタイプ]**」を選択して、重複の処理方法を定義します。[和集合](#union)の節を参照してください。
1. 残りの母集団を処理するには、「**[!UICONTROL 補集合を生成]**」オプションをオンにします。補集合には、すべてのインバウンドアクティビティから積集合を引いた結果の和集合が含まれます。その後、追加のアウトバウンドトランジションがアクティビティに追加されます。

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

1. 「**[!UICONTROL 結合の設定]**」セクションで、インバウンドトランジションから「**[!UICONTROL プライマリセット]**」を選択します。 これは、要素の除外元のセットです。 これ以外のセットは、プライマリセットから除外する前の要素に一致します。
1. 必要に応じて、インバウンドテーブルを操作できます。別のディメンションからターゲットを除外するには、このターゲットが同じターゲティングディメンションをメインターゲットとして返します。 それには、「**[!UICONTROL 除外ルール]**」セクションの「**[!UICONTROL ルールを追加]**」をクリックし、ディメンションの変更条件を指定します。 データの紐付けは、属性または結合を使用して実行されます。
1. 残りの母集団を処理するには、「**[!UICONTROL 補集合を生成]**」オプションをオンにします。[積集合](#intersection)の節を参照してください。

## 例{#combine-examples}

次の例では、**[!UICONTROL 結合]** アクティビティを使用しており、**[!UICONTROL 和集合]** を追加して、18～27 歳のユーザーと 34～40 歳のユーザーという 2 つのクエリのすべてのプロファイルを取得します。

![](../assets/workflow-union-example.png)

次の例は、2 つのクエリアクティビティの&#x200B;**[!UICONTROL 積集合]**&#x200B;を示しています。ここでは、18～27 歳のプロファイルと、メールアドレスが指定されたプロファイルを取得するために使用されています。

![](../assets/workflow-intersection-example.png)

次の&#x200B;**[!UICONTROL 除外]**&#x200B;例は、18～27 歳で、アドビのメールドメインを持つプロファイルをフィルタリングするように設定された 2 つのクエリを示しています。以降、アドビのメールドメインを持つプロファイルが、最初のセットから除外されます。

![](../assets/workflow-exclusion-example.png)
