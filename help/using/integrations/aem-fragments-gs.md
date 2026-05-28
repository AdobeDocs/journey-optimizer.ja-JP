---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントへのアクセスと管理の方法について説明します。
topic: Content Management
role: User
level: Beginner
exl-id: c36a53a4-c324-4082-838e-ed27bd3b2e90
TQID: https://experienceleague.adobe.com/GRQ3Wz7Y4YJ3545mTtju0R8en9BYiejyo8UoMx558nM
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
subfeature_v2:
  - id: c7dc31c0-c4f7-42a7-8cf5-a8c5aeb0de74
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 269
ht-degree: 44%

---

# Adobe Experience Manager コンテンツフラグメントの概要 {#aem-fragments}

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。

Adobe Experience Manager as a Cloud Service を Adobe Journey Optimizer と統合することで、AEM コンテンツフラグメントを Journey Optimizer のコンテンツにシームレスに組み込めるようになりました。 この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンやジャーニーの作成が可能になります。

AEM コンテンツフラグメントについて詳しくは、Experience Manager ドキュメントの[コンテンツフラグメントの操作](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"}を参照してください。

## コンテンツフラグメントライフサイクル

![](assets/do-not-localize/AEM_CF.png)

コンテンツフラグメントは、存在するAdobe Experience Manager層に応じて、様々なライフサイクルステージに従います。 [詳しくは、Adobe Experience Manager ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)を参照してください。

コンテンツは&#x200B;**オーサー層**&#x200B;で作成および管理されます。フラグメントには、新規、ドラフト、公開済み、変更済み、未公開などのステータスを設定できます。 これらのステータスは、**オーサー層**&#x200B;にのみ適用され、コンテンツの作成とレビューをサポートします。

コンテンツフラグメントが公開されると、コピーが&#x200B;**パブリッシュ層**&#x200B;に作成され、未認証の公開エンドポイントを通じて公開されます。 Journey Optimizerは、この&#x200B;**パブリッシュ層**&#x200B;とのみ統合されます。

そのため、Journey Optimizerでは、公開済みまたは変更されたコンテンツフラグメントのみを表示し、常に最新の公開済みバージョンを使用します。 公開後に行われた変更は、コンテンツフラグメントが再公開されるまでJourney Optimizerに反映されません。
