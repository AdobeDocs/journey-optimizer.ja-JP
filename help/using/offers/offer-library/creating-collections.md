---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: コレクションを作成
description: コレクションを使用してオファーを整理する方法を説明します
badge: label="レガシー" type="Informative"
feature: Decision Management, Collections
topic: Integrations
role: User
level: Intermediate
exl-id: 0c8808e3-9148-4a33-9fd5-9218e02c2dfd
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/7IXZss-Qpg5D67uPfkFbo3Gmp1n2gdSD24Y4rbL3-Fk
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 0%

---

# コレクションを作成 {#create-collections}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

>[!CONTEXTUALHELP]
>id="ajo_decisioning_decision_collection"
>title="オファーコレクションについて"
>abstract="オファーコレクションを使用すると、オファーを任意のカテゴリにグループ化して整理できます。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_collection_dynamic"
>title="動的コレクション"
>abstract="コレクション修飾子を使用して、コレクションのオファーを動的に修飾します。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_collection_static"
>title="静的コレクション"
>abstract="ステータス、コレクション修飾子、日付、チャネルなどの基準を使用して、オファーを手動で選択し、グループ化します。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_collection_static_select"
>title="静的コレクションのプレビュー"
>abstract="静的コレクションは、コレクションに含める個々のオファーを手動で選択することによって作成されます。 コレクションは、手動で追加のオファーを追加することによってのみ更新できます。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_collection_dynamic_select"
>title="動的コレクションのプレビュー"
>abstract="動的コレクションは、コレクション修飾子に基づいてオファーを収集します。 これらのコレクションは自動的に更新されます。 例えば、「sports」コレクション修飾子を使用して新しいオファーを作成すると、対応するコレクションに自動的に追加されます。"

コレクションを使用すると、オファーを任意のカテゴリにグループ化して整理できます。 例えば、スポーツ関連のオファーのみを含む「スポーツ」コレクションを作成できます。

➡️ [この機能をビデオで見つける](#video)

オファーコレクションのリストには、**[!UICONTROL オファー]** メニューからアクセスできます。

![](../assets/collections_list.png)

2種類のコレクションを作成できます。

* **動的コレクション**&#x200B;は、コレクション修飾子（旧称「タグ」）に基づくオファーのコレクションです。 これらのコレクションは自動的に更新されます。 例えば、選択したコレクション修飾子を使用して新しいオファーが作成された場合、そのオファーは自動的にコレクションに追加されます。

* **静的コレクション**&#x200B;は、コレクションに含める個別のオファーを手動で選択して作成されたコレクションです。 コレクションは、手動で追加のオファーを追加することによってのみ更新できます。

コレクションを作成するには、次の手順に従います。

1. 「**[!UICONTROL コレクション]**」タブに移動し、「**[!UICONTROL コレクションを作成]**」をクリックします。

1. 作成するコレクションの名前とタイプを指定します。

   ![](../assets/collection_create.png)

1. 動的コレクションを作成するには、左側のペインを使用して、コレクションに追加するオファーのコレクション修飾子を選択し、**[!UICONTROL 保存]**&#x200B;をクリックします。 選択したコレクション修飾子を含むすべてのオファーがコレクションに保存されます。

   コレクション修飾子の作成について詳しくは、[ コレクション修飾子の作成](../offer-library/creating-tags.md)を参照してください。

   ![](../assets/dynamic_collection.png)

1. 静的コレクションを作成するには、左側のペインを使用してオファーのリスト（ステータス、コレクション修飾子、日付、チャネル、コンテンツタイプ）をフィルタリングし、コレクションに追加するオファーを選択します。

   ![](../assets/static_collection.png)

   >[!NOTE]
   >
   >静的コレクションは自動的には更新されません。 静的コレクションにオファーを追加するには、そのコレクションを編集し、手動で追加する必要があります。

1. カスタムまたはコアのデータ使用ラベルを静的コレクションに割り当てるには、**[!UICONTROL アクセスの管理]**&#x200B;を選択します。 [ オブジェクトレベルのアクセス制御（OLAC）について詳しく見る](../../administration/object-based-access.md)

   >[!NOTE]
   >
   >動的コレクションでは、OLACの使用は使用できません。 オファーレベルで管理する必要があります。 したがって、これらのオファーのいずれかにアクセスできない場合、動的コレクションにオファーが表示されない可能性があります。

1. コレクションを作成すると、リストに表示されます。 選択して編集または削除できます。

   ![](../assets/collection_created.png)

## チュートリアルビデオ {#video}

>[!VIDEO](https://video.tv.adobe.com/v/329376?quality=12)


