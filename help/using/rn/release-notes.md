---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 64228dfbd0e8c2884df179767d0ec9fe13d6fdf6
workflow-type: tm+mt
source-wordcount: '2226'
ht-degree: 87%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 9 月の更新 {#sep-updates}

### 新機能 {#Sep-25-features}

<table>
<thead>
<tr>
<th><strong>E メールデザイナーでのダークモード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer E メールデザイナーに、ダークモード表示に切り替える機能が追加されました。この機能を使用すると、ダークモードでメールを読む受信者にのみ表示される特定のカスタム設定を定義できます。</p>
<p>次のことに注意してください。</p>
<ul>
<li>ダークモードの最終的なレンダリングは、受信者のメールクライアントに応じて異なります。</li>
<li>すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。さらに、一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードのみが適用されます。どちらの場合も、E メールデザイナーで定義したカスタム設定はレンダリングできません。</li>
</ul>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>詳しくは、<a href="../email/dark-mode.md">詳細なドキュメント</a>を参照してください。</p>
 <p>公開日：2025 年 9 月 16 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい最適化ノードを使用して特定のオーディエンスにターゲットを設定するか、A/B テストを実行して、ビジネス目標に焦点を合わせた KPI を達成する最適なパスを決定します。</p>
<p>このツールを使用すると、コミュニケーション、シーケンス、タイミングをテスト、調整、カスタマイズし、顧客に最も効果的にリーチできます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/optimize.gif"/></p>
<p>詳しくは、<a href="../building-journeys/optimize.md">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025 年 9 月 4 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サブドメインのカスタムデリゲーションメソッド</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>完全なデリゲーションと CNAME メソッドに加えて、新しいサブドメイン設定メソッドとして、カスタムデリゲーションメソッドが使用できるようになりました。これにより、メッセージの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を完全に制御および管理できます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../configuration/delegate-custom-subdomain.md">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025 年 9 月 4 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>パーソナライゼーションと意思決定へのAdobe Experience Platform データの使用 – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前パブリックベータ版でリリースされていましたが、この機能は、すべての環境で限定提供（LA）で利用できるようになりました。 このリリースでは、次の機能強化が導入されました。</p>
<ul><li>インバウンドチャネルでのデータセットルックアップパーソナライゼーションのサポート。</li>
<li>「datasetLookup」ヘルパー関数を式フラグメント内で使用できるようになりました。 現時点では、この機能は一部のお客様のみが利用できます。 アクセスするには、アドビ担当者にお問い合わせください。</li>
<li>データセット管理インターフェイスのオプションを使用すると、API 呼び出しを実行しなくても、ルックアップパーソナライゼーション用のレコードベースのデータセットを有効にできるようになりました。</li>
<li>データ取り込みステータスを追跡し、データセットの検索準備が整ったタイミングを把握するための監視機能を強化しました。</li>
<li>最適なパフォーマンスと信頼性を確保するために、使用ガイドラインとガードレールを更新しました。</li>
<li>Adobe Experience Platform データセットを決定キャッピングルールで活用できるようになりました。</li></ul></p>
<p>詳しくは、<a href="../data/lookup-aep-data.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 9 月 1 日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#Sep-25-improv}

* **時間単位での頻度キャップのリセット** - チャネルルールセットに対して時間単位でキャップを適用できるようになりました。以前は限定提供（LA）で利用できましたが、現在はすべての環境で利用でき、1 時間（以前は 3 時間）を選択できるようになりました。 [ 詳細情報 ](../conflict-prioritization/channel-capping.md)。 実施可能日：9 月 17 日（PT）

* **動的ドメインのサポート** - Journey Optimizerで、Adobeが受け入れる事前定義済みドメインの完全/ベース URL パーソナライゼーションがサポートされるようになりました。 [ 詳細を表示 ](../personalization/personalization-build-expressions.md#where)<!--Availability date: September 12-->

  >[!NOTE]
  >
  >この機能は、一連のお客様に対して限定提供で利用できます。

* **決定キャッピングルールの式** – 決定項目のキャッピングルールのしきい値を定義する独自の式を作成できるようになりました。 [詳細情報](../experience-decisioning/items.md#capping)

  >[!NOTE]
  >
  >この機能は、現在、すべてのユーザーに対する限定提供として利用できます。

* **チャネル設定の監視アラート** - カスタムサブドメインデリゲーションタイプを使用したメールチャネル設定エラーが発生した場合に、メールまたはJourney Optimizer通知センターでシステムアラートを受け取ることを登録できるようになりました。 [詳細情報](../reports/alerts.md#alert-dns-record-missing)

## 2025年8月リリースノート {#25-8-rn}

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
<p><img src="assets/do-not-localize/PauseResume.gif"/></p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../building-journeys/journey-pause.md">詳細なドキュメント</a>を参照してください。</p>
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
<li>日付でのナビゲーションのデザインの改善</li>
<li>開始日と終了日を設定した場合に、ドラフトキャンペーンを表示する機能。</li>
<li>長期間実行されているカレンダー項目の表示と非表示を切り替える新しい設定。</li>
</ul>
<p><img src="assets/do-not-localize/calendar.gif"/></p>
<p>詳しくは、<a href="../building-journeys/journey-ui.md#calendar">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Use Adobe Experience Platform data for personalization</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Leverage data from [!DNL Adobe Experience Platform] in the personalization editor to personalize your content and decision attributes. In particular, this allows you to extend the definition of your attributes to additional data in datasets for bulk updates that change periodically without having to manually update the attributes one at a time.</p>
<p>With this release, the following enhancements have been introduced:</p>
<ul>
<li>Support of inbound channels,</li>
<li>The "datasetLookup" helper function can now be used within expression and visual fragments to personalize content using data from Adobe Experience Platform datasets,</li>
<li>An option in the dataset now allows you to enable datasets for lookup personalization, without having to perform an API call.</li>
</ul>
<p>This capability is available in Limited Availability. Contact your Adobe representative to gain access.</p>
<p>For more information, refer to the <a href="../personalization/aep-data-perso.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

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
<th><strong>ジャーニーのアクションアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer は、単一アクションと複数アクションのインバウンドアクショングループの両方を設定できる新しい汎用アクションアクティビティをサポートしているので、ジャーニーキャンバス内でのアクション設定を効率化できます。特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/action-activity.gif"/></p>
<p>詳しくは、<a href="../building-journeys/journey-action.md">詳細なドキュメント</a>を参照してください</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールへの PDF 添付ファイル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer で送信されるメールメッセージに静的 PDF ファイルを添付できるようになりました。</p>
<ul>
<li>プロファイルごとに、年間最大 6 件の PDF 添付ファイル付きメッセージを送信できます。</li>
<li>各添付ファイルの最大許容ファイルサイズは 5 MB です。</li>
<li>追加のサイズまたはボリュームについては、添付ファイルパックアドオンを購入できます。詳しくは、アドビ担当者にお問い合わせください。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/pdf-attachments.gif"/></p>
<p>詳しくは、<a href="../email/pdf-attachments.md">詳細なドキュメント</a>を参照してください</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Landing page custom forms</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>With [!DNL Journey Optimizer], you can now capture profile attributes though your landing pages.</p>
<p>Create, design and manage custom forms tailored to your needs based on a specific dataset. You can then leverage these forms in landing pages to add the profile attributes of your choice into the dataset defined for each form.</p>
<p>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>キャンペーンの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、ツールを使用して、パーソナライズされ、最適化されたコンテンツをオーディエンスに提供できるようになりました。これにより、コンテンツ実験の実行、ルールベースのターゲティングの作成、および両方の高度な組み合わせの使用ができ、キャンペーンとジャーニーの効果を最大限に高めることができます。</p>
<p>最適化では、次のことができます。</p>
<ul>
<li>コンテンツの複数のバリエーションをテストして、最も効果的なメッセージングを特定します。</li>
<li>ユーザー属性とコンテキストデータに基づいてパーソナライズされたコンテンツを配信します。</li>
<li>高度な戦略のために、ターゲティングと実験を組み合わせます。</li>
<li>バリアント条件に一致しないユーザーをフィルターで除外します。</li>
<li>ユーザーエンゲージメントを維持するためのフォールバックメカニズムを確保します。</li>
</ul>
<P>ジャーニーやキャンペーンがライブになると、プロファイルは定義済みの条件に照らして評価され、一致条件に基づいて、適切なエクスペリエンスまたはコンテンツで配信されます。</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<p>この処理能力は、以前は 8月8日（PT）にキャンペーンでのみリリースされていましたが、現在は 8月22日（PT）以降のジャーニーでも使用できるようになりました。</p>
<p>詳しくは、<a href="../campaigns/campaigns-message-optimization.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#Aug-25-8-improv}

このリリースに含まれる機能強化を以下に示します。

* **管理**

   * **チャネル設定のモニタリングアラート** - <!--a channel configuration failure happens or if -->DNS レコードが見つからない場合に、メールまたは Journey Optimizer 通知センターでシステムアラートを受信するよう登録できるようになりました。[詳細情報](../reports/alerts.md#alert-dns-record-missing)

* **AI アシスタント**

   * **複数の言語でのコンテンツ生成** - フランス語、スペイン語、ドイツ語、イタリア語、日本語、スウェーデン語、オランダ語、ノルウェー語でコンテンツを生成できるようになりました。[詳細情報](../content-management/generative-uc.md#languages)

     公開日：8月25日（PT）


* **キャンペーン**

   * **アウトバウンドキャンペーンのレート制御** - アウトバウンドキャンペーン（メール、SMS、プッシュ通知）のレート制御を有効にできるようになりました。これにより、ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムの過負荷を防ぐことができます。[詳細情報](../campaigns/campaign-schedule.md#rate-control)

   * **アクションキャンペーンのスケジュール設定** - キャンペーンの毎日、毎週、毎月のスケジューラーが更新され、繰り返しスケジュールをより詳細に制御できるようになりました。

      * **毎週の繰り返し**：キャンペーンを毎週または 2 週間ごとに繰り返すように選択し、実行する曜日を選択できるようになりました。

      * **毎月の繰り返し**：キャンペーンを毎月または隔月で繰り返すように選択し、実行する月の日を選択できるようになりました。

      * **毎日、毎週、毎月のスケジュール**：繰り返しスケジュールを特定の日付に停止するか、特定の回数の発生後に停止するかを指定できます。

   * **スケジュール済みトランザクションアクションキャンペーン** - スケジュール済みトランザクションアクションキャンペーンを使用して、メール、SMS、プッシュチャネル経由でバッチのオーディエンスベースのトランザクション通信を送信できるようになりました。

* **チャネル - コンテンツカード**

   * **コンテンツカードレイアウトテンプレート** - コンテンツカードチャネルでは、オーサリングエクスペリエンスを効率化する OOTB メッセージレイアウトが提供されるようになりました。このリリースには、小さい画像、大きい画像、画像のみのレイアウトテンプレートが含まれています。[詳細情報](../content-card/design-content-card.md)

* **チャネル - プッシュ**

   * **プッシュ通知の有効期限** - 各プッシュ通知に有効期限を指定できるようになりました。これにより、時間的制約のあるメッセージ（Black Friday セールなど）が特定の日付以降に送信されなくなるので、顧客に悪いエクスペリエンスを提供することを回避できます。

* **チャネル - SMS**

   * **ファジーオプトアウト** - 有効にすると、「**ファジーオプトアウト**」オプションは、定義済みのオプトアウトキーワード（「CANCIL」など）に非常に類似したインバウンドメッセージを検出し、ユーザーの登録解除の意図を検証する確認返信を自動的に送信します。定義済みのプロンプトを通じてユーザーが確認すると、登録解除されます。[詳細情報](../sms/sms-configuration-sinch.md)

     >[!NOTE]
     >
     >**あいまいオプトアウト**&#x200B;は、Sinch と Infobip でのみ使用できます。

   * **SMS 接続を検証** - 指定されたデバイスにサンプルメッセージを送信して、Adobe Journey Optimizer 内で SMS API 資格情報を簡単にテストおよび検証できるようになりました。[詳細情報](../sms/sms-configuration-sinch.md)

* **設定**

   * **ワンクリック登録解除 URL を使用したカスタム属性のサポート** - Journey Optimizer では、アドビ以外で同意を管理している場合、メール設定で独自のワンクリック登録解除リンクを定義して、外部カスタムエンドポイントを設定できます。受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

     ワンクリック登録解除リンクをさらにパーソナライズするのに、同意イベントにも追加されるカスタム属性を定義できるようになりました。[詳細情報](../email/list-unsubscribe.md#custom-attributes)

* **データセット**

   * **エクスペリエンス決定オブジェクトリポジトリ** - パーソナライズされたオファー項目 - 組み込みの書き出しデータセットで、すべてのオファー属性とライフサイクルステータスが取得されるようになり、完全なパーソナライゼーションとレポートが可能になりました。[詳細情報](../data/export-datasets.md)

   * 一貫性を向上させ、変更を追跡して項目をより確実に提供するために、`etag` フィールドを介したバージョンチェックを導入しました。

* **決定**

   * **フラグメントを決定項目に添付** - Journey Optimizer では、決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できるフラグメントを決定項目に添付できるようになりました。この機能は、一連のお客様に対する限定提供で使用できます。[詳細情報](../experience-decisioning/create-decision.md#fragments)

* **ジャーニー**

   * **ジャーニーの一括操作** - ジャーニーのリストから、複数の項目を選択できるようになりました。選択すると、一度に最大 10 件のジャーニーを一時停止または再開できます。

   * **カスタムアクションでのリダイレクト（302）サポート** - カスタムアクションでは、リクエストごとに HTTP 302 リダイレクトを処理できるようになりました。これにより、ローカライズされた URL または地域固有の URL にリクエストをリダイレクトする API とジャーニーを統合できます。リダイレクトは自動的に実行されるので、追加の設定なしで正しいコンテンツが配信されます。

   * **ジャーニーでの複数のインバウンドアクション** - ジャーニーオーケストレーションを簡素化するために、1 つのジャーニーで複数のインバウンドアクションを定義できるようになりました。以前はキャンペーンで使用可能であった、この機能により、複数のコードベースのエクスペリエンス、アプリ内メッセージ、コンテンツカード、web アクションを、同時に異なる場所に配信し、各アクションに特定のコンテンツを含めることができます。[詳細情報](../building-journeys/journey-action.md#multi-action)

## キャンペーンオーケストレーション

**公開日**：2025年8月4日（PT）

Journey Optimizer に、ブランド主導のバッチキャンペーン専用の新しい機能である&#x200B;**キャンペーンオーケストレーション**&#x200B;が含まれるようになりました。このリリースでは、キャンペーンオーケストレーションキャンバスと強化されたデータモデリングが導入され、これらを連携することで、マーケターがパーソナライズされたクロスチャネルキャンペーンを計画、ターゲット、配信できます。

>[!IMPORTANT]
>
>キャンペーンオーケストレーションにアクセスするには、ライセンスに **Journey Optimizer - キャンペーンとジャーニー**&#x200B;または **Journey Optimizer - キャンペーン**&#x200B;パッケージのいずれかが含まれている必要があります。ライセンスを確認し、必要に応じて更新するには、アドビ担当者にお問い合わせください。

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

Adobe Journey Optimizer では、人物ベースのプロファイルにリンクされたリレーショナルエンティティ（製品、店舗、予約、契約など）がサポートされるようになりました。これにより、マルチディメンションのデータ構造をまたいでセグメント化とパーソナライゼーションが許可され、次のようなユースケースが可能になります。

* 予約、登録または契約ごとに 1 つのメッセージ

* 関連するエンティティ属性（例：製品カテゴリ、店舗の場所）に基づいてセグメント化

* 強化されたアドレサビリティ（例：エンティティに関連付けられたすべての既知の連絡先に送信）

### これが重要な理由

このリリースでは、マーケターは、柔軟なデータモデリングと専用のオーケストレーションエクスペリエンスを組み合わせることで、ブランド主導のオーディエンスベースのバッチマーケティングを完全に制御できます。リアルタイムのジャーニーからのバッチキャンペーンオーケストレーション専用に設計され、同時に高度なパーソナライゼーションとスケーラビリティを提供します。

### 詳細情報

詳しくは、[キャンペーンオーケストレーションドキュメント](../orchestrated/gs-orchestrated-campaigns.md)を参照してください。


