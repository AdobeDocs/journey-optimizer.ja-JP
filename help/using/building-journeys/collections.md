---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションを使用したコレクションの動的な受け渡し
description: Campaign v7 または v8 を使用したメッセージの送信
feature: Journeys, Use Cases, Custom Actions, Collections
topic: Content Management
role: Developer, Data Engineer
level: Experienced
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
version: Journey Orchestration
source-git-commit: 8f25fd5110777c148246864b364d02e4c6bf00da
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 58%

---


# カスタムアクションを使用したコレクションの動的な受け渡し{#passing-collection}

実行時に値が動的に設定されるカスタムアクションパラメーターにコレクションを渡すことができます。 次の 2 種類のコレクションがサポートされています。

* **単純なコレクション**：単純なデータタイプを要素とする配列。以下に listString の例を示します。

  ```json
  {
   "deviceTypes": [
       "android",
       "ios"
   ]
  }
  ```

* o **bject コレクション**:JSON オブジェクトの配列。例：

  ```json
  {
  "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20.1
     },
     {
        "id":"productB",
        "name":"B",
        "price":10.0
     },
     {
        "id":"productC",
        "name":"C",
        "price":5.99
     }
   ]
  }
  ```


## 一般的な手順 {#general-procedure}

この節では、次の JSON ペイロードの例を使用します。 これは、単純なコレクションのフィールドを持つオブジェクトの配列です。

```json
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

`products` は 2 つのオブジェクトの配列であることがわかります。 少なくとも 1 つのオブジェクトが必要です。

1. カスタムアクションを作成します。詳しくは、[このページ](../action/about-custom-action-configuration.md)を参照してください。

1. 「**[!UICONTROL アクションパラメーター]**」セクションに、JSON の例を貼り付けます。表示される構造は静的です。ペイロードを貼り付けたときに、すべてのフィールドが定数として定義されます。

   ![](assets/uc-collection-1.png)

1. 必要に応じて、フィールドタイプを調整します。コレクションでは、listString、listInteger、listDecimal、listBoolean、listDateTime、listDateTimeOnly、listDateOnly、listObject の各フィールドタイプがサポートされています。

   >[!NOTE]
   >
   >フィールドタイプは、ペイロードの例に従って自動的に推測されます。

1. オブジェクトを動的に渡す場合は、変数として設定する必要があります。この例では、変数として `products` を設定します。 オブジェクトに含まれているすべてのオブジェクトフィールドは、変数に自動的に設定されます。

   >[!NOTE]
   >
   >サンプルペイロードの最初のオブジェクトは、フィールドの定義に使用されます。

1. フィールドごとに、ジャーニーキャンバスに表示されるラベルを定義します。

   ![](assets/uc-collection-2.png){width="70%" align="left"}

1. ジャーニーを作成し、作成したカスタムアクションを追加します。詳しくは、[このページ](../building-journeys/using-custom-actions.md)を参照してください。

1. 「**[!UICONTROL アクションパラメーター]**」セクションで、高度な式エディターを使用して配列パラメーター（この例では `products`）を定義します。

   ![](assets/uc-collection-3.png)

1. 次のオブジェクトフィールドごとに、ソース XDM スキーマ内の対応するフィールド名を入力します。名前が同じ場合は、この操作は不要です。この例では、「`product id`」と「color」のみを定義する必要があります。

   ![](assets/uc-collection-4.png){width="50%" align="left"}

配列フィールドの場合は、高度な式エディターを使用してデータ操作を実行することもできます。次の例では、[filter](functions/functionfilter.md) 関数と [intersect](functions/functionintersect.md) 関数を使用しています。

![](assets/uc-collection-5.png)

## 制限および制約事項 {#limitations}

* **カスタムアクションでのネストされた配列のサポート**

  Adobe Journey Optimizerでは、カスタムアクション内のオブジェクトのネストされた配列 **レスポンスペイロード** をサポートしていますが、このサポートは **リクエストペイロード** では制限されています。

  リクエストペイロードでは、カスタムアクション設定で定義されているように、ネストされた配列に一定数の項目が含まれている場合にのみサポートされます。 例えば、ネストされた配列に常に 3 つの項目が含まれる場合は、定数として設定できます。 項目数を動的にする必要がある場合は、ネストされていない配列（下部レベルの配列）のみを変数として定義できます。

  例：

   1. 次の例は、**サポートされていないユースケース** を示しています。

      この例では、products 配列に、動的な項目数を持つネストされた配列（`locations`）が含まれています。これはリクエストペイロードではサポートされていません。

      ```json
      {
      "products": [
         {
            "id": "productA",
            "name": "A",
            "price": 20,
            "locations": [
            { "name": "Paris" },
            { "name": "London" }
            ]
         }
      ]
      }
      ```

   2. 定数として定義された固定項目でサポートされる例。

      この場合、ネストされた場所は固定フィールド（`location1`、`location2`）に置き換えられ、ペイロードはサポートされる設定内で有効なままになります。

      ```json
      {
      "products": [
         {
            "id": "productA",
            "name": "A",
            "price": 20,
            "location1": { "name": "Paris" },
            "location2": { "name": "London" }
         }
      ]
      }
      ```


* テストモードを使用してコレクションをテストするには、コードビューモードを使用する必要があります。ビジネスイベントに対しては、現時点ではコードビューモードはサポートされていません。コレクションは、単一の要素でのみ送信できます。


## 特殊な例{#examples}

異種混在タイプと配列の配列の場合、配列は listAny タイプで定義されます。個々の項目のみをマッピングできますが、配列を変数に変更することはできません。

![](assets/uc-collection-heterogeneous.png){width="70%" align="left"}

異種混在タイプの例：

```json
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

配列の配列の例：

```json
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**関連トピック**

[カスタムアクションの使用](../building-journeys/using-custom-actions.md)
