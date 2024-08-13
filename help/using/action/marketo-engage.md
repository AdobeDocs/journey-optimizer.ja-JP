---
solution: Journey Optimizer
product: journey optimizer
title: Marketo Engageとの統合
description: Marketo Engageアクションの使用方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate
hide: true
hidefromtoc: true
keywords: marketo、marketo engage 統合
source-git-commit: 6a49f4b2e0220b1c875b42f70dcb44f3405c6ad2
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---


# Marketo Engageとの統合 {#integrating-with-marketo-engage}

Marketo Engageとのシームレスなデータ統合のジャーニーに乗り出します。 Journey Optimizerのこの特定のカスタムアクションは、次の 2 つの主要なデータタイプの取り込みをサポートしています。

* 人物（プロファイル）: Marketoは、プロファイルを実用的なインサイトに変換します。
* カスタムオブジェクト：製品などのカスタムオブジェクトを使用してデータをカスタマイズし、パーソナライズされたマーケティングアプローチを実現します。

## 前提条件 {#prerequisites}

* Marketo Engageのお客様のインスタンスは、IMS を有効にする必要があります。
* Marketo Engageインスタンスと AEP/AJO インスタンスは、同じ IMS 組織にある必要があります。+リンク
* 顧客は MktoSync：取り込みサービスへのアクセス（ここに追加するメモ + リンク）をプロビジョニングする必要があります

## アクションの設定 {#configure-marketo-action}

* 管理/設定/アクションに移動し、「管理」をクリックします。
* 「アクション」リストから、「アクションを作成」をクリックします。 カスタムアクションの作成について詳しくは、こちらを参照してください（+リンク）
* 「名前」、「説明」を入力し、「アクションタイプ」として「Adobe Marketo Engage」を選択します。

![](assets/engage-customaction-creation.png)

* **リクエスト** ペイロードと **応答** ペイロードの「ペイロードを編集」をクリックします。
* 両方に対して、ペイロードを作成し、専用のポップアップに貼り付けます。

![](assets/engage-customaction-payload.png)

* ペイロード値のInspectと設定
メモ：値を動的に渡すには、フィールドごとに **定数** を **変数** に変更します。

![](assets/engage-customaction-payload-fields.png)

* フィールド設定ウィンドウで **保存**」をクリックし、カスタムアクションで **保存** をクリックします。

専用のキャンバスでカスタムアクションを使用できるようになりました。


## ペイロード構文 {#payload-syntax}

### 人物

![](assets/payload-person.png)

### CustomObject

![](assets/payload-customobject.png)


**Person のペイロードの例**

```json
{
   "munchkinID": "388-KKG-245",  
   "person": {
    "priority": "normal",
    "partitionName": "XYZ",
    "dedupeFields": {
      "field1": "email",
      "field2": "firstName"
    },
    "objects": [
      {
        "email": "Email address",
        "firstName": "First name",
        "lastName": "Last name"
      }
    ]
  }
}
```

**カスタムオブジェクトのペイロードの例**

```json
{
  "munchkinID": "388-KKG-245", 
  "customObject": {
    "priority": "normal",
    "objectName": "products",
    "objects": [
      {
        "email": "Email Address",
        "productName": "Product Name",
        "productQty": "Product Quantity",
        "priceTotal": "Price Total"
      }
    ]
  }
}
```


## アクションの使用 {#engage-using}

* カスタムアクションをジャーニーキャンバスにドラッグします。 （カスタムアクション/リンクの使用方法を参照）
* リクエストパラメーターで、ペイロードに設定した動的な値を持つ各パラメーターに対して「編集」をクリックします。

![](assets/engage-use-canvas.png)

