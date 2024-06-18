---
title: オファーの配信
description: 意思決定管理は、マーケターがビジネスロジックと決定ルールを使用してエンドユーザー向けにパーソナライズされたオファーエクスペリエンスを作成し、あらゆるチャネルとアプリケーションに配信できるようにする、一連のサービスと UI プログラムで構成されています。
feature: Decision Management, API
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 692d0aae-6fa1-40b8-a35f-9845d78317a3
source-git-commit: ae0bd349b6287002f264ed716b6454fb9d8357c9
workflow-type: tm+mt
source-wordcount: '1018'
ht-degree: 46%

---

# Decisioning API を使用したオファーの配信 {#decisioning-api}

意思決定管理を使用すると、ビジネスロジックと決定ルールを使用し、あらゆるチャネルやアプリケーションをまたいで、パーソナライズされたオファーエクスペリエンスを作成し、エンドユーザーに配信できます。
オファーは、オファーを表示する資格のあるユーザーを指定するルールが関連付けられているマーケティングメッセージです。

に対してPOSTリクエストを実行することで、オファーを作成して配信できます。 [!DNL Decisioning] API です。

このチュートリアルでは、特に意思決定管理に関して、API の実用的な理解が必要です。
詳しくは、[意思決定管理 API デベロッパーガイド](../getting-started.md)を参照してください。
このチュートリアルでは、一意のプレースメント ID と決定 ID も必要です。これらの値を取得していない場合は、[プレースメントの作成](../offers-api/placements/create.md)および[決定の作成](../activities-api/activities/create.md)に関するチュートリアルを参照してください。

