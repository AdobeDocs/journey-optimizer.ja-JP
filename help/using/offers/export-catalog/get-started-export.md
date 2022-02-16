---
title: オファーカタログの書き出しの概要
description: オファーカタログをデータセットとして書き出す方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: f30abea1-b204-4470-9836-75fae916bbb1
source-git-commit: 0545cda9f91ff18791310a4ee2463b2287ac7557
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# オファーカタログの書き出しの概要 {#export-catalog}

Journey Optimizer を使用すると、オファーカタログを Adobe Experience Platform に自動的にの書き出すことができます。

書き出すと、オファーライブラリのオブジェクトごとにデータセットが 1 つ作成されます（「[書き出したデータセットへのアクセス](../export-catalog/access-dataset.md)」を参照してください）。次のものがあります。

* パーソナライズされたオファー
* フォールバックオファー
* プレースメント
* 決定（旧称：オファーアクティビティ）

オファーライブラリでこれらのオブジェクトの 1 つが変更されるたびに、新しいエクスポートジョブが自動的に実行され、データセットが更新されます。

>[!NOTE]
>
>この機能は、デフォルトでは有効になっていません。この機能を使用する場合は、アドビの担当者に連絡して、カタログに対して有効になるように依頼してください。有効になると、エクスポートジョブは自動化され、ユーザー側からのアクションは不要になります。
