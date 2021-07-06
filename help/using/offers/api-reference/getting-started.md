---
title: はじめに
description: 決定管理エンジンで主要な操作を実行するために必要な、オファーライブラリ API の使用方法を説明します。
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: b07970ff11f1ba7c4e6db30dc2eca1252a579ca4
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 81%

---

# 決定管理 API デベロッパーガイド

このデベロッパーガイドでは、[!DNL Offer Library] API を使い始めるのに役立つ手順を説明します。決定管理エンジンで主要な操作を実行するための API 呼び出しの例についても説明します。

➡️ [この機能をビデオで確認](#video)

## 前提条件

このガイドは、Adobe Experience Platform の次のコンポーネントを実際に利用および理解しているユーザーを対象としています。

* [[!DNL Experience Data Model (XDM) System]](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}:顧客体験データを整理する際に使用す [!DNL Experience Platform] る標準化されたフレームワーク。
   * [スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja){target=&quot;_blank&quot;}:XDMスキーマの基本的な構成要素について説明します。
* [Decision Management](../../../using/offers/get-started/starting-offer-decisioning.md)：エクスペリエンス判定全般（特に Offer Decisioning）で使用される概念とコンポーネントについて説明します。顧客のエクスペリエンスで提示できる最適なオプションを選択するための戦略を示します。
* [[!DNL Profile Query Language (PQL)]](https://experienceleague.adobe.com/docs/experience-platform/segmentation/pql/overview.html?lang=ja){target=&quot;_blank&quot;}:PQLは、XDMインスタンスを使用して式を書く強力な言語です。PQL は、決定ルールを定義する際に使用されます。

## API 呼び出し例の読み取り

ここでは、リクエストの形式を説明するために API 呼び出しの例を示します。これには、パス、必須ヘッダー、適切な形式のリクエストペイロードが含まれます。また、API レスポンスで返されるサンプル JSON も示されています。ドキュメントで使用されるAPI呼び出し例の表記について詳しくは、[!DNL Experience Platform]トラブルシューティングガイドの[API呼び出し例](https://experienceleague.adobe.com/docs/experience-platform/landing/troubleshooting.html#how-do-i-format-an-api-request?lang=ja){target=&quot;_blank&quot;}の読み方に関する節を参照してください。

## 必須ヘッダーの値の収集

[!DNL Platform] APIを呼び出すには、まず[認証に関するチュートリアル](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=ja){target=&quot;_blank&quot;}を完了する必要があります。 次に示すように、すべての [!DNL Experience Platform] API 呼び出しに必要な各ヘッダーの値は認証チュートリアルで説明されています。

* `Authorization: Bearer {ACCESS_TOKEN}`
* `x-api-key: {API_KEY}`
* `x-gw-ims-org-id: {IMS_ORG}`

ペイロード（POST、PUT、PATCH）を含んだすべてのリクエストには、以下の追加ヘッダーが必要です。

* `Content-Type: application/json`

## コンテナへのアクセスの管理

コンテナとは、異なる関心事を切り分けるための分離メカニズムです。コンテナ ID は、すべてのリポジトリー API の最初のパス要素です。すべての決定オブジェクトはコンテナ内に存在します。

管理者は、類似したプリンシパル、リソースおよびアクセス権限をプロファイルにグループ化できます。これにより、管理上の負担が軽減され、[Adobe Admin Console](https://adminconsole.adobe.com/) でサポートされます。プロファイルを作成し、ユーザーを割り当てるには、組織内の Adobe Experience Platform の製品管理者である必要があります。1 回限りの手順で特定の権限に一致する製品プロファイルを作成し、その後、それらのユーザーにプロファイルを追加するだけで十分です。プロファイルは、権限が付与されたグループとして機能し、そのグループ内のすべての実際のユーザーまたは技術ユーザーは、権限を継承します。

管理者権限を付与された場合は、[Adobe Admin Console](https://adminconsole.adobe.com/){target=&quot;_blank&quot;}を使用して、ユーザーに権限を付与または取り消すことができます。 詳しくは、「[アクセス制御の概要](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja){target=&quot;_blank&quot;}」を参照してください。

### ユーザーと統合機能からアクセス可能なコンテナのリスト

**API 形式**

```http
GET /{ENDPOINT_PATH}?product={PRODUCT_CONTEXT}&property={PROPERTY}==decisioning
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{PRODUCT_CONTEXT}` | コンテナのリストを、製品コンテキストとの関連付けによってフィルターします。 | `acp` |
| `{PROPERTY}` | 返されるコンテナの種類をフィルターします。 | `_instance.containerType==decisioning` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/?product=acp&property=_instance.containerType==decisioning' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

**応答**

正常な応答では、決定管理コンテナに関する情報が返されます。これには `instanceId` 属性が含まれ、値がコンテナ ID になります。

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

## 次の手順

このドキュメントでは、コンテナ ID の取得など、[!DNL Offer Library] API を呼び出すために必要な前提条件に関する知識を説明しました。これで、この開発者ガイドに記載されているサンプル呼び出しに進んで、その手順に従うことができます。

## チュートリアルビデオ {#video}

次のビデオは、「決定マネジメント」の構成要素の理解をサポートするためのものです。

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329919?quality=12)
