---
solution: Journey Optimizer
product: journey optimizer
title: 分岐アクティビティの使用
description: 調整されたキャンペーンでの分岐アクティビティの使用方法について説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 52e8057b-dac1-45f5-9dd0-1b28a59adde9
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 82%

---

# 分岐 {#fork}

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork"
>title="「分岐」アクティビティ"
>abstract="**分岐**&#x200B;アクティビティを使用すると、アウトバウンドトランジションを作成して、複数のアクティビティを同時に開始できます。"

>[!CONTEXTUALHELP]
>id="ajo_orchestration_fork_transitions"
>title="分岐アクティビティのトランジション"
>abstract="デフォルトでは、**分岐**&#x200B;アクティビティで 2 つのトランジションが作成されます。 「**トランジションを追加**」ボタンをクリックして追加のアウトバウンドトランジションを定義し、そのラベルを入力します。"

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| [ 調整されたキャンペーンの基本を学ぶ ](../gs-orchestrated-campaigns.md)<br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](../gs-schemas.md)</li><li>[ 手動スキーマ ](../manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](../file-upload-schema.md)</li><li>[ データの取り込み ](../ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](../access-manage-orchestrated-campaigns.md) | [調整されたキャンペーンを作成する主な手順](../gs-campaign-creation.md)<br/><br/>[キャンペーンの作成とスケジュール](../create-orchestrated-campaign.md)<br/><br/>[アクティビティの調整](../orchestrate-activities.md)<br/><br/>[キャンペーンの開始と監視](../start-monitor-campaigns.md)<br/><br/>[レポート](../reporting-campaigns.md) | [ルールビルダーの操作](../orchestrated-rule-builder.md)<br/><br/>[最初のクエリの作成](../build-query.md)<br/><br/>[式の編集](../edit-expressions.md)<br/><br/>[リターゲティング](../retarget.md) | [アクティビティの基本を学ぶ](about-activities.md)<br/><br/>アクティビティ：<br/>[AND 結合](and-join.md) - [オーディエンスを作成](build-audience.md) - [ディメンションを変更](change-dimension.md) - [チャネルアクティビティ](channels.md) - [結合](combine.md) - [重複排除](deduplication.md) - [エンリッチメント](enrichment.md) - <b>[分岐](fork.md)</b> - [紐付け](reconciliation.md) - [オーディエンスを保存](save-audience.md) - [分割](split.md) - [待機](wait.md) |

{style="table-layout:fixed"}

+++


<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

**[!UICONTROL 分岐]**&#x200B;アクティビティは、複数のアウトバウンドトランジションを作成し、複数のアクティビティを並行して実行できる&#x200B;**[!UICONTROL フロー制御]**&#x200B;コンポーネントです。

## 分岐アクティビティの設定{#fork-configuration}

次の手順に従って、**[!UICONTROL 分岐]**&#x200B;アクティビティを設定します。

![](../assets/workflow-fork.png)

1. **[!UICONTROL 分岐]**&#x200B;アクティビティを調整されたキャンペーンに追加します。

1. **[!UICONTROL ラベル]**&#x200B;を定義します。

1. 各アウトバウンドトランジションにラベルを割り当てます。デフォルトでは、2 つのトランジションが指定されています。

1. トランジションを削除するには、「![](../assets/do-not-localize/Smock_Delete_18_N.svg)」アイコンをクリックします。

1. 必要に応じて、「**[!UICONTROL トランジションを追加]**」をクリックして、さらにアウトバウンドトランジションを追加します。
