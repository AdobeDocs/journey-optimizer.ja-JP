---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform データの使用（Beta）
description: Adobe Experience Platform データセットを Decisioning 機能およびパーソナライゼーション機能で使用する方法  [!DNL Journey Optimizer]  説明します。
badge: label="ベータ版" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
exl-id: 44a8bc87-5ab0-45cb-baef-e9cd75432bde
source-git-commit: 4c78163cfc34937888cd323b461246f5955232bb
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 79%

---

# Adobe Experience Platform データの使用 {#aep-data}

>[!AVAILABILITY]
>
>この機能は現在、パブリックベータ版としてすべてのお客様に対して提供されています。
>
>この機能を使用するには、まず組織のベータ版の条項に同意する必要があります。

Journey Optimizerでは、Adobe Experience Platformのデータを [!DNL Journey Optimizer] で活用できます。 これを行うには、まず、以下で説明するように、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、パーソナライゼーションと意思決定の機能 [!DNL Journey Optimizer] 使用してそのデータを利用できます。

## ベータ版の制限事項とガイドライン {#guidelines}

開始する前に、次の制限事項とガイドラインを確認してください。

* **データセットのサイズ**&#x200B;は、実稼動データセットでは 5 GB、開発サンドボックスデータセットでは 1 GB までに制限されています。
* 組織ごとの参照では、**最大 50 個のデータセットを有効にできます**。
* **レコードの数**&#x200B;は、実稼動データセットでは 5,000 万件、開発サンドボックスデータセットでは 1,000 万件に制限されています。
* **データ使用のラベル付けと適用**&#x200B;は、現時点では、参照が有効なデータセットには適用されていません。
* **参照が有効になっているデータセットやパーソナライゼーションで使用されているデータセットは、削除から保護されません**。パーソナライゼーションに使用されているデータセットを追跡し、データセット削除の有無を確認するのは、お客様の責任です。
* **データ使用のラベル付けと適用**&#x200B;は、現時点では、参照が有効なデータセットには適用されていません。

## データ参照用データセットの有効化 {#enable}

データセットのデータをパーソナライゼーションに活用するには、API 呼び出しを使用してそのステータスを取得し、参照サービスを有効にする必要があります。

### 前提条件 {#prerequisites-enable}

* [このドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/authentication/)で説明されている手順に従って、API コマンドを送信するように環境を設定します。
* 開発者プロジェクトには、Adobe Journey Optimizer と Adobe Experience Platform API がプロジェクトに追加されている必要があります。

  ![](assets/aep-data-api.png)

* 役割の一部としてデータセットの管理権限が必要です。
* データセットの基となるスキーマには、参照キーとして機能する&#x200B;**プライマリ ID** が含まれている必要があります。

### API 呼び出し構造 {#call}

```
curl -s -XPATCH "https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}" \ -H "Authorization: Bearer ${ACCESS_TOKEN}" \ -H "x-api-key: ${API_KEY}" \ -H "x-gw-ims-org-id: ${IMS_ORG}" \ -H "x-sandbox-name: ${SANDBOX_NAME}"
```

次のとおりです。

* **URL** は `https://platform.adobe.io/data/core/entity/lookup/dataSets/${DATASET_ID}/${ACTION}` です。
* **データセット ID** は、有効にするデータセットです。
* **アクション**&#x200B;は、有効または無効です。
* **アクセストークン**&#x200B;は、Developer Console から取得できます。
* **API キー**&#x200B;は、Developer Console から取得できます。
* **IMS 組織 ID** は Adobe 組織です。
* **サンドボックス名**&#x200B;は、データセットが含まれるサンドボックス名です（実稼動、開発など）。

>[!NOTE]
>
>データセットの有効化に API 呼び出しを試行した際に以下のエラーが発生した場合は、Developer Console プロジェクトから Adobe Journey Optimizer API を削除してから、再度追加します。
>
>```
>
>"error_code": "403003", 
>"message": "Api Key is invalid"
>
>```

API 呼び出しを使用した検索に対してデータセットが有効になると、そのデータをパーソナライゼーション機能と意思決定機能 [!DNL Journey Optimizer] 使用できます。

* [Adobe Experience Platform データをパーソナライゼーションに使用する](../personalization/aep-data-perso.md)
* [Adobe Experience Platform データを意思決定に使用する](../experience-decisioning/aep-data-exd.md)
