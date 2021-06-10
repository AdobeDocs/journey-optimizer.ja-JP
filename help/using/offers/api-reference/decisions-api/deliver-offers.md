---
title: オファーの配信
description: 決定管理は、マーケターがビジネスロジックと決定ルールを使用し、あらゆるチャネルとアプリケーションをまたいで、パーソナライズされたオファーエクスペリエンスを作成してエンドユーザーに配信できるようにする、一連のサービスと UI プログラムで構成されています。
source-git-commit: 741fe2b614e3ded57c4a7ecd9b7333bdd99ab359
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 99%

---

# 決定 API を使用したオファーの配信

決定管理を使用すると、ビジネスロジックと決定ルールを使用し、あらゆるチャネルやアプリケーションをまたいで、パーソナライズされたオファーエクスペリエンスを作成し、エンドユーザーに配信できます。オファーとは、オファーを表示する資格のあるユーザーを指定するルールが関連付けられているマーケティングメッセージです。

[!DNL Decisions] API に対して POST リクエストを実行することで、オファーを作成し、配信できます。

このチュートリアルでは、特に 決定管理に関して、API の実用的な理解が必要です。詳しくは、[決定管理 API デベロッパー ガイド](../getting-started.md)を参照してください。このチュートリアルでは、一意のプレースメント ID と決定 ID も必要です。これらの値を取得していない場合は、[プレースメントの作成](../offers-api/placements/create.md)および[決定の作成](../activities-api/activities/create.md)に関するチュートリアルを参照してください。

