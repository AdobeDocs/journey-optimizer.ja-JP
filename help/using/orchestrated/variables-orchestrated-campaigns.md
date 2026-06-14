---
solution: Journey Optimizer
product: journey optimizer
title: オーケストレーションされたキャンペーンでの変数の使用
description: オーケストレーションキャンペーンでイベント変数を使用して、条件とターゲティングルールを構築する方法を説明します。
feature: Campaigns
topic: Content Management
role: User
level: Intermediate
version: Campaign Orchestration
exl-id: 3f2a1c0d-8e9b-4a7c-b5d1-0f2e3a4b5c6d
feature_v2: 
subfeature_v2: id: b5e335a9-0e5f-4dda-8845-c4ac5dca2be4
source-git-commit: cda41058be1eb26538f4b0ef8c7b6c3f1c01eccd
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 1%

---


# オーケストレーションされたキャンペーンでの変数の使用 {#variables-oc}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、シグナルまたはグローバル定義から変数を設定し、それらを使用してオーケストレーションされたキャンペーンでターゲティング、条件、テスト アクティビティ ロジックを促進する方法を説明します。

>[!ENDSHADEBOX]

## 変数の設定方法 {#set}

オーケストレーションキャンペーンでは、変数（ターゲティングを促進する値、**[!UICONTROL テスト]**&#x200B;条件、その他のキャンバスロジック）を使用して作業できます。 これらの値は、次の2つの場所から取得できます。

* **シグナル** — キャンペーン スケジュールが&#x200B;**[!UICONTROL シグナル]**&#x200B;によってトリガーされる場合、キャンペーンを実行するときにパラメーターを渡すことができます。 これらのパラメーターは、その実行のトリガーされたオーケストレーションキャンペーンで変数として使用できるようになります。 [ シグナルを使用してオーケストレーションされたキャンペーンをトリガーする方法を学ぶ](trigger-orchestrated-campaign.md)

* **グローバル変数** — **[!UICONTROL 変数の編集]** メニューを使用して、キャンペーン上で名前と値のペアを直接定義できます。APIやシグナルは必要ありません。 [ オーケストレーションされたキャンペーンでグローバル変数を定義する方法を学ぶ](global-variables.md)

>[!NOTE]
>
>現時点では、変数は&#x200B;**text**&#x200B;の値のみをサポートしています。
>
>変数は&#x200B;**キャンバスロジック** （ルール、条件）を駆動するので、メッセージのパーソナライズには使用できません。

## キャンバスでの変数の使用 {#use}

変数は、キャンバスの次の場所で使用できます。

* **ルールビルダー** — ルールの式エディターを開き、**イベント変数** ピッカーを使用して変数を選択し、その参照を式に挿入します。 [詳しくは、式の編集方法を参照してください。](edit-expressions.md)

  次の例では、`brand`という名前の変数が渡され、ルールはそれをフィルター条件として使用します。

  ![ イベント変数からブランド変数を使用するルールビルダー条件](assets/variables-rule.png){zoomable="yes"}

* **[!UICONTROL テスト ] アクティビティ** – 条件を定義すると、**[!UICONTROL 条件タイプ]** ドロップダウンには、スコープ内のすべての変数が&#x200B;**[!UICONTROL 人口数]**&#x200B;と共に一覧表示されます。 テスト ブランチのベースとして使用する変数を選択します。 [**[!UICONTROL テスト]** アクティビティ ](activities/test.md)の設定方法について説明します

  以下の例では、`channel`変数を使用して、その値に応じて異なる遷移にフローをルーティングします。

  ![ チャネル変数を一覧表示するアクティビティ条件タイプのドロップダウンをテスト ](assets/variables-test.png){zoomable="yes"}
