---
solution: Journey Optimizer
product: journey optimizer
title: Journey OptimizerへのGenStudio統合の概要
description: Journey OptimizerでGenStudioを使用する方法を学ぶ
feature: Content Assistant, Integrations
topic: Content Management, Artificial Intelligence
role: User
level: Beginner, Intermediate
exl-id: c22a44a8-e4e2-453a-9ca2-b80f7c0edc19
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 9%

---

# GenStudio の統合の基本を学ぶ {#gs-genstudio}

>[!CONTEXTUALHELP]
>id="ajo_genstudio_button"
>title="GenStudio で作成したテンプレートの使用"
>abstract="GenStudio for Performance Marketing とのシームレスな統合により、Adobe AI テクノロジーで強化された GenStudio テンプレートを簡単に読み込むことができます。"

>[!AVAILABILITY]
>
>[!DNL Adobe Journey Optimizer] のGenStudio統合は、現在、**Healthcare Shield** または **Privacy and Security Shield** アドオン機能では使用できません。
>
>この機能は、メールチャネルでのみ使用できます。

[Adobe GenStudio for Performance Marketing](https://business.adobe.com/jp/products/genstudio-for-performance-marketing.html){target="_blank"} は、生成 AI ファーストのアプリケーションで、マーケティングチームが独自の広告やメールを作成し、ブランド標準を遵守し、企業ポリシーに準拠した、インパクトのあるパーソナライズされたマーケティングキャンペーンを推進できるようにします。 Adobeの AI テクノロジーを活用することで、コンテンツの作成と管理の複雑さを軽減する包括的なツールスイートを提供し、クリエイティブ担当者がイノベーションに集中できるようにします。

[!DNL GenStudio for Performance Marketing] について詳しくは、該当する [ ドキュメント ](https://experienceleague.adobe.com/ja/docs/genstudio-for-performance-marketing/user-guide/home){target="_blank"} を参照してください。

>[!INFO]
>
>詳細については、こちらの [ 概要 ](https://business.adobe.com/products/genstudio-for-performance-marketing.html#watch-overview){target="_blank"} と [!DNL Adobe GenStudio for Performance Marketing] の [ デモ ](https://business.adobe.com/products/genstudio-for-performance-marketing.html#demo){target="_blank"} を参照してください。

<!--To access the GenStudio integration in [!DNL Adobe Journey Optimizer] feature, users need to be granted the **xxx** permission. [Learn more](../administration/permissions.md)

>[!IMPORTANT]
>
>* Before starting using this capability, read out related [Guardrails and Limitations](#generative-guardrails).-->

マーケティング効率を高め、ブランドの一貫性を保つために、[!DNL **GenStudio for Performance Marketing**] のエクスペリエンスを [!DNL **Adobe Journey Optimizer**] とシームレスに統合できます。 これにより、[!DNL GenStudio] の高度なオーケストレーション機能に加えて、[!DNL Journey Optimizer] の AI 機能を活用したコンテンツ作成が可能になります。

<!--![](../rn/assets/do-not-localize/genstudio.gif)-->

<!--Guardrails and limitations {#genstudio-guardrails}

General guidelines for using the GenStudio integration in [!DNL Adobe Journey Optimizer] for email generation are listed below:

See if guidelines/limitations such as the ones listed [here](gs-generative.md#generative-guardrails) for the AI Assistant can apply.

The following limitations apply to GenStudio integration in [!DNL Adobe Journey Optimizer]:-->

## Journey OptimizerでのGenStudio機能の活用 {#use-genstudio}

[!DNL GenStudio for Performance Marketing] と [!DNL Journey Optimizer] の統合により、会社のマーケターがより適切に連携してプロセスを合理化できます。

例えば、[!DNL Journey Optimizer] を使用してメールキャンペーンを開発および自動化するテクニカルマーケターは、[!DNL GenStudio] を使用してコンテンツを作成するパフォーマンスマーケターと共同作業できます。

この統合により、両方の組織が連携してオンブランドのコンテンツを [!DNL GenStudio] から [!DNL Journey Optimizer] に簡単に統合し、特定の顧客セグメントをターゲットにして売上を伸ばす魅力的なメールを配信できます。

### Journey OptimizerからGenStudioへのHTML テンプレートの書き出し {#export-from-ajo-to-genstudio}

まず、ブランドのガイドラインを含んだ [!DNL Journey Optimizer] HTML テンプレートを [!DNL GenStudio for Performance Marketing] に書き出すことができます。 次の手順に従います。

1. [!DNL Journey Optimizer] では、ジャーニーまたはキャンペーンでメールのコンテンツにアクセスします。 [方法について詳しくは、こちらを参照してください](../email/get-started-email-design.md#key-steps)

1. メールDesignerで、「**[!UICONTROL 詳細]**」ボタンから **[!UICONTROL HTMLを書き出]** を選択します。

   ![](assets/genstudio-export-template.png){zoomable="yes"}

1. このHTMLに書き出したテンプレートを [!DNL GenStudio for Performance Marketing] にアップロードします。<!--Make sure you detect the fields that the generative AI uses to insert content in order to create an actionable template.-->

   >[!NOTE]
   >
   >HTML テンプレートを [!DNL GenStudio] にアップロードする方法については、[Adobe GenStudio for Performance Marketing ユーザーガイド ](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/content/templates/use-templates#templates-from-ajo-and-marketo){target="_blank"} の専用セクションを参照してください。

1. GenStudioでは、このテンプレートを使用して、AI プロンプトで複数のメールのバリエーションを作成し、保存します。

   >[!NOTE]
   >
   >メールエクスペリエンスを作成する方法については、GenStudio専用の [ 節 ](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/create/create-email-experience){target="_blank"} を参照してください。

### Journey OptimizerでのGenStudio エクスペリエンスの活用 {#leverage-genstudio-experiences}

[!DNL Journey Optimizer] に読み込んで作成した [!DNL GenStudio] メールのバリエーションを活用するには、次の手順に従います。

1. [!DNL Journey Optimizer] では、キャンペーンに [ メールを追加 ](../email/create-email.md) します。

1. キャンペーンの設定画面で、[ コンテンツを編集画面 ](../email/create-email.md#define-email-content) に移動し、**[!UICONTROL メール本文を編集]** をクリックして、メールDesignerを開きます。 [方法について詳しくは、こちらを参照してください](../email/get-started-email-design.md#key-steps)

1. 電子メールDesignerのホームページで、「**[!UICONTROL HTMLを読み込む]** を選択し、「**[!UICONTROL Adobe GenStudio for Performance Marketing]**」ボタンをクリックします。

   ![](assets/genstudio-pem-import-email.png){zoomable="yes"}

1. GenStudioのエクスペリエンスを参照して、コンテンツの作成を開始します。 製品、ペルソナ、ブランド、さらには色など、複数の条件でエクスペリエンスをフィルタリングできます。

   <!--![](assets/genstudio-filter-experiences.png){zoomable="yes"}-->

1. エクスペリエンスを選択し、「**[!UICONTROL 使用]**」をクリックします。

   ![](assets/genstudio-use-experience.png){zoomable="yes"}

1. GenStudio エクスペリエンスを読み込むフォルダーを選択します。

   ![](assets/genstudio-choose-destination.png){zoomable="yes"}

1. 選択したコンテンツが電子メールDesignerに表示されます。

   ![](assets/genstudio-email-content.png){zoomable="yes"}

   >[!NOTE]
   >
   >GenStudioのエクスペリエンス [ テンプレートから作成 ](#export-from-ajo-to-genstudio) は  [!DNL Journey Optimizer]  メールDesignerに直接読み込まれます。 [!DNL Journey Optimizer] テンプレートなしで作成されたGenStudio エクスペリエンスは、[ 互換モード ](../email/existing-content.md) に読み込まれます。

   [ メールコンテンツ編集ツール ](../email/content-from-scratch.md) および [ パーソナライゼーションフィールド ](../personalization/personalize.md) を使用して、メールを必要に応じて編集します。 コンテンツを保存します。

1. キャンペーンの概要ページに戻り、「**[!UICONTROL 実験を作成]**」をクリックして実験を使用します。 [ コンテンツ実験の作成方法を学ぶ ](../content-management/content-experiment.md)

   <!--![](assets/genstudio-create-experiment.png){zoomable="yes"}-->

1. 複数の処理を作成し、上記の手順を繰り返してインポートを行うと、[!DNL GenStudio] で作成した他のメールエクスペリエンスバリエーションをすばやく活用できます。

   ![](assets/genstudio-define-treatments.png){zoomable="yes"}

1. 変更を保存し、キャンペーンを [ アクティブ化 ](../campaigns/review-activate-campaign.md) します。

実験を実行した後、[ 実験キャンペーンレポート ](../reports/campaign-global-report-cja-experimentation.md) を使用してキャンペーン処理のパフォーマンスを追跡します。 その後、実験の結果を解釈できます。 [方法について詳しくは、こちらを参照してください](../content-management/get-started-experiment.md#interpret-results)