➡️  [ビデオでこの機能を確認する](#video)

## 必須ヘッダー {#required-headers}

次の表に、を構成する有効な値を示します *Content-Type* および *承諾* リクエストヘッダーのフィールド :

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"` |
| Content-Type | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"` |
| 認証 | `Bearer {ACCESS_TOKEN}` |
| x-gw-ims-org-id | `{IMS_ORG}` |
| x-sandbox-name | `{SANDBOX_NAME}` |
| x-api-key | `{API_KEY}` |

* ペイロード（POST、PUT、PATCH）を含むすべてのリクエストには、content-type ヘッダーが必要です

## API リクエスト {#request}

### API 形式

```https
POST /{ENDPOINT_PATH}/decisions
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ API のエンドポイントパス。 | `https://platform.adobe.io/data/core/ods` |

### リクエスト

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/ods/decisions' \
  -H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
  -H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"'
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {IMS_ORG}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}'
  -d '{
        "xdm:propositionRequests": [
            {
              "xdm:placementId": "xcore:offer-placement:ffed0456",
              "xdm:activityId": "xcore:offer-activity:ffed0123",
              "xdm:itemCount": 2
            },
            {
              "xdm:placementId": "xcore:offer-placement:ffed0012",
              "xdm:activityId": "xcore:offer-activity:fffc0789"
            }
        ],
        "xdm:profiles": [
            {
              "xdm:identityMap": {
                "SWCUSTID": [
                {
                    "xdm:id": "123@abc.com"
                }
                ]
            },
            "xdm:decisionRequestId": "0AA00002-0000-1224-c0de-cjf98Csj43"
            }
        ],
        "xdm:allowDuplicatePropositions": {
            "xdm:acrossActivities": true,
            "xdm:acrossPlacements": true
        },
        "xdm:mergePolicy": {
            "xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"
        },
        "xdm:responseFormat": {
            "xdm:includeContent": true,
            "xdm:includeMetadata": {
            "xdm:activity": [
                "name"
            ],
            "xdm:option": [
                "name"
            ],
            "xdm:placement": [
                "name"
            ]
            }
        }
      }'
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `xdm:propositionRequests` | このオブジェクトには、プレースメント ID と決定 ID が含まれています。 |
| `xdm:propositionRequests.xdm:placementId` | 一意のプレースメント ID。 | `"xdm:placementId": "xcore:offer-placement:ffed0456"` |
| `xdm:propositionRequests.xdm:activityId` | 一意の決定 ID。 | `"xdm:activityId": "xcore:offer-activity:ffed0123"` |
| `xdm:itemCount` | 返されるオファーの数。 最大数は 30 です。 | `"xdm:itemCount": 2` |
| `xdm:profiles` | このオブジェクトは、決定がリクエストされるプロファイルに関する情報を保持します。 API リクエストの場合、これには 1 つのプロファイルが含まれます。 |
| `xdm:profiles.xdm:identityMap` | このオブジェクトは、ID の名前空間統合コードに基づいて、エンドユーザー ID のセットを保持します。 ID マップは、各名前空間の複数の ID を持つことができます。 名前空間の詳細については、[このページ](../../../audience/get-started-identity.md)を参照してください。 | `Email: [{"xdm:id": "123@abc.com"}]` |
| `xdm:profiles.xdm:decisionRequestId` | プロファイル決定リクエストを一意に識別するために使用できる、クライアントで生成された ID。 この ID は応答にエコーバックされ、決定の結果には影響しません。 | `"xdm:decisionRequestId": "0AA00002-0000-1224-c0de-cjf98Csj43"` |
| `xdm:allowDuplicatePropositions` | このオブジェクトは、重複除外ルールの制御構造を示します。 これは、特定のディメンションに対して同じオプションを提案できるかどうかを示す一連のフラグで構成されます。 フラグが true に設定されている場合、重複は許可されており、フラグが示すカテゴリ全体で削除することはできません。 フラグを false に設定した場合、決定エンジンはディメンション全体で同じ提案を行わず、代わりにサブデシジョンの 1 つに対して次に最適なオプションを選択する必要があります。 |
| `xdm:allowDuplicatePropositions.xdm:acrossActivities` | True に設定すると、複数の決定に同じオプションが割り当てられる場合があります。 | `"xdm:acrossActivities": true` |
| `xdm:allowDuplicatePropositions.xdm:acrossPlacements` | true に設定すると、複数のプレースメントに同じオプションが割り当てられる場合があります。 | `"xdm:acrossPlacements": true` |
| `xdm:mergePolicy.xdm:id` | プロファイルアクセスサービスから返されるデータを制御するための結合ポリシーを識別します。 リクエストで指定されていない場合、意思決定管理はプロファイルアクセスサービスに何も渡さず、指定されている場合は呼び出し元が提供する ID を渡します。 | `"xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"` |
| `xdm:responseFormat` | 応答コンテンツを書式設定するフラグのセット。 |
| `xdm:responseFormat.xdm:includeContent` | ブール値（に設定されている場合） `true`、応答にコンテンツを含めます。 | `"xdm:includeContent": true` |
| `xdm:responseFormat.xdm:includeMetadata` | 返される追加のメタデータを指定するために使用されるオブジェクト。 このプロパティが含まれていない場合は、 `xdm:id` および `repo:etag` はデフォルトで返されます。 | `name` |
| `xdm:responseFormat.xdm:activity` | このフラグは、返される特定のメタデータ情報を識別します。 `xdm:activity`. | `name` |
| `xdm:responseFormat.xdm:option` | このフラグは、返される特定のメタデータ情報を識別します。 `xdm:option`. | `name`、`characteristics` |
| `xdm:responseFormat.xdm:placement` | このフラグは、返される特定のメタデータ情報を識別します。 `xdm:placement`. | `name`、`channel`、`componentType` |

### 応答

応答が成功すると、一意のものを含め、提案に関する情報が返されます `xdm:propositionId`.

```json
{
  "xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8",
  "xdm:propositions": [
    {
      "xdm:activity": {
        "xdm:id": "xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "xcore:placement:ffed0456",
        "repo:etag": 1
      },
      "xdm:options": [
        {
          "xdm:id": "xcore:personalized-option:ccc0111",
          "repo:etag": 3,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>some html</html>"
        },
        {
          "xdm:id": "xcore:personalized-option:ccc0222",
          "repo:etag": 5,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>hello, world</html>",
          "xdm:score": 45.65
        }
      ]
    },
    {
      "xdm:activity": {
        "xdm:id": "xcore:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "xcore:placement:ffed0789",
        "repo:etag": 2
      },
      "xdm:fallback": {
        "xdm:id": "xcore:fallback:ccc0222",
        "repo:etag": 5,
        "@type": "https://ns.adobe.com/experience/decisioning/content-component-imagelink",
        "dc:format": "image/png",
        "xdm:deliveryURL": "https://cdn.adobe.com/content/1445323-1134331.png",
        "xdm:content": "https://www.adobe.com/index2.html"
      }
    }
  ],
  "ode:createDate": 1566497582038
}
```

