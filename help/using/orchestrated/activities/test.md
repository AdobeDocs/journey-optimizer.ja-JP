---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンでのテスト アクティビティの使用
description: テストアクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: edd70849-0a21-45f2-91f3-4774a0cad9dd
source-git-commit: 3be1b238962fa5d0e2f47b64f6fa5ab4337272a5
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 62%

---

# テスト {#test}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test"
>title="テストアクティビティ"
>abstract="**テスト**&#x200B;アクティビティは&#x200B;**フロー制御**&#x200B;アクティビティです。指定した条件に基づいたトランジションを有効にできます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_test_conditions"
>title="条件"
>abstract="**テスト**&#x200B;アクティビティには、複数の出力トランジションを含めることができます。オーケストレーションされたキャンペーンの実行中、各条件のいずれかが満たされるまで、各条件が順番にテストされます。 どの条件も満たさない場合、オーケストレーションされたキャンペーンは **[!UICONTROL デフォルトの条件]** のパスに沿って続行されます。 デフォルトの条件が有効化されていない場合、オーケストレートキャンペーンはこの時点で停止します。"

+++ 目次

| オーケストレートキャンペーンへようこそ | 初めてのオーケストレートキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [ オーケストレーションされたキャンペーンを作成 ](../gs-campaign-creation.md)<br/><br/>[ キャンペーンを作成およびスケジュール ](../create-orchestrated-campaign.md)<br/><br/>[ アクティビティをオーケストレーション ](../orchestrate-activities.md)<br/><br/>[ キャンペーンを開始および監視 ](../start-monitor-campaigns.md)<br/><br/>[ レポート ](../reporting-campaigns.md) 主な手順 | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - [分岐](fork.md) - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL テスト]**&#x200B;アクティビティは&#x200B;**[!UICONTROL フロー制御]**&#x200B;アクティビティです。指定した条件に基づいたトランジションを有効にできます。

## テストアクティビティの設定 {#test-configuration}

**[!UICONTROL テスト]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL テスト]** アクティビティをオーケストレーションされたキャンペーンに追加します。

1. デフォルトでは、**[!UICONTROL テスト]**&#x200B;アクティビティは、単純なブール値テストを提示します。「True」トランジションで定義された条件が満たされると、このトランジションがアクティブ化されます。それ以外の場合は、デフォルトの「False」トランジションがアクティブ化されます。

1. トランジションに関連付けられた条件を設定するには、**[!UICONTROL パーソナライズ機能ダイアログを開く]**&#x200B;アイコンをクリックします。式エディターを使用して、このトランジションをアクティブ化するために必要なルールを定義します。また、イベント変数、条件、日付／時刻関数も活用できます。

   さらに、「**[!UICONTROL ラベル]**」フィールドを変更して、オーケストレーションされたキャンペーンキャンバスでトランジションの名前をパーソナライズできます。

   ![](../assets/workflow-test-default.png)

1. 複数の出力トランジションを&#x200B;**[!UICONTROL テスト]**&#x200B;アクティビティに追加できます。これを行うには、「**[!UICONTROL 条件を追加]**」ボタンをクリックし、ラベルと各トランジションに関連付けられた条件を設定します。v
1. オーケストレーションされたキャンペーンの実行中、各条件のいずれかが満たされるまで、各条件が順番にテストされます。 どの条件も満たさない場合、オーケストレーションされたキャンペーンは **[!UICONTROL デフォルトの条件]** のパスに沿って続行します。 デフォルト条件がアクティブ化されていない場合、ワークフローはこの時点で停止します。

## 例 {#example}

この例では、**[!UICONTROL オーディエンスを作成]**&#x200B;アクティビティがターゲットとするプロファイルの数に基づいて、様々なトランジションが有効化されます。

* ターゲットとするプロファイルが 10,000 個以上の場合は、メールメッセージが送信されます。
* 1,000～10,000 個のプロファイルの場合、SMS が送信されます。
* ターゲットプロファイルが 1,000 個未満に該当する場合は、「連絡しない」トランジションに送信されます。

![](../assets/workflow-test-example.png)

これを行うには、`vars.recCount` イベント変数を「メール」および「sms」条件で活用して、ターゲットプロファイルの数をカウントし、適切なトランジションをアクティブ化します。

![](../assets/workflow-test-example-config.png)
