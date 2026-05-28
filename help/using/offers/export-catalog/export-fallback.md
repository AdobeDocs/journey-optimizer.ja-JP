---
solution: Journey Optimizer, Experience Platform
product: Journey Optimizer
title: フォールバックオファーデータセット
description: この節では、フォールバックオファー用にエクスポートしたデータセットで使用するすべてのフィールドをリストします。
badge: label="レガシー" type="Informative"
feature: Decision Management, Datasets
topic: Integrations
role: User, Developer
level: Intermediate
exl-id: 73bfdc24-28cf-4cfd-bac9-a4ff1ea543e3
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/eRaNYYWH1ECH4zmW0-3wGdh7Bls1CC4fZgb-EEplNAw
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
source-wordcount: 458
ht-degree: 71%

---

# フォールバックオファーデータセット {#fallback-dataset}

>[!TIP]
>
>[!DNL Adobe Journey Optimizer] の新しい決定機能である決定が、コードベースのエクスペリエンスチャネルとメールチャネルを通じて使用できるようになりました。 [詳細情報](../../experience-decisioning/gs-experience-decisioning.md)

オファーが変更されるたびに、フォールバックオファーの自動生成データセットが更新されます。

正常に更新された、データセットの最新のバッチが右側に表示されます。 データセットのスキーマの階層ビューが左側のペインに表示されます。

![](../assets/dataset-fallback.png)

>[!NOTE]
>
>削除済みのフォールバックオファーは、データセット内でアーカイブ済みとしてマークされます。

次に、**[!UICONTROL 決定オブジェクトリポジトリー（フォールバックオファー）]**&#x200B;データセットで使用できるすべてのフィールドのリストを示します。

+++ 識別子

**フィールド：** _id
**タイトル：**&#x200B;識別子
**説明：** レコードの一意のID。
**型：**&#x200B;文字列

+++

+++ _experience

**フィールド：** _experience
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning

**フィールド：**&#x200B;決定
**タイプ：**&#x200B;オブジェクト

+++

+++ _experience > decisioning > characteristics

**フィールド：**&#x200B;特性
**タイトル：**&#x200B;決定オプションの特性
**説明：**&#x200B;この特定の決定オプションに属する追加のプロパティまたは属性。インスタンスごとに異なる特性（マップ内のキー）を持つことができます。 特性は、ある決定オプションと他の決定オプションを区別するために使用される名前の値のペアです。特性は、この決定オプションを表すコンテンツの値として、およびオプションのパフォーマンスを分析および最適化するための機能として使用されます。すべてのインスタンスが同じ属性またはプロパティを持つ場合、その側面は、決定オプションの詳細から派生する拡張スキーマとしてモデル化する必要があります。
**タイプ：** オブジェクト

+++

<!--Field under Characteristics without title = additionalProperties? Desc = Value of the property. Type: string-->

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
     **説明：** リソースの物理的またはデジタルの実現。通常、「形式」には、リソースのメディアタイプを含める必要があります。形式は、リソースの表示または操作に必要なソフトウェア、ハードウェアまたはその他の機器を決定するために使用できます。推奨されるベストプラクティスは、制御されたボキャブラリから値を選択することです（例えば、[Internet Media Types] （https://www.iana.org/ assignments/media-types/）のリストは、コンピュータのメディア形式を定義します）。
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

+++

+++ _experience > decisioning > contents > Placement

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

+++ _experience > decisioning > tags

**フィールド：** タグ
**タイトル：** タグ
**説明：**&#x200B;このエンティティに関連付けられているコレクション修飾子（以前は「タグ」と呼ばれていました）のセット。コレクション修飾子は、フィルター式で使用され、在庫全体をサブセット（カテゴリ）に制限します。
**型：**&#x200B;配列

+++

<!--Field without name under collection qualifiers: Description: An identifier of a collection qualifier object. The value is the @id of the collection qualifier that is referenced. See tag schema: https://ns.adobe.com/experience/decisioning/tag. Type: string-->

+++ _repo

**フィールド：** _repo
**タイプ：**&#x200B;オブジェクト

+++

+++ _repo／決定オプション ETag

**フィールド：** etag
**タイトル：**&#x200B;決定オプション ETag
**説明：** スナップショットの取得時に決定オプションオブジェクトが存在したリビジョン。
**型：**&#x200B;文字列

+++
