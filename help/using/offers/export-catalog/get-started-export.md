---
title: オファーカタログの書き出しの概要
description: オファーカタログをデータセットとして書き出す方法を説明します
feature: Decision Management, Datasets
topic: Integrations
role: User, Data Engineer
level: Intermediate
exl-id: f30abea1-b204-4470-9836-75fae916bbb1
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: ht
source-wordcount: '83'
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

<!--
>[!NOTE]
>
>This feature is not enabled by default. If you want to use it, reach out to your Adobe contact to have it activated for your catalog. Once it is enabled, export jobs will be automated and will require no action from your side.
-->
