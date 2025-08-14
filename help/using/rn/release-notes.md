---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 2afc9c4eb2a0433a22f1b369824086db2f5618ec
workflow-type: tm+mt
source-wordcount: '1776'
ht-degree: 44%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。


## 2025年8月プレリリースノート {#25-8-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日に公開されます。

[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**：2025年8月19日（PT）


### 新機能 {#Aug-25-8-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>ジャーニーの一時停止と再開</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを一時停止して再開できるようになりました。この機能により、顧客体験を止めずにライブジャーニーを一時中断できるので、ジャーニー実務担当者はより優れた制御と柔軟性を得ることができます。一時停止すると、通信は送信されず、ジャーニーが再開されるまでプロファイルは中断状態のままになります。</p>
<p>1 つのジャーニーのみを一時停止および再開することや、ジャーニーのグループに対して一括で一時停止および再開の操作を実行することができます。</p>
<p>さらに、一時停止したジャーニーにグローバルフィルターを適用して、属性に基づいてプロファイルを除外できます。</p>
<p><!--img src="assets/do-not-localize/PauseResume.gif"/>--></p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-pause.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カレンダー表示</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーとキャンペーンのリストでカレンダー表示を使用できるようになりました。これにより、すべてのジャーニーとキャンペーンのアクティベーションをそれぞれのリストで視覚化できます。</p>
<p>この機能は、以前は限定提供でしたが、現在はすべての環境で使用できるようになりました。この一般提供リリースでは、この機能には次のものが含まれます。</p>
<ul>
<li>日付のナビゲーションのデザインの改善、</li>
<li>開始日と終了日を設定した場合に、ドラフトキャンペーンを表示する機能。</li>
<li>実行されているカレンダー項目の表示/非表示を長時間切り替える新しい設定です。</li>
</ul>
<p><!--img src="assets/do-not-localize/calendar.gif"/>--></p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-ui.md#journeys-calendar">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Dark mode in the Email Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Journey Optimizer Email Designer now offers the ability to switch to dark mode view, where you can additionally define specific custom settings that will display only for recipients reading their emails in dark mode.</p>
<p>Note the following:</p>
<ul>
<li>The dark mode final rendering may vary and depends on the recipient's email client.</li>
<li>Not all email clients support custom dark mode. Moreover, some email clients only apply their own default dark mode for all emails that are received. In both cases, the custom settings that you defined in the Email Designer cannot be rendered.</li>
</ul>
<P>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>For more information, refer to the <a href="../email/dark-mode.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform データをパーソナライゼーションに使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライゼーションエディターの [!DNL Adobe Experience Platform] のデータを活用して、コンテンツと決定属性をパーソナライズします。 特に、これを使用すると、属性の定義をデータセット内の追加データに拡張して、定期的に変更される一括更新を行うことができます。属性を 1 つずつ手動で更新する必要はありません。</p>
<p>このリリースでは、次の機能強化が導入されました。</p>
<ul>
<li>インバウンドチャネルのサポート、</li>
<li>式およびビジュアルフラグメント内で「datasetLookup」ヘルパー関数を使用して、Adobe Experience Platform データセットのデータを使用してコンテンツをパーソナライズできるようになりました。</li>
<li>データセット内のオプションを使用すると、API 呼び出しを実行しなくても、データセットで参照パーソナライゼーションを有効にできるようになりました。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Use Decisioning in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add Decision policies into email journeys and campaigns. Decision policies are containers for your offers that leverage the Decisioning engine to dynamically return the best content to deliver for each audience member.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<p><img src="assets/do-not-localize/FILE.gif"/></p>
<p><For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerに追加されたツールを使用すると、AI および実験フレームワークを活用してジャーニーを最適化しながら、条件と最適化機能のシームレスな操作性と差別化を実現できます。</p>
<p>パスの最適化を使用して、AI をターゲット、実験、使用し、通信のシーケンス、それらの間の時間、チャネルの組み合わせ、ジャーニーキャンバスで夢見ることができるものを決定します。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーのアクションアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで新しい汎用アクションアクティビティがサポートされ、単一アクションと複数アクションのインバウンドアクショングループの両方を設定でき、ジャーニーキャンバス内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内のシンプルなネイティブアクション設定。</li>
<li>複数アクションのインバウンドノードを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/pdf-attachments.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールへのPDF添付ファイル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで送信されるメールメッセージに、静的PDF ファイルを添付できるようになりました。</p>
<ul>
<li>プロファイルごとにPDF添付ファイルを含むメッセージを年間 6 件まで送信できます。</li>
<li>各添付ファイルに許可される最大ファイルサイズは 5 MB です。</li>
<li>サイズやボリュームを追加する場合は、添付ファイルパックアドオンを購入できます。 詳しくは、Adobe担当者にお問い合わせください。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ランディングページのカスタムフォーム</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>[!DNL Journey Optimizer] を使用すると、ランディングページ全体でプロファイル属性を取り込めるようになりました。</p>
<p>特定のデータセットに基づいて、ニーズに合わせてカスタマイズされたカスタムフォームを作成、デザイン、管理します。 その後、ランディングページでこれらのフォームを活用し、選択したプロファイル属性を各フォーム用に定義されたデータセットに追加できます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.--></p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>キャンペーンの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、ツールを使用して、パーソナライズされ、最適化されたコンテンツをキャンペーンのオーディエンスに提供できるようになりました。これにより、コンテンツ実験の実行、ルールベースのターゲティングの作成、および両方の高度な組み合わせの使用ができ、キャンペーンの効果を最大限に高めることができます。</p>
<p>最適化では、次のことができます。</p>
<ul>
<li>コンテンツの複数のバリエーションをテストして、最も効果的なメッセージングを特定します。</li>
<li>ユーザー属性とコンテキストデータに基づいてパーソナライズされたコンテンツを配信します。</li>
<li>高度なキャンペーン戦略のために、ターゲティングと実験を組み合わせます。</li>
<li>バリアント条件に一致しないユーザーをフィルターで除外します。</li>
<li>ユーザーエンゲージメントを維持するためのフォールバックメカニズムを確保します。</li>
</ul>
<P>キャンペーンがライブになると、プロファイルは定義済みの条件に照らして評価され、一致条件に基づいて、キャンペーンからの適切なエクスペリエンスまたはコンテンツで配信されます。</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<p>リリース日：2025 年 8 月 8 日（PT）</p>
<p>詳しくは、<a href="../campaigns/campaigns-message-optimization.md">詳細なドキュメント</a>を参照してください</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#Aug-25-8-improv}

このリリースに含まれる機能強化を以下に示します。

* **管理**

   * **チャネル設定の監視アラート** - <!--a channel configuration failure happens or if -->A DNS レコードがない場合に、メールまたはJourney Optimizer通知センターでシステムアラートを受け取るように登録できるようになりました。

* **キャンペーン**

   * **アウトバウンドキャンペーンのレートコントロール** - アウトバウンドキャンペーン（メール、SMS、プッシュ通知）のレートコントロールを有効にして、ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムでの過負荷を防ぐことができるようになりました。

   * **アクションキャンペーンのスケジュール設定** - キャンペーンの日別、週別および月別のスケジューラーが更新され、繰り返しスケジュールをより詳細に制御できるようになりました。

      * **毎週の繰り返し**：キャンペーンを毎週または 2 週間ごとに繰り返し、キャンペーンを実行する曜日を選択できるようになりました。

      * **毎月の繰り返し**：キャンペーンを毎月または 2 か月ごとに繰り返し、キャンペーンを実行する日を選択できるようになりました。

      * **日別、週別、月別のスケジュール**：繰り返しスケジュールを特定の日付に停止するか、特定の回数の発生後に停止するかを指定できます。

   * **スケジュールされたトランザクションアクションキャンペーン** - スケジュールされたトランザクションアクションキャンペーンで、メール、SMS、プッシュチャネルを介してバッチ、オーディエンスベースのトランザクション通信を送信できるようになりました。

* **チャネル – プッシュ**

   * **プッシュ通知の有効期限** – 各プッシュ通知に有効期限を指定できるようになりました。これにより、特定の日付を過ぎると時間依存のメッセージ（ブラックフライデーセールなど）が送信されなくなるので、顧客に悪いエクスペリエンスを提供するのを防ぐことができます。

* **チャネル - SMS**

   * **ファジーオプトアウト** – 有効にすると、「**ファジーオプトアウト**」オプションは、定義済みのオプトアウトキーワード（「CANCIL」など）に非常に似た受信メッセージを検出し、ユーザーの購読解除の意図を確認する確認返信を自動的に送信します。 定義済みのプロンプトで確認すると、購読は解除されます。

     **ファジーオプトアウト** は、Sinch および Infobip でのみ使用できます。

   * **SMS 接続の検証** - サンプルメッセージを指定されたデバイスに送信することで、Adobe Journey Optimizer内で SMS API 資格情報を簡単にテストおよび検証できるようになりました。

* **設定**

   * **動的ドメインのサポート** - Journey Optimizerでは、チャネル設定レベルでリストされる事前定義済みドメインのトラッキング URL でのパーソナライゼーションをサポートするようになりました。

   * **ワンクリック登録解除 URL でのカスタム属性のサポート** - Journey Optimizerを使用すると、Adobe以外で同意を管理している場合、メール設定に独自のワンクリック登録解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が購読解除リンクをクリックすると、Journey Optimizerによって、プロファイル固有のデフォルトのパラメーターが同意更新イベントに追加されます。

     ワンクリック購読解除リンクをさらにパーソナライズするために、同意イベントにも追加されるカスタム属性を定義できるようになりました。

* **決定**

   * **決定項目にフラグメントを添付** - Journey Optimizerでは、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できる決定項目にフラグメントを添付する機能を提供するようになりました。

* **ジャーニー**

   * **ジャーニーの一括操作** - ジャーニーのリストから、複数の項目を選択できるようになりました。 選択すると、一度に 10 件までのジャーニーを一時停止または再開できます。

   * **カスタムアクションでのリダイレクト（302）のサポート** - カスタムアクションでは、リクエストごとに HTTP 302 リダイレクトを処理できるようになりました。 これにより、ジャーニーは、ローカライズされた、または地域固有の URL にリクエストをリダイレクトする API と統合できます。 リダイレクトに自動的に従うため、追加の設定を行うことなく正しいコンテンツが配信されます。

* **データセット**

   * **Experience Decisioning オブジェクトリポジトリ – パーソナライズされたオファー項目** – 組み込みの書き出しデータセットは、すべてのオファー属性とライフサイクルステータスをキャプチャし、完全なパーソナライゼーションとレポートを可能にしました。

## キャンペーンオーケストレーション

**公開日**：2025年8月4日（PT）

Journey Optimizer に、ブランド主導のバッチキャンペーン専用の新しい機能である&#x200B;**キャンペーンオーケストレーション**&#x200B;が含まれるようになりました。このリリースでは、キャンペーンオーケストレーションキャンバスと強化されたデータモデリングが導入され、これらを連携することで、マーケターがパーソナライズされたクロスチャネルキャンペーンを計画、ターゲット、配信できます。

>[!IMPORTANT]
>
>Campaign オーケストレーションにアクセスするには、ライセンスに **Journey Optimizer - キャンペーンとジャーニー** または **Journey Optimizer - キャンペーン** パッケージが含まれている必要があります。 ライセンスを確認して必要に応じて更新するには、Adobeの担当者にお問い合わせください。

![キャンペーンオーケストレーションの GIF](assets/do-not-localize/release.gif)

これには、[リレーショナルスキーマとデータセット](#oc-relational)および[キャンペーンキャンバス](#oc-canvas)が含まれます。これら 2 つのイノベーションを組み合わせることで、Journey Optimizer でのバッチキャンペーンの調整に対する新しい標準が確立されます。主な機能は次のとおりです。

### 主な機能 {#oc-capabilities}

* **複数ステップのワークフロー**

  新しい専用のキャンペーンオーケストレーションキャンバスを使用して、高度なマルチチャネルバッチキャンペーンを推進します。

* **オンデマンドオーディエンス**

  即時にアクティブ化できるよう、オンデマンドでオーディエンスをセグメント化します。

* **マルチエンティティセグメント化**

  製品、店舗、更新、予約などのビジネスコンテキスト（人物以外のディメンション）を使用してオーディエンスを作成します。

* **送信前の表示**

  キャンペーン開始前およびキャンペーン実行中に、オーディエンスとキャンペーンをレビュー、調整、最適化します

### キャンペーンキャンバス {#oc-canvas}

バッチキャンペーン専用に作成されたまったく新しいビジュアルオーケストレーションインターフェイス。このキャンバスでは、次のことが可能です。

* 複数ステップ、マルチチャネルのキャンペーンフローの視覚的な計画

* リレーショナルクエリから作成されたオンデマンドオーディエンスのサポート

* 高度なオーディエンス分割、待機、条件付きロジック

* ビジネスルールとフィルターを適用した後の正確な事前送信数

### リレーショナルスキーマとデータセット {#oc-relational}

Adobe Journey Optimizerは、人物ベースのプロファイルにリンクされたリレーショナルエンティティ（商品、店舗、予約、契約など）をサポートするようになりました。 これにより、マルチディメンションのデータ構造をまたいでセグメント化とパーソナライゼーションが許可され、次のようなユースケースが可能になります。

* 予約、登録または契約ごとに 1 つのメッセージ

* 関連するエンティティ属性（例：製品カテゴリ、店舗の場所）に基づいてセグメント化

* 強化されたアドレサビリティ（例：エンティティに関連付けられたすべての既知の連絡先に送信）

### これが重要な理由

このリリースでは、マーケターは、柔軟なデータモデリングと専用のオーケストレーションエクスペリエンスを組み合わせることで、ブランド主導のオーディエンスベースのバッチマーケティングを完全に制御できます。リアルタイムのジャーニーからのバッチキャンペーンオーケストレーション専用に設計され、同時に高度なパーソナライゼーションとスケーラビリティを提供します。

### 詳細情報

詳しくは、[キャンペーンオーケストレーションドキュメント](../orchestrated/gs-orchestrated-campaigns.md)を参照してください。


