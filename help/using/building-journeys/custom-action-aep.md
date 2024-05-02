---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションを使用した AEP へのジャーニーイベントの書き込み
description: カスタムアクションを使用した AEP へのジャーニーイベントの書き込み
feature: Journeys, Use Cases, Custom Actions
topic: Content Management
role: Developer, Data Engineer
level: Experienced
source-git-commit: 0571a11eabffeb5e318bebe341a8df18da7db598
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# ユースケース：カスタムアクションを使用してExperience Platformにジャーニーイベントを書き込む{#custom-action-aep}

このユースケースでは、カスタムアクションと認証済み呼び出しを使用して、ジャーニーからAdobe Experience Platformにカスタムイベントを書き込む方法を説明します。

## I/O プロジェクトの設定

1. Adobe Developerコンソールで、 **プロジェクト** そして、あなたの I/O プロジェクトを開きます。

1. が含まれる **資格情報** セクションで、をクリック **OAuth サーバー間**.

   ![](assets/custom-action-aep-1.png)

1. クリック **cURL 表示コマンド**.

   ![](assets/custom-action-aep-2.png)

1. cURL コマンドをコピーし、client_id、client_secret、grant_type および scope を格納します。

```
curl -X POST 'https://ims-na1.adobelogin.com/ims/token/v3' -H 'Content-Type: application/x-www-form-urlencoded' -d 'grant_type=client_credentials&client_id=1234&client_secret=5678&scope=openid,AdobeID,read_organizations,additional_info.projectedProductContext,session'
```

## HTTP API インレットを使用したソースの設定

1. Adobe Experience Platformでエンドポイントを作成し、ジャーニーからデータを書き込みます。

1. Adobe Experience Platformで、 **ソース**、の下 **接続** 左メニューの 次の下 **HTTP API**&#x200B;を選択し、 **データを追加**.

   ![](assets/custom-action-aep-3.png)

1. を選択 **新しいアカウント** 認証を有効にします。 クリックする **ソースに接続**.

   ![](assets/custom-action-aep-4.png)

1. クリックする **次** データを書き込むデータセットを選択します。 クリック **次** および **終了**.

   ![](assets/custom-action-aep-5.png)

1. 新しく作成したデータフローを開きます。 スキーマペイロードをコピーしてメモ帳に保存します。

```
{
"header": {
"schemaRef": {
"id": "https://ns.adobe.com/<your_org>/schemas/<schema_id>",
"contentType": "application/vnd.adobe.xed-full+json;version=1.0"
},
"imsOrgId": "<org_id>",
"datasetId": "<dataset_id>",
"source": {
"name": "Custom Journey Events"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"id": "https://ns.adobe.com/<your_org>/schemas/<schema_id>",
"contentType": "application/vnd.adobe.xed-full+json;version=1.0"
}
},
"xdmEntity": {
"_id": "test1",
"<your_org>": {
"journeyVersionId": "",
"nodeId": "", "customer_Id":""
},
"eventMergeId": "",
"eventType": "",
"producedBy": "self",
"timestamp": "2018-11-12T20:20:39+00:00"
}
}
}
```

## カスタムアクションの設定

1. Adobe Journey Optimizerを開き、 **設定**、の下 **管理** 左メニューの 次の下 **アクション**&#x200B;を選択し、 **管理** をクリックして、 **アクションを作成**.

1. URL を設定し、Post メソッドを選択します。

   `https://dcs.adobedc.net/collection/<collection_id>?syncValidation=false`

1. ヘッダー（Content-Type、Charset、sandbox-name）が設定されていることを確認します。

   ![](assets/custom-action-aep-7bis.png)

### 認証の設定

1. 「」を選択します **タイプ** as **カスタム** 次のペイロードで置き換えます。

1. client_secret、client_id、scope、grant_type を（以前に使用した IO プロジェクトペイロードから）貼り付けます。

   ```
   {
   "type": "customAuthorization",
   "authorizationType": "Bearer",
   "endpoint": "https://ims-na1.adobelogin.com/ims/token/v3",
   "method": "POST",
   "headers": {},
   "body": {
   "bodyType": "form",
   "bodyParams": {
   "grant_type": "client_credentials",
   "client_secret": "********",
   "client_id": "<client_id>",
   "scope": "openid,AdobeID,read_organizations,additional_info.projectedProductContext,session"
   }
   },
   "tokenInResponse": "json://access_token",
   "cacheDuration": {
   "duration": 28000,
   "timeUnit": "seconds"
   }
   }
   ```

1. の使用 **クリックして認証をテスト** 接続をテストするボタン。

   ![](assets/custom-action-aep-8.png)

### ペイロードの設定

1. が含まれる **リクエスト** および **応答** フィールドに、以前に使用したソース接続からペイロードを貼り付けます。

   ```
   {
   "xdmMeta": {
   "schemaRef": {
   "id": "https://ns.adobe.com/<your_org>/schemas/<schema_id>",
   "contentType": "application/vnd.adobe.xed-full+json;version=1.0"
   }
   },
   "xdmEntity": {
   "_id": "/uri-reference",
   "<your_org>": {
   "journeyVersionId": "Sample value",
   "nodeId": "Sample value",
   "customer_Id":""
   },
   "eventMergeId": "Sample value",
   "eventType": "advertising.completes,
   "producedBy": "self",
   "timestamp": "2018-11-12T20:20:39+00:00"
   }
   }
   ```

1. フィールド設定の変更元 **定数** 対象： **変数** （動的に入力されるフィールド用）。 カスタムアクションを保存します。

## ジャーニー

1. 最後に、ジャーニーでこのカスタムアクションを使用して、カスタムジャーニーイベントを記述します。

1. ユースケースに従って、ジャーニーバージョン ID、ノード ID、ノード名、その他の属性を設定します。

   ![](assets/custom-action-aep-9.png)


