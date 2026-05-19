---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: オファーカタログの書き出しの基本を学ぶ
description: オファーカタログをデータセットとしてエクスポートする方法を説明します
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: f30abea1-b204-4470-9836-75fae916bbb1
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/71W86v7R-wgsa7JDTE3d6Lddc71MOcTxrY5l0Ts600o
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
feature_v2: id: ed0d8d0e-04b9-4326-be72-a0fbca265377id: fe338112-e2ce-4876-8989-fc4d497613f1id: fe96aceb-8194-4a8a-a6b0-75302d02804d
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 100%

---

# オファーカタログの書き出しの基本を学ぶ {#export-catalog}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

Journey Optimizer を使用すると、オファーカタログを Adobe Experience Platform に自動的にのエクスポートできます。

エクスポートすると、オファーライブラリのオブジェクトごとにデータセットが 1 つ作成されます（「[エクスポートしたデータセットへのアクセス](../export-catalog/access-dataset.md)」を参照してください）。 次のものがあります。

* パーソナライズされたオファー
* フォールバックオファー
* プレースメント
* 決定

オファーライブラリでこれらのオブジェクトの 1 つが変更されるたびに、新しいエクスポートジョブが自動的に実行され、データセットが更新されます。

>[!NOTE]
>
>この機能は、デフォルトで有効になっています。 追加のアクティベーション手順を行わずに使用を開始できます。 有効化されると、エクスポートジョブは自動化され、ユーザー側からのアクションは不要になります。

<!--
>[!NOTE]
>
>This feature is not enabled by default. If you want to use it, reach out to your Adobe contact to have it activated for your catalog. Once it is enabled, export jobs will be automated and will require no action from your side.
-->
