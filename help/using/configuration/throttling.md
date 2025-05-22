---
solution: Journey Optimizer
product: journey optimizer
title: Throttling API
description: Throttling API の使用方法を学ぶ
feature: Journeys, API
role: User
level: Beginner
keywords: 外部, API, Optimizer, キャッピング
exl-id: b837145b-1727-43c0-a0e2-bf0e8a35347c
source-git-commit: 9f801b1fdcab38bffff851675eca5e2fb61dfbf9
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 81%

---

# Throttling API の使用

Throttling API を使用すると、スロットル設定を作成、設定および監視して、1 秒あたりに送信されるイベントの数を制限できます。

この節では、API の使用方法に関する全体的な情報を示します。API について詳しくは、[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/)を参照してください。

## 必読

* **組織ごとに 1 つの設定：** 現在、組織ごとに 1 つの設定のみが許可されています。 設定は、（ヘッダーの `x-sandbox-name` を通じて指定される）実稼動サンドボックスで定義する必要があります。
* **組織レベルのアプリケーション：** 設定は組織レベルで適用されます。
* **API 制限処理：** API で設定された制限に達すると、以降のイベントは最大 6 時間キューに入れられます。 この値は変更できません。
* **`maxHttpConnections`パラメーター：** 「maxHttpConnections」パラメーターは、キャッピング API で使用できるオプションのパラメーターで、Journey Optimizerが外部システムに対して開く接続数を制限することができます。 [Capping API の使用方法を学ぶ ](../configuration/capping.md)

  接続数を制限するだけでなく、これらの外部呼び出しをスロットルする場合は、同じエンドポイントに、スロットルとキャッピングの 2 つの設定を設定できます。 1 つのエンドポイントに対して、両方の設定を共存させることができます。 スロットルされたエンドポイントに「maxHttpConnections」を設定するには、Throttling API を使用してスロットルしきい値を設定し、Capping API を使用して「maxHttpConnections」を設定します。 Capping API を呼び出す際に、キャッピングルールが実質的に有効にならないように、キャッピングしきい値をスロットルしきい値よりも大きく設定できます。

## スロットル API の説明とPostman コレクション {#description}

次の表に、スロットル API で使用できるコマンドを示します。リクエストサンプル、パラメーター、応答形式などの情報について詳しくは、[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/journeys/)を参照してください。

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | スロットル設定のリストを取得します |
| [!DNL POST] | /throttlingConfigs | スロットル設定を作成します |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | スロットル設定をデプロイします |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | スロットル設定のデプロイを解除します |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | スロットル設定をデプロイできるかどうかを確認します |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | スロットル設定を更新します |
| [!DNL GET] | /throttlingConfigs/`{uid}` | スロットル設定を取得します |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | スロットル設定を削除します |

