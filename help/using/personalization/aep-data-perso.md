---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform データをパーソナライズ機能に活用（ベータ版）
description: Adobe Experience Platform データをパーソナライゼーションに使用する方法を説明します。
badge: label="ベータ版" type="Informative"
feature: Personalization, Rules
topic: Personalization
role: Data Engineer
level: Intermediate
keywords: 式, エディター
exl-id: 2fc10fdd-ca9e-46f0-94ed-2d7ea4de5baf
source-git-commit: 7e378cbda6ee2379a8bd795588c328cb14107aa4
workflow-type: ht
source-wordcount: '849'
ht-degree: 100%

---

# Adobe Experience Platform データをパーソナライゼーションに使用{#aep-data}

>[!AVAILABILITY]
>
>この機能は現在、パブリックベータ版としてすべてのお客様に対して提供されています。
>
>この機能を使用するには、まず、パーソナライゼーションエディターで新しい「datasetLookup」ヘルパー関数を追加する際に表示される、組織のベータ版利用条件に同意する必要があります。

Journey Optimizer を使用すると、パーソナライゼーションエディターで Adobe Experience Platform のデータを利用して、[コンテンツをパーソナライズする](../personalization/personalize.md)ことができます。これを行うには、まず、以下で説明するように、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、そのデータを使用して、コンテンツを [!DNL Journey Optimizer] にパーソナライズできます。

## ベータ版の制限事項とガイドライン {#guidelines}

開始する前に、次の制限事項とガイドラインを確認してください。

* **サポートされているチャネル**：現時点では、この機能は、メール、SMS およびダイレクトメールチャネル内でのみ使用できます。
* **フラグメント**：現時点では、データセット参照のパーソナライゼーションを式フラグメントやビジュアルフラグメント内に配置できません。

### 決定 {#decisioning}

エクスペリエンス決定のランキング式とルールで [!DNL Adobe Experience Platform] データセットを活用する機能は、近日リリース予定です。

それまでの間、以下に説明する現在のガードレールを確認してください。

* 決定ポリシーは、3 つのデータセットに制限されています。
* 決定ルールでは、3 つのデータセットを使用できます。
* ランキング式では、3 つのデータセットを使用できます。
* 決定ポリシーは、1000 個のレコードクエリに制限されています。

>[!NOTE]
>
>この機能へのアクセス権をご希望の場合は、アカウント担当者にお問い合わせください

## データ参照用データセットの有効化 {#enable}

データセットのデータをパーソナライゼーションに活用するには、API 呼び出しを使用してそのステータスを取得し、参照サービスを有効にする必要があります。詳しくは、[ [!DNL Journey Optimizer]](../data/lookup-aep-data.md) の Adobe Experience Platform データセットの活用の節を参照してください。

## パーソナライゼーションへのデータセットの活用 {#leverage}

API 呼び出しを使用してデータセットの参照パーソナライゼーションが有効になると、そのデータを使用してコンテンツを [!DNL Journey Optimizer] にパーソナライズできます。

1. メッセージなどのパーソナライズ機能を定義でき、すべてのコンテキストで使用できるパーソナライゼーションエディターを開きます。[パーソナライゼーションエディターの操作方法を学ぶ](../personalization/personalization-build-expressions.md)

1. ヘルパー関数リストに移動して、**datasetLookup** ヘルパー関数をコードペインへ追加します。

   ![](assets/aep-data-helper.png)

1. この関数は、Adobe Experience Platform データセットからフィールドを呼び出すことができる、定義済みの構文を提供します。構文は以下の通りです。

   ```
   {{datasetLookup datasetId="datasetId" id="key" result="store" required=false}}
   ```

   * **datasetId** は作業中のデータセットの ID です。
   * **id** は、参照データセットのプライマリ ID と結合する必要があるソース列の ID です。

     >[!NOTE]
     >
     >このフィールドに入力する値は、フィールド ID（*profile.packages.packageSKU*）、ジャーニーイベントで渡されるフィールド（*context.journey.events.event_ID.productSKU*）、または静的な値（*sku007653*）です。いずれの場合も、システムは値を使用してデータセットを検索し、キーと一致するかどうかを確認します。
     >
     >キーにリテラル文字列値を使用する場合は、テキストを引用符で囲みます。例：`{{datasetLookup datasetId="datasetId" id="SKU1234" result="store" required=false}}`。属性値を動的キーとして使用する場合は、引用符を削除します。例：`{{datasetLookup datasetId="datasetId" id=category.product.SKU result="SKU" required=false}}`

   * **result** はデータセットから取得するすべてのフィールド値を参照するために指定する必要がある、任意の名前です。この値はコード内で各フィールドを呼び出すために使用されます。

   * **required=false**：required が TRUE に設定されている場合、一致するキーが見つかった場合にのみメッセージが配信されます。false に設定した場合は、一致するキーは必要なく、メッセージを配信できます。false に設定した場合、メッセージコンテンツのフォールバックまたはデフォルト値を考慮することをお勧めします。

   +++データセット ID はどこで取得できますか？

   データセット ID は、Adobe Experience Platform ユーザーインターフェイスで取得できます。データセットの操作方法について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/user-guide#view-datasets){target="_blank"}を参照してください。

   ![](assets/aep-data-dataset.png)

+++

1. ニーズに合わせて構文を調整します。この例では、乗客のフライトに関連するデータを取得します。構文は以下の通りです。

   ```
   {{datasetLookup datasetId="1234567890abcdtId" id=profile.upcomingFlightId result="flight"}}
   ```

   * ID が「1234567890abcdtId」のデータセットで作業しています。
   * ルックアップデータセットとの結合に使用するフィールドは、*profile.upcomingFlightId* です。
   * 「フライト」参照の下のすべてのフィールド値を含めるようにします。

1. Adobe Experience Platform データセットで呼び出す構文が設定されたら、取得するフィールドを指定できます。構文は以下の通りです。

   ```
   {{result.fieldId}}
   ```

   >[!NOTE]
   >
   >データセットフィールドを参照する場合は、スキーマ内で定義されている完全なフィールドパスと一致することを確認します。

   * **result** は **MultiEntity** ヘルパー関数で **result** パラメーターに割り当てた値です。この例では「フライト」です。
   * **fieldID** は取得するフィールドの ID です。この ID は、データセットに関連するレコードスキーマを参照する際に、[!DNL Adobe Experience Platform] ユーザーインターフェイスに表示されます。

     +++フィールド ID はどこで取得できますか？

     フィールド ID は、Adobe Experience Platform ユーザーインターフェイスでデータセットをプレビューするときに取得できます。データセットのプレビュー方法について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/user-guide#preview){target="_blank"}を参照してください。

     ![](assets/aep-data-field.png)

+++

   この例では、乗客の搭乗時間と搭乗口に関する情報を使用します。したがって、次の 2 行を追加します。

   * `{{flight._myorg.booking.boardingTime}}`
   * `{{flight._myorg.booking.gate}}`

1. コードの準備が整いました。通常通りにコンテンツを完成させ、「**コンテンツをシミュレート**」ボタンを使用してテストし、パーソナライズ機能を確認することができます。[コンテンツのプレビューとテストの方法について学ぶ](../content-management/preview-test.md)


   ![](assets/aep-data-sample.png)
