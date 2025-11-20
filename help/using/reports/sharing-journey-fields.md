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
source-git-commit: 6961a07e2874f9beb76a9beaebb29997d114d8e7
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 60%

---

# ジャーニーのフィールド {#sharing-journey-fields}

このフィールドグループは、**ジャーニー**&#x200B;のスキーマで（**journeyStepEvent** と関連して）使用します。以下に示すフィールドが含まれます。


>[!NOTE]
>
>ジャーニーのプロパティ属性について詳しくは、[この節](../building-journeys/expression/journey-properties.md#journey-properties-fields)を参照してください。


## journeyID {#journeyid-field}

メインジャーニーの ID。

型：文字列

## journeyVersionID {#journeyversionid-field}

ジャーニーバージョンの ID。この ID はジャーニーを表します。

型：文字列

## name {#name-field}

ジャーニーの名前。

型：文字列

>[!NOTE]
>
>ジャーニー名は、ジャーニー実行データをレポートデータセットにリンクするために使用されます。 ジャーニーの名前を変更する場合は、正確なレポートを維持するために、新しい名前がレポートデータセットの名前と一致することを確認してください。 不一致により、レポートデータが期待どおりに表示されない場合があります。 詳しくは、[ レポートデータが見つからないトラブルシューティング ](../building-journeys/report-journey.md#troubleshooting-missing-data) を参照してください。

## description {#description-field}

ジャーニーの説明。

型：文字列

## バージョン {#version-field}

バージョン。`major``minor` で表します。

型：文字列