| プロパティ | 説明 | 例 |
| -------- | ----------- | ------- |
| `xdm:propositionId` | XDM DecisionEvent に関連付けられた提案エンティティの一意の ID。 | `"xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8"` |
| `xdm:propositions` | このオブジェクトには、決定の提案が 1 つ含まれています。決定に対して複数のオプションが返されることもあります。オプションが見つからない場合は、決定のフォールバックオファーが返されます。1 つの決定の提案には、`options` プロパティまたは `fallback` プロパティが常に含まれています。`options` プロパティは（存在する場合）、空にすることはできません。 |
| `xdm:propositions.xdm:activity` | このオブジェクトには、決定の一意の ID が含まれます。 | `"xdm:id": "xcore:activity:ffed0123"` |
| `xdm:propositions.xdm:placement` | このオブジェクトには、オファープレースメントの一意の ID が含まれます。 | `"xdm:id": "xcore:placement:ffed0456"` |
| `xdm:propositions.xdm:options` | このオブジェクトには、一意の ID を含む単一のオプションが含まれています。 このオブジェクトは（存在する場合）、空にすることはできません。 | `xdm:id": "xcore:personalized-option:ccc0111` |
| `xdm:propositions.xdm:options.@type` | コンポーネントのタイプを定義します。 `@type` クライアントの処理契約として機能します。 エクスペリエンスが組み立てられると、コンポーザーは特定のタイプを持つコンポーネントを探します。 | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:content` | 応答コンテンツの形式。 | 応答コンテンツには次のようなものがあります。 `text`, `html block`、または `image link` |
| `xdm:score` | オプションのスコア。オプションのスコアは、オプションまたは決定に関連付けられたランキング関数の計算結果です。このフィールドは、ランキング関数がランキング中のオファーのスコアの決定に関係している場合に、API によって返されます。 | `"xdm:score": 45.65` |
| `xdm:propositions.xdm:fallback` | このオブジェクトには、一意の ID を含む単一のフォールバックオファーが含まれています。 | `"xdm:id": "xcore:fallback:ccc0222"` |
| `xdm:propositions.xdm:fallback.dc:format` | リソースの物理的またはデジタル表現。 通常、形式にはリソースのメディアタイプを含める必要があります。 形式は、リソースの表示や操作に必要なソフトウェア、ハードウェア、その他の機器を決定するために使用できます。 制御された語彙から値を選択することをお勧めします（例えば、 [インターネットメディアタイプ](https://www.iana.org/assignments/media-types/) コンピュータのメディア形式の定義。 | `"dc:format": "image/png"` または `"image/jpeg"` |
| `xdm:propositions.xdm:fallback.xdm:deliveryURL` | コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを読み取るオプションの URL。 この URL は、ユーザーエージェントからアセットに公開でアクセスするために使用されます。 | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `ode:createDate` | 決定応答メッセージが作成された時間。 これはエポック時間として表されます。 | `"ode:createDate": 1566497582038` |

**応答コード**

次の表に、応答で返されるすべてのコードを示します。

| コード | 説明 |
|  ---  |  ---  |
| 200 | 成功です。指定されたアクティビティに対して決定が行われました |
| 400 | 無効なリクエストパラメーターです。構文が正しくないため、サーバーがリクエストを認識できません。 |
| 403 | 許可されていません。権限が不十分です。 |
| 422 | 処理できないエンティティです。 リクエストの構文は正しいですが、セマンティックエラーが原因で処理できません。 |
| 429 | リクエストが多すぎます。 ユーザーが一定の時間に送信したリクエストが多すぎます。 |
| 500 | 内部サーバーエラー。サーバーで予期しない状況が発生し、リクエストを完了できません。 |
| 503 | サーバー過負荷のため、サービスを利用できません。一時的な過負荷のため、サーバーは現在リクエストを処理できません。 |

<!-- ## Tutorial video {#video}

The following video is intended to support your understanding of the components of Decision Management.

>[!NOTE]
>
>This video applies to the Offer Decisioning application service built on Adobe Experience Platform. However, it provides generic guidance to use Offer in the context of Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329919/?quality=12) -->

## 次の手順 {#next-steps}

この API ガイドでは、を使用してオファーを作成および配信しました。 [!DNL Decisions] API です。 詳しくは、[意思決定管理の概要](../../../offers/get-started/starting-offer-decisioning.md)を参照してください。
