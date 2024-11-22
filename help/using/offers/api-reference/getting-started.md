---
title: はじめに
description: 意思決定エンジンを使用して主要な操作を実行するために、Offer Library API の使用を開始する方法について説明します。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
source-git-commit: ac8ccb52bd16a26c14dea148f989256e28170765
workflow-type: ht
source-wordcount: '353'
ht-degree: 100%

---

# 意思決定管理 API デベロッパーガイド {#decision-management-api-developer-guide}

>[!CONTEXTUALHELP]
>id="od_api_support"
>title="新しい意思決定管理 API"
>abstract="意思決定管理オブジェクトの作成と管理のための新しい API が使用できるようになりました。従来の API は、2024年3月27日（PT）までサポートされます。"

>[!CONTEXTUALHELP]
>id="ajo_decisioning_api_support"
>title="新しい意思決定管理 API"
>abstract="意思決定管理オブジェクトの作成と管理のための新しい API が使用できるようになりました。従来の API は、2024年3月27日（PT）までサポートされます。"

このデベロッパーガイドでは、[!DNL Offer Library] API を使い始めるのに役立つ手順を説明します。次に、このガイドでは、意思決定エンジンを使用して主要な操作を実行するための API 呼び出しのサンプルを提供します。

➡️ [意思決定管理のコンポーネントについて詳しくは、このビデオを参照してください](#video)

## 前提条件 {#prerequisites}

このガイドは、Adobe Experience Platform の次のコンポーネントを実際に利用および理解しているユーザーを対象としています。

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}：[!DNL Experience Platform] が、カスタマーエクスペリエンスデータを整理する際に使用する、標準化されたフレームワーク。
   * [スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja){target="_blank"}：XDM スキーマの基本的な構成要素について説明します。
* [意思決定管理](../../../using/offers/get-started/starting-offer-decisioning.md)：決定全般、特に意思決定管理に使用される概念とコンポーネントについて説明します。顧客のエクスペリエンスで提示する最適なオプションを選択するための戦略を示します。
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja){target="_blank"}：PQL は XDM インスタンス上で式を書くための強力な言語です。PQL は、決定ルールを定義する際に使用されます。

## API 呼び出し例の読み取り {#reading-sample-api-calls}

ここでは、リクエストの形式を説明するために API 呼び出しの例を示します。これには、パス、必須ヘッダー、適切な形式のリクエストペイロードが含まれます。また、API レスポンスで返されるサンプル JSON も示されています。ドキュメントで使用される API 呼び出し例の表記について詳しくは、[!DNL Experience Platform] トラブルシューテングガイドの [API 呼び出し例の読み方](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html?lang=ja#how-do-i-format-an-api-request){target="_blank"}に関する節を参照してください。

## 必須ヘッダーの値の収集 {#gather-values-for-required-headers}

[!DNL Adobe Experience Platform] API を呼び出すには、まず[認証チュートリアル](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=ja){target="_blank"}を完了する必要があります。次に示すように、すべての [!DNL Experience Platform] API 呼び出しに必要な各ヘッダーの値は認証チュートリアルで説明されています。

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`
* `x-sandbox-name: {SANDBOX_NAME}`

ペイロード（POST、PUT、PATCH）を含んだすべてのリクエストには、以下の追加ヘッダーが必要です。

* `Content-Type: application/json`

## 次の手順 {#next-steps}

このドキュメントでは、[!DNL Offer Library] API を呼び出すために必要な前提条件に関する知識を説明しました。これで、この開発者ガイドに記載されているサンプル呼び出しに進んで、その手順に従うことができます。
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = "Mobile_Sheliak"`.
-->

<!-- ## How-to video {#video}

The following video is intended to support your understanding of the components of Decision Management.

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12) -->

