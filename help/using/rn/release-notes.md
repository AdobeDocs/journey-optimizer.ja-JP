---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: a53e94f0199cda211d32be55c8e9a52303dc3d25
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 36%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。


## キャンペーンオーケストレーション

**公開日**:2025 年 8 月 4 日（PT）

Journey Optimizerには、ブランド主導のバッチキャンペーン専用の新しい機能である **キャンペーンオーケストレーション** が含まれるようになりました。 このリリースでは、キャンペーンオーケストレーションキャンバスと強化されたデータモデリングが導入され、マーケターが連携して、パーソナライズされたクロスチャネルキャンペーンを計画、ターゲット設定、配信できるようになります。

![ キャンペーンオーケストレーションGIF](assets/do-not-localize/release.gif)

[ リレーショナルスキーマとデータセット ](#oc-relational) および [ キャンペーンキャンバス ](#oc-canvas) が含まれます。 これら 2 つのイノベーションを組み合わせることで、Journey Optimizerでバッチキャンペーンを調整するための新しい標準が解放されます。 主な機能は次のとおりです。

### 主な機能 {#oc-capabilities}

* **複数ステップのワークフロー**

  新しい専用キャンペーンオーケストレーションキャンバスを使用して、高度なマルチチャネルバッチキャンペーンを推進します。

* **オンデマンドオーディエンス**

  即時にアクティブ化するために、オンデマンドでオーディエンスをセグメント化します。

* **マルチエンティティセグメント化**

  製品、店舗、更新、予約などのビジネスコンテキスト（人物以外のディメンション）を使用してオーディエンスを作成します。

* **送信前の表示**

  ローンチ前およびキャンペーンの実行中に、オーディエンスとキャンペーンをレビュー、調整、最適化します

### キャンペーンキャンバス {#oc-canvas}

バッチキャンペーン専用のまったく新しいビジュアルオーケストレーションインターフェイス。 このキャンバスでは、次のことが可能です。

* 複数ステップ、複数チャネルのキャンペーンフローの視覚的な計画

* リレーショナルクエリから作成されたオンデマンドオーディエンスのサポート

* 高度なオーディエンス分割、待機および条件付きロジック

* ビジネスルールおよびフィルターを適用した後の正確な事前送信数

### リレーショナルスキーマとデータセット {#oc-relational}

Adobe Journey Optimizerは、人物ベースのプロファイルにリンクされたリレーショナルエンティティ（商品、店舗、予約、契約など）をサポートするようになりました。 これにより、多次元データ構造全体でセグメント化とパーソナライゼーションが可能になり、次のようなユースケースが可能になります。

* 予約、購読または契約ごとに 1 つのメッセージ

* 関連するエンティティ属性（製品カテゴリや店舗の場所など）に基づくセグメント化

* アドレス可能性の向上（例：エンティティに関連付けられたすべての既知の連絡先に送信）

### これが重要な理由

このリリースでは、マーケターは、柔軟なデータモデリングと専用のオーケストレーションエクスペリエンスを組み合わせて、ブランド主導のオーディエンスベースのバッチマーケティングを完全に制御できます。 高度なパーソナライゼーションとスケーラビリティを提供しながら、リアルタイムジャーニーからのバッチキャンペーンオーケストレーション用に特別に設計されています。

### 詳細情報

詳しくは、[Campaign オーケストレーションドキュメント ](../orchestrated/gs-orchestrated-campaigns.md) を参照してください。

<!--
## August '25 pre release notes {#25-7-rn}

**Pre release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.

**Release date**: August 19, 2025


### New capabilities {#Aug-25-8-features}

New capabilities coming with this release are detailed below.

### Improvements {#Aug-25-8-improv}

Improvements coming with this release are listed below.
-->


## 2025 年 7 月リリースノート {#25-7-rn}

**リリース日**：2025年7月29日（PT）

### 新機能 {#features-25-7}

このリリースに含まれる新機能を以下に示します。

#### 機能

<table>
<thead>
<tr>
<th><strong>WhatsApp チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerは、WhatsApp によるダイレクトメッセージをサポートするようになり、ジャーニーとキャンペーンにスムーズに統合し、受信者とのコミュニケーションとエンゲージメントを向上させることができます。 このネイティブチャネルは、標準の WhatsApp テンプレート統合、メッセージのプレビュー、パーソナライゼーション、配信レポート、Webhook、オプトイン、オプトアウトの同意管理などを提供します。</p>
<p>以前にBetaでリリースされたこの機能は、すべての環境で利用できるようになりました（一般提供）。</p>
<p><img src="../whatsapp/assets/do-not-localize/WA-Animation.gif"/><p>
<p>詳しくは、<a href="../whatsapp/get-started-whatsapp.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ブランド</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>独自のブランドを作成およびカスタマイズし、コミュニケーション全体で視覚的および言語的な ID を明確に定義できるようになりました。ブランド整合性スコアを使用すると、コンテンツがブランドのトーン、スタイル、ガイドラインをどの程度反映しているかに関するフィードバックをリアルタイムで受信でき、送信するすべてのメッセージでブランドに即して一貫性を保つことができます。</p>
<p>以前にBetaでリリースされたこの機能は、すべての環境で利用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/brand-score.gif"/></p>
<p>詳しくは、<a href="../content-management/brands.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールチャネルでの Use Decisioning</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールジャーニーとキャンペーンに決定ポリシーを追加できるようになりました。 決定ポリシーは、決定エンジンを活用してオーディエンスメンバーごとに配信する最適なコンテンツを動的に返す、オファーのコンテナです。</p>
<p>この機能は、限定提供（LA）で利用できます。 アクセス権を取得するには、Adobe担当者にお問い合わせください。</p>
詳しくは、<a href="../experience-decisioning/create-decision.md"> 詳細ドキュメント </a> を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>LINE チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer では、クロスチャネル機能を拡張し、LINE チャネルのサポートを含めました。この機能強化により、LINE エクスペリエンスを作成、編集、プレビューできます。これにより、よりパーソナライズされた魅力的なインタラクションが可能になります。LINE を使用すると、より多くのお客様とつながり、関連性の高いコンテンツを送信し、エンゲージメントを向上させることができます。</p>
<p>以前はリクエストのみ可能でしたが、すべてのユーザーが LINE チャネルを利用できるようになりました（一般公開）。</p>
<p>詳しくは、<a href="../line/get-started-line.md">詳細なドキュメント</a>を参照してください。</p></td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Optimization in campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer now empowers you with the tools to deliver personalized and optimized content to your campaigns' audience, allowing you to run content experiments, create rule-based targeting, and use advanced combinations of both, to maximize the effectiveness of your campaigns.</p>
<p>With Optimization, you can:</p>
<ul>
<li>Test multiple content variations to identify the most effective messaging.</li>
<li>Deliver personalized content based on user attributes and contextual data.</li>
<li>Combine targeting and experimentation for advanced campaign strategies.</li>
<li>Filter out users that do not match variant criteria.</li>
<li>Ensure fallback mechanisms to maintain user engagement.</li>
</ul>
<P>Once the campaign is live, profiles are evaluated against the defined criteria, and based on matching criteria, they are delivered with the appropriate experience or content from the campaign.</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table>
-->



<table>
<thead>
<tr>
<th><strong>ジャーニードライラン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーのドライランは、Adobe Journey Optimizer の特別なジャーニー公開モードで、ジャーニー実務担当者は実際の顧客に連絡したり、プロファイル情報を更新したりすることなく、実際の実稼動データを使用してジャーニーをテストできます。この機能により、ジャーニー実務担当者は、ジャーニーをライブで公開する前に、ジャーニーのデザインとオーディエンスのターゲティングに自身を持つことができます。</p>
<img src="assets/do-not-localize/DryRun.gif">
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます（一般提供）。</p>
<p>詳しくは、<a href="../building-journeys/journey-dry-run.md"> 詳細ドキュメント </a> を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ジャーニーの追加 ID</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プロファイル ID と、注文 ID、サブスクリプション ID、処方箋 ID などの別の識別子を使用してジャーニーをトリガーできるようになりました。これにより、同じプロファイルを同じジャーニーに複数回同時に含めることができます。これにより、各インスタンスがジャーニーを通じて独自のパスに従いながら、複数の注文やサブスクリプションを並行して管理するなどのシナリオが可能になります。</p>
<p>以前は限定提供でリリースされていましたが、ジャーニーでの追加の ID の使用はすべての環境で利用できるようになりました。 この一般提供リリースで、この機能には、オーディエンスを読み取りジャーニーのサポートが含まれるようになりました。</p>
<p><img src="assets/do-not-localize/gif-supplemental.gif"/></p>
<p>詳しくは、<a href="../building-journeys/supplemental-identifier.md"> 詳細ドキュメント </a> を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 製品内アラート

Journey Optimizer製品リリースに関する **メールおよび製品内アラート** を登録できるようになりました。

登録するには：

* **Adobe Experience Cloud環境設定** に移動します
* **Notifications** で、**Journey Optimizerの新しいリリース** を見つけます
* アプリ内通知およびメール通知の有効化

![](assets/do-not-localize/pulse-notif.png){width="70%" align="left"}


### ジャーニー条件の変更 {#ee-change@}

7月8日（PT）以降、新しい顧客組織では、ジャーニー条件で使用される式エディターで、エクスペリエンスイベントを使用した式の作成はサポートされなくなります。その結果、[Experience Platform データソース](../datasource/adobe-experience-platform-data-source.md)のエクスペリエンスイベントは式の作成に使用できません。エクスペリエンスイベントを使用して式／ロジックを作成する際の代替アプローチとベストプラクティスについて詳しくは、[こちら](../building-journeys/exp-event-lookup.md)を参照してください。

単一ジャーニーでジャーニーコンテキストイベントデータにアクセスする方法に変更はありません。式エディターとパーソナライゼーションエディターでは、ユーザーは最初のジャーニーイベントで渡されたデータに引き続きアクセスできます。

詳しくは、[この FAQ](../building-journeys/exp-event-lookup.md#faq-ee) を参照してください。

### 機能強化 {#25-7-improv}

このリリースに含まれる機能強化を以下に示します。

* **キャンペーン**

   * **キャンペーンでの複数のインバウンドアクション** - キャンペーンオーケストレーションを簡素化するために、1 つのキャンペーンで複数のインバウンドアクションを定義できるようになりました。 この機能を使用すると、複数のコードベースのエクスペリエンス、アプリ内メッセージ、コンテンツカード、web アクションを異なる場所に同時に配信できます。各アクションには特定のコンテンツが含まれます。
  <!-- [Read more](../FILE.md) -->

   * **キャンペーン在庫の再編成** - スケジュール済みキャンペーンと API トリガーキャンペーンがキャンペーンインベントリの別々のタブに分割され、ナビゲーションと管理が容易になりました。

[詳細情報](../campaigns/modify-stop-campaign.md)

* **データ管理**
   * **意思決定管理システムデータセットの更新** – 削除されたパーソナライズされたオファーとフォールバックオファーは、「decision_object_repository_personaled_offers」および「decision_object_repository_fallback_offers」データセットでアーカイブ済みとしてマークされるようになりました。 データセット内の既存のレコードは変更されません。

[詳細情報](../offers/export-catalog/access-dataset.md)

* **ジャーニー**
   * **ジャーニーサンドボックスツールの機能強化** - パッケージの書き出しと読み込み機能を使用して、複数のサンドボックス間でジャーニーをコピーする際に、次の機能も使用できるようになりました。
      * 宛先で既存のイベントを選択
      * ジャーニーとは別にイベント上でコピーする
      * フィールドグループ/データソースの関係を検出し、存在する場合は宛先でリンクし、存在しない場合は作成する。

[詳細情報](../configuration/copy-objects-to-sandbox.md)

* **チャネル – アプリ内**
   * **アプリ内キーと値のペア** - アプリ内メッセージを使用すると、キーと値のペアを定義して、メッセージペイロードにカスタム変数を含めることができます。 これらのキーと値のペアを使用すると、特定の設定およびユースケースに基づいて追加のデータを渡すことができます。 [詳細情報](../in-app/design-in-app.md)

* **チャネル – コンテンツカード**

   * **ルールベースのキャンペーンの不適格** – 追加の配信ルールを編集する際に、メッセージのタイミングと表示をより適切に制御するために、以前の「配信ルール」オプションが 3 つの異なるルールタイプに置き換えられました。
      * 次の場合にメッセージを表示：コンテンツカードを表示するタイミングを決定する条件。
      * 次の場合にメッセージを閉じる：コンテンツカードを一時的に非表示にする条件。 表示条件が再び満たされると、再び表示される場合があります。
      * 次の場合にメッセージを無効にする：コンテンツカードが二度と表示されないようにする条件。

[詳細情報](../content-card/design-content-card.md)

* **決定**
   * **移行ツール API** - Journey Optimizer チームは現在、意思決定管理エンティティを Decisioning に移行するための移行ツール API に取り組んでいます。 このツールを使用すると、依存関係の解決とロールバック機能により、サンドボックス間でシームレスな移行を実行できます。 興味がある場合は、Adobe担当者にお問い合わせください。

* **パーソナライゼーション**
   * 新しいヘルパー関数「SHA256」がパーソナライゼーションエディターに追加されました。 この関数は、文字列の sha256 ハッシュを計算して返すために使用されます。

[詳細情報](../personalization/functions/string.md#sha256)
