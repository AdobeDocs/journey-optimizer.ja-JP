---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer での GenStudio for Performance Marketing の操作
description: Journey Optimizer で GenStudio for Performance Marketing を操作する方法について説明します
feature: Content Assistant, Integrations
topic: Content Management, Artificial Intelligence
badge: label="限定提供" type="Informative"
role: User
level: Beginner, Intermediate
exl-id: c22a44a8-e4e2-453a-9ca2-b80f7c0edc19
source-git-commit: c03fc0e53cdaaa735c4fa48113db7b4f848e33a8
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 46%

---

# GenStudio for Performance Marketing の操作 {#ajo-genstudio}

>[!CONTEXTUALHELP]
>id="ajo_genstudio_button"
>title="GenStudio で作成したテンプレートの使用"
>abstract="GenStudio for Performance Marketing とのシームレスな統合により、Adobe AI テクノロジーで強化された GenStudio テンプレートを簡単に読み込むことができます。"

## GenStudio の基本を学ぶ {#gs-genstudio}

[Adobe GenStudio for Performance Marketing](https://experienceleague.adobe.com/ja/docs/genstudio-for-performance-marketing/user-guide/home){target="_blank"} は、マーケティングチームが独自の広告やメールを作成し、ブランド標準および企業ポリシーに準拠した、効果的でパーソナライズされたマーケティングキャンペーンを推進できるようにする生成 AI 中心のアプリケーションです。アドビの AI テクノロジーを活用することで、コンテンツの作成と管理の複雑さを軽減し、クリエイターが革新性に焦点を当てることができるようにする包括的なツールスイートを提供します。

>[!AVAILABILITY]
>
>* [!DNL Adobe Journey Optimizer] での GenStudio 統合は、現在、**Healthcare Shield** または **Privacy and Security Shield** アドオン製品では使用できません。
>
>* この機能は、メールチャネルでのみ使用できます。

マーケティングを効率化しブランドの一貫性を保つために、[!DNL **GenStudio for Performance Marketing**] のエクスペリエンスを [!DNL **Adobe Journey Optimizer**] とシームレスに統合できます。 これにより、[!DNL GenStudio] の高度なオーケストレーション機能に加えて、[!DNL Journey Optimizer] の AI を活用したコンテンツ作成を活用できます。

![Adobe Journey Optimizer への GenStudio コンテンツのインポート](../rn/assets/do-not-localize/genstudio.gif)

>[!INFO]
>
>詳しくは、この[概要](https://business.adobe.com/products/genstudio-for-performance-marketing.html#watch-overview){target="_blank"}と [!DNL Adobe GenStudio for Performance Marketing] の[デモ](https://business.adobe.com/products/genstudio-for-performance-marketing.html#demo){target="_blank"}を参照してください。

➡️ [この機能をビデオで確認](#video)

## 前提条件 {#genstudio-prerequisites}

[!DNL GenStudio for Performance Marketing] で [!DNL Journey Optimizer] 統合を使用するには、次の要件が満たされていることを確認します。

* [!DNL GenStudio for Performance Marketing] の有効なライセンスが必要です。

* [!DNL GenStudio for Performance Marketing] と [!DNL Adobe Journey Optimizer] の両方が同じ IMS 組織に属している必要があります。

* 統合機能を利用するには、ユーザーが少なくとも **共同作業者** の役割以上を持ってい [!DNL GenStudio for Performance Marketing] 必要があります。 [GenStudioのユーザーロールの詳細情報 ](https://experienceleague.adobe.com/en/docs/genstudio-for-performance-marketing/user-guide/intro/user-roles){target="_blank"}

<!--To access the GenStudio integration in [!DNL Adobe Journey Optimizer] feature, users need to be granted the **xxx** permission. [Learn more](../administration/permissions.md)

>[!IMPORTANT]
>
>* Before starting using this capability, read out related [Guardrails and Limitations](#generative-guardrails).-->

<!--Guardrails and limitations {#genstudio-guardrails}

General guidelines for using the GenStudio integration in [!DNL Adobe Journey Optimizer] for email generation are listed below:

See if guidelines/limitations such as the ones listed [here](../content-management/gs-generative.md#generative-guardrails) for AI Assistant can apply.

The following limitations apply to GenStudio integration in [!DNL Adobe Journey Optimizer]:-->

## Journey OptimizerでのGenStudio機能の活用 {#use-genstudio}

[!DNL GenStudio for Performance Marketing] と [!DNL Journey Optimizer] の統合により、会社のマーケターが共同作業を効率化してプロセスを合理化できます。

例えば、[!DNL GenStudio] を使用してメールキャンペーンを開発および自動処理するテクニカルマーケターは、[!DNL Journey Optimizer] を使用してコンテンツを作成するパフォーマンスマーケターと共同作業できます。

この統合により、両者は共同作業で [!DNL GenStudio] のブランドに即したコンテンツを [!DNL Journey Optimizer] に簡単に統合し、特定の顧客セグメントをターゲットにして売上を推進する魅力的なメールを配信できます。

### 主な機能 {#genstudio-capabilities}

この統合により、マーケティング組織の次のような強力な機能が利用できるようになります。

* **AI を活用したコンテンツ生成**: Adobeの生成 AI を活用して、インテリジェントなコピー提案とデザイン要素により、複数のオンブランド電子メールのバリエーションを効率的に作成します。

* **シームレスなワークフロー統合**:Journey OptimizerのメールテンプレートをGenStudioに書き出し、AI プロンプトでバリエーションを作成し、合理化されたプロセスでJourney Optimizerに読み込みます。

* **一元的なアセット管理**:Adobe Experience Manager Assetsを活用したGenStudioの ContentHub にアクセスして、すべてのデジタルアセットを 1 か所で整理、保存、取得します。

* **コンテンツ実験**：複数のGenStudio メールのバリエーションをJourney Optimizerに読み込み、実験機能を活用して、最もパフォーマンスの高いコンテンツをテストおよび特定します。

* **パフォーマンス主導のインサイト**: AI を活用した分析でキャンペーンのパフォーマンスを追跡し、オーディエンスの共感を得るクリエイティブ要素を把握し、今後のキャンペーンを最適化します。

### よくあるユースケース {#genstudio-use-cases}

[!DNL GenStudio for Performance Marketing] と [!DNL Journey Optimizer] の統合は、様々なマーケティングシナリオをサポートします。

* **製品ローンチキャンペーン**：製品のお知らせ用に複数の E メールバリアントをすばやく生成し、それらを様々なオーディエンスセグメントでテストし、顧客ベース全体で勝者バージョンを拡大します。

* **ホリデープロモーションとシーズンプロモーション**:GenStudio テンプレートを使用して、時間的制約が厳しいキャンペーンコンテンツを大規模に作成し、厳しい締め切りに間に合わせながら、ブランドの一貫性を確保します。

* **大規模な A/B テスト**:GenStudioで多数のコンテンツバリエーションを作成し、Journey Optimizerで体系的にテストして、メールのパフォーマンスを継続的に向上させます。

* **マルチセグメントパーソナライゼーション**:GenStudioで様々な顧客のペルソナ向けにカスタマイズされたコンテンツを生成したあと、最大の関連性を実現するために、各バリエーションをJourney Optimizerの対応するセグメントにデプロイします。

## GenStudio統合の使用 {#how-to-use}

統合ワークフローは、Journey OptimizerからJourney Optimizerへのテンプレートの書き出しとGenStudioへのGenStudio エクスペリエンスの読み込みの 2 つの主な手順で構成されます。

### Journey Optimizer から GenStudio への HTML テンプレートのエクスポート {#export-from-ajo-to-genstudio}

まず、ブランドのガイドラインを含む [!DNL Journey Optimizer] HTML テンプレートを [!DNL GenStudio for Performance Marketing] に書き出します。 次の手順に従います。

1. [!DNL Journey Optimizer] で、ジャーニーまたはキャンペーンのメールのコンテンツにアクセスします。[方法についてはこちらを参照](../email/get-started-email-design.md#key-steps)

1. E メールデザイナーで、「**[!UICONTROL 詳細]**」ボタンから「**[!UICONTROL HTML をエクスポート]**」を選択します。

   ![](assets/genstudio-export-template.png){zoomable="yes"}

1. この HTML をエクスポートしたテンプレートを [!DNL GenStudio for Performance Marketing] にアップロードします。<!--Make sure you detect the fields that the generative AI uses to insert content in order to create an actionable template.-->

   >[!NOTE]
   >
   >HTML テンプレートを [!DNL GenStudio] にアップロードする方法について詳しくは、[Adobe GenStudio for Performance Marketing ユーザーガイド](https://experienceleague.adobe.com/ja/docs/genstudio-for-performance-marketing/user-guide/content/templates/use-templates#templates-from-ajo-and-marketo){target="_blank"}の専用の節を参照してください。

1. GenStudio では、このテンプレートを使用して、AI プロンプトを含む複数のメールのバリエーションを作成し、保存します。

   >[!NOTE]
   >
   >メールエクスペリエンスを作成する方法について詳しくは、GenStudio 専用の[節](https://experienceleague.adobe.com/ja/docs/genstudio-for-performance-marketing/user-guide/create/create-email-experience){target="_blank"}を参照してください。

### Journey Optimizer での GenStudio エクスペリエンスの活用 {#leverage-genstudio-experiences}

GenStudioでメールのバリエーションを作成したら、キャンペーンで使用するために [!DNL Journey Optimizer] にインポートし直します。 次の手順に従います。

1. [!DNL Journey Optimizer] で、キャンペーンに[メールを追加](../email/create-email.md)します。

1. キャンペーンの設定画面で、[コンテンツを編集画面](../email/create-email.md#define-email-content)に移動し、「**[!UICONTROL メール本文を編集]**」をクリックして、E メールデザイナーを開きます。[方法についてはこちらを参照](../email/get-started-email-design.md#key-steps)

1. E メールデザイナーのホームページで、「**[!UICONTROL HTML をインポート]**」を選択し、「**[!UICONTROL Adobe GenStudio for Performance Marketing]**」ボタンをクリックします。

   ![](assets/genstudio-pem-import-email.png){zoomable="yes"}

1. GenStudio エクスペリエンスを参照して、コンテンツの作成を開始します。製品、ペルソナ、ブランド、カラーなど、複数の条件でエクスペリエンスをフィルタリングできます。

   <!--![](assets/genstudio-filter-experiences.png){zoomable="yes"}-->

1. エクスペリエンスを選択し、「**[!UICONTROL 使用]**」をクリックします。

   ![](assets/genstudio-use-experience.png){zoomable="yes"}

1. GenStudio エクスペリエンスをインポートするフォルダーを選択します。

   ![](assets/genstudio-choose-destination.png){zoomable="yes"}

1. 選択したコンテンツが E メールデザイナーに表示されます。

   ![](assets/genstudio-email-content.png){zoomable="yes"}

   >[!NOTE]
   >
   >GenStudioのエクスペリエンス [ テンプレートから作成  [!DNL Journey Optimizer]  は ](#export-from-ajo-to-genstudio) 完全な編集機能を使用して、メールDesignerに直接読み込まれます。 [!DNL Journey Optimizer] テンプレートを使用せずに作成されたGenStudio エクスペリエンスは [ 互換モード ](../email/existing-content.md) に読み込まれますが、その場合、編集機能が制限される可能性があります。

1. [ メールコンテンツ編集ツール ](../email/content-from-scratch.md) および [ パーソナライゼーションフィールド ](../personalization/personalize.md) を使用して、必要に応じてメールを編集します。 コンテンツを保存します。

1. キャンペーンの概要ページに戻り、「**[!UICONTROL 実験を作成]**」をクリックして、実験を使用します。[詳しくは、コンテンツ実験の作成方法を参照してください](../content-management/content-experiment.md)

   <!--![](assets/genstudio-create-experiment.png){zoomable="yes"}-->

1. 複数の処理を作成し、上記の手順を繰り返して、[!DNL GenStudio] で作成した他のメールエクスペリエンスのバリエーションをインポートし、すばやく活用します。

   ![](assets/genstudio-define-treatments.png){zoomable="yes"}

1. 変更を保存し、キャンペーンを[アクティベート](../campaigns/review-activate-campaign.md)します。

1. 実験を実行した後、[実験キャンペーンレポート](../reports/campaign-global-report-cja-experimentation.md)を使用して、キャンペーン処理のパフォーマンスを追跡します。その後、実験の結果を解釈できます。[方法についてはこちらを参照](../content-management/get-started-experiment.md#interpret-results)

## よくある質問 {#genstudio-faq}

[!DNL GenStudio for Performance Marketing] との [!DNL Journey Optimizer] 統合に関するよくある質問への回答を示します。

+++メール以外のチャネルにGenStudio統合を使用できますか？

現在、[!DNL GenStudio for Performance Marketing] 統合は、メールチャネルでのみ使用できます。 追加のチャネルのサポートは、今後のリリースで追加される可能性があります。
+++

+++GenStudioとの統合は、Journey Optimizerのすべてのユーザーが利用できますか？

この統合は、現在、**Healthcare Shield** または **プライバシーとセキュリティシールド** アドオン機能を使用している組織では利用できません。
+++

+++GenStudioのコンテンツをJourney Optimizerに読み込んだ後に編集できますか？

はい。GenStudio エクスペリエンスを [!DNL Journey Optimizer] に読み込んだ後、メールDesigner[ コンテンツ編集ツール ](../email/content-from-scratch.md) を使用して [ パーソナライゼーションフィールド ](../personalization/personalize.md) を追加し、メールコンテンツをさらにカスタマイズできます。
+++

+++Journey Optimizer テンプレートを使用せずに作成されたGenStudio エクスペリエンスはどうなりますか。

[!DNL Journey Optimizer] テンプレートから作成されたGenStudio エクスペリエンスは、電子メールDesignerに直接読み込まれます。 [!DNL Journey Optimizer] テンプレートを使用せずに作成した GenStudio エクスペリエンスは、[互換モード](../email/existing-content.md)にインポートされます。
+++

+++Journey Optimizerで複数のGenStudio メールのバリエーションをテストできますか？

はい。様々なGenStudio メールのバリエーションを読み込むことで、複数のコンテンツ処理を作成し、Journey Optimizerの [ コンテンツ実験 ](../content-management/content-experiment.md) 機能を使用して、オーディエンスに最も効果の高いバリエーションをテストできます。
+++

+++GenStudioでは、ブランドの一貫性をどのように確保していますか？

GenStudioでは、AI を活用したブランドチェックを使用して、生成されたすべてのコンテンツがブランドの標準やガイドラインに準拠していることを確認します。 ブランド要素を含んだテンプレートをアップロードすると、GenStudioは、プラットフォーム内で作成されるすべてのコンテンツバリエーションにこれらの標準を適用します。
+++

+++GenStudio エクスペリエンスで他のチームメンバーと共同作業できますか？

はい、GenStudioは共同作業のために設計されています。 適切な権限を持つ複数のチームメンバーが協力してメールエクスペリエンスの作成と調整を行ってから、それらを [!DNL Journey Optimizer] に読み込むことができます。
+++

## チュートリアルビデオ {#video}

Journey Optimizer から GenStudio for Performance Marketing にメールテンプレートをエクスポートし、GenStudio のテンプレートを使用してブランドに準拠したメールを作成し、Journey Optimizer にシームレスにインポートするプロセスについて説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3456038/?quality=12)