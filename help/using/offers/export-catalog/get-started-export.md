---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: オファーカタログのエクスポートの概要
description: オファーカタログをデータセットとしてエクスポートする方法を説明します
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: f30abea1-b204-4470-9836-75fae916bbb1
version: Journey Orchestration
source-git-commit: 8732a73118b807eaa7f57cfdad60355b535282ff
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 100%

---

# オファーカタログの書き出しの概要 {#export-catalog}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。[詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

Journey Optimizer を使用すると、オファーカタログを Adobe Experience Platform に自動的にのエクスポートできます。

エクスポートすると、オファーライブラリのオブジェクトごとにデータセットが 1 つ作成されます（「[エクスポートしたデータセットへのアクセス](../export-catalog/access-dataset.md)」を参照してください）。次のものがあります。

* パーソナライズされたオファー
* フォールバックオファー
* プレースメント
* 決定

オファーライブラリでこれらのオブジェクトの 1 つが変更されるたびに、新しいエクスポートジョブが自動的に実行され、データセットが更新されます。

>[!NOTE]
>
>この機能は、デフォルトで有効になっています。追加のアクティベーション手順を行わずに使用を開始できます。有効化されると、エクスポートジョブは自動化され、ユーザー側からのアクションは不要になります。

<!--
>[!NOTE]
>
>This feature is not enabled by default. If you want to use it, reach out to your Adobe contact to have it activated for your catalog. Once it is enabled, export jobs will be automated and will require no action from your side.
-->
