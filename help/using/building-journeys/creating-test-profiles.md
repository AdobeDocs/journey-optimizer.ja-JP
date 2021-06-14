---
title: テストプロファイルの作成
description: テストプロファイルの作成方法
feature: ジャーニー
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 74%

---

# テストプロファイルの作成 {#create-test-profiles}

![](../assets/do-not-localize/badge.png)

ジャーニーでテストモードを使用する場合は、テストプロファイルが必要です。[既存のプロファイル](../building-journeys/creating-test-profiles.md#turning-profile-into-test)をテストプロファイルにするか、[テストプロファイルを作成](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)します。テストモードの使用方法については、[この節](../building-journeys/testing-the-journey.md)を参照してください。

Adobe Experience Platform でテストプロファイルを作成するには、様々な方法があります。このドキュメントでは、[CSV ファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)のアップロードと [API 呼び出し](../building-journeys/creating-test-profiles.md#create-test-profiles-api)の使用の 2 とおりの方法を重点的に説明します。また、データセットに JSON ファイルをアップロードすることもできます。[データ取得のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html?lang=ja#add-data-to-dataset)を参照してください。

テストプロファイルの作成は、Adobe Experience Platform で通常のプロファイルを作成する場合と似ています。詳しくは、[リアルタイム顧客プロファイルのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。

## 前提条件{#test-profile-prerequisites}

プロファイルを作成するには、まずAdobe[!DNL Journey Optimizer]でスキーマとデータセットを作成する必要があります。

まず、**スキーマを作成**&#x200B;する必要があります。次の手順に従います。

1. 「管理」セクションで、「**[!UICONTROL スキーマ]**」をクリックします。
   ![](../assets/test-profiles-0.png)
1. 右上の「**[!UICONTROL スキーマを作成]**」をクリックして、スキーマの種類を選択します（例：**XDM 個人プロファイル**）。
   ![](../assets/test-profiles-1.png)
1. 適切なフィールドグループを選択します。 必ず&#x200B;**Profile test details**フィールドグループを追加してください。
   ![](../assets/test-profiles-1-ter.png)
完了したら、「 **[!UICONTROL Add field groups]**」をクリックします。フィールドグループのリストが、スキーマの概要画面に表示されます。
   ![](../assets/test-profiles-2.png)

   >[!NOTE]
   >
   >* スキーマの名前をクリックして変更し、そのプロパティを更新します。
      >
      >
   * 「フィールドグループ」セクションの「**[!UICONTROL 追加]**」ボタンをクリックして、スキーマに追加する他のフィールドグループを選択します


1. フィールドのリストで、プライマリ ID として定義するフィールドをクリックします。
   ![](../assets/test-profiles-3.png)
1. **[!UICONTROL フィールドのプロパティ]**&#x200B;の右パネルで、「****[!UICONTROL ID]**」および「****[!UICONTROL プライマリID]**」オプションをオンにし、名前空間を選択します。 メールアドレスをプライマリ ID にする場合は、「**メール**」名前空間を選択します。「**適用**」をクリックします。
   ![](../assets/test-profiles-4.png)
1. スキーマを選択し、**[!UICONTROL スキーマのプロパティ]**&#x200B;で「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-5.png)
1. 「**保存**」をクリックします。

>[!NOTE]
>
>スキーマ作成の詳細については、[XDM のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja#prerequisites)を参照してください。

次に、プロファイルのインポート先となる&#x200B;**データセットを作成**&#x200B;する必要があります。次の手順に従います。

1. **[!UICONTROL データセット]**&#x200B;を参照し、「**[!UICONTROL データセットを作成]**」をクリックします。
   ![](../assets/test-profiles-6.png)
1. 「**[!UICONTROL スキーマからデータセットを作成]**」を選択します。
   ![](../assets/test-profiles-7.png)
1. 作成済みのスキーマを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   ![](../assets/test-profiles-8.png)
1. 名前を選択し、「**[!UICONTROL 終了]**」をクリックします。
   ![](../assets/test-profiles-9.png)
1. 「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> データセットの作成について詳しくは、[カタログサービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja#getting-started)を参照してください。

## プロファイルをテストプロファイルに変換する{#turning-profile-into-test}

既存のプロファイルをテストプロファイルに変換できます。プロファイルの作成時と同じ方法でプロファイル属性を更新できます。

これをおこなう簡単な方法は、ジャーニーで&#x200B;**[!UICONTROL プロファイル]**&#x200B;を更新アクションアクティビティを使用し、 testProfileブール値フィールドをfalseからtrueに変更することです。

ジャーニーは、「**[!UICONTROL セグメントを読み取り]**」アクティビティと「**[!UICONTROL プロファイルを更新]**」アクティビティで構成されます。まず、テストプロファイルに変換するプロファイルをターゲットにしたセグメントを作成する必要があります。

>[!NOTE]
>
> **testProfile** フィールドを更新することになるので、選択したプロファイルには、このフィールドを含める必要があります。関連するスキーマには、「**プロファイルテストの詳細**」Mixin が必要です。[この節](../building-journeys/creating-test-profiles.md#test-profiles-prerequisites)を参照してください。

1. **Segments**&#x200B;を参照し、右上の&#x200B;**Create segment**を選択します。
   ![](../assets/test-profiles-22.png)
1. セグメント名を定義してセグメントを作成する：目的のプロファイルをターゲットするフィールドと値を選択します。
   ![](../assets/test-profiles-23.png)
1. 「**保存**」をクリックし、セグメントによってターゲットとするプロファイルが正しくされていることを確認します。
   ![](../assets/test-profiles-24.png)

   >[!NOTE]
   >
   > セグメントの計算には時間がかかる場合があります。セグメントの詳細については、[この節](../segment/about-segments.md)を参照してください。

1. 次に、**[!UICONTROL セグメントの読み取り]**&#x200B;オーケストレーションアクティビティを使用して、新しいジャーニーを作成および開始します。
1. 以前に作成したセグメントと、プロファイルが使用する名前空間を選択します。
   ![](../assets/test-profiles-25.png)
1. **[!UICONTROL プロファイル更新]**&#x200B;アクションアクティビティを追加します。
1. スキーマ、**testProfiles**&#x200B;フィールド、データセットを選択し、値を&#x200B;**True**&#x200B;に設定します。 これを実行するには、「**[!UICONTROL 値]**」フィールドで、右側の&#x200B;**ペン**&#x200B;アイコンをクリックし、「**[!UICONTROL 詳細設定モード]**」を選択して、「**true**」と入力します。
   ![](../assets/test-profiles-26.png)
1. **終了**&#x200B;アクティビティを追加して、「**[!UICONTROL 公開]**」をクリックします。
1. 「**[!UICONTROL Segments]**」セクションで、プロファイルが正しく更新されていることを確認します。
   ![](../assets/test-profiles-28.png)

   >[!NOTE]
   >
   > **[!UICONTROL プロファイルの更新]**&#x200B;アクティビティについては、[この節](../building-journeys/update-profiles.md)を参照してください。

## csvファイル{#create-test-profiles-csv}を使用したテストプロファイルの作成

Adobe Experience Platform では、様々なプロファイルフィールドを含む CSV ファイルをデータセットにアップロードして、プロファイルを作成できます。これが最も簡単なメソッドです。

1. スプレッドシートソフトウェアを使用して、単純な CSV ファイルを作成します。
1. 必要な各フィールドごとに 1 列ずつ追加しますプライマリ ID フィールド（上記の例では「personID」）を追加し、「testProfile」フィールドを「true」に設定するようにしてください。
   ![](../assets/test-profiles-11.png)
1. プロファイルごとに 1 行追加し、各フィールドの値を入力します。
   ![](../assets/test-profiles-12.png)
1. スプレッドシートを CSV ファイルとして保存します。カンマが区切り文字として使用されていることを確認します。
1. Adobe Experience Platform **ワークフロー**を参照します。
   ![](../assets/test-profiles-14.png)
1. 「**CSV を XDM スキーマにマッピング**」を選択し、「**開始**」をクリックします。
   ![](../assets/test-profiles-16.png)
1. プロファイルの読み込み先となるデータセットを選択します。「**次へ**」をクリックします。
   ![](../assets/test-profiles-17.png)
1. 「**ファイルを選択**」をクリックし、csv ファイルを選択します。ファイルをアップロードしたら、「**次へ**」をクリックします。
   ![](../assets/test-profiles-18.png)
1. ソース csv フィールドをスキーマフィールドにマッピングし、「**終了**」をクリックします。
   ![](../assets/test-profiles-19.png)
1. データの読み込みが開始します。ステータスが「**処理中**」から「**成功**」に変わります。右上の「**データセットのプレビュー**」をクリックします。
   ![](../assets/test-profiles-20.png)
1. テストプロファイルが正しく追加されていることを確認します。
   ![](../assets/test-profiles-21.png)

テストプロファイルが追加され、ジャーニーのテストで使用できるようになりました。[この節](../building-journeys/testing-the-journey.md)を参照してください。
>[!NOTE]
>
> CSV の読み込みについて詳しくは、[データ取得ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=ja#tutorials)を参照してください。

## API呼び出しを使用したテストプロファイルの作成{#create-test-profiles-api}

また、API 呼び出しを使用してテストプロファイルを作成することもできます。詳しくは、この[ページ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

「プロファイルテストの詳細」Mixin を含むプロファイルスキーマを使用する必要があります。testProfile フラグは、この Mixin の一部です。

プロファイルを作成する場合は、次の値を渡す必要があります：testProfile = true

既存のプロファイルを更新して、testProfile フラグを「true」に変更することもできます。

テストプロファイルを作成するための API 呼び出しの例を以下に示します。

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
