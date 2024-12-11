---
title: コンテンツカードのデザイン
description: コンテンツカードコンテンツのデザイン方法について説明します。
topic: Content Management
feature: Content Cards
role: User
level: Beginner
exl-id: b83bdade-7275-4eef-9c49-fc1d157cee0d
source-git-commit: 7e5dbd6106b8a5ffd9bee8b1364a7bf5b995668c
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# コンテンツカードコンテンツのデザイン {#design-content-card}

カードのオーサリング構造は、フォームベースのオーサリングエクスペリエンスを提供し、マーケターが基本入力を提供できるようにします。この入力は開発者がレンダリングするのに使用できます。

コンテンツを定義し、パーソナライズしたら、レビューしてアクティブ化できます。設定したスケジュールに従ってキャンペーンが送信されます。詳しくは、[このページ](../campaigns/review-activate-campaign.md)を参照してください。

## 「コンテンツ」タブ {#content-tab}

「**[!UICONTROL コンテンツ]**」タブから、コンテンツカードのコンテンツと「**[!UICONTROL 閉じる]**」ボタンのデザインの両方を定義して、コンテンツカードをカスタマイズできます。さらに、このタブからメディアを使用してコンテンツを拡張したり、アクションボタンを直接追加したりできます。

### 「閉じる」ボタン {#close-button}

![](assets/content-card-design-1.png)

**[!UICONTROL 「閉じる」ボタン]**&#x200B;の&#x200B;**[!UICONTROL スタイル]**&#x200B;を選択して、表示方法をカスタマイズします。

選択できるスタイルは次のとおりです。

* **[!UICONTROL なし]**
* **[!UICONTROL シンプル]**
* **[!UICONTROL 円]**

### コンテンツ {#title-body}

メッセージを作成するには、「**[!UICONTROL タイトル]**」フィールドと「**[!UICONTROL 本文]**」フィールドにテキストを入力します。

![](assets/content-card-design-2.png)

メッセージをさらにカスタマイズする場合は、**[!UICONTROL パーソナリゼーション]**&#x200B;アイコンを使用して、パーソナライズされた要素を追加します。パーソナリゼーション機能の使用方法について詳しくは、[この節](../personalization/personalize.md)を参照してください。

<!--
+++More options with advanced formatting

If the **[!UICONTROL Advanced formatting mode]** is switched on, you can choose for your **[!UICONTROL Header]** and **[!UICONTROL Body]**:

* the **[!UICONTROL Font]**
* the **[!UICONTROL Pt size]**
* the **[!UICONTROL Font Color]**
* the **[!UICONTROL Alignment]**
+++
-->

### メディア {#add-media}

「**[!UICONTROL メディア]**」フィールドを使用すると、メディアを追加してコンテンツカードを強化し、エンドユーザーにとってプレゼンテーションをより魅力的にすることができます。

![](assets/content-card-design-3.png)

メディアを含めるには、使用するメディアの URL を入力するか、**[!UICONTROL アセットを選択]**&#x200B;アイコンをクリックして、アセットライブラリに保存されているアセットから選択します。[アセット管理の詳細情報](../content-management/assets.md)。

<!--
+++More options with advanced formatting

If the **[!UICONTROL Advanced formatting mode]** is switched on, you can add an **[!UICONTROL Alternative text]** for screen reading applications and another asset in the **[!UICONTROL Dark Mode Media URL]** field.

+++
-->

### ボタン {#add-buttons}

ユーザーがコンテンツカードを操作するボタンを追加します。

![](assets/content-card-design-4.png)

1. **[!UICONTROL 「追加」ボタン]**&#x200B;をクリックして、新しいアクションボタンを作成します。

1. ボタンの「**[!UICONTROL タイトル]**」フィールドを編集して、ボタンに表示するラベルを指定します。

1. 「**[!UICONTROL インタラクトイベント]**」を選択して、ユーザーがボタンをクリックまたは操作したときにトリガーされるアクションを定義します。

1. 「**[!UICONTROL ターゲット]**」フィールドに、ユーザーがボタンを操作した後に遷移する web URL またはディープリンクを入力します。

<!--
+++More options with advanced formatting

If the **[!UICONTROL Advanced formatting mode]** is switched on, you can choose for your **[!UICONTROL Buttons]**:

* the **[!UICONTROL Font]**
* the **[!UICONTROL Pt size]**
* the **[!UICONTROL Font Color]**
* the **[!UICONTROL Alignment]**

+++
-->

### クリック時の動作

![](assets/content-card-design-5.png)

「**[!UICONTROL ターゲット URL]**」フィールドに、コンテンツカードとのやり取りの後でユーザーを目的の宛先に誘導する web URL またはディープリンクを入力します。これは、外部 web サイト、アプリ内の特定のページ、またはユーザーのインタラクションに基づいてユーザーを誘導するその他の場所です。

## 「データ」タブ

## カスタムデータ {#custom-data}

![](assets/content-card-design-6.png)

**[!UICONTROL カスタムデータ]**&#x200B;セクションで、「**[!UICONTROL キーと値のペアを追加]**」をクリックして、ペイロードにカスタム変数を含めます。これらのキーと値のペアを使用すると、特定の設定に応じて、追加のデータを渡すことができます。これにより、パーソナライズされたコンテンツ、動的コンテンツ、トラッキング情報または設定に関連するその他のデータを追加できます。
