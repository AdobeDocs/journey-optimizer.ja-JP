---
title: 配置データセット
description: このセクションでは、エクスポートされた配置データセットで使用されるすべてのフィールドをリストします。
source-git-commit: 958bf03f3d3c2dd1606daba9dfef1284e2ed5cdd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 92%

---

# 配置データセット{#placements-dataset}

オファーが変更されるたびに、自動生成された配置のデータセットが更新されます。

![](../../assets/dataset-placements.png)

正常に更新された最新のデータセットのバッチが右側に表示されます。 データセットのスキーマの階層表示が左側のペインに表示されます。

>[!NOTE]
>
>オファーライブラリの各オブジェクト用にエクスポートしたデータセットにアクセスする方法については、[このセクション](../export-catalog/access-dataset.md)を参照してください。

以下に、**[!UICONTROL 決定オブジェクトリポジトリ - プレースメント]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

## 識別子

**フィールド：** _id 
**タイトル：**識別情報
**説明：**&#x200B;レコードの一意の識別子。**型：**&#x200B;文字列

## _experience

**フィールド：**_experience 
**型：**&#x200B;オブジェクト

### _エクスペリエンス/判定

**フィールド：**decisioning
**型：**&#x200B;オブジェクト

#### _エクスペリエンス/判定/プレースメントのチャネル識別子

**フィールド：** channelID 
**タイトル：** プレースメントの チャンネル識別子 
**** 説明：提案が行われたチャネル。値は有効なチャネルURIです。 https://ns.adobe.com/xdm/channels/channel をご覧ください。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/コンテンツコンポーネントタイプ

**フィールド：** componentType 
**タイトル：** コンテンツコンポーネントタイプ 
**説明：** URIの列挙型のセット。各値は、コンテンツコンポーネントに指定されたタイプにマップされます。コンテンツ表現の一部のコンシューマーは、@type値が、コンテンツコンポーネントの追加のプロパティを説明するスキーマの参照であることを期待しています。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/ contentTypes

**フィールド：** contentTypes 
**型：** 配列

* **MIMEメディアタイプ**

   **タイトル：** MIME メディアタイプ
   **説明：** その配置に必要なコンポーネントのメディアタイプに対する制約。異なる画像形式など、1 つのコンポーネントに対して複数のメディアタイプが存在する場合があります。
   **型：**&#x200B;文字列

#### _エクスペリエンス/判定/配置の説明

**フィールド：** 説明
**タイトル：** 配置の説明
**説明：** メッセージ配信全体での動的コンテンツの使用方法について、人が読める意図を伝えるために使用します。Webページ内の特定のスペースが「バナー」であることが、正式な方法ではなく、説明を介して伝えられることがよくあります。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/配置名

**フィールド：** 名前 
**タイトル：** プレースメント名 
**説明：** 人の操作によってプレースメントを参照するために割り当てられたプレースメント名。**型：**&#x200B;文字列

## _repo

**フィールド：**_repo 
**型：**&#x200B;オブジェクト

### _repo >配置ETag

**フィールド：** etag 
**タイトル：** プレースメントETag 
**説明：** スナップショットが作成された時点で、決定オプションオブジェクトのリビジョン。**型：**&#x200B;文字列
