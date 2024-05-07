---
title: 決定ルール
description: 決定ルールの操作方法を学ぶ
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="Beta"
exl-id: 033a11b8-c848-4e4a-b6f0-62fa0a2152bf
source-git-commit: 29228a17176421ccf29598d6ebba815b800db7a2
workflow-type: ht
source-wordcount: '652'
ht-degree: 100%

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

例えば、女性向けに作られたヨガ関連製品を特集した決定項目があるシナリオを考えてみましょう。決定ルールを使用すると、性別が「女性」で、「ヨガ」に「興味」を示したプロファイルにのみ、これらの項目を表示するように指定できます。

>[!NOTE]
>
>項目および選択戦略レベルの決定ルールに加えて、キャンペーンレベルで意図したオーディエンスを定義することもできます。[詳細情報](../campaigns/create-campaign.md#audience)

決定ルールのリストには、**[!UICONTROL 設定]**／**[!UICONTROL 決定ルール]**&#x200B;メニューからアクセスできます。

![](assets/decision-rules-list.png)

## 決定ルールの作成 {#create}

決定ルールを作成するには、次の手順に従います。

1. **[!UICONTROL 設定]**／**[!UICONTROL 決定ルール]**&#x200B;に移動し、「**[!UICONTROL ルールを作成]**」ボタンをクリックします。

1. 決定ルール作成画面が開きます。ルールに名前を付け、説明を入力します。

1. Adobe Experience Platform セグメントビルダーを使用して、ニーズに合った決定ルールを作成します。それには、Adobe Experience Platform から取得したプロファイル属性、オーディエンス、コンテキストデータなどの様々なデータソースを活用できます。[決定ルールでコンテキストデータを活用する方法を学ぶ](#context-data)

   ![](assets/decision-rules-build.png)

   >[!NOTE]
   >
   >決定ルールを作成するために用意されているセグメントビルダーは、Adobe Experience Platform セグメント化サービスで使用されるものと比べて、特異性がいくつかあります。ただし、本ドキュメントで説明されているグローバルプロセスは、決定ルールを作成する場合にも有効です。[詳しくは、セグメント定義の作成方法を参照してください](../audience/creating-a-segment-definition.md)

1. ワークスペースに新しいフィールドを追加および設定すると、**[!UICONTROL オーディエンスのプロパティ]**&#x200B;パネルに、オーディエンスに属する推定プロファイルに関する情報が表示されます。「**[!UICONTROL 予測を更新]**」をクリックして、データを更新します。

   >[!NOTE]
   >
   >プロファイルの予測は、コンテキストデータなどのプロファイルにないデータがルールパラメーターに含まれている場合は使用できません。

1. 決定ルールの準備が整ったら、「**[!UICONTROL 保存]**」をクリックします。作成されたルールはリストに表示され、決定項目と選択戦略で使用して、プロファイルへの決定項目の表示を制御できます。

## 決定ルールでのコンテキストデータの活用 {#context-data}

エクスペリエンス決定ルールの作成画面では、Adobe Experience Platform で入手可能な任意の情報を活用して、決定ルールを作成できます。例えば、現在の気温が 80 ℃以上であることを条件とする決定ルールを設計できます。

それには、まず、エクスペリエンス決定で使用できるようにするデータを定義する必要があります。完了すると、このデータは決定ルールの作成時に使用できる「**[!UICONTROL コンテキストデータ]**」タブでエクスペリエンス決定にシームレスに統合されます。

![](assets/decision-rules-context.png)

エクスペリエンス決定に Adobe Experience Platform データをフィードする手順は、次のとおりです。

1. Adobe Experience Platform で&#x200B;**エクスペリエンスイベントスキーマ**&#x200B;およびそれに関連する&#x200B;**データセット**&#x200B;を作成します。[スキーマの作成方法については、こちらを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. 新しい Adobe Experience Platform データストリームを次の手順で作成します。

   1. **[!UICONTROL データストリーム]**&#x200B;メニューに移動し、「**[!UICONTROL 新規データストリーム]**」を選択します。

   1. **[!UICONTROL イベントスキーマ]**&#x200B;ドロップダウンリストで、先ほど作成したエクスペリエンスイベントスキーマを選択し、「**[!UICONTROL 保存]**」をクリックします。

      ![](assets/decision-rule-context-datastream.png)

   1. 「**[!UICONTROL サービスを追加]**」をクリックし、サービスとして「Adobe Experience Platform」を選択します。**[!UICONTROL イベントデータセット]**&#x200B;ドロップダウンリストで、先ほど作成したイベントデータセットを選択し、「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。

      ![](assets/decision-rules-context-datastream-service.png)

データストリームを保存すると、選択したデータセットの情報が自動的に取得されてエクスペリエンス決定に統合され、通常は約 24 時間以内に使用可能になります。

Adobe Experience Platform の操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

* [エクスペリエンスデータモデル（XDM）スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [データセット](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview){target="_blank"}
