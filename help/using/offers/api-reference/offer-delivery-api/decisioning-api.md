---
title: 配信オファー
description: 意思決定管理とは、ビジネスロジックと意思決定ルールを使用して、チャネルやアプリケーションの間でエンドユーザーがカスタマイズした特典を作成および配信できる、サービスおよび UI プログラムの集合体です。
feature: Offers
topic: Integrations
role: Data Engineer
level: Experienced
exl-id: 692d0aae-6fa1-40b8-a35f-9845d78317a3
source-git-commit: d3a22f223353dfa5d43acab400cea3d5c314662f
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 0%

---

# Decisioning API を使用した提供を提供します。 {#decisioning-api}

意思決定管理を使用すると、ビジネスロジックと意思決定規則を使用して、チャネルやアプリケーションにわたってエンドユーザーがカスタマイズした特典を作成および配信することができます。 オファーとは、キャンペーンに関連付けられたルールが含まれるマーケティングメッセージのことです。これによって、誰に提供されるかを指定することができます。

API に対し [!DNL Decisioning] て POST 要求を行うことによって、オファーを作成および配信することができます。

このチュートリアルでは、特に意思決定管理について、Api について理解しておく必要があります。 詳しくは、『意思決定管理 API デベロッパーガイド』 ](../getting-started.md) を参照してください [ 。このチュートリアルでは、一意の配置 ID と ID の値を使用可能にする必要もあります。 これらの値を取得していない場合は、配置 ](../offers-api/placements/create.md) を作成し [ 、決定 ](../activities-api/activities/create.md) を作成するための [ チュートリアルを参照してください。

➡️  [ ビデオでのこの機能の検出](#video)

## Accept ヘッダーと Content-type ヘッダー {#accept-and-content-type-headers}

次の表は、要求ヘッダー内の Content-type *および* Accept *フィールドを構成* する有効な値を示しています。

| ヘッダー名 | 数値 |
| ----------- | ----- |
| よう | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"` |
| コンテンツタイプ | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"` |

**API フォーマット**

```https
POST /{ENDPOINT_PATH}/{CONTAINER_ID}/decisions
```

| 指定 | つい | 一 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ Api の endpoint path。 | `https://platform.adobe.io/data/core/ode/` |
| `{CONTAINER_ID}` | 決定が配置されているコンテナを指定します。 | `e0bd8463-0913-4ca1-bd84-6309134ca1f6` |

**要求**

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

| &quot; | つい | 一 |
| -------- | ----------- | ------- |
| `xdm:propositionRequests` | このオブジェクトには、配置および決定識別子が含まれています。 |
| `xdm:propositionRequests.xdm:placementId` | 一意の配置識別子。 | `"xdm:placementId": "xcore:offer-placement:ffed0456"` |
| `xdm:propositionRequests.xdm:activityId` | 一意の決定識別子。 | `"xdm:activityId": "xcore:offer-activity:ffed0123"` |
| `xdm:itemCount` | 返されるオファー数を指定します。 最大数は30です。 | `"xdm:itemCount": 2` |
| `xdm:profiles` | このオブジェクトは、決定が要求されたプロファイルに関する情報を保持しています。 API 要求の場合は、1つのプロファイルが格納されます。 |
| `xdm:profiles.xdm:identityMap` | このオブジェクトは、アイデンティティの名前空間統合コードに基づいてエンドユーザー id のセットを保持します。 Id マップには、名前空間ごとに複数の id を渡すことができます。 名前空間について詳しくは、このページ ](../../../segment/get-started-identity.md) を参照して [ ください。 | `Email: [{"xdm:id": "123@abc.com"}]` |
| `xdm:profiles.xdm:decisionRequestId` | プロファイル決定要求を一意に識別するために使用できる、クライアントによって生成される ID。 この ID は応答にエコーバックされ、決定の結果に影響を与えることはありません。 | `"xdm:decisionRequestId": "0AA00002-0000-1337-c0de-c0fefec0fefe"` |
| `xdm:allowDuplicatePropositions` | このオブジェクトは、デデュープルールの制御構造を行います。 これは、同じオプションが特定の次元にわたって提示できるかどうかを示す一連のフラグで構成されています。 True に設定されたフラグに設定されている場合は、重複が許可されているので、フラグで指定されているカテゴリーを越えて削除することはできません。 フラグが false に設定されている場合は、決定エンジンが次元に対して同じ操作を実行するのではなく、いずれかのサブ決定について次に最適なオプションを選択する必要があることを意味します。 |
| `xdm:allowDuplicatePropositions.xdm:acrossActivities` | True に設定されている場合は、複数の決定に同じオプションが割り当てられることがあります。 | `"xdm:acrossActivities": true` |
| `xdm:allowDuplicatePropositions.xdm:acrossPlacements` | True に設定されている場合は、複数の配置に同じオプションが割り当てられることがあります。 | `"xdm:acrossPlacements": true` |
| `xdm:mergePolicy.xdm:id` | プロファイルアクセスサービスによって返されるデータを管理するために使用するマージポリシーを指定します。 そのような情報が要求に含まれていない場合、意思決定管理がプロファイルアクセスサービスによって渡されることはありません。それ以外の場合は、呼び出し元によって提供された id が渡されます。 | `"xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"` |
| `xdm:responseFormat` | 応答コンテンツをフォーマットする一連のフラグ。 |
| `xdm:responseFormat.xdm:includeContent` | ブール値。に `true` 設定されている場合は、コンテンツが応答に含まれます。 | `"xdm:includeContent": true` |
| `xdm:responseFormat.xdm:includeMetadata` | どのような追加のメタデータを返すかを指定するために使用されるオブジェクト。 このプロパティが含まれていない場合は、 `xdm:id` `repo:etag` 初期設定で戻り値が返されます。 | `name` |
| `xdm:responseFormat.xdm:activity` | このフラグは、に `xdm:activity` 返される特定のメタデータ情報を識別します。 | `name` |
| `xdm:responseFormat.xdm:option` | このフラグは、に `xdm:option` 返される特定のメタデータ情報を識別します。 | `name`, `characteristics` |
| `xdm:responseFormat.xdm:placement` | このフラグは、に `xdm:placement` 返される特定のメタデータ情報を識別します。 | `name`, `channel`, `componentType` |

**対し**

応答が成功した場合は、その一意 `xdm:propositionId` の情報が含まれます。

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

| &quot; | つい | 一 |
| -------- | ----------- | ------- |
| `xdm:propositionId` | XDM DecisionEvent に関連付けられた提案エンティティの一意の識別子。 | `"xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8"` |
| `xdm:propositions` | このオブジェクトには、1つの意思決定命題が含まれています。 この決定には、複数のオプションを返すことができます。 オプションが見つからない場合は、その意思決定の代替オファーが返されます。 1つのディシジョンプロポジションには、プロパティまたはプロパティの `fallback` いずれか `options` が含まれています。このプロパティが指定されて `options` いる場合、プロパティを空にすることはできません。 |
| `xdm:propositions.xdm:activity` | このオブジェクトには、決定の一意の識別子が格納されています。 | `"xdm:id": "xcore:activity:ffed0123"` |
| `xdm:propositions.xdm:placement` | このオブジェクトには、オファーを配置するための一意の識別子が含まれています。 | `"xdm:id": "xcore:placement:ffed0456"` |
| `xdm:propositions.xdm:options` | このオブジェクトには、一意の識別子を含む1つのオプションが含まれています。 存在する場合は、このオブジェクトを空にすることはできません。 | `xdm:id": "xcore:personalized-option:ccc0111` |
| `xdm:propositions.xdm:options.@type` | コンポーネントの型を定義します。 `@type` クライアントの処理契約の役割を果たします。 エクスペリエンスがアセンブルされると、コンポーザーは、特定のタイプのコンポーネントを検索します。 | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:content` | 応答コンテンツの形式。 | 応答の内容: `text` 、 `html block` 、または `image link` |
| `xdm:score` | オプションまたは決断に関連付けられたランキング関数によって計算されたオプションのスコアです。 このフィールドは、ランク付け中に特典の得点を決定するためにランキング関数が必要になった場合に API によって返されます。 | `"xdm:score": 45.65` |
| `xdm:propositions.xdm:fallback` | このオブジェクトには、一意の識別子を含む1つのフォールバックオファーが含まれています。 | `"xdm:id": "xcore:fallback:ccc0222"` |
| `xdm:propositions.xdm:fallback.dc:format` | リソースの物理的またはディジタル manifestation 通常、フォーマットには、リソースのメディアタイプが含まれている必要があります。 フォーマットを使用して、リソースを表示または操作するために必要なソフトウェア、ハードウェア、またはその他の機器を決定することができます。 制限された語彙、例えば、コンピューターのメディアフォーマットを定義するインターネットメディアタイプ ](http://www.iana.org/assignments/media-types/) のリストの [ 中から、値を選択することをお勧めします。 | `"dc:format": "image/png"` か `"image/jpeg"` |
| `xdm:propositions.xdm:fallback.xdm:deliveryURL` | コンテンツ配信ネットワークまたはサービスのエンドポイントからアセットを読み取るオプションの URL です。 この URL を使用して、ユーザーエージェントから一般に公開されたアセットにアクセスすることができます。 | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `ode:createDate` | 意思決定応答メッセージが作成された時刻 これは、エポック時間を表しています。 | `"ode:createDate": 1566497582038` |

## チュートリアルビデオ {#video}

以下のビデオは、デシジョンマネジメントのコンポーネントについての理解をサポートすることを目的としています。

>[!NOTE]
>
>このビデオは、Adobe エクスペリエンスプラットフォームに組み込まれた Offer Decisioning application サービスに適用されます。 ただし、この機能は、旅のオプティマイザーのコンテキストでオファーを使用するための一般的なガイダンスを提供します。

>[!VIDEO](https://video.tv.adobe.com/v/329919/?quality=12)

## 次の手順 {#next-steps}

この API ガイドを使用すると、この api を使用 [!DNL Decisions] するオファーを作成し、提供しています。 詳細については、「意思決定管理 ](../../../offers/get-started/starting-offer-decisioning.md) 」の概要を参照してください [ 。
