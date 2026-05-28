---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: プレースメントデータセット
description: この節では、プレースメント用にエクスポートしたデータセットで使用するすべてのフィールドをリストします。
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: 3e45f3cf-e17e-43a6-8424-98afef07aaa3
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/UFE7I-hQM4jKPpclDl3avrcE-q-vwRq-c91WOLdPBgo
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 179
ht-degree: 87%

---

# プレースメントデータセット {#placements-dataset}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

オファーを変更するたびに、プレースメントの自動生成データセットが更新されます。

![](../assets/dataset-placements.png)

データセット内の最新の成功したバッチが右側に表示されます。 データセットのスキーマの階層ビューが左側のペインに表示されます。

>[!NOTE]
>
>[この節](../export-catalog/access-dataset.md)では、オファーライブラリの各オブジェクト用にエクスポートしたデータセットにアクセスする方法を説明します。

以下に、**[!UICONTROL 決定オブジェクトリポジトリー（プレースメント）]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

+++ 識別子

**フィールド：** _id
**タイトル：**識別子
**説明：** レコードの一意のID。
**型：**&#x200B;文字列

+++

+++ _experience

**フィールド：** _experience
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning

**フィールド：**決定
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning > Placement&#39;s Channel Identifier

**フィールド：** channelID
**タイトル：** プレースメントのチャネル Id
**説明：**提案が行われたチャネル。値は有効なチャネル URIです。https://ns.adobe.com/xdm/channels/channelを参照してください。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Content Component Type

**フィールド：** componentType
**タイトル：** コンテンツコンポーネントタイプ
**説明：**各値がコンテンツコンポーネントに指定された型にマッピングされるURIの列挙セット。コンテンツ表現の一部の消費者は、@typeの値がコンテンツコンポーネントの追加のプロパティを記述するスキーマへの参照であることを期待しています。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > contentTypes

**フィールド：** contentTypes
**タイプ：**&#x200B;配列

+++

+++_experience > decisioning > contentTypes > MIME Media Type

**タイトル：** MIME メディアタイプ
**説明：**そのプレースメントで想定されるコンポーネントのメディアタイプの制約。異なる画像形式など、1つのコンポーネントに対して複数のメディアタイプが可能な場合があります。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Placement Description

**フィールド：**説明
**タイトル：**配置の説明
**説明：** メッセージ全体の配信で動的コンテンツがどのように使用されるかについて、人間が読みやすい意図を伝えるために使用されます。ウェブページの特定のスペースが「バナー」であるということは、多くの場合、正式な方法ではなく、説明を通して伝えられます。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Placement Name

**フィールド：**名
**タイトル：** プレースメント名
**説明：**人間とのやり取りにおいて、プレースメントを参照するために割り当てられた名前。
**型：**&#x200B;文字列

+++

+++ _repo

**フィールド：** _repo
**タイプ：**&#x200B;オブジェクト

+++

+++ _repo／プレースメント ETag

**フィールド：** etag
**タイトル：** プレースメント ETag
**説明：** スナップショットの取得時に決定オプションオブジェクトが存在したリビジョン。
**型：**&#x200B;文字列

+++
