---
title: 電子メールプレースメントの作成
description: メールの決定ポリシーに関連付けるプレースメントを作成する方法について説明します。
feature: Decisioning
topic: Integrations
role: User
level: Experienced
source-git-commit: 29532b5ebd140f9609a29c1375ceedecf55d0dfb
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 18%

---


# プレースメントの操作 {#create-decision}

## プレースメントについて {#about}

プレースメントは、決定項目のショーケースに使用するコンテナです。 適切なオファーコンテンツがメッセージ内の適切な場所に表示されるようにします。

決定ポリシーをメールに追加する場合は、返された決定項目を表示するコンポーネントにプレースメントを関連付ける必要があります。 これにより、例えば、レポートで異なるプレースメントをまたいで決定項目のパフォーマンスを追跡できます。

プレースメントのリストには、**[!UICONTROL 戦略設定]** メニューでアクセスできます。 フィルターは、特定のチャネルサーフェスまたはタグに従ってプレースメントを取得するのに役立ちます。

![](assets/placements-list.png)

>[!NOTE]
>
>現時点では、プレースメントはメールチャネルでのみ使用できます。

## プレースメントの作成 {#create}

プレースメントを作成するには、次の手順に従います。

1. **[!UICONTROL 戦略設定]** メニューを参照し、「**[!UICONTROL メール]**」を選択して **[!UICONTROL プレースメントを作成]** ボタンをクリックします。

   決定ポリシーを追加する際に、電子メールデザイナーから直接プレースメントを作成することもできます。 [ メールコンポーネントにプレースメントを関連付ける方法を学ぶ ](../experience-decisioning/create-decision.md#save)

1. プレースメントのプロパティを定義します。

   ![](assets/placement-create.png)

   * **[!UICONTROL 名前]**：プレースメントの名前。わかりやすい名前を定義して、取得しやすくします。
   * **[!UICONTROL 説明]**：プレースメントの説明。
   * **[!UICONTROL タグ]**:Adobe Experience Platform統合タグをプレースメントに割り当てます。 これにより、簡単に分類し、検索を改善できます。[タグの操作方法について詳しくは、こちらを参照してください](../start/search-filter-categorize.md#tags)
   * **[!UICONTROL チャネル]**：プレースメントが使用されるチャネル。 現在、プレースメントはメールでのみ使用できます。
   * **[!UICONTROL チャネル設定]**：プレースメントにチャネル設定を関連付けます。 [詳しくは、チャネル設定の指定方法を参照してください](../configuration/channel-surfaces.md)。

1. 「**[!UICONTROL 作成]**」をクリックします。

プレースメントが作成されると、決定ポリシーをメールに追加する際に、プレースメント リストに表示されます。 選択してプロパティを表示し、編集できます。 [ 決定ポリシーの作成方法を学ぶ ](../experience-decisioning/create-decision.md)

![](assets/placement-list.png)
