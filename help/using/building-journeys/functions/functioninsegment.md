---
product: journey optimizer
title: inSegment
description: inSegment 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inSegment, 関数, 式, ジャーニー
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: 85a8d0713f87a8b3505a2294402156ba6598c8bb
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 100%

---

# inSegment {#inSegment}

個人が特定のオーディエンスに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のオーディエンスを取得できます。

オーディエンス名は、文字列定数にする必要があります。フィールド参照や式は使用できません。

オーディエンスは [Adobe Experience Platform](https://platform.adobe.com/audience/overview) で定義されます。式エディターには、自動入力されたオーディエンスリストが表示されます。

オーディエンスには次の 2 つのステータスがあります。

* 適合：エンティティがセグメント定義の対象となります。
* 離脱：エンティティがセグメント定義から離脱します。

なお、オーディエンスの参加ステータスが&#x200B;**適合**&#x200B;の個人のみが、オーディエンスのメンバーと見なされます。オーディエンスの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

`IF inSegment('segmentName') == true` は、セグメントメンバーシップがエントリまたは既存のステータスになっていることを意味します。

`ELSE inSegment('segmentName') == false` は、離脱ステータスのセグメントメンバーシップがあることを意味します。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`inSegment(<parameter>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| セグメント | オーディエンス名 | `<string>` |

## シグネチャと戻り値のタイプ

`inSegment(<string>)`

ブール値を返します。

## 例

`inSegment("men over 50")`

説明：

ジャーニーインスタンス内の個人が「men over 50」という名前の Adobe Experience Platform オーディエンスに属している場合、この関数は **[!UICONTROL true]** を返します。それ以外の場合は **[!UICONTROL false]** を返します。
