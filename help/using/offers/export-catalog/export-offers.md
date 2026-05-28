---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: パーソナライズされたオファーデータセット
description: この節では、オファー用にエクスポートしたデータセットで使用するすべてのフィールドをリストアップします。
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: c7f691aa-8f89-4f23-b897-53211863eb6d
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/ZnlEExKq7uM-qxcva2e0MxLFHXwGoW00axWjS-XaTZo
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
  - id: ad78185d-8f79-40ad-9bad-cbde74af74ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
  - id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 873
ht-degree: 76%

---

# パーソナライズされたオファーデータセット {#offers-dataset}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

オファーを変更するたびに、パーソナライズされたコンテンツオファーの自動生成データセットが更新されます。

正常に更新された、データセットの最新のバッチが右側に表示されます。 データセットのスキーマの階層ビューが左側のペインに表示されます。

![](../assets/dataset-offers.png)

>[!NOTE]
>
>削除済みのパーソナライズされたオファーは、データセット内でアーカイブ済みとしてマークされます。

次に、**[!UICONTROL 決定オブジェクトリポジトリ（パーソナライズされたオファー）]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

<!--Personalized offers form the set of choices for a decision. The objective for decisioning is to take a large inventory of items and apply numerous constraint rules to that inventory to narrow it down and then to rank the qualifying options according to a criteria. The resulting propositions assemble and personalize the experience for specific individuals.-->

+++ 識別子

**フィールド：** _id
**タイトル：**&#x200B;識別子
**説明：** レコードの一意のID。
**型：**&#x200B;文字列

+++

