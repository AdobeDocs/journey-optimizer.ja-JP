---
solution: Journey Optimizer
product: journey optimizer
title: 調整されたキャンペーンの基本を学ぶ
description: 調整されたキャンペーンを開始する方法を学ぶ
badge: label="アルファ版"
hide: true
hidefromtoc: true
exl-id: 611dd06d-aa18-4fa3-a477-8a910cec21d8
source-git-commit: 1a9ea09fcbf304b1649a5ae88da34bd209e9ac8b
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 7%

---

# 調整されたキャンペーンの基本を学ぶ {#orchestrated-camp}

+++ 目次

| 調整されたキャンペーンへようこそ | 最初の調整されたキャンペーンの開始 | データベースのクエリ | 調整されたキャンペーンアクティビティ |
|---|---|---|---|
| <b>[ 調整されたキャンペーンの基本を学ぶ ](gs-orchestrated-campaigns.md)</b><br/><br/> リレーショナルスキーマとデータセットの作成および管理：</br> <ul><li>[ スキーマとデータセットの概要 ](gs-schemas.md)</li><li>[ 手動スキーマ ](manual-schema.md)</li><li>[ ファイルアップロードスキーマ ](file-upload-schema.md)</li><li>[ データの取り込み ](ingest-data.md)</li></ul>[ オーケストレーションされたキャンペーンへのアクセスと管理 ](access-manage-orchestrated-campaigns.md)<br/><br/>[ オーケストレーションされたキャンペーンを作成するための主な手順 ](gs-campaign-creation.md) | [ キャンペーンの作成とスケジュール設定 ](create-orchestrated-campaign.md)<br/><br/>[ アクティビティのオーケストレーション ](orchestrate-activities.md)<br/><br/>[ キャンペーンの開始と監視 ](start-monitor-campaigns.md)<br/><br/>[ レポート ](reporting-campaigns.md) | [ ルールビルダーの操作 ](orchestrated-rule-builder.md)<br/><br/>[ 最初のクエリの作成 ](build-query.md)<br/><br/>[ 式の編集 ](edit-expressions.md)<br/><br/>[ リターゲティング ](retarget.md) | [ アクティビティの基本を学ぶ ](activities/about-activities.md)<br/><br/> アクティビティ：<br/>[AND 結合 ](activities/and-join.md) - [ オーディエンスを作成 ](activities/build-audience.md) - [ ディメンションの変更 ](activities/change-dimension.md) - [ チャネルアクティビティ ](activities/channels.md) - [ 結合 ](activities/combine.md) - [ 重複排除 ](activities/deduplication.md) - [ エンリッチメント ](activities/enrichment.md) - [ 分岐 ](activities/fork.md) - [ 紐付け ](activities/reconciliation.md) [&#128279;](activities/save-audience.md) [&#128279;](activities/split.md) [&#128279;](activities/wait.md) - |

{style="table-layout:fixed"}

+++

<br/>

>[!BEGINSHADEBOX]

</br>

このページのコンテンツは最終的なものではなく、変更される場合があります。

>[!ENDSHADEBOX]

[!DNL Adobe Journey Optimizer] のキャンペーンオーケストレーションは、あらゆるチャネルにわたって高度な、ブランド主導のマーケティングキャンペーンを強化し、エンゲージメント、収益、顧客ロイヤルティを大規模に推進するのに役立ちます。

クロスチャネルマーケティングは必須ですが、調整されたキャンペーンにより、シームレスに行うことができます。 視覚的なドラッグ&amp;ドロップインターフェイスを使用すると、複数のチャネルをまたいで、セグメント化からメッセージ配信に至る複雑なマーケティングワークフローをデザインして自動化できます。 すべてが、速度、制御、効率のために構築された、1 つの直感的な環境で行われます。

![](assets/canvas-example-diagram.png){zoomable="yes"}

## コア機能

キャンペーンオーケストレーションは、次の 4 つの主要な柱に基づいて構築されます。

<table style="table-layout:auto">
<tr style="border: 0;">
<td><img alt="オンデマンドオーディエンス" src="assets/do-not-localize/icon-audience.svg" width="50px"></a></td><td><b> オンデマンドオーディエンス </b><br/> データセット間で即座にクエリを実行し、データタイプとディメンションの任意の組み合わせを使用してオーディエンスセグメントを作成します。</td></tr>
<tr style="border: 0;">
<td><img alt="マルチエンティティのセグメント化と送信" src="assets/do-not-localize/icon-entity.svg" width="50px"></a></td><td><b> マルチエンティティのセグメント化と送信 </b><br/> ユーザーベースのキャンペーンを超えて、製品カタログ、店舗の場所、サービスデータなどのエンティティを使用して、正確にターゲットを設定します。</td></tr>
<tr style="border: 0;">
<td><img alt="送信前の可視性と精度" src="assets/do-not-localize/icon-visibility.svg" width="50px"></a></td><td><b> 事前送信の可視性と精度 </b><br/> ローンチ前に正確なセグメント化数と完全なキャンペーン範囲を取得し、精度と信頼性を確保します。</td></tr>
<tr style="border: 0;">
<td><img alt="複数ステップのキャンペーンワークフロー" src="assets/do-not-localize/icon-multistep.svg" width="50px"></a></td><td><b> 複数手順のキャンペーンワークフロー </b><br/> 毎日のメッセージから、季節的なプロモーションや主要な製品の発売などの複雑なキャンペーンまで、複数手順のキャンペーンを設計します。</td></tr>
</table>

## 調整されたキャンペーンとジャーニー

調整されたキャンペーンのビジュアライゼーションはジャーニーに類似していますが、様々な目的やユースケースが解決されます。

* **ジャーニー** – 各プロファイルが自分のペースで異なるステップを進む 1～1 つのキャンバス。 リアルタイムのアクションをトリガーするために、各顧客のステータスはコンテキスト内に維持されます。

* **オーケストレートキャンペーン** - ジャーニーとは異なり、オーケストレートキャンペーンは、セグメントを計算するバッチキャンバスを使用して動作します。 すべてのプロファイルが同時に処理されます。

## 前提条件

調整されたキャンペーンを操作する前に、適切な権限を持っていることを確認することが重要です。 オーケストレーションされたキャンペーンへのアクセスは、オーケストレーションされたキャンペーン管理者、オーケストレーションされたキャンペーン承認者、オーケストレーションされたキャンペーンマネージャー、オーケストレーションされたキャンペーンビューアなど、関連する **[!UICONTROL 製品プロファイル]** に割り当てられているユーザーに制限されます。

オーケストレーションされたキャンペーン機能にアクセスできない場合は、管理者に連絡して必要な権限をリクエストしてください。

➡️[ オーケストレートキャンペーンに関連する製品プロファイルの詳細情報 ](../administration/ootb-product-profiles.md)

## さらに深く掘り下げましょう

これで、共有キャンペーンの概要を理解できたので、ドキュメントの節で詳しく説明し、この機能の使用を開始します。

<table><tr style="border: 0; text-align: center;">
<td>
<a href="gs-campaign-creation.md">
<img alt="ワークフローへのアクセスと管理" src="assets/do-not-localize/workflow-access.jpeg">
</a>
<div>
<a href="gs-campaign-creation.md"><strong>設定の手順</strong></a>
</div>
<p>
</td>
<td>
<a href="create-orchestrated-campaign.md">
<img alt="リード" src="assets/do-not-localize/workflow-create.jpeg">
</a>
<div><a href="create-orchestrated-campaign.md"><strong> オーケストレーションされたキャンペーンの作成 </strong>
</div>
<p>
</td>
<td>
<a href="activities/about-activities.md">
<img alt="低頻度" src="assets/do-not-localize/workflow-activities.jpeg">
</a>
<div>
<a href="activities/about-activities.md"><strong> アクティビティの操作 </strong></a>
</div>
<p></td>
</tr></table>
