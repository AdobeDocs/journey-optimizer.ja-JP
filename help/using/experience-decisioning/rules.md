---
title: 決定ルール
description: 決定ルールの操作方法を学ぶ
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: 29228a17176421ccf29598d6ebba815b800db7a2
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 36%

---

# 決定ルール {#rules}

>[!CONTEXTUALHELP]
>id="ajo_exd_config_rules"
>title="決定ルールの作成"
>abstract="決定ルールを使用すると、決定項目レベルで直接、または特定の選択戦略内で制約を適用することで、決定項目のオーディエンスを定義できます。これにより、アイテムを提示する対象を正確に制御できます。"

>[!BEGINSHADEBOX 「このドキュメントガイドの内容は次のとおりです」]

* [エクスペリエンス決定の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理：[項目カタログの設定](catalogs.md) - [決定項目の作成](items.md) - [項目コレクションの管理](collections.md)
* 項目の選択の設定：**[決定ルールの作成](rules.md)** - [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーを作成](create-decision.md)

>[!ENDSHADEBOX]

決定ルールを使用すると、決定項目レベルで直接、または特定の選択戦略内で制約を適用することで、決定項目のオーディエンスを定義できます。これにより、アイテムを提示する対象を正確に制御できます。

例えば、女性向けに作られたヨガ関連製品を特集した決定項目があるシナリオを考えてみましょう。決定ルールを使用すると、これらの項目は、性別が「女性」で、「ヨガ」に「目標点」を示したプロファイルにのみ表示されるように指定できます。

>[!NOTE]
>
>項目および選択戦略レベルの決定ルールに加えて、キャンペーンレベルで意図したオーディエンスを定義することもできます。[詳細情報](../campaigns/create-campaign.md#audience)

決定ルールのリストには、**[!UICONTROL 設定]**／**[!UICONTROL 決定ルール]**&#x200B;メニューからアクセスできます。

![](assets/decision-rules-list.png)

## 決定ルールの作成 {#create}

決定ルールを作成するには、次の手順に従います。

1. に移動します。 **[!UICONTROL 設定]** / **[!UICONTROL 決定ルール]** 次に、 **[!UICONTROL ルールを作成]** ボタン。

1. 決定ルール作成画面が開きます。 ルールに名前を付け、説明を入力します。

1. Adobe Experience Platform セグメントビルダーを使用して、ニーズに合った決定ルールを作成します。 これを行うには、Adobe Experience Platformから取得したプロファイル属性、オーディエンス、コンテキストデータなど、様々なデータソースを TOU で活用します。 [決定ルールでコンテキストデータを活用する方法を学ぶ](#context-data)

   ![](assets/decision-rules-build.png)

   >[!NOTE]
   >
   >決定ルールを作成するために用意されているセグメントビルダーは、Adobe Experience Platform Segmentation サービスで使用されるものと比較して、特異性がいくつかあります。  ただし、ドキュメントで説明されているグローバルプロセスは、決定ルールを作成する場合にも有効です。 [詳しくは、セグメント定義の作成方法を参照してください](../audience/creating-a-segment-definition.md)

1. ワークスペースに新しいフィールドを追加および設定すると、**[!UICONTROL オーディエンスのプロパティ]**&#x200B;パネルに、オーディエンスに属する推定プロファイルに関する情報が表示されます。「**[!UICONTROL 予測を更新]**」をクリックして、データを更新します。

   >[!NOTE]
   >
   >プロファイルの予測は、ルールパラメーターにコンテキストデータなど、プロファイルに含まれないデータが含まれる場合は使用できません。

1. 決定ルールの準備が整ったら、 **[!UICONTROL 保存]**. 作成したルールはリストに表示され、決定項目や選択戦略で使用して、プロファイルに対する決定項目の表示を制御できます。

## 決定ルールでのコンテキストデータの活用 {#context-data}

Experience Decisioning ルールの作成画面では、Adobe Experience Platformで使用可能な任意の情報を活用して、決定ルールを作成できます。 例えば、現在の天気を≥80 度にする決定ルールをデザインできます。

それには、まず、Experience Decisioning で利用できるようにするデータを定義する必要があります。 完了すると、このデータはで Experience Decisioning にシームレスに統合されます **[!UICONTROL コンテキストデータ]** 決定ルールの作成時に使用可能なタブ。

![](assets/decision-rules-context.png)

Experience Decisioning にAdobe Experience Platform データをフィードする手順は次のとおりです。

1. を作成 **エクスペリエンスイベントスキーマ**  Adobe Experience Platformおよび関連する **データセット**. [スキーマの作成方法を学ぶ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. 新しいAdobe Experience Platform データストリームを作成します。

   1. に移動します。 **[!UICONTROL データストリーム]** メニューと選択 **[!UICONTROL 新規データストリーム]**.

   1. が含まれる **[!UICONTROL イベントスキーマ]** ドロップダウンリストから、前に作成したエクスペリエンスイベントスキーマを選択し、「」をクリックします **[!UICONTROL 保存]**.

      ![](assets/decision-rule-context-datastream.png)

   1. クリック **[!UICONTROL サービスを追加]** そして、サービスとして「Adobe Experience Platform」を選択します。 が含まれる **[!UICONTROL イベントデータセット]** ドロップダウンリストから、前に作成したイベントデータセットを選択し、 **[!UICONTROL Adobe Journey Optimizer]** オプション。

      ![](assets/decision-rules-context-datastream-service.png)

データストリームが保存されると、選択したデータセットの情報が自動的に取得され、Experience Decisioning に統合されます。通常、約 24 時間以内に使用可能になります。

Adobe Experience Platformの操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

* [エクスペリエンスデータモデル（XDM）スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [データセット](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [データストリーム](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview){target="_blank"}
