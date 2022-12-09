---
solution: Journey Optimizer
product: journey optimizer
title: カスタムアクションによるコレクションの動的なパス
description: キャンペーン v7/v8 を使用したメッセージの送信
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 23627545ffe290a5a482b3cecf54b2f51d2053e3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---


# 使用例: カスタムアクションを使用して動的にコレクションを渡します。{#passing-collection}

カスタムアクションパラメーターにコレクションを渡して、実行時に動的に値が設定されるようにすることができます。 サポートされるコレクションには、次の2種類があります。

* 単純なコレクション: listString などの単純なデータ型の配列。

   ```
   {
    "deviceTypes": [
        "android",
        "ios"
    ]
   }
   ```

* オブジェクトコレクション: JSON オブジェクトの配列。例えば、次のようになります。

   ```
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

## 限界 {#limitations}

* オブジェクト配列内にネストされたオブジェクトの配列は、現在サポートされていません。 例えば：

   ```
   {
   "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20,
        "locations": [{"name": "Paris"}, {"name": "London"}]
     },
    ]
   }
   ```

* テストモードを使用してコレクションをテストするには、コードビューモードを使用する必要があります。 コードビューモードは、現在のところ、ビジネスイベントではサポートされていません。 1つのエレメントを含むコレクションのみを送信できます。

## 一般的な手順 {#general-procedure}

この節では、次の JSON ペイロードの例を使用します。 これは、単純なコレクションであるフィールドを含むオブジェクトの配列です。

```
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

「Products」というは、2つのオブジェクトから成る配列であることを示しています。 オブジェクトが少なくとも1つ必要です。

1. カスタムアクションを作成します。 このページ ](../action/about-custom-action-configuration.md) を参照してください [ 。

1. **[!UICONTROL Action parameters]**&#x200B;セクションで、JSON の例をペーストします。表示される構造は静的で、ペイロードをペーストする場合は、すべてのフィールドが定数として定義されます。

   ![](assets/uc-collection-1.png)

1. 必要に応じて、フィールドタイプを調整します。 コレクションでは次のフィールドタイプがサポートされています。 listString、Liststring、Liststring、Liststring、Liststring、listDateTimeOnly、listDateOnly、listObject

   >[!NOTE]
   >
   >フィールドタイプは、ペイロードの例に従って自動的に推論されます。

1. オブジェクトを動的に渡す必要がある場合は、それらを変数として設定する必要があります。 この例では、&quot;products&quot; を変数として設定します。 オブジェクトに含まれているすべてのオブジェクトフィールドは、自動的に変数に設定されます。

   >[!NOTE]
   >
   >ペイロードの例の最初のオブジェクトは、フィールドを定義するために使用されます。

1. 各フィールドについて、旅の canvas に表示されるラベルを定義します。

   ![](assets/uc-collection-2.png)

1. 旅を作成し、作成したカスタムアクションを追加します。 このページ ](../building-journeys/using-custom-actions.md) を参照してください [ 。

1. **[!UICONTROL Action parameters]**「高度な式エディター」を使用して、セクションに array パラメーター (この例では &quot;products&quot;) を定義します。

   ![](assets/uc-collection-3.png)

1. 次の「オブジェクト」フィールドには、それぞれソースの XDM スキーマから、対応するフィールド名を入力します。 名前が同じであれば、これは必要ありません。 この例では、「product id」と「color」だけを定義する必要があります。

   ![](assets/uc-collection-4.png)

「配列」フィールドでは、高度な式エディターを使用して、データの操作を実行することもできます。 次の例では、フィルター ](functions/functionfilter.md) 関数と [ intersect ](functions/functionintersect.md) 関数を使用 [ しています。

![](assets/uc-collection-5.png)

## 特定の状況{#examples}

異種型および配列の配列の場合、この配列は listAny type によって定義されます。 個別の項目をマップすることはできますが、配列を variable に変更することはできません。

![](assets/uc-collection-heterogeneous.png)

異種型の例を次に示します。

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

配列の配列の例を次に示します。

```
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
