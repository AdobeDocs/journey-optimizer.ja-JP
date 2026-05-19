---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: Adobe Experience Managerの導入方法
description: Offer Library APIを使用して、決定エンジンを使用して主要操作を実行する方法を説明します。
badge: label="レガシー" type="Informative"
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/LZVllKIbmPvNnT0wCskFj3mcNYcKRmvAT85UqWlsztA
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: c132d929-fa62-4271-803e-b823be07b914
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 447
ht-degree: 0%

---

# 意思決定管理API開発者ガイド {#decision-management-api-developer-guide}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

>[!CONTEXTUALHELP]
>id="od_api_support"
>title="新しい意思決定管理API"
>abstract="意思決定管理オブジェクトの作成と管理用の新しいAPIが利用可能になりました。 従来のapiは、2024年3月27日（PT）までサポートされます。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_api_support"
>title="新しい意思決定管理API"
>abstract="意思決定管理オブジェクトの作成と管理用の新しいAPIが利用可能になりました。 従来のapiは、2024年3月27日（PT）までサポートされます。"

この開発者ガイドでは、[!DNL Offer Library] APIの使用を開始するための手順を説明します。 次に、このガイドでは、決定エンジンを使用してキー操作を実行するためのサンプル API呼び出しを提供します。

➡️ [意思決定管理のコンポーネントについて詳しくは、このビデオをご覧ください](#video)

## 前提条件 {#prerequisites}

このガイドでは、Adobe Experience Platformの次のコンポーネントについて理解する必要があります。

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}: [!DNL Experience Platform]が顧客体験データを整理するための標準化されたフレームワークです。
   * [&#x200B; スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja){target="_blank"}: XDM スキーマの基本的な構成要素について説明します。
* [意思決定管理](../../../using/offers/get-started/starting-offer-decisioning.md)：一般的な意思決定に使用される概念とコンポーネント、特に意思決定管理について説明します。 顧客体験中に提示する最適なオプションを選択するために使用される戦略を示します。
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja){target="_blank"}: PQLは、XDM インスタンス上でエクスプレッションを書き込むための強力な言語です。 PQLは、意思決定ルールを定義するために使用されます。

## サンプル API呼び出しの読み取り {#reading-sample-api-calls}

このガイドでは、リクエストのフォーマット方法を示すAPI呼び出しの例を示します。 これには、パス、必要なヘッダー、適切な形式のリクエストペイロードが含まれます。 また、API応答で返されるサンプル JSONも提供されます。 サンプル API呼び出しに関するドキュメントで使用される規則について詳しくは、[!DNL Experience Platform] トラブルシューティングガイドの[&#x200B; サンプル API呼び出しの読み方](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html?lang=ja#how-do-i-format-an-api-request){target="_blank"}の節を参照してください。

## 必要なヘッダーの値を収集する {#gather-values-for-required-headers}

[!DNL Adobe Experience Platform]個のAPIを呼び出すには、まず[認証チュートリアル &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=ja){target="_blank"}を完了する必要があります。 認証チュートリアルを完了すると、以下に示すように、すべての[!DNL Experience Platform] API呼び出しで必要な各ヘッダーの値が提供されます。

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`
* `x-sandbox-name: {SANDBOX_NAME}`

ペイロード（POST、PUT、PATCH）を含むすべてのリクエストには、次のヘッダーが必要です。

* `Content-Type: application/json`

>[!NOTE]
>
>権限のチェックは、割り当てられた製品プロファイルに従って実施されます。 関連する製品プロファイルで付与された権限のみが、APIを介してアクセスまたは管理できるリソースを決定します。

## 次のステップ {#next-steps}

このドキュメントでは、[!DNL Offer Library] APIを呼び出すために必要な前提条件の知識について説明しました。 これで、この開発者ガイドで提供されているサンプル呼び出しに進み、その指示に従うことができます。
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = "Mobile_Sheliak"`.
-->

<!--
 
## How-to video {#video}

The following video is intended to support your understanding of the components of Decision Management.

>[!VIDEO](https://video.tv.adobe.com/v/342831?captions=jpn&quality=12)
-->
