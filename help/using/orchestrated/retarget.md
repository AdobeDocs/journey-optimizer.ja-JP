---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerを使用した調整されたキャンペーンの開始と監視
description: Adobe Journey Optimizerでオーケストレーションされたキャンペーンを開始および監視する方法について説明します。
hide: true
hidefromtoc: true
exl-id: 3c1cad30-3ed7-4df1-a46a-60394a834e79
source-git-commit: b1bee7a5ee05e0e535a982c31bafafdc760d21ae
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 1%

---

# リターゲティングクエリの作成 {#retarget}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/><b>[ リターゲティング ](retarget.md)</b> | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [ ](activities/save-audience.md) [ ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

</br>

>[!BEGINSHADEBOX]

ドキュメントを処理中

>[!ENDSHADEBOX]

リターゲティングを使用すると、以前にオーケストレーションされたキャンペーンに対する受信者の応答方法に基づいて、受信者をフォローアップできます。 例えば、最初のメールを受け取ったがクリックしなかったプロファイルに、2 番目のメールを送信できます。

**[!UICONTROL Orchestrated Campaign]** には、次の 2 つの主なデータソースが用意されています。

* **[!UICONTROL メッセージフィードバック]**：送信済みメッセージ、開封済みメッセージ、バウンスなど、配信に関連するイベントをキャプチャします。
* **[!UICONTROL メールトラッキング]**：ユーザーのアクション（クリック数や開封数など）をキャプチャします。

## フィードバックベースのリターゲティングルールの作成 {#feedback-retarget}

フィードバックベースのリターゲティングルールを使用すると、「メッセージフィードバック **データセットに取り込まれたメッセージ配信イベントに基づいて受信者をリターゲティングでき** す。 これらのイベントには、メッセージが送信される、開かれる、バウンスされる、スパムと見なされるなどの結果が含まれます。

このデータを使用すると、特定の配信ステータスに基づいたフォローアップ通信を可能にする、以前のメッセージを受信した受信者を識別するルールを定義できます。

1. 新しい **[!UICONTROL オーケストレートキャンペーン]** を作成します。

1. **[!UICONTROL オーディエンスを作成]** アクティビティを追加し、ターゲティングディメンションを **[!UICONTROL 受信者（caas）]** に設定します。

1. **[!UICONTROL ルールビルダー]** で **[!UICONTROL 条件を追加]** をクリックし、**[!UICONTROL 属性ピッカー]** から **[!UICONTROL メッセージフィードバック]** を選択します。 「**[!UICONTROL 確認]**」をクリックして、**メッセージフィードバックが存在する** 条件を作成します。

   ![](assets/retarget_1.png)

1. **[!UICONTROL フィードバックステータス]** 属性を選択して、メッセージ配信イベントをターゲットにします。

+++ 詳細な手順

   1. **[!UICONTROL メッセージフィードバック]** 属性にリンクされた別の条件を追加します。

   1. **[!UICONTROL フィードバックステータス]** 属性を検索して、「**[!UICONTROL 確認]**」をクリックします。

      ![](assets/retarget_3.png)

   1. **[!UICONTROL カスタム条件]** メニューの **[!UICONTROL 値]** ドロップダウンで、追跡する配信ステータスを選択します。

      ![](assets/retarget_4.png)

+++

1. **[!UICONTROL オーケストレーションされたキャンペーン名]** 属性を選択して、特定のオーケストレーションされたキャンペーンをターゲットにします。

+++ 詳細な手順

   1. **[!UICONTROL メッセージフィードバック]** 属性にリンクされた別の条件を追加し、**[!UICONTROL エンティティ]** を検索して、次に移動します。

      `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign entity`。

   1. **[!UICONTROL オーケストレーションされたキャンペーン名]** を選択します。

      ![](assets/retarget_5.png)

   1. **[!UICONTROL カスタム条件]** メニューの **[!UICONTROL 値]** フィールドでキャンペーン名を指定します。

+++

1. **[!UICONTROL オーケストレーションされたキャンペーンアクション名]** 属性を選択して、オーケストレーションされたキャンペーン内の特定のメッセージまたはアクティビティをターゲットにします。

+++ 詳細な手順

   1. **[!UICONTROL メッセージフィードバック]** 属性にリンクされた別の条件を追加し、**[!UICONTROL エンティティ]** を検索して、次に移動します。

      `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign entity`。

   1. **[!UICONTROL オーケストレーションされたキャンペーンアクション名]** を選択します。

      ![](assets/retarget_6.png)

   1. **[!UICONTROL カスタム条件]** メニューの **[!UICONTROL 値]** フィールドでキャンペーンアクション名を指定します。

      アクション名は、キャンバスのアクティビティの横にある ![ 情報アイコン ](assets/do-not-localize/info-icon.svg) をクリックすると見つかります。

   ++

1. 別の方法として、Campaign のプロパティにある **[!UICONTROL キャンペーン ID]** （UUID）でフィルタリングすることもできます。

## トラッキングベースのリターゲティングルールを作成

トラッキングベースのリターゲティングルールは、**[!UICONTROL メールトラッキング]** データセットからのデータを使用して、メッセージとのインタラクションに基づいて受信者をターゲットに設定します。 メールの開封数やリンクのクリック数など、ユーザーのアクションをキャプチャします。

メッセージのインタラクション（開く、クリックなど）に基づいて受信者を再ターゲットするには、次のように **[!UICONTROL メールトラッキング]** エンティティを使用します。

1. 新しい **[!UICONTROL オーケストレートキャンペーン]** を作成します。

1. **[!UICONTROL オーディエンスを作成]** アクティビティを追加し、ターゲティングディメンションを **[!UICONTROL 受信者（caa）]** に設定して、以前に調整されたキャンペーン受信者に焦点を当てます。

1. **[!UICONTROL ルールビルダー]** で「**[!UICONTROL 条件を追加]**」をクリックし、**[!UICONTROL 属性ピッカー]** から **[!UICONTROL メールトラッキング]** を選択します。

   「**[!UICONTROL 確認]**」をクリックして、**メールトラッキングが存在する** 条件を作成します。

   ![](assets/retarget_2.png)

1. プロファイルのメッセージとのインタラクションをターゲットにするには、**[!UICONTROL メールトラッキング]** 属性にリンクされた別の条件を追加し、**[!UICONTROL インタラクションタイプ]** 属性を検索します。

   ![](assets/retarget_7.png)

1. カスタム条件オプションから、「**[!UICONTROL 次に含む]**」を演算子として使用し、ユースケースに応じて 1 つ以上の値を選択します（例：**[!UICONTROL メッセージが開封されました]** または **[!UICONTROL メッセージリンクがクリックされました]**。

   ![](assets/retarget_8.png)

1. トラッキングデータを特定のキャンペーンに関連付けるには、新しい **[!UICONTROL メッセージフィードバック]** 条件を追加し、（この節 [ で説明されている手順に従っ ](#feedback-retarget) ください。
