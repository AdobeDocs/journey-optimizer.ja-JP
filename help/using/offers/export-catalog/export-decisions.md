---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: 決定データセット
description: この節では、決定にエクスポートしたデータセットで使用するすべてのフィールドをリストアップします。
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: 064762b7-9774-42eb-bcef-1d92bc94a988
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/DTi8clyXof5lmdx0elOPHQGm0cwQuKwAm0KbQ-U-Fmo
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 668
ht-degree: 80%

---

# 決定データセット {#decisions-dataset}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

オファーを変更するたびに、自動生成された決定データセットが更新されます。

![](../assets/dataset-activities.png)

正常に更新された、データセットの最新のバッチが右側に表示されます。 データセットのスキーマの階層ビューが左側のペインに表示されます。

>[!NOTE]
>
>[この節](../export-catalog/access-dataset.md)では、オファーライブラリの各オブジェクト用にエクスポートしたデータセットにアクセスする方法を説明します。

次に、**[!UICONTROL 決定オブジェクトリポジトリー（決定）]**&#x200B;データセット（旧称：決定オブジェクトリポジトリー（アクティビティ））で使用できるすべてのフィールドのリストを示します。

<!--A decision (formerly known as offer decision) is used to control the decisioning process. It specifies the filter applied to the total inventory to narrow down offers by topic/category, the placement to narrow down the inventory to those offers that technically fit into the reserved space for the offer and specifies a fallback option should the combined constraints disqualify all available personalization offers.-->

+++ 識別子

**フィールド：** _id
**タイトル：**識別子
**説明：** レコードの一意のID。
**型：**&#x200B;文字列

+++

+++ _experience

**フィールド：** _experience
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning

**フィールド：**決定
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning > criteria

**フィールド：**条件
**タイトル：**条件
**説明：**それぞれに一連の制約が含まれる一連の決定条件を定義します。
**型：**&#x200B;配列

+++

+++ _experience > decisioning > criteria > description

**フィールド：**説明
**タイトル：**説明
**説明：**条件の説明。この基準がどのように、またはなぜ構築され、それが決定にどのような影響を与えているかについて、人間が読み取り可能な意図を伝えるために使用されます。
**型：**&#x200B;文字列

+++

+++_experience > decisioning > criteria > optionSelection

**フィールド：** optionSelection
**タイトル：** オプションの選択
**説明：** オプションの選択は、このコンテキストにおけるオプションの有効性/適用性を定義します。
**タイプ：** オブジェクト

* 説明

  **フィールド：**description
  **タイトル：**説明
  **説明：** オプション選択の説明。このオプションの選択がどのように作成されたか、なぜ作成されたか、どのオプションが一致するかについて、人間が読みやすい意図を伝えるために使用されます。
  **タイプ：**&#x200B;文字列

* オプションフィルター

  **フィールド：**filter
  **タイトル：**オプションフィルター
  **説明：** コレクション修飾子（旧称「タグ」）ベースのフィルターへの参照。添付されたコレクション修飾子を使用して、インベントリのオプションに一致します。値は、参照される決定ルールのURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/filterを参照してください。
  **タイプ：**&#x200B;文字列

* プロファイル制約タイプ

  **フィールド：**optionSelectionType
  **タイトル：**プロファイル制約タイプ
  **説明：**現在、制約が設定されているかどうか、および制約の表現方法を決定します。フィルタークエリを使用するか、1つ以上のオーディエンスメンバーシップを使用します。
  **タイプ：**文字列
  **使用可能な値：** &quot;none&quot;（デフォルト）、&quot;directList&quot;、&quot;filter&quot;

* オプションリスト

  **フィールド：**options
  **タイトル：**オプションリスト
  **説明：** フィルタークエリを評価せずに、オプションを直接指定するリスト。オプションリストまたはオプションフィルタールールのいずれかを指定できます。
  **型：**&#x200B;配列

<!--Missing title under Option List? Desc = An identifier of an decision option entity. The value value refers to an `@id` property of a decision option. Type: string-->

+++

+++_experience > decisioning > criteria > placements

