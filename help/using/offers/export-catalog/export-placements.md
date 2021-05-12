---
title: 配置データセット
description: このセクションでは、エクスポートされた配置データセットで使用されるすべてのフィールドをリストします。
translation-type: tm+mt
source-git-commit: 70c172e19d5900c898d4850801468a2e186e682d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 4%

---

# 配置データセット{#placements-dataset}

オファーが変更されるたびに、自動生成された配置のデータセットが更新されます。

![](../../assets/dataset-placements.png)

データセット内で成功した最新のバッチが右側に表示されます。 データセットのスキーマの階層表示が左側のペインに表示されます。

>[!NOTE]
>
>[このセクション](../export-catalog/access-dataset.md)で、オファーライブラリの各オブジェクト用に書き出したデータセットにアクセスする方法を説明します。

以下に、**[!UICONTROL Decision Object Repository - Placements]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

## 識別子

**Field:** _id 
**Title:** Identifier 
**** Description：レコードの一意の識別子。**型：**&#x200B;文字列

## _エクスペリエンス

**フィールド：** _experience 
**Type:** object

### 判定

**フィールド：** 判定の
**種類：** オブジェクト

#### プレースメントのチャネルID

**Field:** channelID 
**Title:** PlacementのチャネルID 
**** Description：提案が行われたチャネル。値は有効なチャネルURIです。 https://ns.adobe.com/xdm/channels/channelを参照してください。
**型：**&#x200B;文字列

#### コンテンツコンポーネントの種類

**Field:** componentType 
**Title:** Content Component Type 
**** Description:URIの列挙型のセット。各値は、コンテンツコンポーネントに指定された型にマップされます。コンテンツ表現の一部のコンシューマーは、@type値が、コンテンツコンポーネントの追加のプロパティを説明するスキーマの参照であることを期待しています。
**型：**&#x200B;文字列

#### contentTypes

**Field:** contentTypes 
**Type:** array

* **MIMEメディアタイプ**

   **タイトル：** MIME Media Type
   **説明：** その配置に必要なコンポーネントのメディアタイプに対する制約。異なる画像形式など、1つのコンポーネントに複数のメディアタイプが存在する可能性があります。
   **型：**&#x200B;文字列

#### 配置の説明

**フィールド：** 説明
**タイトル：** 配置の説明
**** ：説明：メッセージ配信全体での動的コンテンツの使用方法について、人が読める意図を伝えるために使用します。Webページ内の特定のスペースが「バナー」であることは、正式な方法ではなく、説明を介して伝えられることがよくあります。
**型：**&#x200B;文字列

#### 配置名

**Field:** name 
**Title:** Placement Name 
**** Description：人間の操作によってプレースメントを参照するために割り当てられたプレースメント名。**型：**&#x200B;文字列

## _repo

**Field:** _repo 
**Type:** object

### ETagの配置

**Field:** etag 
**Title:** Placement ETag 
**Description：スナップショットが作成された** 時点で、決定オプションオブジェクトが置かれていたリビジョン。**型：**&#x200B;文字列
