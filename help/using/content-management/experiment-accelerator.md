---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer Experimentation Accelerator
description: 効果的に実験を行い、インサイトを生み出す能力の向上
feature: Experimentation
topic: Content Management
role: User
level: Beginner
keywords: コンテンツ, 実験, 複数, オーディエンス, 処理
hide: true
hidefromtoc: true
source-git-commit: 11c62deaf90b961233a35b9c4be8b81264b4c8e7
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 15%

---

# Journey Optimizer Experimentation Acceleratorの概要 {#content-experiment}

>[!BEGINSHADEBOX]

* **[Journey Optimizer Experimentation Acceleratorの概要](experiment-accelerator.md)**
* [Journey Optimizer Experimentation Acceleratorを使用した AI でのデータ使用](experiment-accelerator-security.md)
* [Journey Optimizer Experimentation Accelerator ベストプラクティス](experiment-accelerator-best-practices.md)
* [実験の監視](experiment-accelerator-monitor.md)
* [実験指標](experiment-accelerator-metrics.md)

>[!ENDSHADEBOX]

>[!AVAILABILITY]
>
>**Journey Optimizer Experimentation Accelerator** では、Adobe TargetまたはAdobe Journey Optimizerのライセンスが必要です。

**0}Journey Optimizer Experimentation Accelerator} は、実験プロセスを合理化および強化するために設計された強力なツールです。** Adobe TargetやAdobe Journey Optimizerと統合することにより、実験を管理、分析および最適化するための一元的なプラットフォームを提供します。 Journey Optimizer Experimentation Acceleratorでは、AI に基づくインサイトとアダプティブテストを活用して、データに基づく意思決定を行い、マーケティング戦略を改善し、測定可能な結果を導くことができます。

主なメリットは次のとおりです。

* **より迅速な実験**：時間の経過と共に調整されるモデルを使用して、アダプティブな常時稼動のテストを実行します。

* **統合プラットフォーム**:Adobe TargetとJourney Optimizerのすべての実験を 1 か所で管理します。

* **AI 駆動型インサイト**：主要な調査結果、パフォーマンスの推進要因、新しい機会を自動的に明らかにします。

* **よりスマートなターゲティング**：行動データとコンテンツデータを使用して効果の高い実験を優先順位付けします。

* **KPI 監視**：実験全体にわたる上昇率や信頼性などの指標を追跡します。

* **シームレスなCollaboration**：結果を簡単に共有し、リアルタイムのアラートでチームロールを管理します。

## Journey Optimizer Experimentation Acceleratorへのアクセス

[ 実験を作成して設定 ](content-experiment.md) し、キャンペーンやジャーニーをプロファイルに送信した後、**[!UICONTROL Journey Optimizer Experimentation Accelerator]** にアクセスして、実験のパフォーマンスを詳しく調べることができます。

**[!UICONTROL 実験]** ドロップダウンの左側のメニューから、またはアプリ切り替えボタンを使用して [!UICONTROL 0}Journey Optimizer Experimentation Accelerator} にアクセスできます。 ]Target ライセンスを持つユーザーのみが、アプリ切り替えボタンからのみアクセスできます。

使用可能な実験は、設定によって異なります。

* **Adobe Journey Optimizer ユーザーの場合**：有効にした組織のサンドボックスで設定した実験は、自動的に含まれます。

* **Journey Optimizerを使用しているAdobe Target ユーザーの場合**:Target の A/B アクティビティは、Journey Optimizerの実稼動サンドボックスの **[!UICONTROL 2}Journey Optimizer Experimentation Accelerator} に表示されます。]**

* **Adobe Targetのみのユーザーの場合**:Target 組織内のすべての A/B アクティビティは、Journey Optimizerの実稼動サンドボックスに含まれます。

**[!UICONTROL Journey Optimizer Experimentation Accelerator]** を使用するには、サンドボックスへのアクセスと、次の関連する権限が必要です。

* **[!UICONTROL 実験を表示]**
* **[!UICONTROL 実験メタデータの管理]**

+++ 実験に関連する権限の割り当て方法を学ぶ

1. **[!DNL Permissions]** 製品で、「**[!UICONTROL 役割]**」タブに移動し、目的の **[!UICONTROL 役割]** を選択します。

1. 「**[!UICONTROL 編集]**」をクリックして、権限を変更します。

1. **[!UICONTROL 実験アクセラレーター]** リソースを追加し、ドロップダウンメニューから **[!UICONTROL 実験を表示]** または **[!UICONTROL 実験メタデータを管理]** を選択します。

   ![](assets/permissions-experiment.png)

1. 「**[!UICONTROL 保存]**」をクリックして、変更を適用します。

この役割に既に割り当てられているユーザーの権限は、自動的に更新されます。

この役割を新しいユーザーに割り当てるには：

1. 役割ダッシュボード内の「**[!UICONTROL ユーザー]**」タブに移動し、「**[!UICONTROL ユーザーを追加]**」をクリックします。

1. ユーザーの名前、メールアドレスを入力するか、リストから選択して、「**[!UICONTROL 保存]**」をクリックします。

   まだユーザーを作成していない場合は、[このドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/abac/permissions-ui/users)を参照してください。

ユーザーは、インスタンスにアクセスする手順が記載されたメールを受信します。

+++

<!--table style="table-layout:fixed"><tr style="border: 0;">
<td><img alt="Overview" href="experiment-accelerator-overview.md" src="assets/do-not-localize/experiments-2.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-overview.md">Overview</a></strong></p></div></td>
<td><img alt="Experiments" href="experiment-accelerator-monitor.md" src="assets/do-not-localize/experiment-overview.jpeg">
<div align="center"><p><strong><a href="experiment-accelerator-monitor.md">Experiments</a></strong></p></div></td>
<td><img alt="Metrics" href="experiment-accelerator-metrics.md" src="assets/do-not-localize/experiment-metrics.png">
<div align="center"><p><strong><a href="experiment-accelerator-metrics.md">Metrics</a></strong></p></div></td>
</tr></table-->
