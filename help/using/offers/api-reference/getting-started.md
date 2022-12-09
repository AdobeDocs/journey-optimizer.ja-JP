---
title: はじめに
description: Decisioning engine を使用して主な操作を実行するために、Offer ライブラリ API の使用を開始する方法について説明します。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 773bee50-849f-4b07-9423-67de5279ad28
source-git-commit: e7431d1b69e460471b01439c9bd2577fd69944ed
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# 意思決定管理 API デベロッパーガイド {#decision-management-api-developer-guide}

この開発ガイドでは、 [!DNL Offer Library] API を使用して作業を開始する方法について説明しています。 このガイドでは、decisioning エンジンを使用して、主な操作を実行するためのサンプル API 呼び出しを提供しています。

このビデオでは、意志決定管理のコンポーネントについて詳しく説明して➡️ [](#video)

## 知識 {#prerequisites}

このガイドでは、Adobe 体験プラットフォームの次のコンポーネントについて、理解しておく必要があります。

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html){target = &quot;_blank&quot;}: カスタマーエクスペリエンスデータを整理するために使用される標準化されたフレームワークを指定 [!DNL Experience Platform] します。
   * [スキーマコンポジション ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) の基礎 {target = &quot;_blank&quot;}: XDM スキーマの基本的な構築ブロックについて説明します。
* [意思決定管理 ](../../../using/offers/get-started/starting-offer-decisioning.md) : 一般的な経験、特に意思決定を Decisioning ために使用されている概念とコンポーネントについて説明します。 では、お客様の操作中に最適なオプションを選択するために使用する方法を示しています。
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html){target = &quot;_blank&quot;}: PQL は、XDM インスタンス上にエクスプレッションを記述するための強力な言語として使用できます。 PQL は、意思決定ルールを定義するために使用されます。

## サンプル API 呼び出しの読み取り {#reading-sample-api-calls}

このガイドでは、要求をフォーマットする方法を示すための API 呼び出しについて説明しています。 このようなインクルードには、パス、必須ヘッダー、および適切にフォーマットされた要求ペイロードがあります。 API 応答に返されるサンプル JSON も提供されています。 サンプル API 呼び出しに関するドキュメントで使用されている表記規則については、「トラブルシューティングガイド」 [!DNL Experience Platform] の「api _blank 呼び出し ](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request) の例」を参照してください [ 。

## 必要なヘッダーの値を収集する {#gather-values-for-required-headers}

Api を [!DNL Adobe Experience Platform] 呼び出すためには、最初に認証チュートリアル ](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html) {target = &quot;_blank&quot;} を完了して [ おく必要があります。認証を完了すると、次に示すように、すべて [!DNL Experience Platform] の API 呼び出しにおいて必要なヘッダーの値が提供されます。

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`

ペイロード (POST、PUT、パッチ) を含むすべての要求に対して、追加のヘッダーが必要になります。

* `Content-Type: application/json`

## コンテナへのアクセスの管理 {#manage-access-to-container}

コンテナは、異なる考慮事項を区別するための分離機構です。 コンテナ ID は、すべてのリポジトリ Api の最初のパスエレメントです。 Decisioning オブジェクトはすべて1つのコンテナ内に配置されます。

管理者は、類似するプリンシパル、リソース、およびアクセス許可をプロファイルに対してグループ化することができます。 これにより、管理負担が軽減されます。また、アドビシステムズ社の管理コンソール ](https://adminconsole.adobe.com/) に [ も対応しています。プロファイルを作成してユーザーを割り当てるには、組織内の Adobe エクスペリエンスプラットフォーム用のプロダクト管理者である必要があります。 1回の操作で特定の権限と一致する製品プロファイルを作成して、それらのプロファイルに単純にユーザーを追加するだけで十分です。 プロファイルは、権限が与えられたグループとして機能し、そのグループ内のすべての実ユーザーまたは技術ユーザーがこれらの権限を継承します。

管理者権限を持つユーザーに対しては、Adobe Admin Console ](https://adminconsole.adobe.com/) (target = &quot;_blank&quot;}) を使用して、ユーザーにパーミッションを付与したり取り消し [ たりすることができます。詳しくは、アクセス制御の [ 概要 ](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html) {target = &quot;_blank&quot;} を参照してください。

### ユーザーと統合にアクセス可能なコンテナのリスト表示 {#list-containers-accessible-to-users-and-integrations}

**API フォーマット**

```http
GET /{ENDPOINT_PATH}?product={PRODUCT_CONTEXT}&property={PROPERTY}==decisioning
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{PRODUCT_CONTEXT}` | 製品コンテキストに関連付けて、コンテナのリストをフィルターします。 | `acp` |
| `{PROPERTY}` | 返されるコンテナのタイプをフィルターします。 | `_instance.containerType==decisioning` |

**要求**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/?product=acp&property=_instance.containerType==decisioning' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**対し**

応答が成功した場合は、意思決定管理コンテナーに関する情報が返されます。 これには属性が含まれ `instanceId` ます。値はコンテナ ID です。

```json
{
    "_embedded": {
        "https://ns.adobe.com/experience/xcore/container": [
            {
                "instanceId": "{INSTANCE_ID}",
                "schemas": [
                    "https://ns.adobe.com/experience/xcore/container;version=0.5"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2020-09-16T07:54:28.319959Z",
                "repo:lastModifiedDate": "2020-09-16T07:54:32.098139Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "containerType": "decisioning",
                    "repo:name": "{REPO_NAME}",
                    "dataCenter": "{DATA_CENTER}",
                    "parentName": "{PARENT_NAME}",
                    "parentId": "{PARENT_ID}"
                },
                "_links": {
                    "self": {
                        "href": "/containers/{INSTANCE_ID}"
                    }
                }
            }
        ]
    },
    "_links": {
        "self": {
            "href": "/?product=acp&property=_instance.containerType==decisioning",
            "@type": "https://ns.adobe.com/experience/xcore/hal/home"
        }
    }
}
```

## 次の手順 {#next-steps}

このドキュメントでは、API を [!DNL Offer Library] 呼び出すために必要な前提条件について説明しています。これを使用して、コンテナ ID を取得することもできます。 これで、この開発ガイドで提供されているサンプル呼び出しに進み、そのインストラクションに従います。
<!--
>[!NOTE]
>
> The In-app messaging channel in Adobe Journey Optimizer uses decision management objects. If your organization uses the in-app messaging channel, then API list requests for objects will include objects created by the in-app messaging service and can be ignored for decision management use cases. Objects created for in-app messages will have `createdBy = “Mobile_Sheliak”`.
-->

## 操作方法のビデオ {#video}

以下のビデオは、デシジョンマネジメントのコンポーネントについての理解をサポートすることを目的としています。

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)

