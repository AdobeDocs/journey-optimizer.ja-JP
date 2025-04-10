---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーレポート
description: ジャーニーレポートからアプリ内データを使用する方法について説明します
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: f10b3ab9-db0a-4759-98e4-2ac1988eb8c4
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 87%

---

# アプリ内ジャーニーレポート {#journey-global-report}

>[!INFO]
>
>ユーザーは一度に複数のジャーニーに関与する可能性があるので、ジャーニーレポートには複数のジャーニーの情報が同時に表示される場合があります。その結果、同時にアクティブなジャーニーに参加しているユーザーに対してインバウンド通信（アプリ内、web およびコードベース）をトリガーした場合、複数のジャーニーに表示される場合があり、データが重複する可能性があります。

>[!BEGINSHADEBOX]

ジャーニー内の「**[!UICONTROL レポート]**」ボタンをクリックして、アプリ内ジャーニーレポートにアクセスできます。 [詳細情報](report-gs-cja.md)

![](assets/report-access.png)

>[!ENDSHADEBOX]

## 表示してクリックのトレンド {#display-click-trend}

![](assets/cja-inapp-impressions-click.png)

**[!UICONTROL 表示とクリックのトレンド]** グラフは、プロファイルのアプリ内メッセージへのエンゲージメントに関する詳細な分析を表示し、プロファイルがコンテンツとどのようにやり取りするかについての貴重なインサイトを提供します。

+++ 詳しくは、ディスプレイとクリックのトレンド指標を参照してください

* **[!UICONTROL クリック数]**：アプリ内メッセージでコンテンツがクリックされた回数。

* **[!UICONTROL 表示数]**：メッセージが開封された回数。

+++

## クリック数 {#clicks-inapp}

**[!UICONTROL クリック数]**&#x200B;のグラフには、アプリ内クリック指標と、コンテンツのクリック総数と、コンテンツをクリックした固有のプロファイル数の両方が表示されます。

+++ クリック数指標の詳細

* **[!UICONTROL ユニーククリック数]**：アプリ内メッセージでコンテンツをクリックしたプロファイルの数。

* **[!UICONTROL クリック数]**：アプリ内メッセージでコンテンツがクリックされた回数。

+++

## 表示 {#display-inapp}

**[!UICONTROL 表示数]**&#x200B;グラフは、メッセージの全体的なリーチと、メッセージに対して何らかのインタラクションを行ったユニークプロファイルの数の両方を理解するのに役立ちます。

+++ 表示指標の詳細

* **[!UICONTROL 表示数]**：メッセージが開封された回数。

* **[!UICONTROL ユニーク表示数]**：メッセージが開封された回数。1 つのプロファイルによる複数回のインタラクションは考慮されません。

+++

## トラッキングデータ {#tracking-data-inapp}

**[!UICONTROL プッシュ - トラッキング統計]**&#x200B;のテーブルには、アプリ内メッセージと結びつけられたプロファイルアクティビティの詳細なスナップショットが表示され、エンゲージメントとアプリ内メッセージの効果に関する重要なインサイトを得ることができます。

+++ トラッキングデータ指標の詳細情報

* **[!UICONTROL 人物]**：アプリ内メッセージのターゲットプロファイルに適格な、ユーザープロファイルの数。

* **[!UICONTROL クリックスルー率（CTR）]**：アプリ内メッセージに対して何らかのアクションを起こしたユーザーの割合。

* **[!UICONTROL クリックスルー開封率（CTOR）]**：アプリ内メッセージが開封された回数。

* **[!UICONTROL クリック数]**：アプリ内メッセージでコンテンツがクリックされた回数。

* **[!UICONTROL ユニーククリック数]**：アプリ内メッセージでコンテンツをクリックしたプロファイルの数。

* **[!UICONTROL 表示数]**：メッセージが開封された回数。

* **[!UICONTROL ユニーク表示数]**：メッセージが開封された回数。1 つのプロファイルによる複数回のインタラクションは考慮されません。。

* **[!UICONTROL 送信数]**：アプリ内メッセージ用の送信の合計数。

* **[!UICONTROL インバウンドトリガー済み]**：ユーザーのインタラクションまたは定義済みイベントによってアプリ内メッセージがトリガーされた回数。

* **[!UICONTROL インバウンド解除数]**：ユーザーがアプリ内メッセージで操作を行わずに解除した回数。

+++

## トラッキング対象リンクラベル {#track-link-label-inapp}

![](assets/cja-inapp-tracked-link-labels.png)

**[!UICONTROL トラッキング対象リンクラベル]**&#x200B;テーブルでは、アプリ内メッセージ内のリンクラベルの包括的な概要を確認できます。最も多くの訪問者トラフィックを生成するリンクラベルはハイライト表示されます。この機能を使用すると、最も人気のあるリンクを識別し、優先順位を付けることができます。

+++ トラッキングされるリンクラベルの指標の詳細

* **[!UICONTROL ユニーククリック数]**：アプリ内メッセージのコンテンツをクリックしたプロファイルの数。

* **[!UICONTROL クリック数]**：アプリ内メッセージでコンテンツがクリックされた回数。

* **[!UICONTROL 表示数]**：メッセージが開封された回数。

* **[!UICONTROL ユニーク表示数]**：メッセージが開封された回数。1 つのプロファイルによる複数回のインタラクションは考慮されません。

+++

## トラッキング対象リンク URL {#track-link-url-inapp}

![](assets/cja-inapp-tracked-link-urls.png)

**[!UICONTROL トラッキング対象リンク URL]** のテーブルには、アプリ内メッセージ内で最も多くの訪問者トラフィックを集めている URL の包括的な概要が表示されます。これにより、最も人気のあるリンクを特定し、優先順位を付けるて、アプリ内メッセージ内の特定のコンテンツに対するプロファイルのエンゲージメントをより深く理解することができます。

+++ トラッキングされるリンク URL の指標についての詳細情報

* **[!UICONTROL ユニーククリック数]**：アプリ内メッセージでコンテンツをクリックしたプロファイルの数。

* **[!UICONTROL クリック数]**：アプリ内メッセージでコンテンツがクリックされた回数。

+++
