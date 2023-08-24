---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツアシスタントを使用したタイトルの生成
description: コンテンツアシスタントの概要
feature: Overview
topic: Content Management
role: User
level: Beginner
badge: label="ベータ版" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: 76eafb06b43d2964c4e85d1f77d35750f93eee0c
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 5%

---

# コンテンツアシスタントを使用したタイトルの生成 {#title-content-assistant}

>[!BEGINSHADEBOX]

**目次**

* [コンテンツアシスタントの基本を学ぶ](gs-generative.md)
* **[コンテンツアシスタントでテキストを生成する](generative-title.md)**
* [コンテンツアシスタントで画像を生成する](generative-image.md)

>[!ENDSHADEBOX]


メッセージを作成し、パーソナライズしたら、コンテンツアシスタントを使用してコンテンツを次のレベルに移動します。

コンテンツアシスタントを利用すると、様々なメインタイトルを試すことで、メッセージの影響を最適化できます。 各バリアントは独自の治療と見なされ、どのタイトルがより効果的にクリックを生み出すかを測定および比較します。

この例では、コンテンツ実験を使用して魅力的なプッシュ通知を送信する方法を説明します。 次の手順に従います。

1. メッセージを作成し、コンテンツ実験を追加します。 コンテンツ実験について詳しくは、 [この節](../campaigns/content-experiment.md)

1. キャンペーンと実験を設定したら、 **[!UICONTROL コンテンツを作成]** 必要に応じて、メッセージの内容をパーソナライズします。

1. 2 番目の **[!UICONTROL 治療]**」をクリックし、生成アシスタントを使用して「タイトル」を変更します。

   の横に **[!UICONTROL ヘッダー]** 「 」フィールドで、「 **[!UICONTROL テキスト生成アシスタントで編集]**.

   ![](assets/gen-ai-title-1.png)

1. 次から： **[!UICONTROL ユーザーアクション]** メニューで、 **[!UICONTROL テキストの絞り込み]**:

   * **[!UICONTROL 要約]**：このオプションを使用して、テキストを短くし、必須要素を維持します。

   * **[!UICONTROL 詳細]**：コンテンツアシスタントで追加のクリエイティブのバリアントでコンテンツを拡張するには、このオプションを使用します。

   ![](assets/gen-ai-title-2.png)

1. 次を使用してバリアントのトーンを選択 **[!UICONTROL 音声のトーンを変更]** メニュー。

1. 次から： **[!UICONTROL フリーフォーム]** メニューを使用すると、結果をより微調整するためのプロンプトを表示することもできます。

   ![](assets/gen-ai-title-3.png)

1. 適切なバリアントが見つかったら、「 **[!UICONTROL ユーザーバリアント]** その後 **[!UICONTROL 適用]**.

   ![](assets/gen-ai-title-4.png)

1. メッセージコンテンツを定義したら、 **[!UICONTROL コンテンツをシミュレート]** ボタンを使用してレンダリングを制御し、テストプロファイルでパーソナライゼーション設定を確認します。 [詳細情報](../email/preview.md)

1. コンテンツ実験の準備が整ったら、キャンペーンの概要ページで、「 **[!UICONTROL 有効化するレビュー]** ：キャンペーンの概要を表示します。 パラメーターが正しくない、または見つからない場合は、警告が表示されます。

1. キャンペーンを開始する前に、すべての設定が正しいことを再確認し、「 」をクリックします。 **[!UICONTROL 有効化]**.

実験とキャンペーンが正常に設定されたら、キャンペーンレポートでキャンペーンをトラッキングできます。 [詳細情報](../reports/campaign-global-report.md#experimentation-report)
