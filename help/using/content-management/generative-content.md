---
solution: Journey Optimizer
product: journey optimizer
title: コンテンツアシスタントを使用したコンテンツの生成
description: コンテンツアシスタント入門
feature: Overview
topic: Content Management
role: User
level: Beginner
badge: label="Beta" type="Informative"
hide: true
hidefromtoc: true
source-git-commit: 32dd999f18bf3ddb3e073631f6d117238dc46c12
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 58%

---

# コンテンツアシスタントを使用したコンテンツの生成 {#title-content-assistant}

>[!BEGINSHADEBOX]

**目次**

* [コンテンツアシスタント入門](gs-generative.md)
* **[コンテンツアシスタントでコンテンツを生成](generative-content.md)**
* [コンテンツアシスタントを使用した画像の生成](generative-image.md)

>[!ENDSHADEBOX]

メッセージを作成してパーソナライズしたら、コンテンツアシスタントを使用してコンテンツを次のレベルに引き上げます。

コンテンツアシスタントを利用すると、別のコンテンツを試すことで、メッセージの影響を最適化できます。 各バリアントは独自の治療と見なされ、どのコンテンツがより効果的にクリックを生み出すかを測定および比較します。

この例では、コンテンツ実験を使用して魅力的なプッシュ通知を送信する方法を説明します。次の手順に従います。

1. プッシュ通知キャンペーンを作成して設定したら、 **[!UICONTROL コンテンツを作成]**.

1. 生成アシスタントを使用して **[!UICONTROL タイトル]**.

   「**[!UICONTROL ヘッダー]**」フィールドの横にある「**[!UICONTROL テキスト生成アシスタントを使用して編集]**」をクリックします。

   ![](assets/gen-ai-title-1.png)

1. **[!UICONTROL ユーザーアクション]**&#x200B;メニューで、「**[!UICONTROL テキストの絞り込み]**」を選択します。

   * **[!UICONTROL 要約]**：このオプションを使用すると、テキストを短くし、要旨を残します。

   * **[!UICONTROL 詳細]**：このオプションを使用すると、コンテンツアシスタントからクリエイティブなバリエーションを追加して、コンテンツを拡充します。

   ![](assets/gen-ai-title-2.png)

1. **[!UICONTROL 口調を変更]**&#x200B;メニューでバリエーションの口調を選択します。

1. **[!UICONTROL フリーフォーム]**&#x200B;メニューから、結果をより細かく調整するためのプロンプトを提供することも選択できます。

   ![](assets/gen-ai-title-3.png)

1. 適切なバリエーションが見つかったら、「**[!UICONTROL ユーザーバリアント]**」をクリックして「**[!UICONTROL 適用]**」をクリックします。

   ![](assets/gen-ai-title-4.png)

1. をパーソナライズした後 **[!UICONTROL 本文]** プッシュ通知の「 」を選択します。 **[!UICONTROL コンテンツアシスタントを表示]**.

   ここでは、元のコンテンツで既にバリエーションのリストを使用できます。

   ![](assets/gen-ai-title-5.png)

1. 生成する内容を記述して、コンテンツを微調整します。

   を有効にします。 **[!UICONTROL 現在のコンテンツで拡張]** オプションを使用します。

1. クリック **[!UICONTROL 置換]** コンテンツを変更するか、複数の **[!UICONTROL バリアント]** を作成します。 **[!UICONTROL トリートメント]** 実験用に」を選択し、 **X 処理を追加**.

   ![](assets/gen-ai-title-6.png)

1. 次にアクセス： **[!UICONTROL 実験設定]** または **[!UICONTROL アクション]** メニューを使用して、Experiment をさらにパーソナライズします。 [詳細情報](../campaigns/content-experiment.md)

   ![](assets/gen-ai-title-7.png)

1. メッセージの内容を定義したら、「**[!UICONTROL コンテンツをシミュレート]**」ボタンをクリックしてレンダリングを制御し、テストプロファイルでパーソナライゼーション設定を確認します。[詳細情報](../email/preview.md)

1. コンテンツ実験の準備が整ったら、キャンペーンの概要ページで「**[!UICONTROL アクティブ化のレビュー]**」をクリックして、キャンペーンの概要を表示できます。パラメーターが正しくない、または見つからない場合は、警告が表示されます。

1. キャンペーンを開始する前に、すべての設定が正しいことを再確認し、「**[!UICONTROL アクティブ化]**」をクリックします。

実験とキャンペーンを正常に設定したら、キャンペーンレポートを使用してキャンペーンをトラッキングできます。[詳細情報](../reports/campaign-global-report.md#experimentation-report)
