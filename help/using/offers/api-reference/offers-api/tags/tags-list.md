---
title: タグの表示
description: タグを使用すると、キャンペーンをより簡単に整理し、並べ替えることができます。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 8cee44ed-5569-416c-b463-e75fb20d4c9c
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# タグの表示 {#list-tags}

タグを使用すると、キャンペーンをより簡単に整理し、並べ替えることができます。 例えば、「Black 金曜」タグに「Black 金曜」というラベルを付けることができます。 その後で、オファーライブラリの検索機能を使用して、そのタグを使用してすべてのサービスを簡単に見つけることができます。

また、タグを使用して、複数のコレクションをまとめてグループ化することもできます。 詳細については、コレクション ](../../../offer-library/creating-collections.md) の作成に [ 関するチュートリアルを参照してください。

API に対し [!DNL Offer Library] て1つの GET 要求を実行することで、コンテナ内のすべてのタグのリストを表示することができます。

**API フォーマット**

```http
GET /{ENDPOINT_PATH}/{CONTAINER_ID}/queries/core/search?schema={SCHEMA_TAG}&{QUERY_PARAMS}
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/xcore/` |
| `{CONTAINER_ID}` | タグが配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |
| `{SCHEMA_TAG}` | タグに関連付けられたスキーマを定義します。 | `https://ns.adobe.com/experience/offer-management/tag;version=0.1` |
| `{QUERY_PARAMS}` | 結果をフィルター処理するためのオプションのクエリパラメーターです。 | `limit=2` |

**要求**

```shell
curl -X GET \
  'https://platform.adobe.io/data/core/xcore/e0bd8463-0913-4ca1-bd84-6309134ca1f6/queries/core/search?schema=https://ns.adobe.com/experience/offer-management/tag;version=0.1&limit=2' \
  -H 'Accept: *,application/vnd.adobe.platform.xcore.hal+json; schema="https://ns.adobe.com/experience/xcore/hal/results"' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
```

## クエリーパラメーターの使用 {#using-query-parameters}

クエリーパラメーターを使用して、リソースをリスト表示するときに結果をページに表示し、フィルターをかけることができます。

### ページャー {#paging}

ページングの最も一般的なクエリーパラメーターは、次のとおりです。

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `q` | 選択されているフィールドで検索するオプションのクエリストリングです。 クエリーストリングは、小文字にする必要があります。また、二重引用符で囲むことによって、トークン化したり、エスケープ特殊文字を使用しないようにすることができます。 この文字 `+ - = && || > < ! ( ) { } [ ] ^ \" ~ * ? : \ /` は特殊な意味を持っており、クエリーストリングに表示されるときに、バックスラッシュでエスケープする必要があります。 | Web サイト JSON |
| `qop` | は、q クエリ文字列パラメーターの値に AND または OR 演算子を適用します。 | `AND` / `OR` |
| `field` | 検索対象を限定するオプションのリストです。 このパラメーターは、次のように反復することもできます。フィールド = field1 [ 、フィールド = field2,... ] および (パス式は、_instance のようなドット区切りパスの形式で記述されています。 xdm: name) | `_instance.xdm:name` |
| `orderBy` | 特定のプロパティで結果を並べ替えます。 「の `-` 前にタイトルを追加」 ( `orderby=-title` ) を指定すると、アイテムは見出し順 (z-index) にソートされます。 | `-repo:createdDate` |
| `limit` | 返されるタグの数を限定します。 | `limit=5` |

**対し**

応答が成功した場合は、アクセス権を持っているコンテナ内に存在するタグのリストが返されます。

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
