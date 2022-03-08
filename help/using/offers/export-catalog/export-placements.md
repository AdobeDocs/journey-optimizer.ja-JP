---
title: プレースメントデータセット
description: この節では、プレースメント用に書き出したデータセットで使用するすべてのフィールドをリストします。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: 3e45f3cf-e17e-43a6-8424-98afef07aaa3
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 100%

---

# プレースメントデータセット {#placements-dataset}

オファーを変更するたびに、プレースメントの自動生成データセットが更新されます。

![](../../assets/dataset-placements.png)

データセット内の最新の成功したバッチが右側に表示されます。データセットのスキーマの階層ビューが左側のペインに表示されます。


>[!NOTE]
>
>[この節](../export-catalog/access-dataset.md)では、オファーライブラリの各オブジェクト用に書き出されたデータセットにアクセスする方法を説明します。

以下に、**[!UICONTROL 決定オブジェクトリポジトリー（プレースメント）]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

<!--A placement describes a location or place in a personalized message. It is used to set technical constraints for content that the personalization decision supplies. The placement also represents a request to produce certain types of metrics when an experience event is produced where this placement is involved. For instance, the placement facilitates a personalized clickable image inside an email shown to an end-user. The placement may for instance request from the assembled experience that the click on its image gets reported in an experience event with a metric https://ns.adobe.com/xdm/data/metrics/web/linkclicks and a reference to this placement.-->

## 識別子 {#identifier}

**フィールド：**_id
**タイトル：**識別子
**説明：**&#x200B;レコードの一意の識別子。**タイプ：**&#x200B;文字列

## _experience {#experience}

**フィールド：**_experience
**タイプ：**&#x200B;オブジェクト

### _experience／決定

**フィールド：**decisioning
**型：**&#x200B;オブジェクト

#### _experience／決定／プレースメントのチャネル識別子

**フィールド：** channelID
**タイトル：**プレースメントのチャンネル識別子
**説明：**提案がおこなわれたチャンネル。値は有効なチャンネル URI です。 https://ns.adobe.com/xdm/channels/channel を参照してください。
**タイプ：**&#x200B;文字列

#### _experience／決定／コンテンツコンポーネントタイプ

**フィールド：** componentType
**タイトル：**コンテンツコンポーネントタイプ
**説明：**各値がコンテンツコンポーネントに指定されたタイプにマッピングされる URI の列挙型セット。コンテンツ表示域を使用する一部のコンテンツは、@type 値がコンテンツコンポーネントの追加のプロパティを記述するスキーマへの参照であることを要求します。
**タイプ：**&#x200B;文字列

#### _experience／決定／contentTypes

**フィールド：**contentTypes
**型：**&#x200B;配列

**_experience／決定／;contentTypes／MIME メディアタイプ**

**タイトル：**MIME メディアタイプ
**説明：**そのプレースメントに必要なコンポーネントのメディアタイプに対する制約。異なる画像形式など、1 つのコンポーネントに対して複数のメディアタイプが存在する場合があります。
**型：**&#x200B;文字列

#### _experience／決定／プレースメントの説明

**フィールド：** description
**タイトル：**プレースメントの説明
**説明：**メッセージ配信全体での動的コンテンツの使用方法に関して、人間が判読できる意図を伝えるために使用されます。Web ページ内の特定のスペースが「バナー」と呼ばれる場合、多くの場合正式な方法ではなく、説明を使用して伝えられます。
**タイプ：**&#x200B;文字列

#### _experience／決定／プレースメント名

**フィールド：** name
**タイトル：**プレースメント名
**説明：**&#x200B;ヒューマンインタラクションでプレースメントを参照するために割り当てられた名前。**タイプ：**&#x200B;文字列

## _repo {#repo}

**フィールド：**_repo
**タイプ：**&#x200B;オブジェクト

### _repo／プレースメント ETag

**フィールド：**etag
**タイトル：**プレースメント ETag
**説明：**&#x200B;決定オプションオブジェクトがスナップショットを取得した際に表示されたリビジョン。**タイプ：**&#x200B;文字列
