---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのフィールド
description: ジャーニーのフィールド
feature: Journeys, Reporting
topic: Content Management
role: Developer, Admin
level: Experienced
exl-id: 177b4a97-c757-40ca-a190-fbd88169e5e2
TQID: https://experienceleague.adobe.com/dpQ6PEm-afX4PZuWSPrpAWDH7yBhUKZHZRF134VehAg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a9f73820-6899-47c2-a597-3fec28ab756a
  - id: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
subfeature_v2:
  - id: d145add9-d5b9-481b-aa8a-e15e6bb7f813
  - id: a7289281-9ae4-47b1-b8cf-4028b98af776
  - id: b5afe8bf-bda6-41b5-ba06-922638872d63
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 100%

---

# ジャーニーのフィールド {#sharing-journey-fields}

このフィールドグループは、**ジャーニー**&#x200B;のスキーマで（**journeyStepEvent** と関連して）使用します。 以下に示すフィールドが含まれます。


>[!NOTE]
>
>ジャーニーのプロパティ属性について詳しくは、[この節](../building-journeys/expression/journey-properties.md#journey-properties-fields)を参照してください。


## journeyID {#journeyid-field}

メインジャーニーの ID。

型：文字列

## journeyVersionID {#journeyversionid-field}

ジャーニーバージョンの ID。 この ID はジャーニーを表します。

型：文字列

## name {#name-field}

ジャーニーの名前。

型：文字列

>[!NOTE]
>
>ジャーニー名は、ジャーニー実行データをレポートデータセットにリンクするために使用されます。 ジャーニーを名前変更する場合は、正確なレポートを維持するために、新しい名前がレポートデータセットの名前と一致していることを確認します。 不一致により、レポートデータが期待どおりに表示されない場合があります。 詳しくは、[レポートデータが欠落している場合のトラブルシューティング](../building-journeys/report-journey.md#troubleshooting-missing-data)を参照してください。

## description {#description-field}

ジャーニーの説明。

型：文字列

## version {#version-field}

バージョン。`major``minor` で表します。

型：文字列
