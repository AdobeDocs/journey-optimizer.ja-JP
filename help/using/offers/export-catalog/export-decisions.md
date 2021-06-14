---
title: オファーカタログエクスポートの基本を学ぶ
description: この節では、決定のためにエクスポートされたデータセットで使用されるすべてのフィールドを示します。
feature: オファー
topic: 統合
role: User
level: Intermediate
source-git-commit: b58c5b527e594c03f3b415549e6b7cd15b050139
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 100%

---

# 決定データセット{#decisions-dataset}

オファーが変更されるたびに、決定（旧称：アクティビティ）用の自動生成データセットが更新されます。

![](../../assets/dataset-activities.png)

データセット内の最新の成功したバッチが右側に表示されます。データセットのスキーマの階層ビューが左側のウィンドウに表示されます。

>[!NOTE]
>
>[この節](../export-catalog/access-dataset.md)では、オファーライブラリの各オブジェクト用に書き出されたデータセットにアクセスする方法を説明します。

次に、**[!UICONTROL 決定オブジェクトリポジトリー（決定）]**&#x200B;データセット（旧称：決定オブジェクトリポジトリー（アクティビティ））で使用できるすべてのフィールドのリストを示します。

<!--A decision (formerly known as offer decision) is used to control the decisioning process. It specifies the filter applied to the total inventory to narrow down offers by topic/category, the placement to narrow down the inventory to those offers that technically fit into the reserved space for the offer and specifies a fallback option should the combined constraints disqualify all available personalization offers.-->

## 識別子

**フィールド：**_id
**タイトル：**識別子
**説明：**&#x200B;レコードの一意の識別子。**タイプ：**&#x200B;文字列

## _experience

**フィールド：**_experience
**タイプ：**&#x200B;オブジェクト

### _experience > decisioning

**フィールド：** decisioning
**タイプ：**&#x200B;オブジェクト

#### _experience > decisioning > criteria

**フィールド：**criteria
**タイトル：**条件
**説明：**&#x200B;各条件に制約のセットが含まれる決定条件のセットを定義します。**タイプ：**&#x200B;配列

**_experience > decisioning > criteria > description**

**フィールド：**description
**タイトル：**説明
**説明：**条件の説明。この基準の構築方法と構築理由、そして基準が決定に与える影響について、目視可能な意図を伝えるために使用されます。
**タイプ：**&#x200B;文字列

**_experience > decisioning > criteria > optionSelection**

**フィールド：**optionSelection
**タイトル：**オプション選択
**説明：**&#x200B;オプション選択は、このコンテキストでのオプションの有効性/適用可能性を定義します。**タイプ：**&#x200B;オブジェクト

* **説明**

   **フィールド：**description
   **タイトル：**説明
   **説明：**オプション選択の説明。このオプション選択の構築方法や構築理由、または一致するオプションについて、判読できる意図を伝えるために使用されます。
   **タイプ：**&#x200B;文字列

* **オプションフィルター**

   **フィールド：**filter
   **タイトル：**オプションフィルター
   **説明：**関連付けられたタグを使用して在庫のオプションに一致するタグベースのフィルターへの参照。値は、参照される決定ルールの URI（@id）です。https://ns.adobe.com/experience/decisioning/filter のスキーマを参照してください。
   **タイプ：**&#x200B;文字列

* **プロファイル制約タイプ**

   **フィールド：**optionSelectionType
   **タイトル：**プロファイル制約タイプ
   **説明：**現在制約が設定されているかどうか、および制約の表現方法を決定します。フィルタークエリを使用するか、1 つ以上のセグメントメンバーシップを使用する場合があります。
   **タイプ：**文字列
   **可能な値：**「none」（デフォルト）、「directList」、「filter」

* **オプションリスト**

   **フィールド：**options
   **タイトル：**オプションリスト
   **説明：**フィルタークエリを評価せずに、オプションを直接指定するリスト。オプションリストまたはオプションフィルタールールを指定できます。
   **タイプ：**&#x200B;配列

   <!--Missing title under Option List? Desc = An identifier of an decision option entity. The value value refers to an `@id` property of a decision option. Type: string-->

**_experience > decisioning > criteria > placements**

**フィールド：**placements
**タイトル：**プレースメント制限
**説明：**&#x200B;プレースメント制約は、この条件がリストに表示されている配置にのみ適用できることを示します。`xdm:placements` リスト内にある対象の配置がオプション選択である場合にのみ選択されます。それ以外の場合は、決定条件全体がスキップされます。「xdm:placements」リストが省略または空の場合、ターゲットプレースメントの条件が考慮されます。ここに示すプレースメントは、オプション選択に対して暗黙の条件を適用します。考慮するオプションは、ターゲットプレースメントの表示域を持つ必要があります。
**タイプ：**&#x200B;配列

