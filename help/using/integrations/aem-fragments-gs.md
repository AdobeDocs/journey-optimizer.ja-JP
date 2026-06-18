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
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: fe96aceb-8194-4a8a-a6b0-75302d02804d
subfeature_v2: id: c7dc31c0-c4f7-42a7-8cf5-a8c5aeb0de74
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 28395abcdcba6ed8fd02f252a57022aa473f3d3b
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 22%

---

# Adobe Experience Manager コンテンツフラグメントの概要 {#aem-fragments}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Experience Manager コンテンツフラグメントの概要を説明します。オーサーとパブリッシュのライフサイクルによって、Journey Optimizerで使用可能なフラグメントがどのように決まるかを理解します。

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>ヘルスケアのお客様の場合、統合は Journey Optimizer Healthcare Shield および Adobe Experience Manager Enhanced Security アドオン製品のライセンスを取得した場合にのみ有効になります。

**[!DNL Adobe Experience Manager as a Cloud Service]**&#x200B;と&#x200B;**[!DNL Adobe Experience Manager Managed Service]**&#x200B;をAdobe Journey Optimizerと統合することで、ジャーニーとキャンペーンでAEM コンテンツフラグメントを使用できます。 **[!DNL Adobe Experience Manager Managed Service]**&#x200B;の場合、統合は&#x200B;**AEM長期サポート （LTS） SP2**&#x200B;の&#x200B;**作成者**&#x200B;および&#x200B;**公開**&#x200B;層をサポートしています。このリリースでは、Adobe Experience Managerからのリアルタイム更新は利用できません。 インスタンスの設定については、Adobe Managed Services担当者にお問い合わせください。次に、[Adobe Experience Manager リポジトリアクセスを設定](aem-admin-settings.md)して、Managed Services リポジトリを追加します。

AEM コンテンツフラグメントについて詳しくは、Experience Manager ドキュメントの[コンテンツフラグメントの操作](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments-with-journey-optimizer){target="_blank"}を参照してください。

## コンテンツフラグメントライフサイクル

![](assets/do-not-localize/AEM_CF.png)

コンテンツフラグメントは、存在するAdobe Experience Manager層に応じて、様々なライフサイクルステージに従います。 [詳しくは、Adobe Experience Manager ドキュメント ](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/authoring/author-publish)を参照してください。

コンテンツは&#x200B;**オーサー層**&#x200B;で作成および管理されます。フラグメントには、新規、ドラフト、公開済み、変更済み、未公開などのステータスを設定できます。 これらのステータスは、**オーサー層**&#x200B;にのみ適用され、コンテンツの作成とレビューをサポートします。

コンテンツフラグメントが公開されると、コピーが&#x200B;**パブリッシュ層**&#x200B;に作成され、未認証の公開エンドポイントを通じて公開されます。 **[!DNL Adobe Experience Manager as a Cloud Service]**&#x200B;の場合、Journey Optimizerは&#x200B;**オーサー層**&#x200B;と&#x200B;**パブリッシュ層**&#x200B;の両方との統合をサポートしています。

そのため、Journey Optimizerでは、公開済みまたは変更されたコンテンツフラグメントのみを表示し、常に最新の公開済みバージョンを使用します。 公開後に行われた変更は、コンテンツフラグメントが再公開されるまでJourney Optimizerに反映されません。
