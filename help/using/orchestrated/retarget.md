---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Journey Optimizerを使用した調整されたキャンペーンの開始と監視
description: Adobe Journey Optimizerでオーケストレーションされたキャンペーンを開始および監視する方法について説明します。
hide: true
hidefromtoc: true
exl-id: 3c1cad30-3ed7-4df1-a46a-60394a834e79
source-git-commit: 0ae8372c179707a87a6b512a5420753a4aaef754
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 2%

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

Orchestrated Campaign には、そのための 2 つの主なデータソースが用意されています。

- **メッセージフィードバック**：送信済みメッセージ、開封済みメッセージ、バウンスなど、配信に関連するイベントをキャプチャします。

- **メールトラッキング**：ユーザーのアクション（クリック数や開封数など）をキャプチャします。

## フィードバックベースのリターゲティングルールの作成

フィードバックベースのリターゲティングルールを使用すると、「メッセージフィードバック **データセットに取り込まれたメッセージ配信イベントに基づいて受信者をリターゲティングでき** す。 これらのイベントには、メッセージが送信される、開かれる、バウンスされる、スパムと見なされるなどの結果が含まれます。

このデータを使用すると、以前のメッセージを受信したが関与しなかった受信者を識別するルールを定義して、特定の配信ステータスに基づくフォローアップ通信を有効にできます。

1. 新しい **オーケストレートキャンペーン** を作成します。

2. **オーディエンスを作成** アクティビティを追加し、ターゲティングディメンションを **受信者（caas）** に設定します。

3. **ルールビルダー** で **条件を追加** をクリックし、属性ピッカーから **メッセージフィードバック** を選択します。 「**確認**」をクリックします。

4. **フィードバックステータス** の条件を追加し、値を **送信済みメッセージ** に設定します。

5. 特定のオーケストレーションされたキャンペーンをターゲットにするには：

   - 別の条件を追加し、`entity` を検索して、次の場所に移動します。\
     `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign`。

   - **オーケストレーションされたキャンペーン名** を選択し、キャンペーン名を指定します。

6. オーケストレーションされたキャンペーン内の特定のメッセージまたはアクティビティをターゲットにするには：

   - 別の条件を追加し、`entity` を検索して、次の場所に移動します。\
     `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign`。

   - **オーケストレーションされたキャンペーンアクション名** を選択し、キャンペーンアクション名を指定します。

     アクション名は、キャンバスのアクティビティの横にある ![ 情報アイコン ](assets/do-not-localize/info-icon.svg) をクリックすると見つかります。

   >[!TIP]
   >
   >名前を使用する代わりに、Campaign のプロパティにある **キャンペーン ID** （UUID）でフィルタリングすることもできます。

## トラッキングベースのリターゲティングルールを作成

トラッキングベースのリターゲティングルールは、**メールトラッキング** データセットからのデータを使用して、メッセージとのインタラクションに基づいて受信者をターゲットに設定します。 メールの開封数やリンクのクリック数など、ユーザーのアクションをキャプチャします。

メッセージのインタラクション（開く、クリックなど）に基づいて受信者を再ターゲットするには、次のように **メールトラッキング** エンティティを使用します。

1. 新しい **オーケストレーションされたキャンペーン** を作成し、**受信者（caas）** をターゲティングディメンションとして使用して **オーディエンスを作成** アクティビティを追加して、以前のオーケストレーションされたキャンペーン受信者に焦点を当てます。

1. **メールトラッキング** の新しい条件を追加します。 「**確認**」をクリックして、「などのメールトラッキングが存在する」条件を作成します。

1. その条件内で条件を追加し、**インタラクションタイプ** 属性を検索します。

1. カスタム条件オプションから、「**次に含む**」を演算子として使用し、ユースケースに応じて 1 つ以上の値を選択します。 例：
   - **メッセージが開かれました**
   - **メッセージリンクをクリック**

1. トラッキングデータを特定のキャンペーンに関連付けるには：

   - メールトラッキングブロック内に条件を追加します。

   - `_experience > CustomerJourneyManagement > Entities > AJO Orchestrated Campaign` に移動します。

   - **オーケストレーションされたキャンペーン名** と、必要に応じて **オーケストレーションされたキャンペーンアクション名** の両方の条件を追加します。

     アクション名は、キャンバスのアクティビティの横にある ![ 情報アイコン ](assets/do-not-localize/info-icon.svg) をクリックすると見つかります。

   >[!TIP]
   >
   >名前を使用する代わりに、Campaign のプロパティにある **キャンペーン ID** （UUID）でフィルタリングすることもできます。
