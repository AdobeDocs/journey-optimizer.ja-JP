---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: オファーの配信
description: 意思決定管理とは、マーケターがビジネスロジックと意思決定ルールを使用して、チャネルやアプリケーションをまたいでパーソナライズされたエンドユーザーのオファー体験を作成および提供できるサービスとUI プログラムのコレクションです。
badge: label="レガシー" type="Informative"
feature: Decision Management, API
topic: Integrations
role: Developer
level: Experienced
exl-id: 692d0aae-6fa1-40b8-a35f-9845d78317a3
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/jhf2EpgMU35YmRWeatijWUFz3KwwjFfKP8lHtX8eyEU
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: c132d929-fa62-4271-803e-b823be07b914
  - id: ed0d8d0e-04b9-4326-be72-a0fbca265377
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
  - id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 1153
ht-degree: 0%

---

# Decisioning APIを使用したオファーの配信 {#decisioning-api}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer]の新しい決定機能である決定機能が、コードベースのエクスペリエンスとメールチャネルで利用できるようになりました。 [詳細情報](../../../experience-decisioning/gs-experience-decisioning.md)

意思決定管理では、ビジネスロジックと意思決定ルールを利用して、チャネルやアプリケーションをまたいで、エンドユーザーにパーソナライズされたオファー体験を構築し、提供できます。 オファーとは、オファーを表示する資格のあるユーザーを指定するルールが関連付けられている場合があるマーケティングメッセージです。

[!DNL Decisioning] APIにPOST リクエストを行うことで、オファーを作成および配信できます。

