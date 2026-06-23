---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションを使用した AEP へのジャーニーイベントの書き込み
description: カスタムアクションを使用した AEP へのジャーニーイベントの書き込み
feature: Journeys, Use Cases, Custom Actions
topic: Content Management
role: Developer
level: Experienced
exl-id: 890a194f-f54d-4230-863a-fb2b924d716a
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/TbX3usHKfEM6WQPjFRjo2jCSb78rcbYEWWmV0tpGdj4
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2: id: b856530c-d60b-42d8-a19d-df2dfd7fe62aid: c2beecbb-b93e-4ae3-baa9-72adcdc06781id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: b5d14f7b40933f110ff666db858e976e5de711db
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 33%

---

# カスタムアクションを使用した Experience Platform のジャーニーイベントの書き込み {#custom-action-aep}

>[!BEGINSHADEBOX]

**このページ：** カスタムアクションと認証済みAPI呼び出しを使用して、ジャーニーからAdobe Experience Platformにカスタムジャーニーイベントを書き込む方法を説明します。

>[!ENDSHADEBOX]

このユースケースでは、カスタムアクションと認証済み呼び出しを使用して、ジャーニーから[!DNL Adobe Experience Platform]にカスタムイベントを書き込む方法について説明します。

## 開発者プロジェクトの設定 {#custom-action-aep-IO}

1. Adobe Developer Console で、「**プロジェクト**」をクリックし、IO プロジェクトを開きます。

1. 「**資格情報**」セクションで、「**OAuth サーバー間**」をクリックします。

   ![アクションタイプドロップダウンを含むカスタムアクション設定画面](assets/custom-action-aep-1.png)

1. 「**cURL コマンドを表示**」をクリックします。

   ![[!DNL Adobe Experience Platform] アクションタイプの選択](assets/custom-action-aep-2.png)

1. cURL コマンドをコピーし、client_id、client_secret、grant_type および scope を保存します。

```
curl -X POST 'https://ims-na1.adobelogin.com/ims/token/v3' -H 'Content-Type: application/x-www-form-urlencoded' -d 'grant_type=client_credentials&client_id=1234&client_secret=5678&scope=openid,AdobeID,read_organizations,additional_info.projectedProductContext,session'
```

