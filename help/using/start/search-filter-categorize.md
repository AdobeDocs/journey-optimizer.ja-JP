---
solution: Journey Optimizer
product: journey optimizer
title: 検索、フィルター、整理
description: Journey Optimizer のユーザーインターフェイスの詳細情報
feature: Overview
topic: Content Management
role: User
level: Intermediate
source-git-commit: b5fa17bfc888236994e73474c35b1aaafcda3ebe
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 100%

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

Adobe Experience Platform [統合タグ](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/overview.html?lang=ja)を使用すると、Journey Optimizer のジャーニーやキャンペーンを簡単に分類し、リストからの検索を改善できます。

>[!AVAILABILITY]
>
>統合タグは現在ベータ版です。 ドキュメントと機能は変更される場合があります。

### オブジェクトへのタグの追加

「**タグ**」フィールドを使用すると、[ジャーニー](../building-journeys/journey-gs.md#change-properties)プロパティまたは[キャンペーン](../campaigns/create-campaign.md#create)プロパティでオブジェクトのタグを定義できます。既存のタグを選択することも、新しいタグを作成することもできます。

目的のタグ名の入力を開始し、リストから選択します。 使用できない場合は、「**作成**」をクリックして、新しいタグを作成し、オブジェクトに追加します。必要な数だけタグを定義できます。

![](assets/tags1.png)

定義したタグのリストは、「**タグ**」フィールドの下に表示されます。

>[!NOTE]
>
> タグでは大文字と小文字が区別されます
> 
> ジャーニーやキャンペーンの新しいバージョンを複製または作成した場合、タグは保持されます。

### タグに対するフィルター

ジャーニーリストおよびキャンペーンリストに専用の列が表示されるので、タグを簡単に視覚化できます。

また、フィルターは、特定のタグを持つジャーニーまたはキャンペーンのみを表示する場合にも使用できます。

![](assets/tags2.png)

任意のタイプのジャーニーまたはキャンペーン（ライブ、ドラフトなど）のタグを追加または削除できます。これを行うには、オブジェクトの横にある「**その他のアクション**」アイコンをクリックし、「**タグを編集**」を選択します。

![](assets/tags3.png)

### タグの管理

管理者は、「**管理**」の下の&#x200B;**タグ**&#x200B;メニューを使用して、タグを削除し、カテゴリ別に整理できます。タグの管理について詳しくは、[統合タグのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/administrative-tags/ui/managing-tags.html?lang=ja)を参照してください。

>[!NOTE]
>
> Journey Optimizer の「**[!UICONTROL タグ]**」フィールドから直接作成されたタグは、組み込みの「未分類」カテゴリに自動的に追加されます。
