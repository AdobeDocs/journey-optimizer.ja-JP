---
solution: Journey Optimizer
product: journey optimizer
title: ブランドの管理
description: 生成モデルの作成および管理方法について説明します
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 9ef6b02c-0a17-4b46-bcd3-8e922eef059a
source-git-commit: 7873c333cbe5002695a11d1edaaf9e15f74a6d3f
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# 生成モデルの作成と管理 {#generative-models}

組み込みモデル、カスタム Firefly モデル、サードパーティの画像生成プロバイダーを使用して AI 画像作成機能を拡張し、特定のニーズを満たし、ブランドの整合性を向上させます。

ニーズに合った適切なモデルの選択：

- Firefly Image Model 4を活用した **[!UICONTROL Adobe モデル]** は標準で提供されており、追加のセットアップを行わなくても即座に画像を生成できます。
- Gemini 2.5 Flash を活用した **[!UICONTROL パートナーモデル]** は、特定のユースケースに特化した機能を提供します。
- **[!UICONTROL カスタムモデル]** は、独自のアセットでトレーニングされ、組織が追加したブランド固有のモデルです。

  **[!UICONTROL カスタムモデル]** について詳しくは、[Adobe Firefly ドキュメントを参照してください &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html)

設定が完了したら、コンテンツで画像を作成する際に、任意の生成モデルを選択できます。 [&#x200B; 詳しくは、画像の生成を参照してください &#x200B;](generative-image.md)。

## 生成モデルの管理

生成モデルを一元的に管理します。 使用可能なすべてのモデルを表示し、特定のモデルを見つけるためにフィルタリングと検索を行い、ブランドに合わせて設定を指定します。

1. **[!UICONTROL ブランド]** メニューから、「**[!UICONTROL 生成モデル]**」タブを選択します。

   ![](assets/gen-model-manage-1.png){zoomable="yes"}

1. ![](assets/do-not-localize/Smock_Filter_18_N.svg) アイコンをクリックして、フィルターメニューにアクセスします。 **[!UICONTROL タイプ]** または **[!UICONTROL ステータス]** でモデルをフィルタリングします。

   ![](assets/gen-model-manage-2.png){zoomable="yes"}

1. 検索バーを使用して、名前で特定の生成モデルを検索します。

1. ![](assets/do-not-localize/Smock_More_18_N.svg) アイコンをクリックして詳細メニューにアクセスすると、モデルの有効化/無効化や削除を行うことができます。

   削除できるのは **[!UICONTROL カスタムモデル]** のみです。

   ![](assets/gen-model-manage-6.png){zoomable="yes"}

1. 「**[!UICONTROL モデルを追加]**」をクリックして、新しい生成モデルを最初から作成します。

コンテンツで画像を作成する際に、生成モデルを選択できるようになりました。 [&#x200B; 詳しくは、画像の生成を参照してください &#x200B;](generative-image.md)。

## 生成モデルの追加

>[!IMPORTANT]
>
>カスタム Firefly モデルを作成するには、Firefly ETLA契約が必要です。

カスタム Firefly モデルは、独自のアセットでトレーニングされたブランド固有の AI モデルであり、ブランドアイデンティティ、スタイル、視覚的ガイドラインに正確に合致する画像を生成できます。

カスタム Firefly モデルプロバイダーを作成すると、デフォルトのモデルの枠を超えて AI 機能を拡張し、生成されるコンテンツがブランド独自の美的および要件を一貫して反映するようにできます。

➡️ [&#x200B; カスタムモデルのトレーニング方法を学ぶ &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/train-firefly-custom-models.html)

1. **[!UICONTROL ブランド]** メニューから「**[!UICONTROL 生成モデル]**」タブにアクセスし、「**[!UICONTROL モデルを追加]**」をクリックします。

   ![](assets/gen-model-manage-4.png){zoomable="yes"}

1. モデルの **[!UICONTROL 名前]** を入力します。

1. **[!UICONTROL モデル ID]** を入力します。

   +++ Firefly モデル ID の検索

   1. Fireflyの web サイトにアクセスし、トレーニング済みモデルに移動します。
   1. [&#x200B; プレビューとテスト &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/train-firefly-custom-models.html#preview-and-test) メニューにアクセスします。
   1. その URL で、`customModelId=` の後の値を探します。 この値をコピーして、モデル ID として使用します。

   詳しくは、[Firefly カスタムモデルのドキュメント &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/manage-custom-models.html) を参照してください。

   ![](assets/gen-model-manage-10.png){zoomable="yes"}

   +++

   </br>

   ![](assets/gen-model-manage-5.png){zoomable="yes"}

1. オプションで、モデルの識別に役立つ **[!UICONTROL 説明]** を入力します。

1. **[!UICONTROL 接続をテスト]** をクリックして、モデル設定を確認します。

1. 接続テストが正常に完了したら、「**[!UICONTROL 保存]**」をクリックしてモデル設定を保存します。

   ![](assets/gen-model-manage-7.png){zoomable="yes"}

1. 保存後、カスタムモデルがモデルリストに追加されます。 この機能は、いつでも無効または削除できます。

   ![](assets/gen-model-manage-8.png){zoomable="yes"}

<!--
1. Once the connection test is successful, choose whether to enable the model for selected brands.

1. Enable or disable the option to connect the model to all brands.

    If disabled, select which brands this model should be applied to.
-->

設定が完了したら、コンテンツで画像を作成する際に、カスタム生成モデルを任意に選択できます。 [&#x200B; 詳しくは、画像の生成を参照してください &#x200B;](generative-image.md)。

![](assets/gen-model-manage-9.png){zoomable="yes"}