また、テスト設定に役立つ Postman コレクションについて詳しくは、[こちら](https://github.com/AdobeDocs/JourneyAPI/blob/master/postman-collections/Journeys_Throttling-API_postman-collection.json)を参照してください。

このコレクションは、__[Adobe I/O コンソールの統合](https://console.adobe.io/integrations)／試す／Postman 用にダウンロード__&#x200B;経由で生成された Postman 変数コレクションを共有するように設定されています。これにより、選択した統合値を含む Postman 環境ファイルが生成されます。

ダウンロードして Postman にアップロードしたら、`{JO_HOST}`、`{BASE_PATH}` および `{SANDBOX_NAME}` の 3 つの変数を追加する必要があります。
* `{JO_HOST}`：[!DNL Journey Optimizer]ゲートウェイ URL。
* `{BASE_PATH}`：API のエントリポイント。
* `{SANDBOX_NAME}`：API 操作が行われるサンドボックス名に対応するヘッダー **x-sandbox-name**（例えば、「prod」）。詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

## スロットル設定{#configuration}

スロットル設定の構造は次のとおりです。**name** 属性と **description** 属性はオプションです。

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

例：

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

>[!IMPORTANT]
>
>設定は、**deploy** エンドポイントを呼び出した後にのみアクティブになります。

## エラー

設定を作成または更新する際に、プロセスは指定された設定を検証し、設定の一意の ID で識別される検証ステータス（次のいずれか）を返します。

```
"ok" or "error"
```

>[!IMPORTANT]
>
>属性 **maxThroughput**、**urlPattern** および **methods** は必須です。
>
>**maxThroughput** 値は 200～5000 の範囲で設定する必要があります。

スロットル設定を作成、削除またはデプロイする際に、次のエラーが発生する場合があります。

* **ERR_THROTTLING_CONFIG_100**：スロットル設定 : `<mandatory attribute>` は必須です
* **ERR_THROTTLING_CONFIG_101**：スロットル設定 : maxThroughput は必須で、200 以上 5000 以下にする必要があります
* **ERR_THROTTLING_CONFIG_104**：スロットル設定 : 不正な URL パターンです
* **ERR_THROTTLING_CONFIG_105**：スロットル設定 : URL パターンのホスト部分ではワイルドカードは使用できません
* **ERR_THROTTLING_CONFIG_106**：スロットル設定 : 無効なペイロードです
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR : 1456**、「デプロイ済みのスロットル設定は削除できません。デプロイを解除してから削除します」
* **THROTTLING_CONFIG_DELETE_ERROR : 1457**、「スロットル設定を削除できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_DEPLOY_ERROR : 1458**、「スロットル設定をデプロイできません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_UNDEPLOY_ERROR : 1459**、「スロットル設定のデプロイを解除できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_GET_ERROR : 1460**、「スロットル設定を取得できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR : 1461**、「スロットル設定を更新できません : ランタイムバージョンがアクティブではありません」
* **THROTTLING_CONFIG_UPDATE_ERROR : 1462**、「スロットル設定を更新できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR : 1463**、「スロットル設定に対する操作が許可されていません : 実稼動以外のサンドボックスです」
* **THROTTLING_CONFIG_CREATE_ERROR : 1464**、「スロットル設定を作成できません : 予期しないエラーが発生しました」
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR : 1465**、「スロットル設定を作成できません : 1 組織あたり 1 つの設定のみ許可されます」
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR : 14466**、「スロットル設定をデプロイできません : 既にデプロイされています」
* **THROTTLING_CONFIG_NOT_FOUND_ERROR : 14467**、「スロットル設定が見つかりません」
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR : 14468**、「スロットル設定のデプロイを解除できません : まだデプロイされていません」

**エラーの例**

実稼動以外のサンドボックスで設定を作成しようとした場合：

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

指定したサンドボックスが存在しない場合：

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

別の設定を作成しようとした場合：

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## ランタイムレベルでの設定のライフサイクル {#config}

設定のデプロイを解除すると、設定がランタイムレベルで非アクティブとマークされ、保留中のイベントは引き続き 24 時間処理されます。その後、ランタイムサービスで削除されます。

設定のデプロイを解除した後は、設定を更新して再デプロイできます。これにより、新しいランタイム設定が作成され、今後のアクションの実行で考慮されます。

既にデプロイされている設定を更新すると、新しい値が直ちに考慮されます。基になるシステムリソースは、自動的に適応されます。これは、設定をデプロイ解除してから再デプロイする場合に比べて最適です。

## 応答の例 {#responses}

**作成 - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**更新 - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**読み取り（更新後）- GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**読み取り（デプロイ後）- GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```

## ユースケース {#uc}

この節では、[!DNL Journey Optimizer] でスロットル設定を管理するための主なユースケースと、そのユースケースを実装するために必要な関連 API コマンドについて説明します。

各 API コマンドについて詳しくは、[API の説明と Postman コレクション](#description)を参照してください。

+++新しいスロットル設定の作成とデプロイ

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`create`** - 新しい設定を作成します。
1. **`candeploy`** - 設定をデプロイできるかどうかを確認します。
1. **`deploy`** - 設定をデプロイします。

+++

+++スロットル設定の更新とデプロイ（まだデプロイされていません）

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`get`** - 特定の設定の詳細を取得します。
1. **`update`** - 設定を変更します。
1. **`candeploy`** - デプロイメントの実施要件を確認します。
1. **`deploy`** - 設定をデプロイします。

+++

+++デプロイ済みのスロットル設定のデプロイ解除と削除

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`undeploy`** - 設定をデプロイ解除します。
1. **`delete`** - 設定を削除します。

+++

+++デプロイ済みのスロットル設定の削除

1 回の API 呼び出しのみで、`forceDelete` パラメーターを使用して設定をデプロイ解除および削除できます。

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`delete`（`forceDelete` パラメーターを使用）**- デプロイ済みの設定を 1 つの手順で強制的に削除します。

+++

+++既にデプロイ済みのスロットル設定の更新

>[!NOTE]
>
>更新前に設定のデプロイを解除する必要はありません

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`get`** - 特定の設定の詳細を取得します。
1. **`update`** - 設定を変更します。

+++
