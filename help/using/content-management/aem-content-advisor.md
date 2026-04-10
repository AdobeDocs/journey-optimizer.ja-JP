---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Manager Content Advisorへのアクセス
description: Adobe Experience Manager Content Advisorにアクセスして、Adobe Journey OptimizerのAIを利用したセマンティック検索を使用して、アセットとコンテンツフラグメントを検索する方法を説明します。
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
exl-id: 842d69e3-be7f-4a81-8161-6c6ecd571f95
source-git-commit: cc047508f06d0ac7eb4313dad125f2fe9ac3cbc7
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Adobe Experience Manager Content Advisorの操作 {#aem-content-advisor}

>[!AVAILABILITY]
>
>Adobe Experience Manager Content Advisorは、チャネルオーサリングワークフローでのみ使用できます。

Adobe Experience Manager Content Advisorは、決定論的な発見を、統一されたサーフェスからの標準化された意図に基づく発見に置き換えます。 これにより、AIを利用して、AssetsとコンテンツフラグメントをJourney Optimizerのオーサリングワークフロー内で直接発見でき、マーケターの生産性とキャンペーンの効率性を向上させることができます。

## 使用可能な機能

### Assetsの場合 {#asset-features}

Adobe Experience Manager Content Advisorには、次のアセット機能が用意されています。

+++ AI セマンティック検索

正確なキーワードやファイル名ではなく、自然言語を使用してアセットを検索できます。 「山の中のコーヒー」など、必要なものを平易な言葉で説明すると、AIはテキストの一致だけでなく、意味や内容にもとづいて文脈的に関連性の高いアセットを見つけます。

![](assets/content-advisor-2.png){zoomable="yes"}

+++

+++ 最近の検索履歴

最近検索した項目にアクセスして、キーワードとコンテキストをすばやく再利用できます。 これにより、類似の施策を展開した場合や、以前の検索内容を絞り込む必要がある場合の時間を節約できます。

![](assets/content-advisor-4.png){zoomable="yes"}

+++ 

+++ 概要をアップロード

マーケティング概要ドキュメントをアップロードすると、キャンペーンのコンテキストに沿ったアセットが自動的に表示されます。 AIが概要を分析し、ドキュメントに記載されているコンテンツと要件にもとづいて、関連アセットを提案します。

![](assets/content-advisor-5.png){zoomable="yes"}

+++

+++ アセット情報パネル

**情報** アイコンを使用して、任意のアセットの詳細なメタデータとプロパティを表示します。 これには、アセットのディメンション、ファイルサイズ、作成日、タグ、その他の関連情報が含まれ、情報にもとづいた意思決定に役立ちます。

![](assets/content-advisor-6.png){zoomable="yes"}

+++

+++ Dynamic Media パネル

リポジトリー設定にもとづいて、ダイナミックレンディション、スマート切り抜き、その場での変更にアクセスできます。

![](assets/content-advisor-1.png){zoomable="yes"}

Dynamic Media パネルでは、ダイナミックレンディション、スマート切り抜き、その場での変更にアクセスできます。 パネルに直接修飾子を入力して、カスタムレンディションを作成できます。

**対象**

Dynamic Mediaの可用性は、リポジトリ設定によって異なります。

* **Scene7**：公開されたアセットで使用できます（ビデオとPDFを除く）。 [Dynamic Media Scene7修飾子の詳細](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/r-is-http-modifiers.html){target="_blank"}

* **OpenAPI**：承認済みアセットで利用できます（ビデオを除く）。 [OpenAPI修飾子を使用したDynamic Mediaについて詳しく見る](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/image-profiles.html?lang=ja){target="_blank"}

* **Scene7とOpenAPI**：両方の設定が存在し、アセットが条件を満たす場合に使用できます。

**スタック選択**

表示されるボタンは、リポジトリ設定によって異なります。

* **Scene7 ボタンのみ**: リポジトリにはScene7設定があり、アセットはDynamic Mediaに公開されます。
* **OpenAPI ボタンのみ**: リポジトリにOpenAPI設定があり、アセットが承認されています。
* **両方のボタン**: リポジトリに設定があり、アセットが公開され、承認されています。
+++

### コンテンツフラグメント用 {#content-fragment-features}

Adobe Experience Manager Content Advisorには、次のコンテンツフラグメント機能が用意されています。

+++ テンプレート表示リスト 

サムネールビューとテーブルビューを切り替えて、ワークフローに最適な形式でコンテンツフラグメントを参照します。 サムネールビューではコンテキストが視覚的に表示され、テーブルビューでは構造化形式で詳細情報が表示されます。

![](assets/content-advisor-7.png){zoomable="yes"}

+++

+++ 情報パネル 

「**[!UICONTROL 情報]**」アイコンをクリックして、フラグメントのバリエーション、プロパティ、**[!UICONTROL 参照元]**&#x200B;の詳細を表示する右側のパネルを開きます。 「**[!UICONTROL 参照元]**」セクションには、フラグメントが使用されているすべてのAdobe Experience Manager エンティティが表示され、これらの参照をAdobe Experience Managerで直接表示するためのリンクが表示されます。

![](assets/content-advisor-8.png){zoomable="yes"}

+++

+++ Adobe Experience Managerで開く

タイトルの横にあるアイコンを使用して、Adobe Experience Managerで直接コンテンツフラグメントを開いて編集できます。 Journey OptimizerとAdobe Experience Managerの間をシームレスに連携できるため、コンテキストを失うことなく切り替えることができます。

![](assets/content-advisor-9.png){zoomable="yes"}

+++

+++ JSON プレビュー

コンテンツフラグメントのJSON構造を、わかりやすく整理された表形式でプレビューします。 これにより、フラグメントのデータ構造を理解し、キャンペーンに使用する前にコンテンツを検証できます。

![](assets/content-advisor-10.png){zoomable="yes"}

+++

## Adobe Experience Manager Content Advisorへのアクセス {#access}

Journey OptimizerでAdobe Experience Manager Content Advisorにアクセスするには、次の手順に従います。

1. Adobe Journey Optimizerでキャンペーンを作成し、電子メールなどのチャネルアクションを追加します。

1. 「**[!UICONTROL コンテンツを編集]**」をクリックし、「**[!UICONTROL メール本文を編集]**」をクリックしてコンテンツエディターを開きます。

1. HTML コンポーネントまたはテキストコンポーネントをメールコンテンツにドラッグ&amp;ドロップします。

1. コンポーネントにカーソルを合わせ、**[!UICONTROL ソースコードを表示]** （HTML コンポーネントの場合）または&#x200B;**[!UICONTROL Personalizationを追加]** （テキストコンポーネントの場合）をクリックします。

1. Personalization エディターで、コンテンツのエントリポイントを選択します。

   * アセットを追加するには、「**[!UICONTROL Assets]**」をクリックし、「**[!UICONTROL AEM Content Advisorを開く]**」をクリックします。

     ![](assets/content-advisor-11.png){zoomable="yes"}

   * Adobe Experience Manager コンテンツフラグメントを追加するには、**[!UICONTROL AEM コンテンツフラグメント]**&#x200B;をクリックし、**[!UICONTROL AEM コンテンツアドバイザーを開きます]**。

     ![](assets/content-advisor-12.png){zoomable="yes"}

1. Adobe Experience Manager リポジトリを選択します。

   ![](assets/content-advisor-13.png){zoomable="yes"}

1. 使用するアセットフラグメントまたはコンテンツフラグメントを参照して選択し、コンテンツに挿入します。
