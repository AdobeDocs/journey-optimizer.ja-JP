---
title: フォールバックオファーデータセット
description: この節では、フォールバックオファー用に書き出したデータセットで使用されるすべてのフィールドをリストします。
translation-type: tm+mt
source-git-commit: 70c172e19d5900c898d4850801468a2e186e682d
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 7%

---

# フォールバックオファーデータセット{#fallback-dataset}

オファーが変更されるたびに、フォールバックオファー用の自動生成データセットが更新されます。

![](../../assets/dataset-fallback.png)

データセット内で成功した最新のバッチが右側に表示されます。 データセットのスキーマの階層表示が左側のペインに表示されます。

>[!NOTE]
>
>[このセクション](../export-catalog/access-dataset.md)で、オファーライブラリの各オブジェクト用に書き出したデータセットにアクセスする方法を説明します。

以下に、**[!UICONTROL Decision Object Repository - Fallbackオファー]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

## 識別子

**Field:** _id 
**Title:** Identifier 
**** Description：レコードの一意の識別子。**型：**&#x200B;文字列

## _エクスペリエンス

**フィールド：** _experience 
**Type:** object

### 判定

**フィールド：** 判定の
**種類：** オブジェクト

#### 特性

**フィールド：** 特性
**タイトル：** 決定オプションの特性
**** の説明：この特定の決定オプションに属する追加のプロパティまたは属性。異なるインスタンスは異なる特性を持つことができます（マップ内のキー）。 特性は、名前と値のペアで、1つの決定オプションを他の決定オプションと区別するために使用されます。 特性は、この決定オプションを表すコンテンツの値として、また、オプションのパフォーマンスを分析し最適化する機能として使用されます。 すべてのインスタンスが同じ属性またはプロパティを持つ場合、その縦横比は、決定オプションの詳細から派生する拡張スキーマとしてモデル化する必要があります。
**タイプ：** オブジェクト

<!--Field under Characteristics without title = additionalProperties? Desc = Value of the property. Type: string-->

#### contents

**フィールド：** コンテンツ
**の** タイトル：
**コンテンツの詳細** 説明：コンテンツ項目を選択し、異なるコンテキストで決定項目をレンダリングします。1つの決定オプションに複数のコンテンツのバリエーションを含めることができます。 コンテンツとは、（デジタル）エクスペリエンスでの消費のオーディエンスに向けた情報です。 コンテンツは、チャネルを介して特定の場所に配信されます。
**Type:** array

