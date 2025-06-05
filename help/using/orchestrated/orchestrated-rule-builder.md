---
solution: Journey Optimizer
product: journey optimizer
title: ルールビルダーの操作
description: オーケストレートキャンペーン用のルールを作成する方法を説明します
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: fb7a0eb2-b2ff-49fa-af1f-f1c10f219b00
source-git-commit: 5872e192c849b7a7909f0b50caa1331b15490d79
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 16%

---


# ルールビルダーの操作 {#orchestrated-rule-builder}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | キャンペーンアクティビティをキャンセル |
|---|---|---|---|
| [ オーケストレーションされたキャンペーンの概要 ](gs-orchestrated-campaigns.md)<br/><br/>[ 設定手順 ](configuration-steps.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ オーケストレーションされたキャンペーンの作成 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ オーケストレーションされたキャンペーンでのメッセージの送信 ](send-messages.md)<br/><br/>[ キャンペーンの開始および監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションを変更 ](activities/change-dimension.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) - [ 分割 ](activities/split.md) [ ](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

オーケストレートキャンペーンには、様々な条件に基づいてデータベースをフィルタリングするプロセスを簡素化するルールビルダーが付属しています。 ルールビルダーは、非常に複雑で長いクエリを効率的に管理し、柔軟性と精度を向上させます。

また、条件内で定義済みフィルターをサポートしているので、ユーザーは包括的なオーディエンスのターゲティングとセグメント化戦略に高度な式と演算子を利用しながら、クエリを簡単に絞り込むことができます。

## ルールビルダーへのアクセス

ルールビルダーは、**[!UICONTROL オーディエンスを作成]** アクティビティでクエリを作成してオーディエンスをターゲットにする際に使用できます。 ターゲットにする母集団を指定し、ニーズに合わせて新しいオーディエンスを簡単に作成できます。

![ オーディエンスを作成アクティビティを示す画像 ](assets/rule-builder-query.png)

## ルールビルダーインターフェイス {#interface}

ルールビルダーは、クエリを構築するための中央キャンバスと、ルールに関する情報を提供するプロパティペインを提供します。

![ ルールビルダーインターフェイスを示す画像 ](assets/rule-builder-interface.png)

* **中央キャンバス** では、様々なコンポーネントを追加および組み合わせてルールを作成します。 ツールバーには、ルールコンポーネントを簡単に操作するためのオプションが用意されています。

  | ツールバーアイコン | 説明 |
  |--- |--- |
  | ![ 選択アイコンを上に移動 ](assets/do-not-localize/rule-builder-icon-up.svg) | コンポーネントを 1 行上に移動します。 |
  | ![ 選択アイコンを下に移動 ](assets/do-not-localize/rule-builder-icon-down.svg) | コンポーネントを行下に移動します。 |
  | ![ グループ選択アイコン ](assets/do-not-localize/rule-builder-icon-group.svg) | 2 つのコンポーネントを 1 つのグループに配置します。 |
  | ![ 選択アイコンのグループ解除 ](assets/do-not-localize/rule-builder-icon-ungroup.svg) | 単一グループのコンポーネントを分離します。 |
  | ![ すべて展開アイコン ](assets/do-not-localize/rule-builder-icon-expand.svg) | すべてのグループを展開します。 |
  | ![ すべて折りたたむアイコン ](assets/do-not-localize/rule-builder-icon-collapse.svg) | すべてのグループを折りたたみます。 |
  | ![ すべて削除アイコン ](assets/do-not-localize/rule-builder-icon-delete.svg) | すべてのグループとコンポーネントを削除します。 |

* **[!UICONTROL ルールのプロパティ]** ペインには、ルールに関する情報が表示されます。 様々な操作を実行してルールを確認し、ニーズに合っていることを確認できます。

  このパネルは、オーディエンスを作成するクエリを作成する際に表示されます。[クエリを確認および検証する方法を学ぶ](build-query.md#check-and-validate-your-query)
