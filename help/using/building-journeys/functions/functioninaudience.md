---
product: journey optimizer
title: inAudience
description: inAudience 関数について学ぶ
feature: Journeys
role: Data Engineer, Architect
level: Experienced
keywords: inAudience, 関数, 式, ジャーニー
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
source-git-commit: 385e27fd4ea34f6a10b8da6b99a2c888edf9d57e
workflow-type: ht
source-wordcount: '229'
ht-degree: 100%

---

# inAudience {#inAudience}

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

`inAudience('audienceName') == true` は、セグメントメンバーシップがエントリ済みになっていることを意味します。

`inAudience('audienceName') == false` は、離脱ステータスのセグメントメンバーシップがあることを意味します。


>[!IMPORTANT]
>
>既存のオーディエンスの名前を変更しても、ジャーニー式内のそのオーディエンスへの参照は自動的に更新されません。条件ノードで `inAudience('oldAudienceName')` が使用されている場合は、新しい名前を使用するように式を手動で編集する必要があります。適切に編集しない場合、ジャーニーの条件が機能しなくなります。

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

