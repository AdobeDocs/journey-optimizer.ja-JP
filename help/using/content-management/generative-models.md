---
solution: Journey Optimizer
product: journey optimizer
title: ブランドの管理
description: 生成モデルの作成と管理方法を学ぶ
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: 9ef6b02c-0a17-4b46-bcd3-8e922eef059a
source-git-commit: d2110b995bc26df861825cdd49ca2fd39f904442
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---

# 生成モデルの作成と管理 {#generative-models}

組み込みモデル、カスタム Firefly モデル、サードパーティの画像生成プロバイダーなど、AI画像作成機能を拡張して、特定のニーズに対応し、ブランドの整合性を向上させることができます。

ニーズに適したモデルの選択：

- Firefly Image Model 4を搭載した&#x200B;**[!UICONTROL Adobe モデル]**&#x200B;は、標準装備で、追加設定なしで即座に画像を生成できます。
- Gemini 2.5 Flashを搭載した&#x200B;**[!UICONTROL パートナーモデル]**&#x200B;は、特定のユースケースに特化した機能を提供します。 AI アシスタントの画像に&#x200B;**Gemini**&#x200B;と&#x200B;**テキストオーバーレイ**&#x200B;を使用するステップバイステップのワークフローについては、[Geminiをテキストオーバーレイ画像](generative-uc.md#generative-gemini)の生成モデルとして使用するを参照してください。
- **[!UICONTROL カスタムモデル]**&#x200B;は、自社のアセットでトレーニングし、自社が追加したブランド固有のモデルです。

  **[!UICONTROL カスタムモデル]**&#x200B;の詳細については、[Adobe Firefly ドキュメント ](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html)を参照してください

一度設定すれば、コンテンツに画像を作成する際に、任意の生成モデルを選択できます。 [画像の生成に関する詳細情報](generative-image.md)。

## 生成モデルの管理

一元的に生成モデルを管理。 利用可能なモデルをすべて表示し、フィルタリングと検索で特定のモデルを見つけ、ブランドに合わせて設定を構成できます。

1. **[!UICONTROL ブランド]** メニューから、「**[!UICONTROL 生成モデル]**」タブを選択します。

   ![](assets/gen-model-manage-1.png){zoomable="yes"}

1. ![](assets/do-not-localize/Smock_Filter_18_N.svg) アイコンをクリックして、フィルターメニューにアクセスします。 **[!UICONTROL Type]**&#x200B;または&#x200B;**[!UICONTROL Status]**&#x200B;でモデルをフィルタリングします。

   ![](assets/gen-model-manage-2.png){zoomable="yes"}

1. 検索バーを使用して、特定の生成モデルを名前で検索します。

1. ![](assets/do-not-localize/Smock_More_18_N.svg) アイコンをクリックして詳細メニューにアクセスします。ここでは、モデルを有効または無効にしたり、削除したりできます。

   削除できるのは&#x200B;**[!UICONTROL カスタムモデル]**&#x200B;のみです。

   ![](assets/gen-model-manage-6.png){zoomable="yes"}

1. 「**[!UICONTROL モデルを追加]**」をクリックして、新しい生成モデルをゼロから作成します。

コンテンツで画像を作成する際に、生成モデルのいずれかを選択できるようになりました。 [画像の生成に関する詳細情報](generative-image.md)。

## 生成モデルの追加

>[!IMPORTANT]
>
>カスタム Firefly モデルを作成するには、Firefly ETLA契約書が必要です。

カスタム Fireflyモデルは、自社のアセットでトレーニングしたブランド固有のAI モデルです。これにより、ブランドアイデンティティ、スタイル、ビジュアルガイドラインに即した画像を生成できます。

カスタムのFireflyモデルプロバイダーを作成することで、AI能力をデフォルトモデル以上に向上させ、ブランド独自のデザインと要件を一貫して反映したコンテンツを生成できます。

➡️ [ カスタムモデルのトレーニング方法を学ぶ](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/train-firefly-custom-models.html)

1. **[!UICONTROL ブランド]** メニューから、**[!UICONTROL 生成モデル]** タブにアクセスし、**[!UICONTROL モデルを追加]**&#x200B;をクリックします。

   ![](assets/gen-model-manage-4.png){zoomable="yes"}

1. モデルの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

1. **[!UICONTROL モデル ID]**&#x200B;を入力します。

   +++ Firefly モデル IDの検索

   1. Fireflyのweb サイトにアクセスし、トレーニングしたモデルに移動します。
   1. 「[ プレビューとテスト ](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/train-firefly-custom-models.html#preview-and-test)」メニューにアクセスします。
   1. URLで、`customModelId=`の後の値を見つけます。 この値をコピーして、モデル IDとして使用します。

   詳しくは、[Firefly カスタムモデルのドキュメント ](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/manage-custom-models.html)を参照してください。

   ![](assets/gen-model-manage-10.png){zoomable="yes"}

   +++

   </br>

   ![](assets/gen-model-manage-5.png){zoomable="yes"}

1. オプションで、**[!UICONTROL 説明]**&#x200B;を入力して、モデルを識別します。

1. 「**[!UICONTROL 接続をテスト]**」をクリックして、モデル設定を確認します。

1. 接続テストが成功したら、**[!UICONTROL 保存]**&#x200B;をクリックして、モデル設定を保存します。

   ![](assets/gen-model-manage-7.png){zoomable="yes"}

1. 保存後、カスタムモデルがモデルリストに追加されます。 いつでも無効化または削除できます。

   ![](assets/gen-model-manage-8.png){zoomable="yes"}

<!--
1. Once the connection test is successful, choose whether to enable the model for selected brands.

1. Enable or disable the option to connect the model to all brands.

    If disabled, select which brands this model should be applied to.
-->

一度設定すれば、コンテンツに画像を作成する際に、任意のカスタム生成モデルを選択できます。 [画像の生成に関する詳細情報](generative-image.md)。

![](assets/gen-model-manage-9.png){zoomable="yes"}