>[!CAUTION]
>
>Adobe Developer Console でプロジェクトを作成したら、開発者と API に対し、適切な権限のアクセス制御を付与してください。 詳しくは、[[!DNL Adobe Experience Platform]  ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/api-authentication#grant-developer-and-api-access-control){target="_blank"}を参照してください

## HTTP API インレットを使用したソースの設定

1. ジャーニーからデータを書き込むエンドポイントを[!DNL Adobe Experience Platform]に作成します。

1. [!DNL Adobe Experience Platform]で、左側のメニューの&#x200B;**接続**&#x200B;の下にある&#x200B;**ソース**&#x200B;をクリックします。 **HTTP API** で「**データを追加**」をクリックします。

   [!DNL Adobe Experience Platform]](assets/custom-action-aep-3.png)の![ サンドボックス選択ドロップダウン

1. 「**新規アカウント**」を選択し、認証を有効にします。 「**ソースに接続**」を選択します。

   ![ストリーミングデータのデータセット選択インターフェイス](assets/custom-action-aep-4.png)

1. 「**次へ**」を選択し、データを書き込むデータセットを選択します。 「**次へ**」、「**終了**」の順にクリックします。

   ![アクションパラメーターにマッピングされる XDM スキーマフィールド](assets/custom-action-aep-5.png)

1. 新しく作成したデータフローを開きます。 スキーマペイロードをコピーして、メモ帳に保存します。

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

## カスタムアクションの設定 {#custom-action-config}

カスタムアクションの設定について詳しくは、[このページ](../action/about-custom-action-configuration.md)を参照してください。

この例では、次の手順に従います。

1. [!DNL Adobe Journey Optimizer]を開き、左側のメニューの&#x200B;**管理**&#x200B;の下にある&#x200B;**設定**&#x200B;をクリックします。 **アクション**&#x200B;で、「**管理**」をクリックし、「**アクションを作成**」をクリックします。

1. URLを設定し、POST メソッドを選択します。

   `https://dcs.adobedc.net/collection/<collection_id>?syncValidation=false`

1. ヘッダー（Content-Type、Charset、sandbox-name）が設定されていることを確認します。

   ![設定パネルを含むジャーニーキャンバスのカスタムアクション](assets/custom-action-aep-7bis.png)

### 認証の設定 {#custom-action-aep-authentication}

1. 次のペイロードを持つ&#x200B;**カスタム**&#x200B;として&#x200B;**タイプ**&#x200B;を選択します。

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

1. 「**クリックして認証をテスト**」ボタンを使用して、接続をテストします。

   ![式エディターを使用したパラメーターマッピングインターフェイス](assets/custom-action-aep-8.png)

### ペイロードの設定 {#custom-action-aep-payload}

1. 「**リクエスト**」フィールドと「**応答**」フィールドに、先ほど使用したソース接続からのペイロードを貼り付けます。

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

1. 動的に入力されるフィールドのフィールド設定を、**定数**&#x200B;から&#x200B;**変数**&#x200B;に変更します。

1. カスタムアクションを保存します。

## ジャーニー

1. 最後に、ジャーニーでこのカスタムアクションを使用して、カスタムジャーニーイベントを書き込みます。

1. ユースケースに応じて、ジャーニーバージョン ID、ノード ID、ノード名およびその他の属性を入力します。

   ![複雑なフィールドマッピングの詳細設定モードエディター](assets/custom-action-aep-9.png)

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

- **TL;DR:**&#x200B;この使用例では、HTTP API インレットとOAuth サーバー間の認証済み呼び出しを使用してジャーニーイベントデータをAdobe Experience Platformに書き込むJourney Optimizerのカスタムアクションを設定する方法について説明します。

**インテント：**
- AEP API認証用のOAuth サーバー間の資格情報を使用したAdobe Developer Console IO プロジェクトの設定
- ストリーミングジャーニーイベントデータを受信するHTTP API インレットソースをAdobe Experience Platformで作成します
- 正しいURL、ヘッダー、およびカスタムベアラートークン認証を使用して、Journey Optimizerでカスタムアクションを設定します
- ジャーニーフィールド（ジャーニーバージョン ID、ノード ID、顧客ID）をカスタムアクションペイロードの変数として動的にマッピングします
- ジャーニーでカスタムアクションを使用して、カスタムイベントをAEP データセットに書き込みます

**用語集：**
- **HTTP API Inlet**: HTTP POST リクエスト *（製品固有）*&#x200B;を介してデータを取り込むためのストリーミングエンドポイントを作成するAdobe Experience Platform ソースコネクタ
- **OAuth Server-to-Server**: Adobe Developer Consoleの認証資格情報タイプで、ユーザーによる操作&#x200B;*（製品固有）*&#x200B;なしに、サーバー間API呼び出しのベアラートークンを生成します
- **カスタム認証**：指定されたエンドポイントからベアラートークンを取得し、設定済みの期間&#x200B;*（製品固有）*&#x200B;にキャッシュするJourney Optimizer カスタムアクション認証タイプ
- **XDM エンティティ**: Experience Data Model スキーマに準拠するデータペイロード構造。HTTP API インレット *（製品固有）*&#x200B;を介してAEPにイベントを書き込む際に本体として使用されます
- **cacheDuration**：新しいトークンが要求されるまでの取得ベアラートークンの再利用時間を制御するカスタム認証設定のトークンキャッシュ設定&#x200B;*（製品固有）*

**ガードレール：**
- Adobe Developer Console プロジェクトの作成後、資格情報を使用する前に、開発者およびAPI アクセス制御の権限を明示的に付与する必要があります
- 認証を有効にしてHTTP API インレット ソースを作成する必要があります。接続エンドポイント URLとスキーマペイロードをコピーして、カスタムアクション設定で使用する必要があります
- カスタムアクションヘッダーには、Content-Type、Charset、およびsandbox-nameを含める必要があります
- 実行時に動的に入力されるフィールドは、カスタムアクションペイロード設定で定数から変数に変更する必要があります

**用語：**
- 正式名称：カスタムアクション – 頭字語：なし – バリアント：カスタムアクション設定、Journey Optimizer カスタムアクション
- 正式名称：Adobe Experience Platform – 頭字語：AEP – 変種：Experience Platform、Platform
- 同義語：「HTTP API インレット」 = 「ストリーミングエンドポイント」 = 「DCS コレクションエンドポイント」
- 混乱しないでください：「OAuth サーバー間」≠「OAuth ユーザー認証」 （サーバー間のログインは必要ありません。クライアント資格情報を使用します）

**FAQ:**
- **Q: Journey Optimizer カスタムアクションからAEP HTTP API インレットを呼び出すために使用される認証の種類は何ですか？** — Adobe IMSトークンエンドポイントから取得したOAuth Server-to-Server クライアント資格情報を使用したカスタムベアラートークン認証。
- **Q: client_id、client_secret、grant_type、およびscopeの値はどこにありますか？** — Adobe Developer Console IO プロジェクトのOAuth サーバー間の資格情報セクションから、「View cURL コマンド」をクリックします。
- **Q: ペイロードでジャーニー固有のフィールド（journeyVersionId、nodeIdなど）を動的にするにはどうすればよいですか？** — カスタムアクションペイロード設定でフィールド設定を定数から変数に変更し、実行時にジャーニーコンテキストから入力されるようにします。
- **Q: Adobe Developer Console プロジェクトにはどのような権限が必要ですか？** — AEP API認証ドキュメントに記載されているように、プロジェクトの作成後に、開発者およびAPI アクセス制御に適切な権限を付与する必要があります。
- **Q：認証ペイロードのcacheDuration設定の目的は何ですか？**  – 取得したBearer トークンが新しいトークンをリクエストするまでのキャッシュと再利用の時間（例では28,000秒）を制御します。

+++
