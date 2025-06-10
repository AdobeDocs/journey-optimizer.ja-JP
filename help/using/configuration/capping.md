---
solution: Journey Optimizer
product: journey optimizer
title: Capping API
description: Capping API の使用方法を学ぶ
feature: Journeys, API
role: User
level: Beginner
keywords: 外部, API, Optimizer, キャッピング
exl-id: 377b2659-d26a-47c2-8967-28870bddf5c5
source-git-commit: 9f801b1fdcab38bffff851675eca5e2fb61dfbf9
workflow-type: ht
source-wordcount: '736'
ht-degree: 100%

---

# Capping API の使用 {#work}

Capping API を使用すると、キャッピング設定を作成、設定および監視できます。

この節では、API の使用方法に関する全体的な情報を示します。API について詳しくは、[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/)を参照してください。

## Capping API の説明と Postman コレクション {#description}

次の表に、Capping API で使用できるコマンドを示します。リクエストサンプル、パラメーター、応答形式などの情報について詳しくは、[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/journeys/)を参照してください。

| メソッド | パス | 説明 |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | エンドポイントキャッピング設定のリストの取得 |
| [!DNL POST] | /endpointConfigs | エンドポイントキャッピング設定の作成 |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | エンドポイントキャッピング設定のデプロイ |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | エンドポイントキャッピング設定のデプロイ解除 |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | エンドポイントキャッピング設定をデプロイできるかどうかの確認 |
| [!DNL PUT] | /endpointConfigs/`{uid}` | エンドポイントキャッピング設定の更新 |
| [!DNL GET] | /endpointConfigs/`{uid}` | エンドポイントキャッピング設定の取得 |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | エンポイントキャッピング設定の削除 |

設定を作成または更新すると、ペイロードの構文と整合性を保証するチェックが自動的に実行されます。
問題が発生した場合は、設定を修正するのに役立つ警告またはエラーが返されます。

また、テスト設定に役立つ Postman コレクションについて詳しくは、[こちら](https://github.com/AdobeDocs/JourneyAPI/blob/master/postman-collections/Journeys_Capping-API_postman-collection.json)を参照してください。

このコレクションは、__[Adobe I/O コンソールの統合](https://console.adobe.io/integrations)／試す／Postman 用にダウンロード__&#x200B;経由で生成された Postman 変数コレクションを共有するように設定されています。これにより、選択した統合値を含む Postman 環境ファイルが生成されます。

ダウンロードして Postman にアップロードしたら、`{JO_HOST}`、`{BASE_PATH}` および `{SANDBOX_NAME}` の 3 つの変数を追加する必要があります。
* `{JO_HOST}`：[!DNL Journey Optimizer]ゲートウェイ URL。
* `{BASE_PATH}`：API のエントリポイント。
* `{SANDBOX_NAME}`：API 操作が行われるサンドボックス名に対応するヘッダー **x-sandbox-name**（例えば、「prod」）。詳しくは、[サンドボックスの概要](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ja)を参照してください。

## エンドポイントの設定

エンドポイント設定の基本構造は次のとおりです。

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>**maxHttpConnections** パラメーターは、オプションです。これを使用すると、Journey Optimizer が外部システムに対して開く接続の数を制限できます。
>
>設定できる最大値は 400 です。何も指定しない場合、システムは動的なスケーリングに応じて、最大で数千の接続を開く可能性があります。
>
>キャッピング設定をデプロイする際に、「maxHttpConnection」値を指定しない場合、デプロイ済みの設定にデフォルトの「maxHttpConnection = -1」が追加されます。つまり、Journey Optimizer はデフォルトのシステム値を使用します。

例：

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  }
}
```

>[!IMPORTANT]
>
>設定は、**デプロイ**&#x200B;エンドポイントを呼び出した後にのみアクティブになります。

## 警告とエラー

**canDeploy**&#x200B;メソッドを呼び出す際、プロセスは設定を検証し、次のいずれかの一意の ID によって識別される検証ステータスを返します。

```
"ok" or "error"
```

潜在的なエラーは次のとおりです。

* **ERR_ENDPOINTCONFIG_100**：キャッピング設定：URL が見つからないか、無効です
* **ERR_ENDPOINTCONFIG_101**：キャッピング設定：不正な URL です
* **ERR_ENDPOINTCONFIG_102**：キャッピングの設定：不正な URL です：host:port で許可されていない URL のワイルド文字
* **ERR_ENDPOINTCONFIG_103**：キャッピング設定：HTTP メソッドがありません
* **ERR_ENDPOINTCONFIG_104**：キャッピング設定：呼び出しの評価が定義されていません
* **ERR_ENDPOINTCONFIG_107**：キャッピング設定：無効な最大呼び出し数（maxCallsCount）です
* **ERR_ENDPOINTCONFIG_108**：キャッピング設定：無効な最大呼び出し数（periodInMs）です
* **ERR_ENDPOINTCONFIG_111**：キャッピング設定：エンドポイント設定を作成できません：無効なペイロードです
* **ERR_ENDPOINTCONFIG_112**：キャッピング設定：エンドポイント設定を作成できません：JSON ペイロードが予想されます
* **ERR_AUTHORING_ENDPOINTCONFIG_1**：無効なサービス名 `<!--<given value>-->`：「dataSource」または「action」である必要があります

潜在的な警告は次のとおりです。

**ERR_ENDPOINTCONFIG_106**：キャッピング設定：最大 HTTP 接続数が定義されていません：デフォルトでは制限なし

## ユースケース

この節では、[!DNL Journey Optimizer] でキャッピング設定を管理する主なユースケースと、そのユースケースを実装するために必要な関連 API コマンドについて説明します。

各 API コマンドについて詳しくは、[API の説明と Postman コレクション](#description)を参照してください。

+++新しいキャッピング設定の作成とデプロイ

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`create`** - 新しい設定を作成します。
1. **`candeploy`** - 設定をデプロイできるかどうかを確認します。
1. **`deploy`** - 設定をデプロイします。

+++

+++キャッピング設定の更新とデプロイ（まだデプロイされていません）

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`get`** - 特定の設定の詳細を取得します。
1. **`update`** - 設定を変更します。
1. **`candeploy`** - デプロイメントの実施要件を確認します。
1. **`deploy`** - 設定をデプロイします。

+++

+++デプロイ済みのキャッピング設定のデプロイ解除と削除

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`undeploy`** - 設定をデプロイ解除します。
1. **`delete`** - 設定を削除します。

+++

+++1 つの手順でのデプロイ済みのキャッピング設定の削除

1 回の API 呼び出しでのみ、`forceDelete` パラメーターを使用して設定をデプロイ解除および削除できます。

使用する API 呼び出し：

1. **`list`** - 既存の設定を取得します。
1. **`delete`（`forceDelete` パラメーターを使用）**- デプロイ済みの設定を 1 つの手順で強制的に削除します。

+++

+++既にデプロイ済みのキャッピング設定の更新

>[!NOTE]
>
>既にデプロイされている設定を更新する場合は、再デプロイが必要です。

使用する API 呼び出し：
1. **`list`** - 既存の設定を取得します。
1. **`get`** - 特定の設定の詳細を取得します。
1. **`update`** - 設定を変更します。
1. **`undeploy`** - 変更を適用する前に設定をデプロイ解除します。
1. **`candeploy`** - デプロイメントの実施要件を確認します。
1. **`deploy`** - 更新された設定をデプロイします。

+++
