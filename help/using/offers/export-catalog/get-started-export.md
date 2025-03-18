---
title: オファーカタログの書き出しの概要
description: オファーカタログをデータセットとして書き出す方法を説明します
feature: Decision Management, Datasets
topic: Integrations
role: User, Data Engineer
level: Intermediate
exl-id: f30abea1-b204-4470-9836-75fae916bbb1
source-git-commit: 91584f394d956df4b69a885feacc40435360dae3
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 100%

---

# オファーカタログの書き出しの概要 {#export-catalog}

Journey Optimizer を使用すると、オファーカタログを Adobe Experience Platform に自動的にの書き出すことができます。

書き出すと、オファーライブラリのオブジェクトごとにデータセットが 1 つ作成されます（「[書き出したデータセットへのアクセス](../export-catalog/access-dataset.md)」を参照してください）。次のものがあります。

* パーソナライズされたオファー
* フォールバックオファー
* プレースメント
* 決定

オファーライブラリでこれらのオブジェクトの 1 つが変更されるたびに、新しい書き出しジョブが自動的に実行され、データセットが更新されます。

>[!NOTE]
>
>この機能は、デフォルトで有効になっています。追加のアクティベーション手順を行わずに使用を開始できます。有効化されると、書き出しジョブは自動化され、ユーザー側からのアクションは不要になります。

<!--
>[!NOTE]
>
>This feature is not enabled by default. If you want to use it, reach out to your Adobe contact to have it activated for your catalog. Once it is enabled, export jobs will be automated and will require no action from your side.
-->
