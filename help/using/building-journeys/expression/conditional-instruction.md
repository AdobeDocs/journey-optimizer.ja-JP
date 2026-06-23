---
solution: Journey Optimizer
product: journey optimizer
title: 条件命令（if、then、else）
description: 条件命令について説明します
feature: Journeys
role: Developer
level: Experienced
keywords: 詳細, 条件, アクション, ジャーニー
exl-id: 5a5b35a7-e3b5-4dc0-8a87-e985956b04a4
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/SObpEvgu0D-pcoLVaKM7iRffLTSP1stp1zcg4Ygs-vQ
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
subfeature_v2:
  - id: cce82f05-fc3c-4af7-85ff-8bba603861a7
  - id: d8353d85-5da7-453d-bd68-40ad33fa0ab7
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: bf5866b0e7437f93936f573fd83ada8526fe004d
workflow-type: tm+mt
source-wordcount: 576
ht-degree: 29%

---

# 条件命令（if、then、else） {#conditional-instruction}

高度なエディターでは、条件命令（if、then、else）をサポートしています。 これにより、より複雑な式を定義できます。 条件命令は、次の要素で構成されています。

* **[!UICONTROL if]**：最初に評価される条件。
* **[!UICONTROL then]**：条件評価の結果が true の場合に評価される式。
* **[!UICONTROL else]**：条件評価の結果が false の場合に評価される式。

>[!NOTE]
>
>すべての式は括弧で囲む必要があります。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` は&#x200B;**ブール値**&#x200B;を返す必要があります。

`<expression2>` と `<expression3>` は、同じタイプまたは互換性のあるタイプを持つ必要があります。 サポートされているシグネチャと戻り値のタイプは次のとおりです。

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**用途**

条件命令を使用すると、条件アクティビティの数を減らして、ジャーニーワークフローを最適化できます。 例えば、同じアクションアクティビティ内で、1 つの条件式のみを使用して、1 つのフィールド定義に 2 つの代替オプションを指定できます。

アクションアクティビティの例（条件命令の結果として文字列を想定するフィールドの場合）：

```json
if (startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@event{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```

+++ AI ナレッジリファレンス

このセクションには、このトピックに関連する解釈、検索、質問への回答をサポートすることを目的とした構造化された知識が含まれています。

理解を深めるには、この情報をこのページのドキュメントと組み合わせる必要があります。 どちらのソースも単独で使用することを意図していません。このページでは、機能について説明しますが、この節では、用語、意図、適用可能性、および制約の曖昧さを解消するのに役立つ追加のコンテキストを提供します。

* **TL;DR:**&#x200B;このページでは、ジャーニーの高度な式エディターで使用できる`if / then / else`の条件付き命令について説明します。これには、構文ルール、サポートされている型の組み合わせ、実用的な使用例が含まれます。

**インテント：**

* `if`、`then`、`else`を使用して条件式を作成し、ブール条件に基づいて異なる値を返します
* 単一のアクションアクティビティにインライン条件ロジックを埋め込むことで、ジャーニー内の条件アクティビティの数を減らすことができます
* `then`および`else`分岐に対して有効なデータ型の組み合わせを決定します
* デバイスモデルに基づいてAPNSまたはFCMにプッシュ通知トークンをルーティングするための条件付き命令を適用します

**用語集：**

* **条件付き命令**: ブール値を評価し、2つの式&#x200B;*（製品固有）*&#x200B;のいずれかを返す高度なエディターの`if / then / else`式コンストラクト
* **高度な式エディター**：条件、待機アクティビティ、およびアクションパラメーターマッピング *（product-specific）*&#x200B;で使用される複雑な式を書き込むためのJourney Optimizer インターフェイス

**ガードレール：**

* `if`、`then`および`else`句のすべての式に括弧が必要です
* `if`句（`<expression1>`）はブール型を返す必要があります
* `then`および`else`式（`<expression2>`および`<expression3>`）は、同じ型または互換性のある型である必要があります（例：`decimal`および`integer`は互換性があり、`string`および`integer`は互換性がありません）
* すべてのタイプの組み合わせがサポートされているわけではありません。サポートされている署名テーブルにリストされているペアのみが有効です

**用語：**

* 正規名：条件付き命令 – 頭字語：なし – バリアント：if/then/else、三元スタイルの条件
* 同義語：&quot;conditional instruction&quot; = &quot;inline condition&quot; = &quot;if-then-else expression&quot;
* 混同しない：条件付き命令（インライン式） ≠条件アクティビティ（ジャーニーキャンバスノード）

**FAQ:**

* **Q: `if`句を括弧で囲む必要がありますか？**  – はい、`if`句の条件を含むすべての式に括弧が必要です。
* **Q: `if / then / else`を使用して、あるブランチの数値を返したり、別のブランチの文字列を返したりできますか？**  – いいえ、`<expression2>`と`<expression3>`は同じまたは互換性のある型である必要があります。
* **Q：条件付き命令によってジャーニーの複雑さが軽減される方法を教えてください。** — 1つの式を使用して、1つのアクションアクティビティ内で2つのフィールド値の代替案を指定し、キャンバス上の別の条件アクティビティノードを回避できます。
* **Q：両方のブランチが文字列の場合、条件付き命令はどのようなタイプを返しますか？** — `string`を返します。
* **Q: `if / then / else`を使用してプッシュ通知チャネルを選択できますか？**  – はい。例えば、Apple デバイスの場合は`'apns'`、その他のデバイスの場合は`'fcm'`を返すようにデバイスモデルを評価しています。

+++