+++ _experience {#experience}

**フィールド：** _experience
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning

**フィールド：**&#x200B;決定
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning > calendarConstraints 

**フィールド：** calendarConstraints
**タイトル：** カレンダー制約の詳細
**説明：** カレンダーの制約は、日付範囲を指定して決定オプションが有効かどうかを決定します。その日付範囲外では、このオプションは提案できません。
**タイプ：** オブジェクト

* **終了日時**

  **フィールド：** endDate
  **タイトル：**&#x200B;終了日時
  **説明：**&#x200B;決定オプションの有効期限の終了日。終了日を過ぎたオプションは、決定プロセスで提案できなくなります。
  **タイプ：**&#x200B;文字列

* **開始日時**

  **フィールド：** startDate
  **タイトル：**&#x200B;開始日時
  **説明：**&#x200B;決定オプションの有効期限の開始日。開始日に達していないオプションは、決定プロセスでまだ提案できません。
  **タイプ：**&#x200B;文字列

+++

+++ _experience > decisioning > characteristics

**フィールド：**&#x200B;特性
**タイトル：**&#x200B;決定オプションの特性
**説明：**&#x200B;特性は、特定の決定オプションに属するオファーの追加の属性またはプロパティです。これらの属性は、キー値のペアです。つまり、値が関連付けられた属性名（キーと呼ばれることもあります）が含まれており、1つの決定オプションを他のオファーと区別するために使用されます。例えば、属性名「color」の場合、特定のオファーの値は「green」になります。<!--Characteristics are used as values in content that represents this decision option and as features to analyze and optimize the performance of an offer. When every instance has the same attribute or property, that aspect should be modeled as an extension schema that derives from the decision option detail.-->
**タイプ：** オブジェクト

+++

+++ _experience > decisioning > contents

**フィールド：**&#x200B;内容
**タイトル：** コンテンツの詳細
**説明：** コンテンツ項目を使用して、異なるコンテキストで決定項目をレンダリングします。1つの決定オプションに複数のコンテンツのバリエーションを含めることができます。コンテンツとは、（デジタル）体験で利用するために、オーディエンスに向けられた情報のことです。コンテンツは、チャネルを通じて特定のプレースメントに配信されます。
**型：**&#x200B;配列

+++

+++_experience > decisioning > contents > components

**フィールド：** コンポーネント
**説明：**&#x200B;決定オプションを表すコンテンツのコンポーネント（言語バリエーションをすべて含む）。特定のコンポーネントは、「dx:format」、「dc:subject」および「dc:language」またはその組み合わせで見つかります。このメタデータは、オファーに関連付けられているコンテンツを検索または表すために使用され、プレースメント契約に従って統合されます。
**型：**&#x200B;配列
**必須：** &quot;_type&quot;, &quot;_dc&quot; <!--TBC?-->

+++

* **_experience > decisioning > contents > components > Content Component Type**

  **フィールド：**&#x200B;_type
  **タイトル：**&#x200B;コンテンツコンポーネントタイプ
  **説明：**&#x200B;各値がコンテンツコンポーネントに指定された型にマッピングされるURIの列挙セット。コンテンツ表現の一部の消費者は、@typeの値がコンテンツコンポーネントの追加のプロパティを記述するスキーマへの参照であることを期待しています。
  **タイプ：**&#x200B;文字列

* **_experience > decisioning > contents > components > _dc**

  **フィールド：**&#x200B;_dc
  **タイプ：**&#x200B;オブジェクト
  **必須：**&quot;format&quot;

   * **形式**

     **フィールド：** format
     **タイトル：**&#x200B;形式
     **説明：** リソースの物理的またはデジタルの実現。通常、「形式」には、リソースのメディアタイプを含める必要があります。形式は、リソースの表示または操作に必要なソフトウェア、ハードウェアまたはその他の機器を決定するために使用できます。推奨されるベストプラクティスは、制御された語彙から値を選択することです（例えば、コンピュータメディア形式を定義する[&#x200B; インターネットメディアタイプ &#x200B;](https://www.iana.org/assignments/media-types/)のリスト）。
     **タイプ：**&#x200B;文字列
     **例：**&quot;application/vnd.adobe.photoshop&quot;

   * **言語**
     **フィールド：** language
     **タイトル：**&#x200B;言語
     **説明：** リソースの言語。\n言語は、[IETF RFC 3066](https://www.ietf.org/rfc/rfc3066.txt)で定義されている言語コードで指定されます。これはBCP 47の一部であり、XDMの他の場所で使用されています。
     **タイプ：**&#x200B;配列
     **例：**&quot;\n&quot;、&quot;pt-BR&quot;、&quot;es-ES&quot;

* **_experience > decisioning > contents > components > _repo**

  **フィールド：** _repo
  **タイプ：**&#x200B;オブジェクト

   * **id**

     **フィールド：** id
     **説明：** コンテンツリポジトリ内のアセットを参照するためのオプションの一意のID。Platform APIを使用して表現を取得する場合、クライアントはアセットを取得するために追加のプロパティ \&quot;repo:resolveUrl\&quot;を期待できます。
     **タイプ：**&#x200B;文字列
     **例：** &quot;urn:aaid:sc:US:6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

   * **名前**

     **フィールド：** name
     **説明：**\&quot;repo:id\&quot; によって外部アセットを保存するリポジトリの場所に関するヒント。
     **タイプ：**&#x200B;文字列

   * **repositoryID**

     **フィールド：** repositoryID
     **説明：** コンテンツリポジトリ内のアセットを参照するためのオプションの一意のID。Platform APIを使用して表現を取得する場合、クライアントはアセットを取得するために追加のプロパティ \&quot;repo:resolveUrl\&quot;を期待できます。
     **タイプ：**&#x200B;文字列
     **例：**&quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

   * **resolveURL**

     **フィールド：** resolveURL
     **説明：** コンテンツリポジトリ内のアセットを読み取るための、オプションの一意のリソース検索ツール。これにより、アセットの管理場所と呼び出すAPIをクライアントが把握することなく、アセットを簡単に取得できるようになります。これはHAL リンクと似ていますが、セマンティックはよりシンプルで目的を持っています。
     **タイプ：**&#x200B;文字列
     **例：**&quot;https://plaftform.adobe.io/resolveByPath?path=&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3&quot;&quot;

* **_experience > decisioning > contents > components > content**

  **フィールド：** content
  **説明：** コンテンツを直接保持するためのオプションのフィールド。アセットリポジトリ内のコンテンツを参照する代わりに、コンポーネントはシンプルなコンテンツを直接保持できます。このフィールドは、複合、複合、バイナリコンテンツアセットには使用されません。
  **タイプ：**&#x200B;文字列

* **_experience > decisioning > contents > components > deliveryURL**

  **フィールド：** deliveryURL
  **説明：** コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを取得するための、オプションの一意のリソース検索ツール。このURLは、ユーザーエージェントがアセットに公開でアクセスするために使用します。
  **タイプ：**&#x200B;文字列
  **例：**&quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

* **_experience > decisioning > contents > components > linkURL**

  **フィールド：** linkURL
  **説明：** ユーザーインタラクション用の一意のリソース ロケーター（オプション）。このURLは、エンドユーザーをユーザーエージェントで参照するために使用され、追跡できます。
  **タイプ：**&#x200B;文字列
  **例：**&quot;https://cdn.adobe.io/tracker?code=23432&redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

+++_experience > decisioning > contents > Placement

**フィールド：** プレースメント
**タイトル：**&#x200B;配置
**説明：**&#x200B;準拠する配置。値は、参照されるオファープレースメントのURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/placementを参照してください。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > Lifecycle Status

**フィールド：** lifecycleStatus
**タイトル：** ライフサイクルステータス
**説明：** ライフサイクルステータスでは、オブジェクトを使用してワークフローを実行できます。ステータスは、オブジェクトが表示される場所、または関連すると見なされる場所に影響する場合があります。ステータスの変更は、オブジェクトを使用するクライアントまたはサービスによって実行されます。
**型：**&#x200B;文字列
**指定可能な値：** 「ドラフト」（デフォルト）、「承認済み」、「ライブ」、「完了」、「アーカイブ済み」

+++

+++ _experience > decisioning > Decision Option Name

**フィールド：**&#x200B;名
**タイトル：**&#x200B;決定オプション名
**説明：**&#x200B;様々なユーザーインターフェイスに表示されるオプション名。
**型：**&#x200B;文字列

+++

+++ _experience > decisioning > profileConstraints

**フィールド：** profileConstraints
**タイトル：** プロファイル制約の詳細
**説明：** プロファイルの制約は、このコンテキストで、現時点でこのプロファイル IDに対してオプションが適格かどうかを決定します。プロファイル制約で各オプションの値を考慮する必要がない場合、つまりオプション選択のオプションが不変である場合、プロファイル制約で「false」と評価すると、オプション選択全体がキャンセルされます。一方、オプションをパラメーターとして取るプロファイル制約ルールは、オプション選択の対象となる各オプションについて評価されます。
**タイプ：** オブジェクト

+++

+++_experience > decisioning > profileConstraints > Description

**フィールド：**&#x200B;説明
**タイトル：**&#x200B;説明
**説明：** プロファイル制約の説明。このプロファイル制約がどのように、なぜ構築されたか、またはそれによってどのようなオプションが含まれるか、または除外されるかについて、人間が読み取れる意図を伝えるために使用されます。
**型：**&#x200B;文字列

+++

+++_experience > decisioning > profileConstraints > Eligibility Rule

**フィールド：**&#x200B;実施要件ルール
**タイトル：**&#x200B;の実施要件ルール
**説明：**&#x200B;特定のプロファイルやその他の特定のコンテキスト XDM オブジェクトに対して、trueまたはfalseと評価される決定ルールへの参照。このルールは、オプションが特定のプロファイルに適格かどうかを判断するために使用されます。値は、参照される決定ルールのURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/ruleを参照してください。
**型：**&#x200B;文字列

+++

+++_experience > decisioning > profileConstraints > Profile Constraint Type

**フィールド：** profileConstraintType
**タイトル：** プロファイル制約タイプ
**説明：**&#x200B;現在、制約が設定されているかどうか、および制約の表現方法を決定します。ルールまたは1人以上のオーディエンスメンバーシップを通じて行うことができます。
**型：**&#x200B;文字列
**指定可能な値：**

* 「なし」（デフォルト）
* 「eligibilityRule」:「プロファイル制約は、制約付きアクションが許可される前に true と評価される必要がある単一の規則として表されます。」
* 「anySegments」:「プロファイル制約は 1 つ以上のオーディエンスとして表され、制約付きアクションが許可されるには、プロファイルが少なくとも 1 つのオーディエンスのメンバーである必要があります。」
* 「allSegments」:「プロファイル制約は 1 つ以上のオーディエンスとして表され、制約付きアクションが許可されるには、プロファイルがすべてのオーディエンスのメンバーである必要があります。」
* 「rules」:「プロファイル制約は実施要件、適用性、適合性など、様々なルールとして表され、制約付きアクションが許可されるには、これらがすべて true として評価される必要があります。」

+++

+++_experience > decisioning > profileConstraints > Segment Identifiers

**フィールド：** セグメント ID
**タイトル：** セグメント識別子
**説明：** オーディエンスの識別子
**タイプ：**&#x200B;配列

* **識別子**

  **フィールド：**&#x200B;_id
  **タイトル：**&#x200B;識別子
  **説明：**&#x200B;関連する名前空間に含まれるオーディエンスの ID。
  **タイプ：**&#x200B;文字列

* **名前空間**

  **フィールド：** 名前空間
  **タイトル：**&#x200B;名前空間
  **説明：**&#x200B;属性に関連付けられた名前空間`xid` 。
  **タイプ：**&#x200B;オブジェクト
  **必須：**「コード」

   * **コード**

     **フィールド：**&#x200B;code
     **タイトル：**&#x200B;コード
     **説明：**&#x200B;コードは、人が読める名前空間の識別子であり、ID グラフ処理に使用される技術名前空間 ID をリクエストするために使用できます。
     **タイプ：**&#x200B;文字列

* **エクスペリエンス識別子**

  **フィールド：**&#x200B;xid
  **タイトル：**&#x200B;エクスペリエンス識別子
  **説明：**&#x200B;存在する場合、この値は、すべての名前空間内の名前空間スコープ識別子全体で一意の名前空間間識別子を表します。
  **タイプ：**&#x200B;文字列

+++

+++ _experience > decisioning > ranking

**フィールド：**&#x200B;件のランキング
**タイトル：** ランキングの詳細
**説明：** ランク （優先度）。 決定基準のコンテキストに基づいて、「最適なアクション」と見なされるアクションを定義します。実施要件の制約を満たす選択されたオプションの中から、ランキング順序によって上位（または上位N）のオプションが決定されます。
**タイプ：** オブジェクト

+++

+++_experience > decisioning > ranking > Order Evaluation

**フィールド：**&#x200B;件の注文
**タイトル：**&#x200B;注文評価
**説明：** 1つ以上の決定オプションの相対的な順序の評価。序数値が高いオプションは、序数値が低いオプションよりも選択されます。この方法で決定された値は順序付けできますが、それらの間の距離を測定することはできず、合計も積も計算できません。中央値とモードは、序数データに使用できる中心傾向の唯一の尺度です。
**タイプ：** オブジェクト

* **スコア関数**

  **フィールド：**&#x200B;function
  **タイトル：**&#x200B;スコア関数
  **説明：**&#x200B;この決定オプションの数値スコアを計算する関数への参照。決定オプションは、そのスコアによって並べ替えられます（ランク付け）。このプロパティの値は、on オプションで一度に呼び出される関数のURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/functionを参照してください。
  **タイプ：**&#x200B;文字列

* **順序評価の種類**

  **フィールド：**&#x200B;orderEvaluationType
  **タイトル：**&#x200B;順序評価のタイプ
  **説明：**&#x200B;使用する順序評価メカニズム、決定オプションの静的優先度、すべてのオプションの数値を計算するスコア関数、またはリストを受け取って順序を決定する AI モデルを指定します。
  **タイプ：**&#x200B;文字列
  **指定可能な値：**「static」、「scoringFunction」、「rankingStrategy」

* **ランキング戦略**

  **フィールド：**&#x200B;rankingStrategy
  **タイトル：**&#x200B;ランキング戦略
  **説明：**&#x200B;決定オプションのリストをランク付けする戦略への参照。決定オプションは、順序付きリストで返されます。このプロパティの値は、on オプションで一度に呼び出される関数のURI （@id）です。スキーマ https://ns.adobe.com/experience/decisioning/rankingStrategyを参照してください。
  **タイプ：**&#x200B;文字列

+++

+++_experience > decisioning > ranking > Priority

**フィールド：**&#x200B;優先度
**タイトル：**&#x200B;優先度
**説明：**&#x200B;他のすべてのオプションに対する、単一の決定オプションの優先度。注文関数が指定されていないオプションは、このプロパティを使用して優先順位付けされます。優先度が高いオプションは、優先度が低いオプションよりも前に選択されます。2つ以上の適格オプションが最優先度の値を共有する場合、1つは均一なランダムで選択され、決定提案に使用されます。
**型：**&#x200B;整数
**最小値：** 0
**デフォルト値：** 0

+++

+++ _experience > decisioning > tags

**フィールド：** タグ
**タイトル：** タグ
**説明：**&#x200B;このエンティティに関連付けられているコレクション修飾子（以前は「タグ」と呼ばれていました）のセット。コレクション修飾子は、フィルター式で使用され、在庫全体をサブセット（カテゴリ）に制限します。
**型：**&#x200B;配列

+++

<!--Field without name under tags: Description: An identifier of a collection qualifier object. The value is the @id of the collection qualifier that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

+++_repo

**フィールド：** _repo
**タイプ：**&#x200B;オブジェクト

+++ 

+++ _repo／決定オプション ETag

**フィールド：** etag
**タイトル：**&#x200B;決定オプション ETag
**説明：** スナップショットの取得時に決定オプションオブジェクトが存在したリビジョン。
**型：**&#x200B;文字列

+++
