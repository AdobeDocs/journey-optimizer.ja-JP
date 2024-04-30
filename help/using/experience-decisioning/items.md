---
title: 決定項目
description: 決定項目の操作方法を学ぶ
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
hide: true
hidefromtoc: true
badge: label="ベータ版"
exl-id: 5c866814-d79a-4a49-bfcb-7a767d802e90
source-git-commit: 50d3be8fb8ae04e1cab747f6ba4b1024c5e3ec97
workflow-type: ht
source-wordcount: '1039'
ht-degree: 100%

---

# 決定項目 {#items}

>[!CONTEXTUALHELP]
>id="ajo_exd_items"
>title="決定項目を管理"
>abstract="Journey Optimizer では、決定項目と呼ばれるマーケティングオファーを作成し、一元化されたカタログとコレクションを作成して整理できます。現在、作成されたすべての決定項目は、単一の「オファー」カタログ内に統合されます。この画面から、「**スキーマを編集**」ボタンを使用してカタログのスキーマにアクセスし、決定項目のカスタム属性を作成することもできます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/decision-items/catalogs.html?lang=ja" text="項目カタログを設定"

>[!BEGINSHADEBOX 「このドキュメントガイドの内容は次のとおりです」]

* [エクスペリエンス決定の基本を学ぶ](gs-experience-decisioning.md)
* 決定項目の管理：[項目カタログの設定](catalogs.md) - **[決定項目の作成](items.md)** - [項目コレクションの管理](collections.md)
* 項目の選択の設定：[決定ルールの作成](rules.md) - [ランキングメソッドの作成](ranking.md)
* [選択戦略の作成](selection-strategies.md)
* [決定ポリシーを作成](create-decision.md)

>[!ENDSHADEBOX]

Journey Optimizer では、決定項目と呼ばれるマーケティングオファーを作成し、一元化されたカタログとコレクションを作成して整理できます。これらは、ニーズに正確に合わせて設計された標準属性とカスタム属性で構成されています。さらに、決定項目を表示可能なユーザーを定義できる、プロファイル制約が組み込まれています。

決定項目を表示する対象を決定する条件を設定する場合は、決定項目を作成する前に、必ず&#x200B;**決定ルール**&#x200B;を作成してください。[決定ルールを作成する方法を学ぶ](rules.md)。

## 最初の決定項目を作成

>[!CONTEXTUALHELP]
>id="ajo_exd_item_priority"
>title="決定項目の優先度を定義"
>abstract="プロファイルが複数の項目に該当する場合、優先度によって、この決定項目を他の項目と比較できるようになります。優先度が高い項目は、他の項目よりも優先されます。"

>[!CONTEXTUALHELP]
>id="ajo_exd_item_custom_attributes"
>title="カスタム属性を定義"
>abstract="カスタム属性は、ニーズに合わせて調整された特定の属性で、決定項目に割り当てることができます。これらは、決定項目のカタログスキーマで作成されます。このセクションは、カタログスキーマに少なくとも 1 つのカスタム属性を追加した場合にのみ表示されます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/decision-items/catalogs.html?lang=ja" text="項目カタログを設定"

>[!CONTEXTUALHELP]
>id="ajo_exd_item_constraints"
>title="オーディエンスまたは決定ルールを追加"
>abstract="デフォルトでは、すべてのプロファイルが決定項目を受け取る資格を持ちますが、オーディエンスまたはルールを使用すると、項目を特定のプロファイルのみに制限できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences.html?lang=ja" text="オーディエンスを使用"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/experience-decisioning/selection/rules.html?lang=ja" text="決定ルールを使用"

決定項目を作成するには、次の手順に従います。

1. **[!UICONTROL エクスペリエンス決定]**／**[!UICONTROL 項目]**&#x200B;に移動します。

