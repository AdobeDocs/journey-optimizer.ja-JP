---
product: journey optimizer
title: inSegment
description: セグメント内の関数について説明します。
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# inSegment {#inSegment}

個別が特定のセグメントに属しているかどうかをチェックします。

>[!NOTE]
>
>最大100のセグメントを取得することができます。

セグメント名は、ストリング定数である必要があります。 フィールド参照または式を指定することはできません。

セグメントは、 [ Adobe エクスペリエンスプラットフォーム ](https://platform.adobe.com/segment/overview) で定義されています。 式エディターには、セグメントの自動完成リストが表示されます。

セグメントには、次の3つの状態があります。

* 既存: エンティティは引き続きセグメント内にあります。
* これにより、エンティティがセグメントに入ることになります。
* 終了: エンティティがセグメントから退出されました。

実際 **に参加した参加状態と** 既存 **のセグメントに参加しているユーザー** のみが、セグメントのメンバーとして扱われます。セグメントの評価方法について詳しくは、セグメンテーションサービスの [ マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results) を参照してください。

`IF inSegment('segmentName') == true` は、状態が &quot;segmentMembership&quot; であることを意味します。

`ELSE inSegment('segmentName') == false` は、終了状態が segmentMembership になっていることを意味します。

## 項目

Adobe エクスペリエンスプラットフォーム

## 関数のシンタックス

`inSegment(<parameter>)`

## パラメーター

| 指定 | つい | 入力 |
|--- |--- |--- |
| セグメント | セグメント名 | `<string>` |

## シグネチャと戻り値の型

`inSegment(<string>)`

ブール値を返します。

## 一

`inSegment("men over 50")`

説明

この関数は、旅インスタンスに属するユーザーが、「男性から50」という名前の Adobe エクスペリエンスプラットフォームセグメントの一部である場合は、 **[!UICONTROL false]** この関数を返し **[!UICONTROL true]** ます。
