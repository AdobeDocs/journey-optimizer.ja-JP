---
solution: Journey Optimizer
product: journey optimizer
title: 複数手順キャンペーン作成の主な原則
description: Adobe Journey Optimizerを使用した複数手順キャンペーンの主な原則を学ぶ
hide: true
hidefromtoc: true
source-git-commit: 00f843300a9cfe798ea4d3a92fbe89ba80e70bc5
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 36%

---


# 複数手順キャンペーン作成の主な原則 {#ms-campaign-creation}

Adobe Journey Optimizerを使用すると、複数の手順から成るキャンペーンを視覚的なキャンバスに作成して、セグメント化、キャンペーン実行、ファイル処理などのクロスチャネルプロセスを設計できます。

## 複数手順キャンペーンの内容は何ですか？ {#gs-ms-campaign-inside}

複数ステップのキャンペーン図は、実行される処理を表したものです。 これは、実行される様々なタスクと、タスク同士の関係を示すものです。

![](assets/workflow-example.png){zoomable="yes"} {zoomable="yes"}

各複数手順キャンペーンには、次のものが含まれます。

* **アクティビティ**：アクティビティとは、実行されるタスクです。各種アクティビティは、ダイアグラム内にアイコンで示されます。各アクティビティには、特定のプロパティと、すべてのアクティビティに共通のその他のプロパティがあります。

  複数ステップのキャンペーン図では、指定されたアクティビティが、特にループまたは繰り返しアクションがある場合に複数のタスクを生成できます。

* **トランジション**：トランジションは、ソースアクティビティを宛先アクティビティにリンクし、そのシーケンスを定義します。

* **作業用テーブル**：作業用テーブルには、トランジションによって実行されるすべての情報が含まれます。各複数ステップのキャンペーンは、複数のワークテーブルを使用します。 これらのテーブルで伝達されたデータは、複数ステップのキャンペーンのライフサイクルを通じて使用できます。

## 複数手順キャンペーンを作成するための主な手順 {#gs-ms-campaign-steps}

複数手順キャンペーンを作成するための主な手順は次のとおりです。

![](assets/workflow-creation-process.png){zoomable="yes"}

