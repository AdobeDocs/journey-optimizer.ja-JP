---
solution: Journey Optimizer
product: journey optimizer
title: インテリジェントサービスとの統合
description: Journey OptimizerでAdobe インテリジェントサービスとCustomer AI予測を活用する方法について説明します
feature: Journeys, Integrations
topic: Artificial Intelligence
role: User
level: Intermediate
keywords: 人工, AI, インテリジェント, ジャーニー, サービス
exl-id: 20da09e1-0611-4d27-a589-30552011e06c
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/rTKcWHwfwleQtD68fcdeqYK2AMQHVaknKtsNDFsOldI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: d998adac-2f81-400b-a669-d07bb196e4eb
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eb30f47f-d87a-400f-8f78-63ce7979ff56
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 669
ht-degree: 16%

---

# インテリジェントサービスとの統合 {#ai-overview}

>[!BEGINSHADEBOX]

**このページでは：** Adobe インテリジェントサービスとCustomer AIの予測をJourney Optimizerと統合し、解約スコアとコンバージョンスコアをプロファイル属性として使用して決定、アクション、セグメント構築する方法について説明します。

>[!ENDSHADEBOX]

**[!DNL Adobe Intelligent Services]** との統合により、顧客体験のユースケースで人工知能と機械学習を活用できます。 これにより、マーケティングアナリストは、データサイエンスの専門知識を必要とせずに、ビジネスレベルの設定を使用して、会社のニーズに合わせた予測を設定できます。

[!DNL Adobe Experience Platform]上に構築された[!DNL Intelligent Services]は、顧客体験チームにサービスとしてのAIを提供します。 顧客の行動を予測し、キャンペーンの影響を測定して、ROIを向上させることができます。 詳しくは、[[!DNL Adobe Experience Platform]  ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/home.html?lang=ja){target="_blank"}を参照してください。

[!DNL Journey Optimizer] と [!DNL Intelligent Services] の統合により、顧客の予測を活用できます。

[!DNL Adobe Intelligent Services] のコンポーネントである顧客 AI は、可能性の高い顧客アクションを予測します。 [[!DNL Adobe Experience Platform] ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=ja){target="_blank"}を参照してください。

顧客 AI を使用すると、ブランドは、チャーンまたはコンバージョンの機械学習に基づくスコアを作成できます。 これらのスコアは、[!DNL Adobe Experience Platform] プロファイル （リアルタイム顧客プロファイル）のプロファイル属性として使用できます。

その結果、これらの属性は、Journey Optimizerの他のプロファイル属性と同様に使用できます。 決定、アクション、セグメント構築のための条件で使用します。

![傾向スコアおよび予測を示す顧客 AI 統合](assets/customer-ai.png)

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

- **TL;DR:**&#x200B;このページでは、Journey OptimizerがAdobe インテリジェントサービス（特にCustomer AI）と統合して、ジャーニーのプロファイル属性としてマシンラーニングベースの傾向スコアを活用する方法について説明します。

**インテント：**
- Adobe Intelligent ServicesとJourney Optimizerの連携の詳細
- Customer AIの傾向スコアを、ジャーニーの条件またはアクションのプロファイル属性として使用します
- データサイエンスの専門知識を必要とせずに、AIを活用した解約やコンバージョンの予測が可能です
- Journey Optimizerのセグメント構築にマシンラーニングスコアを適用し

**用語集：**
- **Adobe インテリジェントサービス**: Adobe Experience Platform上に構築された一連のAI/ML サービスで、データサイエンスの専門知識を必要とせずに顧客体験を予測できます&#x200B;*（製品固有）*
- **Customer AI**：顧客プロファイル *（製品固有）のマシンラーニングベースの解約またはコンバージョン傾向スコアを生成するAdobe Intelligent Servicesのコンポーネント*
- **傾向スコア**: プロファイル属性&#x200B;*（製品固有）として保存された、特定のアクション（解約やコンバージョンなど）を実行する顧客の可能性を表す機械学習ベースのスコア*

**ガードレール：**
- データサイエンスの専門知識は必要ありませんが、ビジネスレベルの設定は、マーケティングアナリストが行う必要があります
- Customer AI スコアは、Journey Optimizerでプロファイル属性として使用できるようにするには、まずAdobe Experience Platformで設定する必要があります

**用語：**
- 正式名称：Adobe Intelligent Services — Acronym: none — バリアント：Intelligent Services, AI services
- 正式名称：顧客AI – 頭字語：なし – バリエーション：顧客AI スコア、傾向スコア
- 同義語：「解約スコア」 = 「解約傾向」、「コンバージョンスコア」 = 「コンバージョン傾向」
- 混同しないでください。「Adobe インテリジェントサービス」≠「AI アシスタント」（インテリジェントサービスは予測マシンラーニングプラットフォームです。AI アシスタントは対話型インターフェイスです）

**FAQ:**
- **Q: Journey OptimizerにおけるCustomer AIとは何ですか？** — Customer AIは、マシンラーニングベースの解約またはコンバージョンスコアを作成するAdobe インテリジェントサービスコンポーネントです。このスコアは、Journey Optimizerの条件、アクション、セグメント構築で使用できるプロファイル属性として使用できます。
- **Q: Adobe インテリジェントサービスを使用するには、データサイエンスのスキルが必要ですか？** — マーケティングアナリストは、データサイエンスの専門知識を必要とせずに、ビジネスレベルの設定を使用して予測を設定できます。
- **Q:Customer AI スコアはどこに保存されますか？** — Adobe Experience Platformのリアルタイム顧客プロファイルにプロファイル属性として保存され、Journey Optimizerの他のプロファイル属性と同様にアクセスできるようになります。
- **Q: ジャーニーでCustomer AI スコアを使用するにはどうすればよいですか？** - プロファイル属性として使用可能になると、スコアは、決定、アクション設定、またはオーディエンスセグメントの構築の条件で使用できます。

+++
