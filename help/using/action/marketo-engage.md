---
solution: Journey Optimizer
product: journey optimizer
title: Marketo Engage との統合
description: Marketo Engage アクションの使用方法を学ぶ
feature: Journeys, Actions, Custom Actions
topic: Administration
role: Developer, Admin
level: Intermediate
keywords: Marketo、Marketo Engage 統合
exl-id: 70d1ef5a-743b-4362-bb65-93a8c996209f
TQID: https://experienceleague.adobe.com/-aRINahKmp9bI1tyW-XA-LzZOFeoEPXpWoH8JydG6Rk
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 96%

---

# Marketo Engage との統合 {#integrating-with-marketo-engage}

Marketo Engage とのシームレスなデータ統合のジャーニーを開始しましょう。 Adobe Journey Optimizer と Marketo Engage を統合するための特定のカスタムアクションがジャーニーで使用できます。 このカスタムアクションは、次の 2 つの主要なデータタイプの取り込みをサポートしています。

* **ユーザー**（プロファイル）：Marketo では、プロファイルを実用的なインサイトに変換します。
* **カスタムオブジェクト**：製品などのカスタムオブジェクトをデータを調整し、パーソナライズされたマーケティングアプローチを実現します。

## 前提条件 {#prerequisites}

この統合には、次の前提条件が適用されます。

* Marketo Engage の顧客インスタンスは、IMS 対応である必要があります。
* Marketo Engage インスタンスと Adobe Experience Platform／Journey Optimizer インスタンスは、同じ組織内に存在する必要があります。
* 顧客は **MktoSync：取り込みサービスへのアクセス**&#x200B;をプロビジョニングする必要があります

## アクションの設定 {#configure-marketo-action}


Journey Optimizer では、Marketo Engage のカスタムアクションを設定する必要があります。 次の手順に従います。

1. 「管理」メニューセクションで「**[!UICONTROL 設定]**」を選択します。
1. 「**[!UICONTROL アクション]**」セクションで、「**[!UICONTROL アクションを作成]**」をクリックします。 画面の右側にアクション設定パネルが開きます。
1. 名前、説明を入力し、**Adobe Marketo Engage**&#x200B;を&#x200B;**アクションタイプとして選択します**
   ![](assets/engage-customaction-creation.png){width="40%" align="left"}
1. **リクエスト**&#x200B;および&#x200B;**応答**&#x200B;ペイロードの&#x200B;**ペイロードを編集**&#x200B;アイコンをクリックします。
1. どちらの場合も、ペイロードを作成し、専用のポップアップに貼り付けます。
   ![](assets/engage-customaction-payload.png){width="70%" align="left"}
1. ペイロード値を検査および設定します

   メモ：値を動的に渡すには、フィールドごとに&#x200B;**定数**&#x200B;を&#x200B;**変数**&#x200B;に変更します。

   ![](assets/engage-customaction-payload-fields.png){width="70%" align="left"}

1. フィールド設定画面で「**保存**」をクリックし、カスタムアクションで「**保存**」をクリックします。

これで、ジャーニーキャンバスでカスタムアクションを使用できるようになりました。

## ペイロード構文 {#payload-syntax}

### 人物

![](assets/payload-person.png)

### CustomObject

![](assets/payload-customobject.png)


**人物のペイロードの例**

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

設定したアクションごとに、ジャーニー designer パレットで Marketo Engage アクションアクティビティを使用できます。

使用するには、次の手順に従います。

1. カスタムアクションをジャーニーキャンバスにドラッグします。

1. このアクションのラベルと説明を入力します。

1. 「**リクエストパラメーター**」セクションで、各パラメーターの「**編集**」アイコンをクリックし、ペイロードで設定した動的な値を選択します。

![](assets/engage-use-canvas.png){width="70%" align="left"}