* **プレースメント識別子**

   **タイトル：**プレースメント ID
   **説明：**プレースメントエンティティへの参照。値は、参照されるオファープレースメントの URI（@id）です。https://ns.adobe.com/experience/decisioning/placement のスキーマを参照してください。
   **タイプ：**&#x200B;文字列

**_experience > decisioning > criteria > profileConstraints**

**フィールド：**profileConstraints
**タイトル：**プロファイル制約
**説明：**プロファイル制約は、このコンテキストにおいて、オプション選択が現時点でこのプロファイル ID に対して適格かどうかを決定します。プロファイル制約で各オプションの値を考慮する必要がない場合（オプション選択のオプションが不変である場合）、「false」と評価されるプロファイル制約では、オプション選択全体がキャンセルされます。一方、オプションをパラメーターとして取るプロファイル制約ルールは、オプション選択の各適合オプションに対して評価されます。
**タイプ：** オブジェクト

* **_experience > decisioning > criteria > profileConstraints > Description**

   **フィールド：**description
   **タイプ：**説明
   **説明：**プロファイル制約の説明。このプロファイル制約の構築方法や構築理由、およびこの制約に含まれる、または除外されるオプションについて、人が読み取れる意図を伝えるために使用されます。
   **タイプ：**&#x200B;文字列

* **_experience > decisioning > criteria > profileConstraints > Eligibility Rule**

   **フィールド：**eligibilityRule
   **タイトル：**実施要件ルール
   **説明：**特定のプロファイルやその他のコンテキスト XDM オブジェクトに対して true または false と評価する決定ルールへの参照。ルールは、オプションが特定のプロファイルに該当するかどうかを決定するために使用されます。値は、参照される決定ルールの URI（@id）です。https://ns.adobe.com/experience/decisioning/rule のスキーマを参照してください。
   **タイプ：**&#x200B;文字列

* **_experience > decisioning > criteria > profileConstraints > Profile Constraint Type**

   **フィールド：**profileConstraintType
   **タイトル：**プロファイル制約タイプ
   **説明：**現在制約が設定されているかどうか、および制約の表現方法を決定します。ルールを使用するか、1 つ以上のセグメントメンバーシップを使用する場合があります。
   **タイプ：**文字列
   **指定可能な値：**
   * 「none」（デフォルト）
   * 「eligibilityRule」:「プロファイル制約は、制約付きアクションが許可される前に true と評価される必要がある単一の規則として表されます。」
   * 「anySegments」:「プロファイル制約は 1 つ以上のセグメントとして表され、制約付きアクションが許可される前に、プロファイルは少なくとも 1 つのセグメントのメンバーである必要があります。」
   * 「allSegments」:「プロファイル制約は 1 つ以上のセグメントとして表され、制約付きアクションが許可される前に、プロファイルはすべてのセグメントのメンバーである必要があります。」
   * 「rules」:「プロファイル制約は、制約付きアクションが許可される前にすべてが true と評価される必要がある実施要件、適用性、適合性など、様々なルールとして表されます。」

* **_experience > decisioning > criteria > profileConstraints > segmentIdentities**

   **フィールド：**segmentIdentities
   **タイトル：**セグメント識別子
   **説明：**セグメント ID。
   **タイプ：**&#x200B;配列

   * **識別子**

      **フィールド：**_id
      **タイトル：**識別子
      **説明：**関連する名前空間のセグメント識別子。
      **タイプ：**&#x200B;文字列

   * **名前空間**

      **フィールド：**namespace
      **タイトル：**名前空間
      **説明：**&#x200B;属性に関連付けられた名前空間`xid` 。
      **タイプ：**オブジェクト
      **必須：**「コード」

      * **コード**

         **フィールド：**code
         **タイトル：**コード
         **説明：**コードは、人が読める名前空間の識別子であり、ID グラフ処理に使用される技術名前空間 ID をリクエストするために使用できます。
         **タイプ：**&#x200B;文字列
   * **エクスペリエンス識別子**

      **フィールド：**xid
      **タイトル：**エクスペリエンス識別子
      **説明：**存在する場合、この値は、すべての名前空間内の名前空間スコープ識別子全体で一意の名前空間間識別子を表します。
      **タイプ：**&#x200B;文字列


**_experience > decisioning > criteria > ranking**

