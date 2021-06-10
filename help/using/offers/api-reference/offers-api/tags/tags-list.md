---
title: タグのリスト
description: タグを使用すると、オファーの整理と並べ替えをより適切におこなうことができます。
source-git-commit: 4ff255b6b57823a1a4622dbc62b4b8886fd956a0
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# タグのリスト

タグを使用すると、オファーの整理と並べ替えをより適切におこなうことができます。例えば、ブラックフライデーオファーに「ブラックフライデー」タグのラベルを付けることができます。オファーライブラリの検索機能を使用して、そのタグを持つすべてのオファーを簡単に見つけることができるようになります。

タグを使用して、オファーをコレクションにグループ化することもできます。詳しくは、[コレクションの作成](../../../offer-library/creating-collections.md)のチュートリアルを参照してください。

[!DNL Offer Library] API に対して単一の GET リクエストを実行することで、コンテナ内のすべてのタグのリストを表示できます。

**API 形式**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_TAG}&{QUERY_PARAMS}
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | タグが配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_TAG}` | タグに関連付けられたスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/tag;version=0.1` |
| `{QUERY_PARAMS}` | 結果をフィルターするオプションのクエリパラメーター。 | `limit=2` |

**リクエスト**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリパラメーターの使用

リソースのリストを表示する際に、クエリパラメーターを使用してページを作成し、結果をフィルターできます。

### ページング

ページングに最も一般的なクエリパラメーターは次のとおりです。

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `q` | 選択したフィールドで検索するオプションのクエリ文字列。クエリ文字列は小文字にする必要があり、二重引用符で囲むことで、トークン化を防ぎ、特殊文字をエスケープできます。次の文字 `+ - = && || > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` は特別な意味を持ち、クエリ文字列に出現する場合はバックスラッシュでエスケープする必要があります。 | Web サイト JSON |
| `qop` | 「q」クエリ文字列パラメーターの値に AND または OR 演算子を適用します。 | `AND` または `OR` |
| `field` | 検索を制限するフィールドのリスト（オプション）。このパラメーターは、field=field1[,field=field2,...] のように繰り返すことができます（パス式は「_instance.xdm:name」などのドット区切りパスの形式です）。 | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。タイトルの前に `-` を追加すると（`orderby=-title`）、アイテムがタイトルの降順（Z-A）に並べ替えられます。 | `-repo:createdDate` |
| `limit` | 返されるタグの数を制限します。 | `limit=5` |

**応答**

正常な応答では、アクセス可能なコンテナ内に存在するタグのリストが返されます。

```json
{
    "containerId": "e0bd8463-0913-4ca1-bd84-6309134ca1f6",
    "schemaNs": "https://ns.adobe.com/experience/offer-management/tag;version=0.1",
    "requestTime": "2020-10-21T20:28:21.521267Z",
    "_embedded": {
        "results": [
            {
                "instanceId": "0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 2,
                "repo:createdDate": "2020-10-16T05:11:26.815213Z",
                "repo:lastModifiedDate": "2020-10-16T22:20:20.190006Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "Sneakers",
                    "@id": "xcore:tag:1246d138ec8cca1f"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/tag;version=0.1#0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/0adf2ef0-0f6e-11eb-b3be-9b775f952952",
                        "@type": "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                    }
                }
            },
            {
                "instanceId": "149e0de0-ff5f-11ea-b017-f98866426d43",
                "schemas": [
                    "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                ],
                "productContexts": [
                    "acp"
                ],
                "repo:etag": 1,
                "repo:createdDate": "2020-09-25T18:44:02.109748Z",
                "repo:lastModifiedDate": "2020-09-25T18:44:02.109748Z",
                "repo:createdBy": "{CREATED_BY}",
                "repo:lastModifiedBy": "{MODIFIED_BY}",
                "repo:createdByClientId": "{CREATED_CLIENT_ID}",
                "repo:lastModifiedByClientId": "{MODIFIED_CLIENT_ID}",
                "_instance": {
                    "xdm:name": "retirement",
                    "@id": "xcore:tag:122c81d2804e69e3"
                },
                "_links": {
                    "self": {
                        "name": "https://ns.adobe.com/experience/offer-management/tag;version=0.1#149e0de0-ff5f-11ea-b017-f98866426d43",
                        "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/instances/149e0de0-ff5f-11ea-b017-f98866426d43",
                        "@type": "https://ns.adobe.com/experience/offer-management/tag;version=0.1"
                    }
                },
                "sandboxName": "ode-prod-va7-edge-testing"
            }
        ],
        "total": 11,
        "count": 2
    },
    "_links": {
        "self": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        },
        "next": {
            "href": "/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?start=149e0de0-ff5f-11ea-b017-f98866426d43&orderby=instanceId&schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2",
            "@type": "https://ns.adobe.com/experience/xcore/hal/results"
        }
    }
}
```