![](../../../assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

## Accept ヘッダーと Content-Type ヘッダー

次の表に、リクエストヘッダーの *Content-Type* フィールドと *Accept* フィールドを構成する有効な値を示します。

| ヘッダー名 | 値 |
| ----------- | ----- |
| Accept | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"` |
| Content-Type | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"` |

**API 形式**

```https
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/decisions
```

| パラメーター | 説明 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリー API のエンドポイントパス。 | `https://platform.adobe.io/data/core/ode/` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナ。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**リクエスト**

```shell
curl -X POST \
  'https://platform.adobe.io/data/core/ode/e0bd8463-0913-4ca1-bd84-6309134ca1f6/decisions' \
  -H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
  -H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0'
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
            "xdm:decisionRequestId": "0AA00002-0000-1337-c0de-c0fefec0fefe"
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
| `xdm:itemCount` | 返されるオファーの数。最大値は 30 です。 | `"xdm:itemCount": 2` |
| `xdm:profiles` | このオブジェクトは、決定がリクエストされるプロファイルに関する情報を保持します。API リクエストの場合は、プロファイルが 1 つ含まれます。 |
| `xdm:profiles.xdm:identityMap` | このオブジェクトは、ID の名前空間統合コードに基づく一連のエンドユーザー ID を保持します。ID マップには各名前空間の複数の ID を保持できます。名前空間について詳しくは、[ID 名前空間の概要](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html)を参照してください。 | `Email: [{"xdm:id": "123@abc.com"}]` |
| `xdm:profiles.xdm:decisionRequestId` | プロファイルの決定リクエストを一意に識別するために使用できる、クライアントによって生成された ID。この ID は応答内にエコーバックされ、決定の結果に影響を与えません。 | `"xdm:decisionRequestId": "0AA00002-0000-1337-c0de-c0fefec0fefe"` |
| `xdm:allowDuplicatePropositions` | このオブジェクトは、重複除外ルールの制御構造を表します。特定のディメンションに対して同じオプションを提案できるかどうかを示す一連のフラグで構成されます。フラグを true に設定した場合は、重複が許可され、フラグで示されるカテゴリ全体で削除されません。フラグを false に設定した場合、決定エンジンはディメンション全体で同じ提案をおこなわず、代わりにサブデシジョンの 1 つに対して次に最適なオプションを選択する必要があります。 |
| `xdm:allowDuplicatePropositions.xdm:acrossActivities` | True に設定すると、複数の決定に同じオプションが割り当てられる場合があります。 | `"xdm:acrossActivities": true` |
| `xdm:allowDuplicatePropositions.xdm:acrossPlacements` | True に設定すると、複数のプレースメントに同じオプションが割り当てられる場合があります。 | `"xdm:acrossPlacements": true` |
| `xdm:mergePolicy.xdm:id` | プロファイルアクセスサービスが返すデータを制御する結合ポリシーを指定します。リクエストで指定されていない場合、決定管理はプロファイルアクセスサービスに何も渡さず、指定されている場合は呼び出し元が提供する ID を渡します。 | `"xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"` |
| `xdm:responseFormat` | 応答コンテンツをフォーマットする一連のフラグ。 |
| `xdm:responseFormat.xdm:includeContent` | ブール値で、`true` に設定した場合、応答にコンテンツを含めます。 | `"xdm:includeContent": true` |
| `xdm:responseFormat.xdm:includeMetadata` | 返される追加のメタデータを指定するために使用されるオブジェクト。このプロパティが含まれていない場合、デフォルトでは `xdm:id` と `repo:etag` が返されます。 | `name` |
| `xdm:responseFormat.xdm:activity` | このフラグは、`xdm:activity` に対して返される特定のメタデータ情報を識別します。 | `name` |
| `xdm:responseFormat.xdm:option` | このフラグは、`xdm:option` に対して返される特定のメタデータ情報を識別します。 | `name`、`characteristics` |
| `xdm:responseFormat.xdm:placement` | このフラグは、`xdm:placement` に対して返される特定のメタデータ情報を識別します。 | `name`、`channel`、`componentType` |

**応答**

正常な応答では、提案に関する情報（一意の `xdm:propositionId` を含む）が返されます。

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
| `xdm:propositions.xdm:options` | このオブジェクトには、単一のオプションが含まれます（一意の ID を含む）。指定する場合、このオブジェクトを空にすることはできません。 | `xdm:id": "xcore:personalized-option:ccc0111` |
| `xdm:propositions.xdm:options.@type` | コンポーネントのタイプを定義します。`@type` は、クライアントの処理契約の役割を果たします。エクスペリエンスがアセンブルされると、コンポーザーは特定のタイプを持つコンポーネントを探します。 | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:content` | 応答コンテンツの形式。 | 応答コンテンツは、`text`、`html block`、または `image link` です。 |
| `xdm:score` | オプションのスコア。オプションのスコアは、オプションまたは決定に関連付けられたランキング関数の計算結果です。ランク付けの際にオファーのスコアの決定にランキング関数が関与する場合、このフィールドは API から返されます。 | `"xdm:score": 45.65` |
| `xdm:propositions.xdm:fallback` | このオブジェクトには、単一のフォールバックオファーが含まれます（一意の ID を含む）。 | `"xdm:id": "xcore:fallback:ccc0222"` |
| `xdm:propositions.xdm:fallback.dc:format` | リソースの物理的またはデジタル的な表示。通常、形式にはリソースのメディアタイプを含める必要があります。形式は、リソースを表示または操作するのに必要なソフトウェア、ハードウェア、または他の機器を決定するために使用できます。コンピューターメディア形式を定義する[インターネットメディアタイプ](http://www.iana.org/assignments/media-types/)のリストなど、制御された用語から値を選択することをお勧めします。 | `"dc:format": "image/png"` または `"image/jpeg"` |
| `xdm:propositions.xdm:fallback.xdm:deliveryURL` | コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを読み取るためのオプションの URL。この URL は、ユーザーエージェントからアセットに公開でアクセスするために使用されます。 | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `ode:createDate` | 決定応答メッセージが作成された時間。これはエポック時間として表されます。 | `"ode:createDate": 1566497582038` |

## チュートリアルビデオ {#video}

次のビデオは、「決定マネジメント」の構成要素の理解をサポートするためのものです。

>[!NOTE]
>
>このビデオは、Adobe Experience Platformで構築された Offer Decisioning アプリケーションサービスに当てはまります。ただし、Journey Optimizer のコンテキストでオファーを使用する際の一般的なガイダンスを提供しています。

>[!VIDEO](https://video.tv.adobe.com/v/329919/?quality=12)

## 次の手順

この API ガイドに従うことで、[!DNL Decisions] API を使用してオファーを作成し、配信できます。詳しくは、[決定マネジメントの概要](../../../offers/get-started/starting-offer-decisioning.md)をご覧ください。
