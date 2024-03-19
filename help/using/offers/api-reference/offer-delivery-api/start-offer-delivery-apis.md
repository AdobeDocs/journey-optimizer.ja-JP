---
title: オファー配信 API の概要
description: パーソナライズされたオファーの配信に使用できる API について詳しく説明します。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 7bc1a4ec-113c-4af7-b549-ee17b843b818
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: ht
source-wordcount: '673'
ht-degree: 100%

---

# オファー配信 API の概要 {#about-decisioning-apis}

**Decisioning** API または **Edge Decisioning** API のいずれかを使用してオファーを配信できます。さらに、**Batch Decisioning** API を使用すると、特定のオーディエンス内のすべてのプロファイルに 1 回の呼び出しでオファーを配信できます。オーディエンス内の各プロファイルに対するオファーコンテンツは、Adobe Experience Platform データセットに配置され、カスタムバッチワークフローで使用できます。

このページでは、**Decisioning** API と **Edge Decisioning** API で利用できる特定の機能について説明します。どちらでも顧客にオファーを配信することができますが、インバウンドのユースケースにはできるだけ **Edge Decisioning** API を使用し、プラットフォームでの待ち時間とスループットを向上できるようにすることをお勧めします。

API の使用方法について詳しくは、次の節を参照してください。
* [Decisioning API](decisioning-api.md)
* [Edge Decisioning API](edge-decisioning-api.md)
* [Batch Decisioning API](batch-decisioning-api.md)

## コンテナへのアクセスの管理 {#manage-access-to-container}

コンテナとは、異なる関心事を切り分けるための分離メカニズムです。コンテナ ID は、すべてのリポジトリ API の最初のパス要素です。すべての決定オブジェクトはコンテナ内に存在します。

管理者は、類似したプリンシパル、リソースおよびアクセス権限をプロファイルにグループ化できます。これにより、管理上の負担が軽減され、[Adobe Admin Console](https://adminconsole.adobe.com/) でサポートされます。プロファイルを作成し、ユーザーを割り当てるには、組織内の Adobe Experience Platform の製品管理者である必要があります。1 回限りの手順で特定の権限に一致する製品プロファイルを作成し、その後、それらのユーザーにプロファイルを追加するだけで十分です。プロファイルは、権限が付与されたグループとして機能し、そのグループ内のすべての実際のユーザーまたは技術ユーザーは、権限を継承します。

管理者権限を持っている場合は、[Adobe Admin Console](https://adminconsole.adobe.com/) からユーザーに権限を付与または取り消すことができます。{target="_blank"}. For more information, see the [Access control overview](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja){target="_blank"}

### ユーザーと統合機能からアクセス可能なコンテナのリスト {#list-containers-accessible-to-users-and-integrations}

**API 形式**

```http
GET /{ENDPOINT_PATH}?product={PRODUCT_CONTEXT}&property={PROPERTY}==decisioning
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
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

正常な応答では、意思決定管理コンテナに関する情報が返されます。これには `instanceId` 属性（値はコンテナ ID）が含まれます。

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
                "repo:createdDate": "2023-09-16T07:54:28.319959Z",
                "repo:lastModifiedDate": "2023-09-16T07:54:32.098139Z",
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

## Edge Decisioning API の機能 {#edge}

**エクスペリエンスイベントと決定リクエストについての一意のリクエスト**

Edge Decisioning API を使用すると、エクスペリエンスイベント自体と決定リクエストを、2 つの異なるリクエストではなく、まとめて 1 つのリクエストで送信できます。

例えば、顧客が web サイトを訪問した場合、リクエストにはエクスペリエンスイベント（顧客のページへの訪問）が含まれ、訪問したページに入力するためのオファーが返されます。

**Adobe Experience Platform へのコンテキストデータの格納**

コンテキストデータは、オファーを返す際にしか分からないデータを指します。例えば、購入した商品の色、購入時の天気などです。

Edge Decisioning API リクエストでコンテキストデータを渡す場合、データは Adobe Experience Platform プロファイルに保存され、後で再利用できるようになります。

>[!NOTE]
>
>コンテキストデータを保存するには、専用の XDM スキーマを設定する必要があります。

**フリークエンシーキャップカウンターの更新**

一部のオファーでフリークエンシーキャップが有効になっていて、キャップカウントがリセットされる頻度が定義されている場合、カウンターが更新され、3 秒未満で Edge Decisioning API の決定で使用できるようになります。[オファーに制約を追加する方法を学ぶ](../../offer-library/add-constraints.md)

## Decisioning API の機能 {#decisioning}

以下に示す機能は、Decisioning API でのみ使用できます。要件を満たすためにこれらのいずれかを利用する必要がある場合は、Decisioning API を使用します。それ以外の場合は、Edge Decisioning API を使用することをお勧めします。

* **オファーのコンテンツと特性**：専用オプションを使用して、オファーのコンテンツや特性を返さないように選択できます。
* **オファーメタデータ**：オファーのメタデータを返すオプションを有効にします。
* **結合ポリシー**：サンドボックスに関連付けられたものとは異なる結合ポリシーをリクエストで使用します。
* **決定イベントとフリークエンシーキャップ**：発生するフリークエンシーキャップによって決定イベントがカウントされないようにします。
* **提案の重複**：提案の重複を排除しないオプションを有効にします。
