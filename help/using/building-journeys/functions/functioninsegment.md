---
product: journey optimizer
title: inSegment
description: inSegment 関数について説明します
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inSegment, 関数, 式, ジャーニー
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: 72bd00dedb943604b2fa85f7173cd967c3cbe5c4
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 35%

---

# inSegment {#inSegment}

個人が特定のオーディエンスに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のオーディエンスを取得できます。

オーディエンス名は、文字列定数である必要があります。 フィールド参照や式は使用できません。

オーディエンスは、 [Adobe Experience Platform](https://platform.adobe.com/audience/overview). 式エディターは、オーディエンスの自動入力リストを表示します。

オーディエンスには次の 3 つのステータスがあります。

* 既存：エンティティが引き続きオーディエンスに存在します。
* 実現：エンティティがオーディエンスに入っています。
* 終了：エンティティがオーディエンスから退出しています。

個人のみ **実現済み** および **既存** オーディエンスのパーティシペーションステータスは、オーディエンスのメンバーと見なされます。 オーディエンスの評価方法について詳しくは、 [セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results).

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

関数はを返します。 **[!UICONTROL true]** ジャーニーインスタンス内の個人が、「men over 50」という名前のAdobe Experience Platformオーディエンスに属している場合、 **[!UICONTROL false]** それ以外の場合は
