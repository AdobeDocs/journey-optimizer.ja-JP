---
title: テストプロファイルの作成
description: テストプロファイルの作成方法
source-git-commit: 4464ea7169424c1ec6212394b8bda79a9bec1913
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 74%

---

# テストプロファイルを作成 {#create-test-profiles}

![](../assets/do-not-localize/badge.png)

テストプロファイルは、ジャーニーでテストモードを使用する場合に必要です。 [既存のプロファイル](../building-journeys/creating-test-profiles.md#turning-profile-into-test)をテストプロファイルにするか、[テストプロファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)を作成します。テストモードの使い方については、[この節](../building-journeys/testing-the-journey.md)を参照してください。

Adobe Experience Platform でテストプロファイルを作成するには、様々な方法があります。 このドキュメントでは、次の 2 つの方法に焦点を当てています。[CSV ファイル](../building-journeys/creating-test-profiles.md#create-test-profiles-csv)のアップロードと、[API コール](../building-journeys/creating-test-profiles.md#create-test-profiles-api)の使用です。また、データセットに JSON ファイルをアップロードすることもできます。[データインジェストドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html?lang=ja#add-data-to-dataset)を参照してください。

テストプロファイルの作成は、Adobe Experience Platform で正規プロファイルを作成するのと似ています。 詳しくは、[リアルタイム顧客プロファイルドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。

## 前提条件{#test-profile-prerequisites}

プロファイルを作成するには、まずAdobe[!DNL Journey Optimizer]でスキーマとデータセットを作成する必要があります。

まず、**スキーマを作成**&#x200B;する必要があります。 次の手順に従います。

1. 「管理」セクションで、「**[!UICONTROL スキーマ]**」をクリックします。
   ![](../assets/test-profiles-0.png)
1. 右上の「**[!UICONTROL スキーマを作成]**」をクリックし、スキーマの種類を選択します（例：**XDM 個人版プロファイル**）。
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
1. **[!UICONTROL フィールドのプロパティ]**&#x200B;の右パネルで、「****[!UICONTROL ID]**」および「****[!UICONTROL プライマリID]**」オプションをオンにし、名前空間を選択します。 プライマリ ID を E メールアドレスにする場合は、「**E メール**」名前空間を選択します。 「**適用**」をクリックします。
   ![](../assets/test-profiles-4.png)
1. スキーマを選択し、「**[!UICONTROL スキーマのプロパティ]**」で「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-5.png)
1. 「**保存**」をクリックします。

>[!NOTE]
>
>スキーマ作成の詳細については、[XDM のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=ja#prerequisites)を参照してください。

次に、プロファイルを読み込む&#x200B;**データセット**&#x200B;を作成する必要があります。 次の手順に従います。

1. **[!UICONTROL データセット]**&#x200B;を参照し、「**[!UICONTROL データセットを作成]**」をクリックします。
   ![](../assets/test-profiles-6.png)
1. 「**[!UICONTROL スキーマからデータセットを作成]**」を選択します。
   ![](../assets/test-profiles-7.png)
1. 以前に作成したスキーマを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   ![](../assets/test-profiles-8.png)
1. 名前を選択し、「**[!UICONTROL 完了]**」をクリックします。
   ![](../assets/test-profiles-9.png)
1. 「**[!UICONTROL プロファイル]**」オプションを有効にします。
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> データセットの作成について詳しくは、[カタログサービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja#getting-started)を参照してください。

## プロファイルをテストプロファイルに変換する{#turning-profile-into-test}

既存のプロファイルをテストプロファイルに変換できます。プロファイルの作成時と同じ方法でプロファイル属性を更新できます。

これをおこなう簡単な方法は、ジャーニーで&#x200B;**[!UICONTROL プロファイル]**&#x200B;を更新アクションアクティビティを使用し、 testProfileブール値フィールドをfalseからtrueに変更することです。

ジャーニーは、「**[!UICONTROL セグメントを読み取り]**」と「**[!UICONTROL プロファイルを更新]**」アクティビティで構成されます。 まず、テストプロファイルにするプロファイルをターゲットにしたセグメントを作成する必要があります。

>[!NOTE]
>
> **testProfile** フィールドを更新するので、選択したプロファイルにこのフィールドを含める必要があります。関連するスキーマには、**プロファイルテストの詳細** Mixin が必要です。詳しくは、[このセクション](../building-journeys/creating-test-profiles.md#test-profiles-prerequisites)を参照してください。

1. **Segments**&#x200B;を参照し、右上の&#x200B;**Create segment**を選択します。
   ![](../assets/test-profiles-22.png)
1. セグメント名を定義し、セグメントを作成します。目的のプロファイルをターゲットするフィールドと値を選択します。
   ![](../assets/test-profiles-23.png)
1. 「**保存**」をクリックし、プロファイルがセグメントのターゲットを正しく設定していることを確認します。
   ![](../assets/test-profiles-24.png)

   >[!NOTE]
   >
   > セグメントの計算には時間がかかる場合があります。 セグメントの詳細については、[このセクション](../segment/about-segments.md)を参照してください。

1. 次に、**[!UICONTROL セグメントの読み取り]**&#x200B;オーケストレーションアクティビティを使用して、新しいジャーニーを作成し開始します。
1. 以前に作成したセグメントと、プロファイルが使用する名前空間を選択します。
   ![](../assets/test-profiles-25.png)
1.  **[!UICONTROL プロファイル更新]** アクションアクティビティを追加します。
1. スキーマ、**testProfiles**&#x200B;フィールド、データセットを選択し、値を&#x200B;**True**&#x200B;に設定します。 これを実行するには、「**[!UICONTROL 値]**」フィールドで、右側の&#x200B;**ペン**&#x200B;アイコンをクリックし、「**[!UICONTROL 詳細設定モード]**」を選択して、「**true**」と入力します。
   ![](../assets/test-profiles-26.png)
1. Add an **終了**&#x200B;アクティビティを追加して、 **[!UICONTROL 公開]**&#x200B;をクリックします。
1. 「**[!UICONTROL Segments]**」セクションで、プロファイルが正しく更新されていることを確認します。
   ![](../assets/test-profiles-28.png)

   >[!NOTE]
   >
   >  **[!UICONTROL プロファイルの更新]** アクティビティにつていは,   [このセクション](../building-journeys/update-profiles.md)を参照してください。

## csvファイル{#create-test-profiles-csv}を使用したテストプロファイルの作成

Adobe Experience Platformでは、様々なプロファイルフィールドを含むCSVファイルをプロファイルセットにアップロードして、プロファイルを作成できます。 これが最も簡単なメソッドです。

1. スプレッドシートソフトウェアを使用して、単純なCSVファイルを作成します。
1. 必要な各フィールドごとに1つの列を追加しますプライマリIDフィールド（上記の例では「personID」）と「testProfile」フィールドを「true」に設定して追加します。
   ![](../assets/test-profiles-11.png)
1. プロフィールごとに1行追加し、各フィールドの値を入力します。
   ![](../assets/test-profiles-12.png)
1. スプレッドシートをCSVファイルとして保存します。 カンマが区切り文字として使用されていることを確認します。
1. Adobe Experience Platform **ワークフロー**を参照します。
   ![](../assets/test-profiles-14.png)
1. 「**CSVをXDMスキーマにマップ**」を選択し、「**起動**」をクリックします。
   ![](../assets/test-profiles-16.png)
1. プロファイルをインポートしたいデータセットを選択します。「**次へ**」をクリックします。
   ![](../assets/test-profiles-17.png)
1. 「**ファイルを選択**」をクリックし、csvファイルを選択します。 ファイルをアップロードしたら、「**次へ**」をクリックします。
   ![](../assets/test-profiles-18.png)
1. ソースcsvフィールドをスキーマフィールドにマップし、「**完了**」をクリックします。
   ![](../assets/test-profiles-19.png)
1. データのインポートが開始されます。 ステータスが&#x200B;**処理中**&#x200B;から&#x200B;**成功**&#x200B;に変わります。 右上の&#x200B;**プレビューデータセット**をクリックします。
   ![](../assets/test-profiles-20.png)
1. テストプロファイルが正しく追加されていることを確認します。
   ![](../assets/test-profiles-21.png)

テストプロファイルが追加され、ジャーニーをテストする際に使用できるようになりました。 [このセクション](../building-journeys/testing-the-journey.md)を参照してください。
>[!NOTE]
>
> CSVのインポートについて詳しくは、[データ取得ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=ja#tutorials)を参照してください。

## API呼び出しを使用したテストプロファイルの作成{#create-test-profiles-api}

また、API呼び出しを使用してテストプロファイルを作成することもできます。 詳しくは、 [こちらのページ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)を参照してください。

「プロファイルテストの詳細」ミックスインが含まれるプロファイルスキーマを使用する必要があります。 testProfileフラグは、このmixinの一部です。

プロファイルを作成する場合は、次の値を渡す必要があります。testProfile = true。

既存のプロファイルを更新して、testProfileフラグを「true」に変更することもできます。

テストプロファイルを作成するためのAPI呼び出しの例を以下に示します。

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