**フィールド：** プレースメント
**タイトル：**配置の制限
**説明：** プレースメントの制約では、この条件はリストされたプレースメントにのみ適用されることを示しています。対象となるプレースメントが`xdm:placements` リストにある場合にのみ、オプションの選択が考慮されます。そうしないと、決定条件全体がスキップされます。「xdm:placements」リストが省略または空の場合、対象となるプレースメントに対して基準が考慮されます。ここに記載されているプレースメントは、オプション選択に暗黙的な基準を課します。考慮するオプションには、対象となるプレースメントの表示域が必要です。
**型：**&#x200B;配列

* プレースメント識別子

  **タイトル：**プレースメント ID
  **説明：**配置エンティティへの参照。値は、参照されるプレースメントのURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/placementを参照してください。
  **タイプ：**&#x200B;文字列

+++

+++_experience > decisioning > criteria > profileConstraints

**フィールド：** profileConstraints
**タイトル：** プロファイル制約
**説明：** プロファイル制約は、このコンテキストで、この時点でオプションの選択がこのプロファイル IDに適格かどうかを決定します。プロファイル制約で各オプションの値を考慮する必要がない場合、つまりオプション選択のオプションが不変である場合、プロファイル制約で「false」と評価すると、オプション選択全体がキャンセルされます。一方、オプションをパラメーターとして取るプロファイル制約ルールは、オプション選択の対象となる各オプションについて評価されます。
**タイプ：** オブジェクト

+++

+++_experience > decisioning > criteria > profileConstraints > Description

**フィールド：**説明
**タイトル：**説明
**説明：** プロファイル制約の説明。このプロファイル制約がどのように、なぜ構築されたか、またはそれによってどのようなオプションが含まれるか、または除外されるかについて、人間が読み取れる意図を伝えるために使用されます。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > criteria > profileConstraints > Eligibility Rule

**フィールド：**実施要件ルール
**タイトル：**の実施要件ルール
**説明：**特定のプロファイルやその他の特定のコンテキスト XDM オブジェクトに対して、trueまたはfalseと評価される決定ルールへの参照。このルールは、オプションが特定のプロファイルに適格かどうかを判断するために使用されます。値は、参照される決定ルールのURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/ruleを参照してください。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > criteria > profileConstraints > Profile Constraint Type

**フィールド：** profileConstraintType
**タイトル：** プロファイル制約タイプ
**説明：**現在、制約が設定されているかどうか、および制約の表現方法を決定します。ルールまたは1人以上のオーディエンスメンバーシップを通じて行うことができます。
**型：**文字列
**指定可能な値：**

* 「なし」（デフォルト）
* 「eligibilityRule」:「プロファイル制約は、制約付きアクションが許可される前に true と評価される必要がある単一の規則として表されます。」
* 「anySegments」:「プロファイル制約は 1 つ以上のオーディエンスとして表され、制約付きアクションが許可されるには、プロファイルが少なくとも 1 つのオーディエンスのメンバーである必要があります。」
* 「allSegments」:「プロファイル制約は 1 つ以上のオーディエンスとして表され、制約付きアクションが許可されるには、プロファイルがすべてのオーディエンスのメンバーである必要があります。」
* 「rules」:「プロファイル制約は実施要件、適用性、適合性など、様々なルールとして表され、制約付きアクションが許可されるには、これらがすべて true として評価される必要があります。」

+++

+++ _experience > decisioning > criteria > profileConstraints > segmentIdentities

**フィールド：** セグメント ID
**タイトル：** セグメント識別子
**説明：** オーディエンスの識別子。
**型：**&#x200B;配列

* 識別子

  **フィールド：**_id
  **タイトル：**識別子
  **説明：**関連する名前空間に含まれるオーディエンスの ID。
  **タイプ：**&#x200B;文字列

* 名前空間

  **フィールド：** 名前空間
  **タイトル：**名前空間
  **説明：**&#x200B;属性に関連付けられた名前空間`xid` 。
  **タイプ：**オブジェクト
  **必須：**「コード」

   * コード

     **フィールド：**code
     **タイトル：**コード
     **説明：**コードは、人が読める名前空間の識別子であり、ID グラフ処理に使用される技術名前空間 ID をリクエストするために使用できます。
     **タイプ：**&#x200B;文字列

* エクスペリエンス識別子

  **フィールド：**xid
  **タイトル：**エクスペリエンス識別子
  **説明：**存在する場合、この値は、すべての名前空間内の名前空間スコープ識別子全体で一意の名前空間間識別子を表します。
  **タイプ：**&#x200B;文字列

