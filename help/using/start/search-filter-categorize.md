---
solution: Journey Optimizer
product: journey optimizer
title: 検索、フィルター、整理
description: Journey Optimizer のユーザーインターフェイスの詳細情報
feature: Overview, Get Started
topic: Content Management
role: User
level: Intermediate
exl-id: 6151aea2-6a34-4000-ba48-161efe4d94d7
source-git-commit: f9f2cd339680d0dbff1812e64c5082ca97a34771
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 82%

---

# 検索、フィルター、整理 {#search-filter-organize}

## 検索{#unified-search}

Adobe Journey Optimizer インターフェイスのどこからでも、上部バーの中央にある Adobe Experience Cloud 統合検索機能を使用して、サンドボックスをまたいでアセット、ジャーニー、データセットなどを検索できます。

コンテンツの入力を開始すると、上位の結果が表示されます。入力したキーワードに関するヘルプ記事も結果に表示されます。

![](assets/unified-search.png)

**Enter** キーを押すと、すべての結果にアクセスでき、ビジネスオブジェクトでフィルタリングできます。

![](assets/search-and-filter.png)

## フィルターリスト{#filter-lists}

ほとんどのリストでは、検索バーを使用して特定の項目を検索し、フィルター条件を定義します。

フィルターにアクセスするには、リストの左上にあるフィルターアイコンをクリックします。フィルターメニューを使用すると、様々な条件に従って表示される要素をフィルタリングできます。特定のタイプまたはステータスの要素、自分で作成した要素、過去 30 日間に変更された要素のみを表示するように選択できます。オプションはコンテキストによって異なります。

さらに、統合タグを使用して、オブジェクトに割り当てられたタグに応じてリストをフィルタリングできます。現時点では、ジャーニーとキャンペーンにタグを使用できます。[タグの操作方法については、こちらを参照してください](#tags)

>[!NOTE]
>
>表示される列は、リストの右上にある設定ボタンを使用してパーソナライズできます。パーソナライズ設定は、各ユーザーに対して個別に保存されます。

リストで、各要素に対して基本的な操作を実行できます。例えば、項目の複製や削除が可能です。

![](assets/journey4.png)

## 統合タグの操作 {#tags}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_tags"
>title="タグ"
>abstract="このフィールドを使用すると、Adobe Experience Platform 統合タグをキャンペーンに割り当てることができます。これにより、キャンペーンを簡単に分類し、キャンペーンリストからの検索を改善できます。"

Adobe Experience Platform[ 統合タグ ](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/overview.html?lang=ja) を使用すると、Journey Optimizer オブジェクトを簡単に分類し、リストからの検索を改善できます。

![](../rn/assets/do-not-localize/campaigns-tag.gif)

Journey Optimizerでオーディエンスに意味のあるタグを追加すると、後でフィルタリングおよび検索して、オーディエンスをより簡単に見つけることができます。 さらに、タグを使用して、オーディエンスを関連性の高い検索可能なフォルダーに整理し、パーソナライズされたオファーとエクスペリエンスを作成し、エクスペリエンス決定ルールで使用することもできます。

### オブジェクトへのタグの追加 {#add-tags}

「**[!UICONTROL タグ]**」フィールドでは、オブジェクトのタグを定義できます。タグは、次のオブジェクトで使用できます。

* [キャンペーン](../campaigns/create-campaign.md#create)
* [決定項目](../experience-decisioning/items.md)
* [フラグメント](../content-management/fragments.md)
* [ジャーニー](../building-journeys/journey-properties.md)
* [ランディングページ](../landing-pages/create-lp.md)
* [サブスクリプションリスト](../landing-pages/subscription-list.md)
* [テンプレート](../content-management/content-templates.md)

既存のタグを選択することも、新しいタグを作成することもできます。これを行うには、以下の手順に従います。

1. 目的のタグの名前を入力するか、リストからタグを選択します。

   ![](assets/tags1.png)

   >[!NOTE]
   >
   > タグでは大文字と小文字が区別されません。

1. 検索中のタグが使用できない場合は、「**[!UICONTROL 作成」「」]** をクリックして新しいタグを定義します。このタグは現在のオブジェクトに自動的に追加され、他のすべてのオブジェクトで使用できるようになります。

   ![](assets/tags4.png)

1. 選択または作成したタグのリストが、「**[!UICONTROL タグ]**」フィールドの下に表示されます。必要な数だけタグを定義できます。

>[!NOTE]
> 
> オブジェクトの新しいバージョンを複製または作成した場合、タグは保持されます。

### タグに関するフィルタリング {#filter-on-tags}

各オブジェクトリストには専用の列が表示されるので、タグを簡単に視覚化できます。

また、フィルターは、特定のタグを持つオブジェクトのみを表示する場合にも使用できます。

![](assets/tags2.png)

任意のタイプのジャーニーまたはキャンペーン（ライブ、ドラフトなど）のタグを追加または削除できます。これを行うには、オブジェクトの横にある「**[!UICONTROL その他のアクション]**」アイコンをクリックし、「**[!UICONTROL タグを編集]**」を選択します。

![](assets/tags3.png)

### タグの管理 {#manage-tags}

管理者は、「**[!UICONTROL 管理]**」の下の&#x200B;**[!UICONTROL タグ]**&#x200B;メニューを使用して、タグを削除し、カテゴリ別に整理できます。タグの管理について詳しくは、[統合タグのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/ui/managing-tags.html?lang=ja)を参照してください。

>[!NOTE]
>
> Journey Optimizer の「**[!UICONTROL タグ]**」フィールドから直接作成されたタグは、組み込みの「未分類」カテゴリに自動的に追加されます。