1. 決定項目の標準属性を定義します。

   1. 名前と説明を入力します。
   1. 開始日と終了日を指定します。項目は、これらの日付内の決定エンジンによってのみ検討されます。
   1. プロファイルが複数の項目に該当する場合は、他の決定項目と比較した決定項目の「**[!UICONTROL 優先度]**」を設定します。優先度が高いと、その項目は他の項目よりも優先されます。
   1. 「**タグ**」フィールドを使用すると、Adobe Experience Platform 統合タグを決定項目に割り当てることができます。これにより、簡単に分類し、検索を改善できます。[タグの操作方法について詳しくは、こちらを参照してください](../start/search-filter-categorize.md#tags)

   ![](assets/item-attributes.png)

   >[!NOTE]
   >
   >優先度は、整数データタイプです。整数データタイプであるすべての属性には、整数値（小数は含まない）を含める必要があります。

1. カスタム属性は、ニーズに合わせて調整された特定の属性で、決定項目に割り当てることができます。これらは、決定項目のカタログスキーマで定義されます。[カタログの操作方法を学ぶ](catalogs.md)

1. 決定項目の属性を定義したら、「**[!UICONTROL 次へ]**」をクリックして、項目のプロファイル制約を設定します。

   デフォルトでは、すべてのプロファイルが決定項目を受け取る資格を持ちますが、オーディエンスまたはルールを使用すると、項目を特定のプロファイルに制限できます。どちらのソリューションも様々な用途に対応します。詳しくは、以下の節を展開してください。

   +++オーディエンスと決定ルールの使用上の違い

   基本的に、オーディエンスの出力はプロファイルのリストです。一方、決定ルールは、決定プロセス中に単一プロファイルに対してオンデマンドで実行される関数です。

   * **オーディエンス**：オーディエンスは、プロファイル属性とエクスペリエンスイベントに基づく特定のロジックに一致する Adobe Experience Platform プロファイルのグループです。ただし、オファー管理ではオーディエンスの再計算は行われないので、オファーを提示する際にオーディエンスが最新でない可能性があります。

   * **決定ルール**：一方、決定ルールは、Adobe Experience Platform で使用可能なデータに基づいており、オファーを誰に表示できるかを決定します。特定のプレースメントのオファーまたは決定でルールが選択されると、決定が行われるたびにそのルールが実行されるので、各プロファイルが最新かつ最適なオファーを確実に取得できます。

+++

   ![](assets/item-constraints.png)

   * 決定項目の表示を 1 つまたは複数の Adobe Experience Platform オーディエンスのメンバーに制限するには、「**[!UICONTROL 1 つまたは複数のオーディエンスに分類される訪問者]**」オプションを選択し、左側のパネルから 1 つ以上のオーディエンスを追加し、**[!UICONTROL And]**／**[!UICONTROL Or]** 論理演算子を使用して結合します。[オーディエンスに関する詳細情報](../audience/about-audiences.md)。

   * 特定の決定ルールを決定項目に関連付けるには、「**[!UICONTROL ルール別]**」を選択し、目的のルールを左側のパネルから中央の領域にドラッグします。[決定ルールに関する詳細情報](rules.md)。

   オーディエンスまたは決定ルールを選択すると、推定される認定プロファイルに関する情報が表示されます。「**[!UICONTROL 更新]**」をクリックして、データを更新します。

   >[!NOTE]
   >
   >プロファイルの予測は、ルールパラメーターにコンテキストデータなど、プロファイルに含まれていないデータが含まれている場合は使用できません。例えば、現在の気温が 80 ℃以上であることを条件とする実施要件ルールがあります。

1. 決定項目の属性を定義したら、「**[!UICONTROL 次へ]**」をクリックして、項目を確認し、保存します。

1. 決定項目が&#x200B;**[!UICONTROL ドラフト]**&#x200B;ステータスでリストに表示されます。プロファイルに表示する準備ができたら、省略記号ボタンをクリックし、「**[!UICONTROL 承認]**」を選択します。

   ![](assets/item-approve.png)

## 決定項目を管理

決定項目リストから、決定項目を編集、そのステータスの変更（**ドラフト**、**承認済み**、**アーカイブ済み**）、複製または削除を行うことができます。

決定項目を変更するには、その項目を開き、変更を加え、保存します。

決定項目を選択するか、省略記号ボタンをクリックすると、以下で説明するアクションが有効になります。

* **[!UICONTROL 承認]**：決定項目のステータスを「承認済み」に設定します。
* **[!UICONTROL 承認を取り消し]**：決定項目のステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;に戻します。
* **[!UICONTROL 複製]**：同じ属性と制約を持つ決定項目を作成します。デフォルトでは、新しい項目のステータスは&#x200B;**[!UICONTROL ドラフト]**&#x200B;になります。
* **[!UICONTROL 削除]**：決定項目をリストから削除します。

  >[!IMPORTANT]
  >
  >削除すると、決定項目とそのコンテンツにアクセスできなくなります。このアクションは取り消せません。決定項目がコレクションまたは決定で使用されている場合は、削除できません。まず、決定項目をオブジェクトから削除する必要があります。

* **[!UICONTROL アーカイブ]**：決定のステータスを&#x200B;**[!UICONTROL アーカイブ済み]**&#x200B;に設定します。決定項目は引き続きリストから利用できますが、ステータスを&#x200B;**[!UICONTROL ドラフト]**&#x200B;または&#x200B;**[!UICONTROL 承認済み]**&#x200B;に戻すことはできません。複製または削除のみ可能です。
