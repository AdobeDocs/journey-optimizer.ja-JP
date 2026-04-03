---
solution: Journey Optimizer
product: journey optimizer
title: AEM コンテンツフラグメント
description: AEM コンテンツフラグメントへのアクセスと管理の方法について説明します。
topic: Content Management
role: User
level: Beginner
source-git-commit: 4f7e36a6cc19e4138e867950e34c5a5e6452b364
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 42%

---

# Adobe Experience Manager コンテンツフラグメントの基本を学ぶ {#aem-fragments}

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。

Adobe Experience Manager as a Cloud Service を Adobe Journey Optimizer と統合することで、AEM コンテンツフラグメントを Journey Optimizer のコンテンツにシームレスに組み込めるようになりました。この合理化された接続により、AEM コンテンツへのアクセスと活用のプロセスが簡略化され、パーソナライズされた動的なキャンペーンやジャーニーの作成が可能になります。

AEM コンテンツフラグメントについて詳しくは、Experience Manager ドキュメントの[コンテンツフラグメントの操作](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"}を参照してください。

## コンテンツフラグメントライフサイクル

![](assets/do-not-localize/AEM_CF.png)

コンテンツフラグメントは、存在するAdobe Experience Manager層に応じて、様々なライフサイクルステージに従います。 [詳しくは、Adobe Experience Manager ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)を参照してください。

コンテンツは&#x200B;**オーサー層**&#x200B;で作成および管理されます。フラグメントには、新規、ドラフト、公開済み、変更済み、未公開などのステータスを設定できます。 これらのステータスは、**オーサー層**&#x200B;にのみ適用され、コンテンツの作成とレビューをサポートします。

コンテンツフラグメントが公開されると、コピーが&#x200B;**パブリッシュ層**&#x200B;に作成され、未認証の公開エンドポイントを通じて公開されます。 Journey Optimizerは、この&#x200B;**パブリッシュ層**&#x200B;とのみ統合されます。

そのため、Journey Optimizerでは、公開済みまたは変更されたコンテンツフラグメントのみを表示し、常に最新の公開済みバージョンを使用します。 公開後に行われた変更は、コンテンツフラグメントが再公開されるまでJourney Optimizerに反映されません。