**フィールド：**ranking
**タイトル：**ランキングの詳細
**説明：**ランク（優先度）。決定基準のコンテキストに基づいて「最良のオプション」を決定する方法を定義します。プロファイルの制約を満たす選択したすべてのオプションの中で、ランキングによって提案する上位（または上位 N）のオプションが決まります。
**タイプ：**&#x200B;オブジェクト

* **_experience > decisioning > criteria > ranking > order**

   **フィールド：**order
   **タイトル：**順序評価
   **説明：**1 つ以上の決定オプションの相対的な順序の評価。序数の値が大きいオプションは、序数の値が小さいオプションよりも優先的に選択されます。この方法で決定された値は順序付けできますが、それらの間の距離は測定できず、合計も積も計算できません。中央値とモードは、序数データに使用できる唯一の代表値です。
   **タイプ：**&#x200B;オブジェクト

   * **スコア関数**

      **フィールド：**function
      **タイトル：**スコア関数
      **説明：**この決定オプションの数値スコアを計算する関数への参照。決定オプションは、そのスコアで並べ替えられます（ランク付け）。このプロパティの値は、on オプションを指定して一度に呼び出す関数の URI（@id）です。https://ns.adobe.com/experience/decisioning/function のスキーマを参照してください。
      **タイプ：**&#x200B;文字列

   * **順序評価の種類**

      **フィールド：**orderEvaluationType
      **タイトル：**順序評価のタイプ
      **説明：**使用する順序評価メカニズム、決定オプションの静的優先度、すべてのオプションの数値を計算するスコア関数、またはリストを受け取って順序を決定するランキング戦略を指定します。
      **タイプ：**文字列
      **指定可能な値：**「static」、「scoringFunction」、「rankingStrategy」

   * **ランキング戦略**

      **フィールド：**rankingStrategy
      **タイトル：**ランキング戦略
      **説明：**決定オプションのリストをランク付けする戦略への参照。決定オプションは、順序付きリストで返されます。このプロパティの値は、on オプションを指定して一度に呼び出す関数の URI（@id）です。https://ns.adobe.com/experience/decisioning/rankingStrategy のスキーマを参照してください。
      **タイプ：**&#x200B;文字列

* **_experience > decisioning > criteria > ranking > Priority**

   **フィールド：**priority
   **タイトル：**優先度
   **説明：**1 つの決定オプションの、他のすべてのオプションに対する優先度。order 関数が指定されていないオプションは、このプロパティを使用して優先順位付けされます。優先度が高いオプションは、優先度が低いオプションの前に選択されます。2 つ以上の絞り込みオプションが最も高い優先度の値を共有する場合、1 つは均一なランダムで選択され、決定の提案に使用されます。
   **タイプ：**整数
   **最小値：**0
   **デフォルト値：** 0

#### _experience > decisioning > Activity End Date and Time

**フィールド：**endTime
**タイトル：**アクティビティの終了日時
**説明：**&#x200B;決定（旧称：アクティビティ）の終了日と終了時刻。プロパティには、http://schema.org/Action で定義された schema.org の「endTime」プロパティの意味があります。**タイプ：**&#x200B;文字列

#### _experience > decisioning > Fallback Option

**フィールド：** fallback
**タイトル：**フォールバックオプション
**説明：**&#x200B;この決定のコンテキストで決定をおこなう際に使用されるフォールバックオプションへの参照は、通常のオプションを制限しません（通常、ハード制約が適用される場合に発生します）。値は、参照されるフォールバックオファーの URI（@id）です。**タイプ：**&#x200B;文字列

#### _experience > decisioning > Activity Name

**フィールド：**name
**タイトル：**アクティビティ名
**説明：**&#x200B;様々なユーザーインターフェイスに表示される決定（旧称：アクティビティ）名。**タイプ：**&#x200B;文字列

#### _experience > decisioning > Activity Start Date and Time

**フィールド：**startTime
**タイトル：**アクティビティ開始日時
**説明：**決定（旧称：アクティビティ）の開始日と終了時刻。プロパティに、schema.org の「startTime」プロパティの意味が http://schema.org/Action で定義されています。
**タイプ：**&#x200B;文字列

## _repo

**フィールド：**_repo
**タイプ：**&#x200B;オブジェクト

### _repo > Activity ETag

**フィールド：**etag
**タイトル：**アクティビティ ETag
**説明：**&#x200B;決定（旧称：アクティビティ）オブジェクトがスナップショットを取ったときに表示されたリビジョン。**タイプ：**&#x200B;文字列
