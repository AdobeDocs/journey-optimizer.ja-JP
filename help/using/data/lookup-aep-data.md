---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform データの使用（ベータ版）
description: ' [!DNL Journey Optimizer]  の決定およびパーソナライゼーション機能での Adobe Experience Platform データセットの使用方法について説明します。'
badge: label="ベータ版" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
exl-id: 44a8bc87-5ab0-45cb-baef-e9cd75432bde
source-git-commit: bd1274a5547f4ea835fc258f280c1efc667b6780
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 100%

---

# Adobe Experience Platform データの使用 {#aep-data}

>[!CONTEXTUALHELP]
>id="lookup-aep-data"
>title="ルックアップで有効にする"
>abstract="ルックアップで有効にする"

>[!AVAILABILITY]
>
>この機能は現在、パブリックベータ版としてすべてのお客様に対して提供されています。
>
>この機能を使用するには、まず組織のベータ版の条件に同意する必要があります。

Journey Optimizer を使用すると、[!DNL Journey Optimizer] で Adobe Experience Platform のデータを活用できます。これを行うには、まず、以下で説明するように、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、そのデータを [!DNL Journey Optimizer] のパーソナライゼーションと決定機能で使用できます。

## ベータ版の制限事項とガイドライン {#guidelines}

開始する前に、次の制限事項とガイドラインを確認してください。

* **データセットのサイズ**&#x200B;は、実稼動データセットでは 5 GB、開発サンドボックスデータセットでは 1 GB までに制限されています。
* 組織ごとの参照では、**最大 50 個のデータセットを有効にできます**。
* **レコードの数**&#x200B;は、実稼動データセットでは 5,000 万件、開発サンドボックスデータセットでは 1,000 万件に制限されています。
* **データ使用のラベル付けと適用**&#x200B;は、現時点では、参照が有効なデータセットには適用されていません。
* **参照が有効になっているデータセットやパーソナライゼーションで使用されているデータセットは、削除から保護されません**。パーソナライゼーションに使用されているデータセットを追跡し、データセット削除の有無を確認するのは、お客様の責任です。

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

API 呼び出しを使用してデータセットの参照を有効にすると、そのデータを [!DNL Journey Optimizer] のパーソナライゼーションと決定機能で使用できます。

* [Adobe Experience Platform データをパーソナライゼーションに使用](../personalization/aep-data-perso.md)
* [Adobe Experience Platform データを決定に使用](../experience-decisioning/aep-data-exd.md)