* **コンポーネント**

   **フィールド：** コンポーネント
   **説明：** 決定オプションを表すコンテンツのコンポーネント。その言語のバリアントもすべて含まれます。「dx:format」、「dc:subject」、「dc:language」、またはこれらの組み合わせで、特定のコンポーネントが見つかります。 このメタデータは、オファーに関連付けられたコンテンツを検索または表し、配置契約に従って統合するために使用されます。
   **Type:** array
   **必須：** &quot;_type&quot;, &quot;_dc&quot;  <!--TBC?-->

   * **コンテンツコンポーネントの種類**

      **フィールド：** _type
      **タイトル：** コンテンツコンポーネントタイプ
      **説明：** 各値がコンテンツコンポーネントに指定された型にマップされるURIの列挙型セットです。コンテンツ表現の一部のコンシューマーは、@type値が、コンテンツコンポーネントの追加のプロパティを説明するスキーマの参照であることを期待しています。
      **型：**&#x200B;文字列

   * **_dc**

      **フィールド：** _dc
      **タイプ：** オブジェクト
      **必須：** &quot;format&quot;

      * **形式**

         **フィールド：** 形式
         **タイトル：** 形式
         **説明：リソ** ースの物理的またはデジタル的な表示。通常、「形式」にはリソースのメディアタイプを含める必要があります。 形式は、リソースの表示や操作に必要なソフトウェア、ハードウェア、その他の機器を特定するために使用できます。ベストプラクティスは、制御された用語から値を選択することです(例えば、コンピューターのメディア形式を定義する[インターネットメディアタイプ](http://www.iana.org/ assignments/media-types/)のリスト)。
         **型：**文字列
         **例：** &quot;application/vnd.adobe.photoshop&quot;

      * **言語**

         **フィールド：** 言語
         **タイトル：** 言語
         **説明：リソ** ースの言語。\n言語は[IETF RFC 3066](https://www.ietf.org/rfc/rfc3066.txt)で定義されているとおり、XDMの他の場所で使用されるBCP 47の一部である言語コードで指定されます。
         **Type:** array
         **例：** &quot;\n&quot;、&quot;pt-BR&quot;、&quot;es-ES&quot;
   * **_repo**

      **フィールド：** _repo
      **タイプ：** オブジェクト

      * **id**

         **フィールド：** id
         **説明：コンテンツリポジトリ** 内のアセットを参照するためのオプションの一意の識別子。プラットフォームAPIを使用して表現を取得する場合、クライアントは追加のプロパティ\&quot;repo:resolveUrl\&quot;を期待してアセットを取得できます。
         **型：**文字列
         **例：** &quot;urn:aid:sc:US:6dc33479-13ca-4b19-b25d-c805eff8a69e&quot;

      * **name**

         **フィールド：** 名前
         **説明：** 「repo:id」を使用して外部アセットを保存するリポジトリの場所に関するヒント。
         **型：**&#x200B;文字列

      * **repositoryID**

         **フィールド：** repositoryID
         **説明：コンテンツリポジトリ** 内のアセットを参照するためのオプションの一意の識別子。プラットフォームAPIを使用して表現を取得する場合、クライアントは追加のプロパティ\&quot;repo:resolveUrl\&quot;を期待してアセットを取得できます。
         **型：**文字列
         **例：** &quot;C87932A55B06F7070A49412D@AdobeOrg&quot;

      * **resolveURL**

         **フィールド：** resolveURL
         **説明：オプション** で、コンテンツリポジトリ内のアセットを読み取る一意のリソースロケーターです。これにより、クライアントがアセットの管理場所や呼び出すAPIを把握しなくても、アセットを簡単に取得できます。 これはHALリンクに似ていますが、セマンティックはよりシンプルで目的に合ったものです。
         **型：**文字列
         **例：** &quot;https://plaftform.adobe.io/resolveByPath?path=&quot;/mycorp/content/projectx/fragment/prod/herobanners/banner14.html3&quot;&quot;
   * **content**

      **フィールド：** コンテンツ
      **説明：コンテンツ** を直接保持するオプションのフィールドです。コンポーネントは、アセットリポジトリ内のコンテンツを参照する代わりに、単純なコンテンツを直接保持できます。 このフィールドは、複合、複雑およびバイナリのコンテンツアセットには使用されません。
      **型：**&#x200B;文字列

   * **deliveryURL**

      **フィールド：** deliveryURL
      **説明：オプション** で、コンテンツ配信ネットワークまたはサービスエンドポイントからアセットを取得する一意のリソースロケーターです。このURLは、ユーザーエージェントによって公開されたアセットにアクセスするために使用されます。
      **型：**文字列
      **例：** &quot;https://cdn.adobe.io/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;

   * **linkURL**

      **フィールド：** linkURL
      **説明：ユーザー** の操作に使用するオプションの一意のリソース・ロケータ。このURLは、エンドユーザをユーザエージェント内で参照するために使用され、追跡できます。
      **型：**文字列
      **例：** &quot;https://cdn.adobe.io/tracker?code=23432&amp;redirect=/content/projectx/fragment/prod/static/1232324wd32.jpeg&quot;



* **配置**

   **フィールド：** 配置
   **タイトル：** 配置
   **説明：** 適合する配置。値は、参照されるオファー配置の URI（@id）です。スキーマhttps://ns.adobe.com/experience/decisioning/placementを参照してください。
   **型：**&#x200B;文字列

#### ライフサイクルステータス

**フィールド：** lifecycleStatus 
**Title:** ライフサイクルステータス
**説明：** ライフサイクルステータスを使用すると、ワークフローをオブジェクトと共に実行できます。ステータスは、オブジェクトが表示される場所や関連性があると見なされる場所に影響を与える場合があります。 ステータスの変更は、オブジェクトを使用するクライアントまたはサービスによって実行されます。
**Type:** string 
**Possible values:** &quot;Draft&quot;, &quot;Approved&quot;, &quot;Live&quot;, &quot;Completed&quot;, &quot;Archived&quot; 
**Default value:** &quot;Draft&quot;

#### Decision Option Name

**Field:** name 
**Title:** Decision Option Name 
**Description:** Option name that is displayed in for mavires user interfaces.**型：**&#x200B;文字列

#### タグ

**Field:** tags 
**Title:** Tags 
**Description:** このエンティティに関連付けられたタグのセット。タグは、フィルタ式で使用され、在庫全体をサブセット(カテゴリ)に制限します。
**Type:** array

<!--Field without name under tags: Description: An identifier of a tag object. The value is the @id of the tag that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

## _repo

### 決定オプションETag

**Field:** etag 
**Title:** Decision Option ETag 
**Description：スナップショットが作成された** 時点で、決定オプションオブジェクトが置かれていたリビジョン。**型：**&#x200B;文字列