このチュートリアルでは、特に意思決定管理に関するAPIに関する実用的な理解が必要です。 詳しくは、[意思決定管理API開発者ガイド &#x200B;](../getting-started.md)を参照してください。 このチュートリアルでは、一意のプレースメント IDと決定IDの値を使用できる必要もあります。 これらの値を取得していない場合は、[&#x200B; プレースメントの作成](../offers-api/placements/create.md)および[決定の作成](../activities-api/activities/create.md)のチュートリアルを参照してください。

>[!NOTE]
>
>**Decisioning リクエストでコンテキストデータを渡す**
>
>Decisioning リクエストにコンテキストデータ（デバイスタイプ、場所、ユーザー設定など）を渡して、動的な適格性ルールを作成し、リアルタイムの条件にもとづいてパーソナライズされたオファーを配信できます。 [&#x200B; コンテキストデータと決定リクエストについて詳しく見る](../../context-data-decisioning.md)

## 必須ヘッダー {#required-headers}

次の表は、リクエストヘッダーの&#x200B;*Content-Type*&#x200B;および&#x200B;*Accept* フィールドを構成する有効な値を示しています。

| ヘッダー名 | 値 |
| ----------- | ----- |
| 承認 | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"` |
| コンテンツタイプ | `application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"` |
| 認証 | `Bearer {ACCESS_TOKEN}` |
| x-gw-ims-org-id | `{IMS_ORG}` |
| x-sandbox-name | `{SANDBOX_NAME}` |
| x-api-key | `{API_KEY}` |

* ペイロード（POST、PUT、PATCH）を含むすべてのリクエストには、content-type ヘッダーが必要です


>[!NOTE]
>
>権限のチェックは、個々のサンドボックスには適用されません。 呼び出し元が有効なトークンを提示している限り、配信APIは通過します。

## API リクエスト {#request}

### API形式

```https
POST /{ENDPOINT_PATH}/decisions
```

| パラメーター | 効果 | 例 |
| --------- | ----------- | ------- |
| `{ENDPOINT_PATH}` | リポジトリ APIのエンドポイントパス。 | `https://platform.adobe.io/data/core/ods` |

### リクエスト

```shell
curl -X POST 'https://platform.adobe.io/data/core/ods/decisions' \
-H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
-H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"' \
-H 'Authorization: Bearer {ACCESS_TOKEN}....' \
-H 'x-api-key: {API_KEY}' \
-H 'x-gw-ims-org-id: {IMS_ORG}' \
-H 'x-sandbox-name: {SANDBOX_NAME}' \
-H 'x-sandbox-id: {SANDBOX_ID}' \
-H 'x-request-id: e9ac8d7e-3e77-4b38-8726-555ef1737b32-example' \
-d '{
    "xdm:propositionRequests": [
        {
            "xdm:activityId": "dps:offer-activity:15ded04b1786ea27",
            "xdm:placementId": "dps:offer-placement:15d9bc01d35e1238"
        }
    ],
    "xdm:profiles": [
        {
            "xdm:identityMap": {
                "Email": [
                    {
                        "xdm:id": "example@adobe.com",
                        "primary": true
                    }
                ]
            }
        }
    ],
    "xdm:allowDuplicatePropositions": {
        "xdm:acrossActivities": true,
        "xdm:acrossPlacements": true
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

| プロパティ | 効果 | 例 |
| -------- | ----------- | ------- |
| `xdm:propositionRequests` | このオブジェクトには、プレースメント識別子と決定識別子が含まれます。 |  |
| `xdm:propositionRequests.xdm:placementId` | 一意のプレースメント ID。 | `"xdm:placementId": "dps:offer-placement:ffed0456"` |
| `xdm:propositionRequests.xdm:activityId` | 一意の意思決定識別子。 | `"xdm:activityId": "dps:offer-activity:ffed0123"` |
| `xdm:itemCount` | 返されるオファーの数。 最大数は30です。 | `"xdm:itemCount": 2` |
| `xdm:profiles` | このオブジェクトは、決定が要求されるプロファイルに関する情報を保持します。 API リクエストの場合、これには1つのプロファイルが含まれます。 |  |
| `xdm:profiles.xdm:identityMap` | このオブジェクトは、IDの名前空間統合コードに基づくエンドユーザーIDのセットを保持します。 ID マップは、各名前空間の複数のIDを持つことができます。 名前空間について詳しくは、[このページ &#x200B;](../../../audience/get-started-identity.md)を参照してください。 | `Email: [{"xdm:id": "123@abc.com"}]` |
| `xdm:profiles.xdm:decisionRequestId` | プロファイル決定リクエストを一意に識別するために使用できる、クライアントによって生成されたID。 このIDは応答にエコーされ、決定の結果には影響しません。 | `"xdm:decisionRequestId": "0AA00002-0000-1224-c0de-cjf98Csj43"` |
| `xdm:allowDuplicatePropositions` | このオブジェクトは、重複排除ルールの制御構造です。 特定のディメンションにわたって同じオプションを提案できるかどうかを示す一連のフラグで構成されています。 trueに設定されているフラグは、重複を許可し、フラグで示されるカテゴリ全体で削除しないでください。 falseに設定されたフラグは、ディメンション全体で決定エンジンが同じ提案を行わず、代わりにサブディシジョンの1つに対する次善のオプションを選択することを意味します。 |  |
| `xdm:allowDuplicatePropositions.xdm:acrossActivities` | trueに設定すると、複数の決定に同じオプションが割り当てられる場合があります。 | `"xdm:acrossActivities": true` |
| `xdm:allowDuplicatePropositions.xdm:acrossPlacements` | trueに設定すると、複数のプレースメントに同じオプションが割り当てられる場合があります。 | `"xdm:acrossPlacements": true` |
| `xdm:enrichedAudience` | カスタムアップロード（CSV）オーディエンスをターゲットとしており、オファー決定応答のエンリッチメントデータを取得する場合は、このパラメーターを`true`に設定します。 [意思決定にCSV オーディエンスを使用する方法の詳細](../../custom-upload-decisioning.md#must-read) | `"xdm:enrichedAudience": true` |
| `xdm:mergePolicy.xdm:id` | プロファイルアクセスサービスから返されるデータを管理する結合ポリシーを指定します。 リクエストで指定されていない場合、意思決定管理はプロファイルアクセスサービスを渡しません。そうでない場合は、呼び出し元から提供されたIDを渡します。 | `"xdm:id": "5f3ed32f-eaf1-456c-b0f0-7b338c4cb18a"` |
| `xdm:responseFormat` | 応答コンテンツをフォーマットする一連のフラグ。 |  |
| `xdm:responseFormat.xdm:includeContent` | `true`に設定した場合、応答にコンテンツを含めるブール値。 | `"xdm:includeContent": true` |
| `xdm:responseFormat.xdm:includeMetadata` | 返される追加メタデータを指定するために使用されるオブジェクト。 このプロパティが含まれていない場合、`xdm:id`と`repo:etag`がデフォルトで返されます。 | `name` |
| `xdm:responseFormat.xdm:activity` | このフラグは、`xdm:activity`に対して返される特定のメタデータ情報を識別します。 | `name` |
| `xdm:responseFormat.xdm:option` | このフラグは、`xdm:option`に対して返される特定のメタデータ情報を識別します。 | `name`、`characteristics` |
| `xdm:responseFormat.xdm:placement` | このフラグは、`xdm:placement`に対して返される特定のメタデータ情報を識別します。 | `name`、`channel`、`componentType` |

### 応答

応答が成功すると、一意の`xdm:propositionId`を含む、提案に関する情報が返されます。

```json
{
  "xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8",
  "xdm:propositions": [
    {
      "xdm:activity": {
        "xdm:id": "dps:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "dps:placement:ffed0456",
        "repo:etag": 1
      },
      "xdm:options": [
        {
          "xdm:id": "dps:personalized-option:ccc0111",
          "repo:etag": 3,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>some html</html>"
        },
        {
          "xdm:id": "dps:personalized-option:ccc0222",
          "repo:etag": 5,
          "@type": "https://ns.adobe.com/experience/decisioning/content-component-html-template",
          "xdm:content": "<html>hello, world</html>",
          "xdm:score": 45.65
        }
      ]
    },
    {
      "xdm:activity": {
        "xdm:id": "dps:activity:ffed0123",
        "repo:etag": 4
      },
      "xdm:placement": {
        "xdm:id": "dps:placement:ffed0789",
        "repo:etag": 2
      },
      "xdm:fallback": {
        "xdm:id": "dps:fallback:ccc0222",
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

| プロパティ | 効果 | 例 |
| -------- | ----------- | ------- |
| `xdm:propositionId` | XDM DecisionEventに関連付けられた提案エンティティの一意の識別子。 | `"xdm:propositionId": "5d0ffb5e-dfc6-4280-99b6-0bf3131cb8b8"` |
| `xdm:propositions` | このオブジェクトには、1つの決定提案が含まれています。 決定に対して複数のオプションを返すことができます。 オプションが見つからない場合は、決定のフォールバックオファーが返されます。 単一の決定提案には、常に`options` プロパティまたは`fallback` プロパティが含まれます。 存在する場合、`options` プロパティを空にすることはできません。 |  |
| `xdm:propositions.xdm:activity` | このオブジェクトには、決定の一意の識別子が含まれます。 | `"xdm:id": "dps:activity:ffed0123"` |
| `xdm:propositions.xdm:placement` | このオブジェクトには、オファープレースメントの一意のIDが含まれます。 | `"xdm:id": "dps:placement:ffed0456"` |
| `xdm:propositions.xdm:options` | このオブジェクトには、一意のIDを含む単一のオプションが含まれます。 存在する場合、このオブジェクトを空にすることはできません。 | `xdm:id": "dps:personalized-option:ccc0111` |
| `xdm:propositions.xdm:options.@type` | コンポーネントのタイプを定義します。 `@type`は、クライアントの処理契約として機能します。 エクスペリエンスを組み立てると、コンポーザーは特定のタイプを持つコンポーネントを探します。 | `https://ns.adobe.com/experience/offer-management/content-component-imagelink` |
| `xdm:propositions.xdm:content` | 応答コンテンツの形式。 | 応答コンテンツには、`text`、`html block`または`image link`を指定できます |
| `xdm:score` | オプションまたは決定に関連付けられたランキング関数の結果として計算されるオプションのスコア。 ランキング関数がランキング中のオファーのスコアの決定に関与している場合、このフィールドはAPIによって返されます。 | `"xdm:score": 45.65` |
| `xdm:propositions.xdm:fallback` | このオブジェクトには、一意のIDを含む1つのフォールバックオファーが含まれます。 | `"xdm:id": "dps:fallback:ccc0222"` |
| `xdm:propositions.xdm:fallback.dc:format` | リソースの物理的またはデジタル表現。 通常、形式にはリソースのメディアタイプを含める必要があります。 この形式は、リソースの表示または操作に必要なソフトウェア、ハードウェアまたはその他の機器を決定するために使用できます。 コンピューターのメディア形式を定義する[&#x200B; インターネットメディアタイプ &#x200B;](https://www.iana.org/assignments/media-types/)のリストなど、制御されている語彙から値を選択することをお勧めします。 | `"dc:format": "image/png"`または`"image/jpeg"` |
| `xdm:propositions.xdm:fallback.xdm:deliveryURL` | コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを読み取るためのオプションのURL。 このURLは、ユーザーエージェントからアセットに公開でアクセスするために使用されます。 | `https://d37yhxrr0p3l3l.cloudfront.net/0fd0f090-a148-11ea-89e3-f1f2ad52f7e8/urn:aaid:sc:US:a68c86a6-9295-4940-a083-11916b665500/0/40d78a12-f8b6-3f07-8e67-7cb8ae2cc7ec` |
| `ode:createDate` | 決定応答メッセージが作成された時刻。 これはエポック時間として表されます。 | `"ode:createDate": 1566497582038` |

**応答コード**

次の表に、応答で返すことができるすべてのコードを示します。

| コード | 効果 |
|  ---  |  ---  |
| 200 | 成功： 特定の活動に対して決定が行われました |
| 400 | 無効なリクエストパラメーターです。 構文が正しくないため、リクエストをサーバーが理解できません。 |
| 403 | 禁止されている、不十分な権限です。 |
| 422 | 処理不可能なエンティティ。 ただし、セマンティックエラーのため、リクエストの構文は正しくありません。 |
| 429 | リクエストが多すぎます。 ユーザーが一定時間内に送信したリクエストが多すぎます。 |
| 500 | 内部サーバーエラー。 サーバーで予期しない状態が発生したため、リクエストを処理できませんでした。 |
| 503 | サーバーの過負荷のため、サービスを利用できません。 一時的な過負荷のため、サーバーは現在、リクエストを処理できません。 |

<!--
 
## Tutorial video {#video}

The following video is intended to support your understanding of the components of Decision Management.

>[!NOTE]
>
>This video applies to the Offer Decisioning application service built on Adobe Experience Platform. However, it provides generic guidance to use Offer in the context of Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/342831/?captions=jpn&quality=12)
-->

## 次のステップ {#next-steps}

このAPI ガイドに従って、[!DNL Decisions] APIを使用してオファーを作成および配信しました。 詳しくは、[意思決定管理の概要](../../../offers/get-started/starting-offer-decisioning.md)を参照してください。
