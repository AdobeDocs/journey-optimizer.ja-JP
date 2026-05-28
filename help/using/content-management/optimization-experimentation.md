---
solution: Journey Optimizer
product: journey optimizer
title: メッセージの最適化に実証済み
description: コンテンツの検証を通じて、コンテンツの複数のバージョンをテストし、最も効果の高いバージョンを特定する方法を解説します。
role: User
level: Intermediate
keywords: A/B テスト，コンテンツ実験，処理
exl-id: 4e8537c4-944f-4a39-be2b-af8ebfb6e099
TQID: https://experienceleague.adobe.com/2ponHAr61o0hTMYuG5l9mQuh79-WeQz9eRuCF7dZjdA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: []
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e1e0219c-f879-479f-8427-888ed2a6e9c2
subfeature_v2: id: f29a52db-c90c-4345-902e-b586d1406d8d
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 72%

---

# 実験の使用 {#experimentation}

>[!NOTE]
>
>このページでは、コンテンツ最適化で実験を使用する方法の概要を説明します。 設定オプション、指標、分析など、コンテンツ実験について詳しくは、[ コンテンツ実験ドキュメント ](../content-management/get-started-experiment.md)を参照してください。

実験により、複数のバージョンのコンテンツをテストし、事前定義済みの成功指標に基づいて最もパフォーマンスが高いバージョンを判断できます。

実験を設定するには、次の手順に従います。

キャンペーンで次のプロモーションメッセージをテストするとします。

* **処理 A**：「次回購入時に 20％オフ」
* **処理 B**：「50 ドルを超える注文で送料無料」
* **処理 C**：「10 ドルのギフトカードを入手」

実験を設定し、最も多くの購入を促すメッセージを特定するには、次の手順に従います。

1. [ジャーニー](../building-journeys/journey-gs.md#jo-build)または[キャンペーン](../campaigns/create-campaign.md)を作成します。

   >[!NOTE]
   >
   >ジャーニー中の場合は、**[!UICONTROL アクション]**&#x200B;アクティビティを追加し、チャネルアクティビティを選択して、「**[!UICONTROL アクションを設定]**」を選択します。 [詳細情報](../building-journeys/journey-action.md#add-action)

1. 「**[!UICONTROL アクション]**」タブから、[コードベースのエクスペリエンス](../code-based/get-started-code-based.md)や[アプリ内](../../rp_landing_pages/in-app-landing-page.md)など、2 つのインバウンドアクションを選択します。

1. 「**[!UICONTROL 最適化]**」セクションで、「**[!UICONTROL 実験を作成]**」を選択します。

   ![](../campaigns/assets/msg-optimization-select-experiment.png){width=85%}

1. 必要に応じて、コンテンツ実験を設計および設定します。 [詳細情報](../content-management/content-experiment.md)

   ![](../campaigns/assets/msg-optimization-create-experiment.png){width=85%}

   実験が定義されると、そのキャンペーンに、またはジャーニー&#x200B;**[!UICONTROL アクション]**&#x200B;アクティビティを通じて挿入されたすべてのアクションに適用され、すべてのサーフェスで同じお客様に同じオファーが表示されます。

   >[!NOTE]
   >
   >他のアクションを選択できます。実験は、キャンペーンまたはジャーニー[ アクションアクティビティ ](../building-journeys/journey-action.md)に追加されたすべてのアクションに適用されます。

1. ジャーニーまたはキャンペーンを[アクティブ化](../campaigns/review-activate-campaign.md)します。

ジャーニー／キャンペーンがライブになると、ユーザーには様々なコンテンツのバリエーションがランダムに割り当てられます。 [!DNL Journey Optimizer] は、より多くの購入を推進したバリエーションを追跡し、実用的なインサイトを提供します。

[ジャーニー](../reports/journey-global-report-cja.md)と[キャンペーン](../reports/campaign-global-report-cja-experimentation.md)のレポートを使用してキャンペーンの成功を追跡します。<!--Link to Experimentation journey reportis missing-->
