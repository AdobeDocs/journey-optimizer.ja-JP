---
solution: Journey Optimizer
product: journey optimizer
title: 最初のコンポジションワークフローの作成
description: コンポジションワークフローを作成して、既存のオーディエンスを組み合わせて配置する方法を説明します。
feature: Journeys
topic: Content Management
role: User
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 8b978900-fcef-46f2-bc19-70776e4f3d43
badge: label="Beta" type="Informative"
source-git-commit: 818c3ff2d159ec3a668c55224996b4736f950e5d
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 100%

---

# 最初のコンポジションワークフローの作成 {#create-compositions}

>[!BEGINSHADEBOX]

このドキュメントの内容は次のとおりです。

* [オーディエンスコンポジションの基本を学ぶ](get-started-audience-orchestration.md)
* **[最初のコンポジションワークフローの作成](create-compositions.md)**
* [コンポジションキャンバスの操作](composition-canvas.md)
* [オーディエンスへのアクセスと管理](access-audiences.md)

>[!ENDSHADEBOX]

## コンポジションワークフローの作成 {#create}

コンポジションワークフローを作成するには、次の手順に従います。

1. **[!UICONTROL セグメント]**&#x200B;メニューにアクセスし、「**[!UICONTROL オーディエンスを作成]**」を選択します。

1. 「**[!UICONTROL オーディエンスを作成]**」を選択します。

   ![](assets/audiences-create.png)

   >[!NOTE]
   >
   >**[!UICONTROL ルールを作成]**&#x200B;の作成方法を使用すると、[セグメント化サービス](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=ja)を使用して新しいセグメント定義を作成できます。

1. コンポジションキャンバスには、次の 2 つのデフォルトアクティビティが表示されます。

   * **[!UICONTROL オーディエンス]**：コンポジションの出発点。このアクティビティを使用すると、ワークフローの基礎として 1 つ以上のオーディエンスを選択できます。

   * **[!UICONTROL 保存]**：コンポジションの最後の手順。このアクティビティを使用すると、ワークフローの結果を新しいオーディエンスに保存できます。
   コンポジションワークフローキャンバスでアクティビティを設定する方法について詳しくは、[コンポジションキャンバスの操作](composition-canvas.md)を参照してください。

1. コンポジションプロパティを開き、タイトルと説明を指定します。

   プロパティでタイトルが定義されていない場合、コンポジションのラベルが「コンポジション」に設定された後に、作成日時が続きます。

   ![](assets/audiences-properties.png)

1. **[!UICONTROL オーディエンス]**&#x200B;アクティビティおよび&#x200B;**[!UICONTROL 保存]**&#x200B;アクティビティの間に必要な数のアクティビティを追加して、コンポジションを設定します。[コンポジションキャンバスの操作方法を学ぶ](composition-canvas.md)

   ![](assets/audiences-publish.png)

1. コンポジションの準備ができたら、「**[!UICONTROL 公開]**」ボタンをクリックして、コンポジションを公開し、結果のオーディエンスを Adobe Experience Platform に保存します。

   >[!IMPORTANT]
   >
   >特定のサンドボックス内で最大 75 個のコンポジションを公開できます。このしきい値に達した場合、新しいコンポジションを公開するためには、コンポジションを削除してスペースを解放する必要があります。

   公開中にエラーが発生した場合は、問題の解決方法に関する情報と共にアラートが表示されます。

   ![](assets/audiences-alerts.png)

1. コンポジションが公開されます。 結果オーディエンスは、Adobe Experience Platform に保存され、Journey Optimizer キャンペーンでターゲットにする準備が整います。[キャンペーンとの連携方法を学ぶ](../campaigns/get-started-with-campaigns.md)

## コンポジションへのアクセス {#access}

>[!CONTEXTUALHELP]
>id="ajo_ao_publish"
>title="オーディエンスの公開"
>abstract="コンポジションを公開して、結果のオーディエンスを Adobe Experience Platform に保存します。"

「**[!UICONTROL コンポジション]**」タブから作成したすべてのコンポジションにアクセスできます。複数のステータスがあります。

* **[!UICONTROL ドラフト]**：コンポジションは進行中で、公開されていません。
* **[!UICONTROL 公開済み]**：コンポジションが公開され、結果オーディエンスが保存され、使用できるようになりました。
* **[!UICONTROL アーカイブ済み]**：コンポジションはアーカイブされています。

![](assets/audiences-compositions.png)

>[!NOTE]
>
>既存のコンポジションは、リストの省略記号ボタンを使用して、いつでも複製または削除できます。