+++

+++_experience > decisioning > criteria > ranking

**フィールド：**件のランキング
**タイトル：** ランキングの詳細
**説明：** ランク （優先度）。 決定基準のコンテキストを考慮して、「\&quot;最適なオプション\」を決定する方法を定義します。プロファイルの制約を満たす選択されたオプションの中から、ランキングによって提案する上位（または上位N）のオプションが決定されます。
**タイプ：** オブジェクト

+++ 

+++_experience > decisioning > criteria > ranking > order

**フィールド：**件の注文
**タイトル：**注文評価
**説明：** 1つ以上の決定オプションの相対的な順序の評価。序数値が高いオプションは、序数値が低いオプションよりも選択されます。この方法で決定された値は順序付けできますが、それらの間の距離を測定することはできず、合計も積も計算できません。中央値とモードは、序数データに使用できる中心傾向の唯一の尺度です。
**タイプ：** オブジェクト

* スコア関数

  **フィールド：**function
  **タイトル：**スコア関数
  **説明：**この決定オプションの数値スコアを計算する関数への参照。決定オプションは、そのスコアによって並べ替えられます（ランク付け）。このプロパティの値は、on オプションで一度に呼び出される関数のURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/functionを参照してください。
  **タイプ：**&#x200B;文字列

* 順序評価の種類**

  **フィールド：**orderEvaluationType
  **タイトル：**順序評価のタイプ
  **説明：**使用する順序評価メカニズム、決定オプションの静的優先度、すべてのオプションの数値を計算するスコア関数、またはリストを受け取って順序を決定する AI モデルを指定します。
  **タイプ：**文字列
  **指定可能な値：**「static」、「scoringFunction」、「rankingStrategy」

* ランキング戦略

  **フィールド：**rankingStrategy
  **タイトル：**ランキング戦略
  **説明：**決定オプションのリストをランク付けする戦略への参照。決定オプションは、順序付きリストで返されます。このプロパティの値は、on オプションで一度に呼び出される関数のURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/rankingStrategyを参照してください。
  **タイプ：**&#x200B;文字列

+++

+++ _experience > decisioning > criteria > ranking > Priority

**フィールド：**優先度
**タイトル：**優先度
**説明：**他のすべてのオプションに対する、単一の決定オプションの優先度。注文関数が指定されていないオプションは、このプロパティを使用して優先順位付けされます。優先度が高いオプションは、優先度が低いオプションよりも前に選択されます。2つ以上の適格オプションが最優先度の値を共有する場合、1つは均一なランダムで選択され、決定提案に使用されます。
**型：**整数
**最小値：** 0
**デフォルト値：** 0

+++

+++ _experience > decisioning > アクティビティ終了日時

**フィールド：** endTime
**タイトル：** アクティビティ終了日時
**説明：**決定（旧称アクティビティ）の終了日と終了時間。このプロパティは、https://schema.org/Actionで定義されているschema.orgの「endTime」プロパティのセマンティックを持ちます。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Fallback Option

**フィールド：** フォールバック
**タイトル：** フォールバックオプション
**説明：**この決定のコンテキストで決定する際に使用されるフォールバックオプションへの参照は、通常のオプションのどれにも当てはまりません（これは通常、ハード制約が適用される場合に発生します）。 値は、参照されるフォールバックオプションのURI （@id）です。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Activity Name

**フィールド：**名
**タイトル：** アクティビティ名
**説明：**様々なユーザーインターフェイスに表示される決定名（旧称アクティビティ）名。
**型：**&#x200B;文字列

+++

+++_experience > 決定 > アクティビティの開始日時

**フィールド：** startTime
**タイトル：** アクティビティ開始日時
**説明：**決定（旧称アクティビティ）の開始日と終了時間。このプロパティには、https://schema.org/Actionで定義されているschema.orgの「startTime」プロパティのセマンティックが含まれています。
**型：**&#x200B;文字列

+++

+++ _repo

**フィールド：** _repo
**タイプ：**&#x200B;オブジェクト

+++

+++ _repo > Activity ETag

**フィールド：** etag
**タイトル：** Activity ETag
**説明：** スナップショットの実行時に決定（以前はアクティビティと呼ばれていた）オブジェクトが行われたリビジョン。
**型：**&#x200B;文字列

+++
