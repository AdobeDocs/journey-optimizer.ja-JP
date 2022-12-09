---
title: パーソナライズされたオファーデータセット
description: このセクションには、提供リストで使用されるすべてのフィールドが一覧表示されます。
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: c7f691aa-8f89-4f23-b897-53211863eb6d
source-git-commit: 882b99d9b49e1ae6d0f97872a74dc5a8a4639050
workflow-type: tm+mt
source-wordcount: '1951'
ht-degree: 0%

---

# パーソナライズされたオファーデータセット {#offers-dataset}

オファーが変更されるたびに、パーソナライズされたコンテンツオファー用に自動生成されたデータセットが更新されます。

![](../assets/dataset-offers.png)

データセット内の最後の成功したバッチが右側に表示されます。 データセットのスキーマの階層ビューが左側のペインに表示されます。

>[!NOTE]
>
>この節 ](../export-catalog/access-dataset.md) で [ は、オファーライブラリの各オブジェクトについて、書き出したデータセットにアクセスする方法について説明します。

以下に、データセットで **[!UICONTROL Decision Object Repository - Personalized Offers]** 使用可能なすべてのフィールドの一覧を示します。

<!--Personalized offers form the set of choices for a decision. The objective for decisioning is to take a large inventory of items and apply numerous constraint rules to that inventory to narrow it down and then to rank the qualifying options according to a criteria. The resulting propositions assemble and personalize the experience for specific individuals.-->

## 識別子 {#identifier}

**フィールド:** _id
**タイトル:** 識別子
**説明:** レコードの一意の識別子。**タイプ:** string

## _experience {#experience}

**フィールド:** _experience
**タイプ:** object

### _experience > decisioning

**フィールド:** decisioning
**タイプ:** object

#### _experience > decisioning > calendarConstraints

**フィールド:** calendarconstraints
**タイトル:** カレンダーの制約の詳細
**説明:** カレンダー制約日付の範囲が指定されている場合に、決定オプションが有効になっているかどうかを判断します。 この日付の範囲外のオプションは指定できません。**タイプ:** object

* **終了日時**

   **フィールド:** endDate
   **タイトル:** 終了日付/時刻
   **説明:** 意思決定オプションの終了日が有効になります。 終了日を過ぎたオプションは、decisioning プロセスで提案できなくなります。
   **タイプ:** string

* **開始日時**

   **フィールド:** startDate
   **タイトル:** 開始日時
   **説明:** 意思決定オプションの開始日の妥当性が有効になります。 開始日に達していないオプションは、decisioning プロセスではまだ提示することはできません。
   **タイプ:** string

#### _experience > decisioning > の特長

**フィールド:** 特性
**タイトル:** 意思決定オプションの特性
**説明:** この特定の決定オプションに属しているその他のプロパティまたは属性を指定します。 各インスタンスによって、異なる特性が設定されていることがあります (マップ内のキー)。 属性とは、他の意思決定オプションを区別するために使用される名前と値のペアです。 特性は、この判断オプションを表すコンテンツ内の値として使用されます。また、オプションのパフォーマンスを分析して最適化するための機能としても使用されます。 各インスタンスの属性またはプロパティが同じである場合は、デシジョンオプション詳細から派生した拡張スキーマとして、そのアスペクトをモデル化する必要があります。**タイプ:** object

#### _experience > decisioning > コンテンツ

**フィールド:** コンテンツ
**タイトル:** コンテンツの詳細
**説明:** Decision item を別のコンテキストで表示するためのコンテンツアイテムです。 1つの決定オプションには、複数のコンテンツのバリエーションを含めることができます。 コンテンツとは、(デジタル) 利用状況において、対象ユーザーに向けられる情報を示します。 コンテンツは、チャネルを通じて特定の場所に配信されます。**タイプ:** array

**_experience > decisioning > contents > components**

**フィールド:** コンポーネント
**説明:** 意思決定オプションを表すコンテンツのコンポーネントです。すべての言語バリエーションが含まれています。 特定のコンポーネントについては、「dx: format」、「dc: subject」および「dc: language」、またはそれらの組み合わせによって確認できます。 このメタデータは、オファーに関連付けられたコンテンツを見つけたり、表現したりするために使用されます。**タイプ:** array
**必要になります。** &quot;_type&quot;、&quot;_dc&quot; <!--TBC?-->

* **_experience > decisioning > contents > component > Content Component Type**

   **フィールド:** _type
   **タイトル:** コンテンツコンポーネントタイプ
   **説明:** 各値がコンテンツコンポーネントに割り当てられた型にマップされている一連の uri です。 コンテンツ表現のコンシューマーによっては、@type 値が、コンテンツコンポーネントの追加のプロパティを記述するスキーマへの参照であると想定されています。
   **タイプ:** string

* **_experience > decisioning > contents > components > _dc**

   **フィールド:** _dc
   **タイプ:** object
   **必須:** 「format」

   * **書式**

      **フィールド:** フォーマット
      **タイトル:** フォーマット
      **説明:** リソースの物理的またはディジタル manifestation 通常、フォーマットには、リソースのメディアタイプが含まれている必要があります。 フォーマットを使用して、リソースを表示または操作するために必要なソフトウェア、ハードウェア、またはその他の機器を決定することができます。 推奨されるベストプラクティスは、制御されたボキャブラリ (コンピューターのメディア形式を定義する Internet Media の種類 ](http://www.iana.org/assignments/media-types/) の [ リストなど) から値を選択することです。
      **タイプ:** string
      **例:** &quot;application/vnd adobe photoshop&quot;

   * **言語**
      **フィールド:** 言語
      **タイトル:** 言語
      **説明: リソースの言語または言語を示し** ます。 \N 言語は、IETF RFC 3066 ](https://www.ietf.org/rfc/rfc3066.txt) で定義 [ されている言語コードに指定されています。 BCP 47 の一部であり、これは XDM の他の場所で使用されます。
      **タイプ:** array
      **例:** &quot;\n&quot;、&quot;pt-BR&quot;、&quot;es-es&quot;

* **_experience > decisioning > contents > components > _repo**

   **フィールド:** _repo
   **タイプ:** object

   * **コード**

      **フィールド:** id
      **説明:** コンテンツリポジトリ内のアセットを参照するためのオプションの一意の識別子。 プラットフォーム Api を使用してイメージを取得する場合、クライアントでは、アセットを取得するために、追加のプロパティ「リポジトリ: resolveUrl」が必要になることがあります。
      **タイプ:** string
      **例:** &quot;urn :aaid: sc :US: 6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

   * **氏名**

      **フィールド:** 名前
      **説明:** 外部アセットが保存されているリポジトリが見つからない場合は、「リポジトリ: id」というヒントが表示されます。
      **タイプ:** string

   * **repositoryID**

      **フィールド:** repositoryID
      **説明:** コンテンツリポジトリ内のアセットを参照するためのオプションの一意の識別子。 プラットフォーム Api を使用してイメージを取得する場合、クライアントでは、アセットを取得するために、追加のプロパティ「リポジトリ: resolveUrl」が必要になることがあります。
      **タイプ:** string
      **例:** &quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

   * **resolveURL**

      **フィールド:** resolveurl
      **説明:** コンテンツリポジトリ内のアセットを読み取るためのオプションの一意のリソースロケーター。 これにより、アセットが管理される場所や、どの Api を呼び出すかをクライアントが理解していなくても、アセットを容易に取得できるようになります。 これは HAL リンクに似ていますが、セマンティクスがより単純で、purposeful になります。
      **タイプ:** string
      **例:** &quot;https://plaftform.adobe.io/resolveByPath? path =&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3 &quot;&quot;

* **_experience > decisioning > コンテンツ > コンポーネント > コンテンツ**

   **フィールド:** コンテンツ
   **説明:** コンテンツを直接保持するためのオプションフィールド。 このコンポーネントは、アセットリポジトリ内のコンテンツを参照するのではなく、単純なコンテンツを直接保持できます。 このフィールドは、コンポジット、複雑、バイナリコンテンツアセットには使用されません。
   **タイプ:** string

* **_experience > decisioning > コンテンツ > コンポーネント > deliveryURL**

   **フィールド:** deliveryurl
   **説明:** コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを取得するための、オプションの一意のリソースロケーターです。 この URL を使用して、ユーザーエージェントがパブリックアセットにアクセスすることができます。
   **タイプ:** string
   **例:** &quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

* **_experience > decisioning > contents > components > linkURL**

   **フィールド:** linkURL
   **説明:** ユーザー操作に使用する、オプションの一意のリソースロケーターを指定します。 この URL は、エンドユーザーがユーザーエージェント内を参照するために使用され、追跡することができます。
   **タイプ:** string
   **例:** &quot;https://cdn.adobe.io/tracker?code=23432&amp;redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

**_experience > decisioning > コンテンツ > 配置**

**フィールド:** 配置
**タイトル:** 設置
**説明:** 適合させる場所。 値は、参照されるオファーの配置の URI (@id) です。 スキーマの https://ns.adobe.com/experience/decisioning/placement を参照してください。**タイプ:** string

#### _experience > decisioning > ライフサイクルの状態

**フィールド:** lifecycleStatus
**タイトル:** ライフサイクルの状態
**説明:** ライフサイクル状態では、オブジェクトを使用したワークフローの実行が許可されます。 状態は、オブジェクトが表示されたり、関係があると考えられる場所に影響する場合があります。 状態の変更は、そのオブジェクトを使用しているクライアントまたはサービスによって行われます。**タイプ:** string
**指定可能な値:** 「下書き」 (初期設定)、「許可」、「有効」、「完了」、「アーカイブ」

#### _experience > decisioning > デシジョンオプション名

**フィールド:** 名前
**タイトル:** 「意思決定オプション」の名前
**説明:** 様々なユーザーインターフェイスに表示されるオプション名です。**タイプ:** string

#### _experience > decisioning > profileConstraints

**フィールド:** profileConstraints
**タイトル:** プロファイル制約の詳細
**説明:** プロファイルの制約によって、オプションがこのプロファイル id の条件を満たしているかどうかが現在のコンテキストで決定されます。 各オプションの値を指定する必要がない場合は、「false」に評価されるプロファイル制約によってオプションの選択全体がキャンセルされます。これは、「false」のような値になります。 これに対して、オプションをパラメーターとして使用するプロファイルの制約ルールは、オプション選択の各オプションについて評価されます。**タイプ:** object

**_experience > decisioning > profileConstraints > 説明**

**フィールド:** 説明
**タイトル:** つい
**説明:** プロファイルの制約の説明。 これは、このプロファイル制約を作成する方法またはその理由について、人間が読み取ることができるようにするために使用されます。または、この設定によって追加または除外されるオプションを指定します。**タイプ:** string

**_experience > decisioning > profileConstraints > 適格性ルール**

**フィールド:** eligibilityRule
**タイトル:** 適格性ルール
**説明:** 指定されたプロファイルとその他の指定のコンテキスト XDM オブジェクトに対して true または false を評価する意思決定規則への参照です。 このルールを使用して、オプションが特定のプロファイルに限定されているかどうかを判断します。 値は、参照される意思決定規則の URI (@id) です。 スキーマの https://ns.adobe.com/experience/decisioning/rule を参照してください。**タイプ:** string

**_experience > decisioning > profileConstraints > Profile Constraint Type**

**フィールド:** profileconstrtype
**タイトル:** プロファイル制約タイプ
**説明:** 拘束条件が現在設定されているかどうか、およびその方法を指定します。 このような場合は、ルールを使用するか、1つ以上のセグメントメンバーシップを使用することができます。**タイプ:** string
**指定可能な値:**
* 「none」を指定します (デフォルト)。
* 「eligibilityRule」: 「プロファイル制約は、制約付きアクションが許可される前に true と評価される必要がある単一のルールとして表されます。
* 「anySegments」: &quot;profile constraint&quot; は1つ以上のセグメントとして表現されるので、そのプロファイルは少なくとも1つに属している必要があります。
* 「allSegments」: &quot;profile constraint&quot; は1つ以上のセグメントとして表現されるので、制限されたアクションを実行するには、そのすべてのメンバーである必要があります。
* 「rules」: 「プロファイル制約」は、条件、適用性、適合性、条件を満たすアクションが実行される前に「true」と評価されます。

**_experience > decisioning > profileConstraints > Segment 識別子**

**フィールド:** segmentIdentities
**タイトル:** セグメントの識別子
**説明:** セグメントの識別子
**タイプ:** array

* **識別子**

   **フィールド:** _id
   **タイトル:** 識別子
   **説明:** 関連する名前空間のセグメントの id。
   **タイプ:** string

* **名前**

   **フィールド:** namespace
   **タイトル:** 名前空間
   **説明:** 属性に `xid` 関連付けられた名前空間。
   **タイプ:** object
   **必須:** 「code」

   * **コード**

      **フィールド:** コード
      **タイトル:** コード
      **説明:** コードは、名前空間のユーザーによる読み取り可能な識別子であり、このコードを使用して、アイデンティティのグラフ処理に使用される技術的な名前空間 id を要求することができます。
      **タイプ:** string

* **エクスペリエンス識別子**

   **フィールド:** xid
   **タイトル:** エクスペリエンス識別子
   **説明:** この値が指定されている場合、この値は、すべての名前空間内のすべての名前空間によって一意になるクロスネームの識別子を表します。
   **タイプ:** string

#### _experience > decisioning > ランキング

**フィールド:** ランク付け
**タイトル:** ランクの詳細
**説明:** ランク (priority)。 意思決定条件のコンテキストを指定し、「best action」とみなす内容を定義します。 適格性制約に適合するように選択されているすべてのオプションの中から、ランク付け順によって、「トップ」 (または「トップ N」) オプションが決定されます。**タイプ:** object

**_experience > decisioning > ランク付け > Order 評価**

**フィールド:** 注文
**タイトル:** 注文の評価
**説明:** 1つまたは複数の decision options を基準とした相対的な評価 序数値が小さいオプションよりも、序数値の大きいオプションが選択されています。 このメソッドによって決定される値は、並べ替えることはできますが、計算することはできません。また、計算することもできません。 Median and モードは、序数データに使用できる最も重要な傾向の基準となります。**タイプ:** object

* **スコアリング関数**

   **フィールド:** 関数
   **タイトル:** スコアリング機能
   **説明:** この決定オプションの数値スコアを計算する関数への参照です。 その後、決定オプションはそのスコアによって順番に (ランク) されます。 このプロパティの値は、一度に on オプションを指定して呼び出す関数の URI (@id) です。 スキーマの https://ns.adobe.com/experience/decisioning/function を参照してください。
   **タイプ:** string

* **Order 評価タイプ**

   **フィールド:** orderevaluationtype
   **タイトル:** 注文の評価タイプ
   **説明:** 使用する order メカニズムを指定します。決定オプションの静的な優先度では、すべてのオプションの数値を計算するスコアリング関数、または、それを並べ替えるリストを受け取るランク付けストラテジが使用されます。
   **タイプ:** string
   **指定できる値は次のとおりです:** &quot;static&quot;、&quot;scoringFunction&quot;、&quot;Ran王国ストラテジー&quot;

* **ランク付け方針**

   **フィールド:** ran王国戦略
   **タイトル:** ランク付け方針
   **説明:** 意思決定オプションのリストをランク付けするストラテジへの参照です。 決定オプションは、番号リストに含まれています。 このプロパティの値は、一度に on オプションを指定して呼び出す関数の URI (@id) です。 スキーマの https://ns.adobe.com/experience/decisioning/rankingStrategy を参照してください。
   **タイプ:** string

**_experience > decisioning > ランキング > Priority**

**フィールド:** priority
**タイトル:** 事項
**説明:** 他のすべてのオプションを基準にした1つの決定オプションの優先度です。 Order 関数が指定されていないオプションについては、このプロパティを使用して優先順位が付けられます。 優先度が高いオプションよりも優先されます。 2つ以上の修飾オプションが最も優先度の高い値を共有している場合は、1つが一様なランダムに選択され、意志決定の意思決定に使用されます。**タイプ:** integer
**最小値:** 0
**初期設定値は0です。**

#### _experience > decisioning > タグ

**フィールド:** タグ
**タイトル:** タグ
**説明:** このエンティティに関連付けられたタグのセット。 これらのタグは、総合インベントリがサブセット (カテゴリー) に制限されるようにフィルター式で使用されます。**タイプ:** array

<!--Field without name under tags: Description: An identifier of a tag object. The value is the @id of the tag that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

## _repo {#repo}

**フィールド:** _repo
**タイプ:** object

### _repo > ディシジョンオプション ETag

**フィールド:** etag
**タイトル:** 決定オプション ETag
**説明:** スナップショットが作成されたときに意思決定オプションオブジェクトに指定されていたバージョンです。**タイプ:** string
