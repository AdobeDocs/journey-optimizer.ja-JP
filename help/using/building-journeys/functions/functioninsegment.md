---
product: journey optimizer
title: inSegment
description: inSegment 関数について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: inSegment, 関数, 式, ジャーニー
exl-id: 8417af75-6e97-4ad4-86b4-3ecd264a5560
version: Journey Orchestration
feature_v2: []
subfeature_v2: []
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 521
ht-degree: 33%

---

# inSegment {#inSegment}

個人が特定のオーディエンスに属しているかどうかを確認します。

>[!NOTE]
>
>最大 100 個のオーディエンスを取得できます。

オーディエンス名は、文字列定数にする必要があります。 フィールド参照や式は使用できません。

オーディエンスは [Adobe Experience Platform](https://platform.adobe.com/audience/overview) で定義されます。 式エディターには、自動入力されたオーディエンスリストが表示されます。

オーディエンスには次の 2 つのステータスがあります。

* 適合：エンティティがセグメント定義の対象となります。
* 離脱：エンティティがセグメント定義から離脱します。

なお、オーディエンスの参加ステータスが&#x200B;**適合**&#x200B;の個人のみが、オーディエンスのメンバーと見なされます。 オーディエンスの評価方法について詳しくは、[セグメント化サービスのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=ja#interpret-segment-results)を参照してください。

`inSegment('segmentName') == true` は、セグメントメンバーシップがエントリまたは既存のステータスになっていることを意味します。

`inSegment('segmentName') == false` は、離脱ステータスのセグメントメンバーシップがあることを意味します。

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

ジャーニーインスタンス内の個人が「men over 50」という名前のAdobe Experience Platform オーディエンスの一部である場合、関数は&#x200B;**[!UICONTROL true]**&#x200B;を返します。それ以外の場合、**[!UICONTROL false]**。

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、ジャーニープロファイルが名前付きAdobe Experience Platform オーディエンスに属しているかどうかを確認し、ブール値を返す従来の`inSegment`関数について説明します。

**インテント：**
* プロファイルが`inSegment`を使用する名前付きオーディエンスのアクティブなメンバーであるかどうかを確認します
* ジャーニー条件で実現（アクティブ）オーディエンスメンバーシップを確認するには、`inSegment('name') == true`を使用します
* `inSegment('name') == false`を使用して、終了した（非アクティブな）オーディエンスメンバーシップを確認します

**用語集：**
* **実現**: エンティティが現在セグメント定義&#x200B;*（製品固有）*&#x200B;に適格であることを意味するオーディエンス参加ステータス
* **終了**: エンティティが離脱しているか、セグメント定義&#x200B;*（製品固有）*&#x200B;から離脱したことを意味するオーディエンス参加ステータス

**ガードレール：**
* 1つのジャーニーで取得できるオーディエンスは最大100個です
* オーディエンス名は文字列定数である必要があります。フィールド参照と式はパラメーターとしてサポートされていません

**用語：**
* 正規の名前：inSegment – 頭字語：none – 変種：inAudience （現在の優先関数）
* 同義語：&quot;inSegment&quot; = &quot;audience membership check&quot; （legacy）
* 混同しないでください。「inSegment」（レガシー/非推奨の関数）≠「inAudience」（現在の推奨関数）
* 混乱しないでください：「認識」（アクティブなメンバー）≠「離脱」（メンバーではなくなりました）

**FAQ:**
* **Q: `inSegment`と`inAudience`の違いは何ですか？** — `inSegment`はレガシー関数名です。`inAudience`は現在の推奨関数です。 両方ともオーディエンスメンバーシップを確認しますが、`inAudience`にはガードレールと伝播タイミングの詳細など、より完全なドキュメントがあります。
* **Q: `inSegment('name') == true`とはどういう意味ですか？** — プロファイルが「realized」セグメントメンバーシップのステータスを持つ、つまり、個人がオーディエンスのアクティブなメンバーであることを意味します。
* **Q：動的式をオーディエンス名として渡すことはできますか？**  – いいえ、オーディエンス名は文字列定数である必要があります。フィールド参照と式はサポートされていません。
* **Q: 1つのジャーニーで評価できるオーディエンスの数は？** - 1つのジャーニーで最大100人のオーディエンスを取得できます。

+++
