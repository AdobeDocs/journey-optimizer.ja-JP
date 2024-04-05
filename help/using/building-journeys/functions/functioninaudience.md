---
product: journey optimizer
title: inAudience
description: inAudience 関数について学ぶ
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inAudience, 関数, 式, ジャーニー
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: d3f0adab52ed8e44a6097c5079396d1e9c06e0a7
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# inAudience {#inAudience}

個人が特定のオーディエンスに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のオーディエンスを取得できます。

オーディエンス名は、文字列定数にする必要があります。フィールド参照や式は使用できません。

オーディエンスは [Adobe Experience Platform](https://platform.adobe.com/audience/overview) で定義されます。式エディターには、自動入力されたオーディエンスリストが表示されます。

オーディエンスには次の 3 つのステータスがあります。

* 既存：エンティティが引き続きオーディエンス内に存在します。
* 適合：エンティティがオーディエンスにエントリします。
* 離脱：エンティティがオーディエンスから離脱します。

オーディエンスの参加ステータスが「**適合**」および「**既存**」の個人のみが、オーディエンスのメンバーと見なされます。オーディエンスの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

`inAudience('audienceName') == true` は、セグメントメンバーシップがエントリ済み／既存ステータスになっていることを意味します。

`inAudience('audienceName') == false` は、セグメントメンバーシップが離脱ステータスになっていることを意味します。

## カテゴリ

Adobe Experience Platform

## 関数の構文

`inAudience(<parameter>)`

## パラメーター

| パラメーター | 説明 | タイプ |
|--- |--- |--- |
| オーディエンス | オーディエンス名 | `<string>` |

## シグネチャと戻り値のタイプ

`inAudience(<string>)`

ブール値を返します。

## 例

`inAudience("men over 50")`

説明：

ジャーニーインスタンス内の個人が「men over 50」という名前の Adobe Experience Platform オーディエンスに属している場合、この関数は **[!UICONTROL true]** を返します。それ以外の場合は **[!UICONTROL false]** を返します。
