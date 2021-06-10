---
title: プレースメントデータセット
description: この節では、書き出されたプレースメントのデータセットで使用されるすべてのフィールドをリストします。
source-git-commit: cd44676a7a0f60ce3e97652ec6459f708557e14c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 85%

---

# プレースメントデータセット {#placements-dataset}

オファーが変更されるたびに、自動生成されたプレースメントデータセットが更新されます。

![](../../assets/dataset-placements.png)

正常に更新された、データセットの最新のバッチが右側に表示されます。データセットのスキーマの階層表示が左ウィンドウに表示されます。

>[!NOTE]
>
>オファーライブラリの各オブジェクト用に書き出したデータセットにアクセスする方法については、[この節](../export-catalog/access-dataset.md)を参照してください。

以下に、「**[!UICONTROL 決定オブジェクトリポジトリ - プレースメント]**」データセットで使用できるすべてのフィールドのリストを示します。

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

## 識別子

**フィールド：** _id
**タイトル：**識別子
**説明：**レコードの一意の ID。
**型：**&#x200B;文字列

## _experience

**フィールド：**_experience 
**型：**&#x200B;オブジェクト

### _エクスペリエンス/判定

**フィールド：** decisioning
**型：**&#x200B;オブジェクト

#### _エクスペリエンス/判定/プレースメントのチャネル識別子

**フィールド：** channelID 
**タイトル：**プレースメントの チャネル識別子 
**** 説明：提案がおこなわれたチャネル。値は有効なチャネル URI です。https://ns.adobe.com/xdm/channels/channel をご覧ください。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/コンテンツコンポーネントタイプ

**フィールド：** componentType 
**タイトル：** コンテンツコンポーネントタイプ 
**説明：** URI の列挙型のセット。各値は、コンテンツコンポーネントに指定された型にマッピングされます。コンテンツを表示する一部のコンシューマーは、@type 値が、コンテンツコンポーネントの追加のプロパティを説明するスキーマの参照であることを期待しています。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/ contentTypes

**フィールド：** contentTypes 
**型：**&#x200B;配列

**_experience /判定/ contentTypes / MIMEメディアタイプ**

**タイトル：** MIME Media Type 
**Description:** その配置に必要なコンポーネントのメディアタイプの制約。異なる画像形式など、1 つのコンポーネントに対して複数のメディアタイプが存在する場合があります。**型：**&#x200B;文字列

#### _エクスペリエンス/判定/配置の説明

**フィールド：** 説明
**タイトル：**プレースメントの説明
**説明：** メッセージ配信全体での動的コンテンツの使用方法について、人間が判読できる意図を伝えるために使用します。Web ページ内の特定のスペースが「バナー」であることが、正式なメソッドではなく、説明を介して伝えられることがよくあります。
**型：**&#x200B;文字列

#### _エクスペリエンス/判定/配置名

**フィールド：**名前 
**タイトル：**プレースメント名 
**説明：**&#x200B;人の操作によってプレースメントを参照するために割り当てられたプレースメント名。**型：**&#x200B;文字列

## _repo

**フィールド：** _repo 
**型：**&#x200B;オブジェクト

### _repo >配置ETag

**フィールド：** etag 
**タイトル：**プレースメントETag 
**説明：**&#x200B;スナップショットが作成された時点の、決定オプションオブジェクトのリビジョン。**型：**&#x200B;文字列
