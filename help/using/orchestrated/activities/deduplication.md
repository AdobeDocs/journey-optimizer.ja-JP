---
solution: Journey Optimizer
product: journey optimizer
title: 重複排除 - 重複アクティビティの使用
description: 重複排除 - 重複アクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 4aa79448-f75a-48d5-8819-f4cb4baad5c7
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 88%

---

# 重複の除外 {#deduplication}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_fields"
>title="重複を識別するためのフィールド"
>abstract="「**重複を識別するためのフィールド**」セクションで、「**属性を追加**」ボタンをクリックして、メールアドレス、名、姓など、同一の値によって重複を識別できるフィールドを指定します。 フィールドの順序によって、最初に処理するフィールドを指定できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication"
>title="重複排除アクティビティ"
>abstract="**重複排除 - 重複**&#x200B;アクティビティでは、インバウンドアクティビティの結果から重複を削除できます。 主に、ターゲティングアクティビティの後と、ターゲティングデータを使用できるアクティビティの前に使用されます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_complement"
>title="補集合の生成"
>abstract="重複として除外された残りの母集団を使用して、追加のアウトバウンドトランジションを生成できます。 これを行うには、「**補集合を生成**」オプションの切替スイッチをオンにします。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_deduplication_settings"
>title="重複排除設定"
>abstract="受信データ内の重複を削除するには、以下のフィールドで「重複排除 - 重複」メソッドを定義します。 デフォルトでは、1 つのレコードのみが保持されます。 また、式または属性に基づいて「重複排除 - 重複」モードを選択する必要があります。 デフォルトでは、重複から除外するレコードはランダムに選択されます。"


+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - <b>[重複排除](deduplication.md)</b> - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティは、**[!UICONTROL ターゲティング]**&#x200B;アクティビティです。このアクティビティでは、受信者リストに重複したプロファイルなど、インバウンドアクティビティの結果から重複を削除できます。**[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティは、通常、ターゲティングアクティビティの後と、ターゲットデータを使用できるアクティビティの前に使用されます。

## 重複排除 - 重複アクティビティの設定{#deduplication-configuration}

**[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティを設定するには、次の手順に従います。


1. **[!UICONTROL 重複排除]** アクティビティを、オーケストレートキャンペーンに追加します。

1. 「**[!UICONTROL 重複を識別するためのフィールド]**」セクションで、「**[!UICONTROL 属性を追加]**」ボタンをクリックして、メールアドレス、名、姓など、同一の値によって重複を識別できるフィールドを指定します。 フィールドの順序によって、最初に処理するフィールドを指定できます。

   ![](../assets/deduplication-1.png)

1. 「**[!UICONTROL 重複排除設定]**」セクションで、「保持する重複数」フィールドを使用して保持する一意のレコードの数を選択します。デフォルトは 1 で、重複グループごとに 1 つのレコードが保持されます。すべての重複を保持するには、0 に設定します。

   例えば、レコード A と B が Y の重複で、レコード C が Z の重複である場合：

   * **このフィールドの値が 1 の場合**：Y レコードと Z レコードのみが保持されます。
   * **このフィールドの値が 0 の場合**：すべてのレコード（A、B、C、Y、Z）が保持されます。
   * **このフィールドの値が 2 の場合**：C と Z が保持されます。さらに、A、B、Y のうち、2 つの値がランダムに、または重複排除方法に基づいて保持されます。

1. **[!UICONTROL 重複排除方法]**&#x200B;を選択します。これにより、重複の各グループから保持するレコードをシステムが決定する方法が定義されます。

   * **[!UICONTROL ランダム選択]**：重複から除外するレコードをランダムに選択します。
   * **[!UICONTROL 式の使用]**：定義した式に基づいて、最大値または最小値のレコードを保持します。
   * **[!UICONTROL 空でない値]**：選択したフィールドが空でないレコードを保持します（例：電話番号のあるプロファイルのみを保持します）。
   * **[!UICONTROL 値のリストに従う]**：1 つ以上のフィールドに対して特定の値に優先順位を付けることができます（例：「国」がフランスに設定されているレコードに優先度を付与できます）。「**[!UICONTROL 属性]**」をクリックしてフィールドを選択するか、カスタム式を作成します。**[!UICONTROL 「追加」ボタン]**&#x200B;を使用して、優先度の順序で優先値を入力します。

   ![](../assets/deduplication-2.png)

1. 残りの母集団を利用するには、「**[!UICONTROL 補集合を生成]**」オプションをチェックします。補集合はすべての重複から構成されます。その後、追加のトランジションがアクティビティに追加されます。

## 例{#deduplication-example}

次の例では、配信を送信する前に、**[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティを使用して、ターゲットオーディエンスから重複レコードを削除します。まず、オーディエンスは、空でない「メール」フィールドを持つプロファイルのみを含むようにフィルタリングされます。次に、**[!UICONTROL 重複排除 - 重複]**&#x200B;アクティビティは、メールアドレスを使用して重複を識別および除外します。

![](../assets/deduplication-3.png)
