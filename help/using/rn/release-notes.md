---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
TQID: https://experienceleague.adobe.com/YJKQFYUi8Kw7yZZKm8blcM-1G9uYsqcsEsopH0hOMhA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a7b2bfc5-be71-4740-b371-76fa6be8df02
subfeature_v2: id: eac3bd2c-b027-4dfa-80d2-0bd752ae4794id: e437f8db-d1f7-44c0-bdc0-b0a361adc4c0id: c4e1378f-bb85-43a2-8b7c-1623ad3b14b5
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 02ce60020012083981c5599789b9e86804190627
workflow-type: tm+mt
source-wordcount: 3006
ht-degree: 86%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。 これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。 このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。 このモデルにより、リリースノートは毎月のリリースの間に更新されます。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

>[!NOTE]
>
>これらのリリースノートに記載されている機能には、各変更がお客様の環境でアクセス可能になるタイミングを示す&#x200B;**公開日**&#x200B;が含まれています。 **近日リリース予定**&#x200B;のアコーディオンへのエントリは、今後数日または数週間以内に予定されています。 次の節の情報は変更される場合があります。


## 26年6月の更新 {#june-26-updates}

<table>
<thead>
<tr>
<th><strong>ジャーニーシミュレーション（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーをシミュレーションに設定できます。 このモードでは、シミュレートされたユーザーを使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。 </p>
<p>この機能は、ジャーニーシミュレーションは限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました。 この一般提供リリースでは、Journey エージェントを使用して、シミュレーションユーザーとイベントをシミュレーションメニューで直接生成できるようになりました。</p>
<p><img src="assets/do-not-localize/journey-simulation.gif"></p>
<p>詳しくは、<a href="../building-journeys/simulate-journey-gs.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化 – ターゲティング（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> アクティビティの最適化</strong>では、<strong> ターゲティングルール </strong>がサポートされるようになりました。これにより、オーディエンスセグメントまたはプロファイル属性に基づいて、顧客が特定のジャーニーパスの対象として選定するために満たす必要がある特定の基準を定義できます。</p>
<p>顧客がランダムにパスに割り当てられる実験とは異なり、ターゲティングでは決定論的ロジックを使用して、適切なオーディエンスまたは顧客プロファイルが目的のパスにルーティングされるようにします。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/optimize.gif"></p>
<p>詳しくは、<a href="../building-journeys/path-targeting.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月8日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーフラグメント（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer で<strong>ジャーニーフラグメント</strong>を作成できるようになりました。 ジャーニーフラグメントは、一度作成すればサンドボックスをまたいで任意のジャーニーにドロップできる、再利用可能なジャーニーノードのセットです。 実施要件の確認、優先チャネルのルーティングロジック、ウェルカムシーケンスなど、フラグメントを使用することで、チームは毎回同じロジックをゼロから再作成することなく、より迅速に作業を進め、一貫性を維持できます。</p>
<p>作成したフラグメントは、専用の<strong>フラグメント在庫</strong>に保存され、<strong>ジャーニーフラグメント</strong>アクティビティを使用して任意のジャーニーに挿入できます。</p>
<p>以前は制限付き可用性で利用可能でしたが、この機能はすべての顧客で一般に利用可能になりました。 ジャーニーフラグメントは<strong> サンドボックスツール </strong>もサポートしており、サンドボックス間でフラグメントをパッケージ化および書き出すことができます。</p>
<p>詳しくは、<a href="../building-journeys/journey-fragments.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>コンテンツのバリエーションをシミュレート：エクスペリエンスの更新とAI バリエーションの生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>2つの更新プログラムが、<strong> コンテンツをシミュレート </strong> ワークフローで利用できるようになりました。</p>
<ul>
<li><strong>新しいデフォルトパス </strong> – 「<strong> コンテンツをシミュレート </strong>」をクリックすると、デフォルトで<strong> コンテンツのバリエーションをシミュレート </strong> エクスペリエンスが開くようになりました。 1つの画面から、手動またはCSV/JSON ファイルからサンプル入力を追加し、シミュレートされたユーザーを再利用し、レンダリングをプレビューし、プルーフを送信できます。 Adobe Experience Platform テストプロファイルを使用してプレビューするには、テストプロファイルデータを使用してプルーフを送信するか、メール受信トレイのレンダリングとスパムレポートを確認するには、<strong> コンテンツをシミュレート </strong>をクリックし、ドロップダウンから<strong> コンテンツをシミュレート（AEP プロファイル） </strong>を選択します。</li>
<li><strong>AIで生成されたコンテンツのバリエーション </strong> — <strong> コンテンツのバリエーションをシミュレート </strong> エクスペリエンスで、<strong>生成</strong>をクリックすると、AIを使用してコンテンツのバリエーションを自動的に作成できます。 メッセージの分析、パーソナライゼーションフィールドと条件付き分岐の検出、現実的な値の入力を可能にし、あらゆるバリエーションを手作業で作成することなくレンダリングを検証できます。</li>
</ul>
<p>詳しくは、<a href="../test-approve/simulate-sample-input.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ダイレクトメールチャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ダイレクトメールジャーニーとキャンペーンに決定ポリシーを追加できるようになりました。 決定ポリシーは、各オーディエンスメンバーに最適なコンテンツを動的に返すことを目的に、決定エンジンを活用するオファーのコンテナです。 また、ダイレクトメール決定は、バッチ決定のユースケースもサポートし、特定の Adobe Experience Platform オーディエンスのすべてのプロファイルに対応するオファー項目をエクスポートできます。 </p>
<p><img src="assets/do-not-localize/exd-dm.gif"></p>
<p>詳しくは、<a href="../experience-decisioning/use-decision-policy.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー式用 AI アシスタント（パブリックベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、ジャーニーの高度な式エディターで機能して、自然言語プロンプトを有効な式と条件付きロジックに変換するようになりました。 作成したい式を説明すると、AI アシスタントがすぐに適用できる使いやすいコードを生成したり、フォローアッププロンプトを通じて調整したりできます。</p>
<p>この機能は、パブリックベータ版としてすべてのユーザーが使用できます。</p>
<p><img src="assets/do-not-localize/expression-assistant.gif"></p>
<p>詳しくは、<a href="../building-journeys/expression/expression-agent.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月3日（PT）</p> 
</td>
</tr>
</tbody>
</table>

* [!BADGE 重要]{type=Informative} **AJO Message Feedback Event Dataset moving to batch ingestion** - **AJO Message Feedback Event Dataset**&#x200B;は、ストリーミング取り込みからバッチ取り込みに移行しています。 その結果、このデータセットに対して最大2時間のデータ待ち時間が期待されます。 Customer Journey Analyticsでレポートを作成している場合や、このデータセットを使用してクエリを実行している場合は、今後この遅延が増加することを考慮してください。 [詳細情報](../data/datasets-query-examples.md#message-feedback-event-dataset)

  ご利用いただけます：2026年6月10日（PT）

* **非繰り返しの読み取りオーディエンスジャーニー**&#x200B;の自動停止 – 繰り返しの&#x200B;**読み取りオーディエンス** ジャーニーが、最後にアクティブなプロファイルが終了すると、自動的に&#x200B;**停止** ステータスに移行するようになりました。 以前は、これらのジャーニーは、プロファイルが流れなくなった場合でも、91 日間のグローバルタイムアウトが期限切れになるまで&#x200B;**ライブ**&#x200B;のままになっていました。 この機能強化により、ジャーニーステータスは完了するとすぐに実際の実行状態を反映するので、手動介入なしでジャーニーインベントリの正確性を維持できます。

  この動作は、待機ノード、反応ノード、イベントトリガーのトランジションなど、待機時間を発生させるノードを含むジャーニーには適用されません。 これらのジャーニーは、標準の 91 日間のグローバルタイムアウトの対象のままです。 [詳細情報](../building-journeys/end-journey.md#auto-stop-non-recurring)

  ご利用いただけます：2026年6月9日（PT）

* **カスタムアクションでの証明書ベースのカスタム認証** - カスタムアクションで、証明書ベースのカスタム認証がサポートされるようになりました。 Journey Optimizer は、カスタム認証設定に `subType: "certificateCredential"` を追加することで、アドビが管理する証明書を使用して JWT クライアントアサーションに署名し、アクセストークンと交換します。クライアント秘密鍵は不要です。 Microsoft Entra IDなど、証明書ベースのID確認を強制するエンタープライズ API向けに設計されています。 [詳細情報](../datasource/external-data-sources.md#certificate-credential)

  ご利用いただけます：2026年6月4日（PT）


* **キャンペーンライフサイクルイベントに関する顧客アラート** - 新しいシステムアラートにより、アクションおよび API トリガーキャンペーンの主要なライフサイクルイベントが通知されるようになりました。 サンドボックスレベルで登録してください。 [詳細情報](../reports/alerts.md)

  公開日：2026年6月1日（PT）

* **URL パラメーターの暗号化** - メールメッセージに追加されたトラッキングリンクやランディングページリンクの URL パラメーターを暗号化できるようになりました。 これにより、機密性の高いパラメーターデータのセキュリティレイヤーが追加されます。 この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。 [詳細情報](../personalization/url-parameter-encryption.md)

  公開日：2026年6月1日（PT）

* **キーレジストリの新しい権限** - URL パラメーターの暗号化に必要なキーにアクセスして管理するには、新しい 2 つの権限（**キーレジストリを管理**&#x200B;と&#x200B;**キーレジストリを表示**）が必要になりました。 [詳細情報](../administration/high-low-permissions.md#administration-permissions)

  公開日：2026年6月1日（PT）

* **外部オーディエンス向けの補助識別子サポート** - ジャーニーの補助識別子は、CSVファイルからインポートされたオーディエンスや、連合オーディエンス構成で作成されたオーディエンスなど、外部オーディエンスに対してサポートされるようになりました。 オーディエンスから ID 以外の属性またはユーザー ID 以外の属性を補助 ID として指定できます。スキーマのラベル付けは不要です。 [詳細情報](../building-journeys/supplemental-identifier.md)

  ご利用いただけます：2026年6月11日（PT）

<!--
+++ Coming soon — **Information below is subject to change.**

* **Override the default execution field in campaigns** - Previously available at the journey level, you can now override the default execution field set globally for your Email, SMS and WhatsApp deliveries in the campaign parameters.

  Availability date: Early June, 2026

+++
-->

## 2026年5月リリースノート {#may-26-rn}

### ジャーニー {#may-26-journeys}

このリリースでは、ジャーニーに次の機能と機能強化が追加されました。 また、追加の変更は今後数日または数週間以内に予定されています。

<table>
<thead>
<tr>
<th><strong>ジャーニーフラグメント（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer で<strong>ジャーニーフラグメント</strong>を作成できるようになりました。 ジャーニーフラグメントは、一度作成すればサンドボックスをまたいで任意のジャーニーにドロップできる、再利用可能なジャーニーノードのセットです。 実施要件の確認、優先チャネルのルーティングロジック、ウェルカムシーケンスなど、フラグメントを使用することで、チームは毎回同じロジックをゼロから再作成することなく、より迅速に作業を進め、一貫性を維持できます。</p>
<p>作成したフラグメントは、専用の<strong>フラグメント在庫</strong>に保存され、<strong>ジャーニーフラグメント</strong>アクティビティを使用して任意のジャーニーに挿入できます。</p>
<!--<p><img src="assets/do-not-localize/journey-fragments.gif"></p>-->
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、 <a href="../building-journeys/journey-fragments.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月13日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーシミュレーション（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを<strong>シミュレーション</strong>に設定できます。 このモードを使用すると、<strong>シミュレートされたユーザー</strong>を使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。</p>
<p>この機能は現在、基本機能を備えた限定提供として、すべてのお客様にご利用いただけます。</p>
<p><img src="assets/do-not-localize/simulate-user.gif"></p>
<p>詳しくは、<a href="../building-journeys/simulate-journey.md">詳細ドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Journey path optimization – Targeting (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Use the new <strong>Optimize</strong> node to target specific audiences to determine the best path to meet your business-centric KPIs.</p>
<p>This tool allows you to develop more effective marketing campaigns that are more likely to resonate at the 1:1 level, improve marketing personalization efforts for customers and enhance critical customer engagement KPIs, such as conversions and revenue.</p>
<p>Previously available in Limited Availability, this capability is now available to all environments.</p>
<p>Availability date: June 1, 2026</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Arbitration – ranking formulas (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use formulas to automatically boost journey priority scores based on customer profile attributes and contextual factors, ensuring customers enter the most relevant journeys.</p>
<p>Previously available in Limited Availability, this capability is now available to all environments.</p>
<p>Availability date: June 1, 2026</p>
</td>
</tr>
</tbody>
</table>
-->

### オーケストレーションキャンペーン {#may-26-oc}

このリリースでは、オーケストレーションキャンペーンに次の機能と機能強化が追加されました。 また、追加の変更は今後数日または数週間以内に予定されています。

<table>
<thead>
<tr>
<th><strong>連結されたオーケストレーションキャンペーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションキャンペーンは、別のオーケストレーションキャンペーンの<strong>終了アクティビティ</strong>から直接トリガーすることで、相互にリンクできるようになりました。</p>
<p>これにより、複雑なオーケストレーションロジックをより小さく再利用可能なフローに分割でき、毎回再作成する代わりに、複数の親キャンペーンから呼び出すことができます。 実行時に渡されるペイロードは、ダウンストリームキャンペーンでセグメント化とパーソナライゼーションに使用できるので、リンクされた各キャンペーンは、受信したコンテキストに基づいて動作できます。</p>
<p><img src="assets/do-not-localize/oc-trigger.gif"></p>
<p>詳しくは、<a href="../orchestrated/trigger-orchestrated-campaign.md#signal-end">詳細ドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **エンリッチメントアクティビティでリンクを追加** - オーケストレーションキャンペーンのエンリッチメントアクティビティで、「リンクを追加」機能が使用できるようになりました。 これにより、作業用テーブルデータと既存のデータベーステーブルとの間に直接的な関係を作成できます。

  公開日：2026年5月20日（PT）

<!--
+++ Coming soon — **Information below is subject to change.**

The following orchestrated campaign capability is expected in the upcoming days or weeks.

<table>
<thead>
<tr>
<th><strong>File-based targeting for orchestrated campaigns (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Orchestrated campaigns now support loading a CSV or TXT file directly into the campaign canvas as the targeting audience, without first ingesting the file into Adobe Experience Platform. The file data is consumed at execution time and is not persisted as an Adobe Experience Platform dataset. During file setup, you can define column mappings, data types, NULL handling, and per-column error policies. This supports ad-hoc sends or partner list campaigns where building a full ingestion pipeline is not practical.</p>
<p>This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<p>Availability date: June 1, 2026</p>
</td>
</tr>
</tbody>
</table>

* **Loop-based personalization for relational data** - The personalization editor now supports a Loop block that iterates over relational collections, such as orders, accounts, or bookings, and renders one content block per record inside a single email or SMS. Collections are configured through the data picker using personalization tokens, with no expression writing required.

  Availability date: Early June, 2026

* **Personalize email sender details per recipient and campaign** - Orchestrated campaigns now support personalization of email header fields, including From name, From address, and Reply-To, using profile attributes or relational data. This allows sender details to reflect the relevant advisor, location, or branch for each recipient, rather than routing all sends through a single corporate address.

  Header values can be set at the channel level and overridden per campaign using contextual data for more precise control.

  Availability date: Early June, 2026

+++
-->

### 決定 {#may-26-decisioning}

このリリースでは、決定に次の機能と機能強化が追加されました。 また、追加の変更は今後数日または数週間以内に予定されています。

<table>
<thead>
<tr>
<th><strong>決定ルールとランキング式 AI 最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>[!DNL Adobe Journey Optimizer] は、AI を使用して、簡素化できる決定ルールとランキング式を検出するようになりました。 在庫では、AI が最適化の機会を特定したルールには赤いインジケーターが表示されます。 インジケーターをクリックすると、AI が提案したバージョンと共に元の式が表示されます。 そこからファイルをダウンロードして、各バージョンでシミュレートされたプロファイルが評価される仕組みを確認し、同一に動作することを確認してから、式を最適化された式に置き換えることができます。</p>
<p><img src="assets/do-not-localize/rule-ai.gif"></p>
<p>詳しくは、 <a href="../start/ai-features.md#decisioning-optimization">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **決定での Adobe Experience Manager コンテンツフラグメント** - Adobe Experience Manager コンテンツフラグメントを決定の決定項目にマッピングし、決定ポリシー内で活用することで、適切なフラグメントを適切な顧客に適切なタイミングで配信できるようになりました。 [詳細情報](../integrations/aem-fragments.md#aem-decisioning)

  この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

  公開日：2026年5月20日（PT）

* **キャンペーンの概要からの決定ポリシーの詳細** - キャンペーンの概要ページから、キャンペーンを複製または編集することなく、選択戦略、決定項目、フォールバックオファーなど、各決定ポリシーの完全な構造を確認できるようになりました。 また、JSON 形式の概要をクリップボードにコピーして、アドビサポートまたはエンジニアリングチームにトラブルシューティングを依頼することもできます。 [詳細情報](../experience-decisioning/use-decision-policy.md#decision-policy-summary)

  公開日：2026年5月20日（PT）

* **移行ワークフローの決定に関する API** - 依存関係分析および移行ワークフローを作成する API 契約が更新されました。リクエスト URL に&#x200B;**クエリパラメーター**&#x200B;として **`request-level`**（`sandbox`、`offer` または `decision`）を渡します。 リクエストレベルは、JSON 本文に含めて送信しないでください。 [詳細情報](../experience-decisioning/decisioning-migration-api.md)

  公開日：2026年5月6日（PT）

### メールチャネル {#may-26-email}

このリリースでは、メールチャネルに次の機能と機能強化が追加されました。 また、追加の変更は今後数日または数週間以内に予定されています。

<table>
<thead>
<tr>
<th><strong>E メールデザイナーのディープリンク</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>E メールデザイナーの専用オプションを使用して、メールコンテンツにディープリンクを追加できるようになりました。 これにより、ユーザーはブラウザーやアプリストアにリダイレクトされずに、アプリ内の適切なコンテンツに直接アクセスでき、コンテキストとエンゲージメントが維持されます。</p>
<p>ディープリンクオプションは、すべてのお客様が使用できますが、ディープリンクは、必要な設定とモバイルアプリの実装手順を完了した場合にのみ機能します。</p>
<p><img src="assets/do-not-localize/deeplinks.gif"></p>
<p>詳しくは、<a href="../email/deeplinks.md">詳細ドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月12日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **フラグメントでの継承の違反の制限** - フラグメントを作成または編集する際に、メールで使用される場合にフラグメントを変更できるかどうかを選択できるようになりました。 フラグメントをロックすることで、表示されるすべての場所で同期が維持され、ブランド標準やコンプライアンス要件に違反する可能性のあるローカル編集を防ぐことができます。 この設定は後で更新でき、今後の使用に適用されます。 [詳細情報](../content-management/create-fragments.md#lock-visual-fragment)

  公開日：2026年5月21日（PT）

### モバイルメッセージ（SMS、MMS、RCS） {#may-26-mobile}

このリリースでは、モバイルメッセージに次の機能と機能強化が追加されました。

<table>
<thead>
<tr>
<th><strong>新しいモバイルメッセージチャネルと強化された RCS メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer では、SMS、MMS、RCS が単一の<strong>モバイルメッセージ</strong>アクションに統合され、すべてのモバイルメッセージタイプを 1 か所から簡単に管理できるようになりました。 この更新の一環として、新しいネイティブなオーサリングエクスペリエンスを通じて、画像、カルーセル、推奨アクションなどのリッチメディア RCS メッセージを Journey Optimizer で直接作成できるようになりました。</p>
<p>詳しくは、 <a href="../mobile/get-started-mobile.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **文字カウント** - Adobe Journey Optimizer では、文字カウントを使用して SMS メッセージの長さをリアルタイムで監視できるようになりました。 メッセージが複数のセグメントに分割されるタイミングを確認できるので、書式設定をより適切に管理し、送信コストの予期しない増加を回避できます。 [詳細情報](../mobile/create-mobile-message.md)

* **カスタムデータセットに対する SMS インバウンド** - **SMS API 資格情報**&#x200B;で、デフォルトのトラッキングデータセットだけでなく、選択した&#x200B;**カスタムのプロファイル対応エクスペリエンスイベントデータセット**&#x200B;に&#x200B;**インバウンド SMS** をルーティングします。 [詳細情報](../mobile/mobile-webhook.md)

* **Webhook インターフェイスの機能強化** - SMS webhook を設定する際に、ユーザーインターフェイスに実用的な例を含む組み込みの設定ガイドが含まれるようになりました。これにより、設定フローを離れることなく、プロバイダーのペイロードを調整し、問題のトラブルシューティングを行うことが簡単になります。 [詳細情報](../mobile/mobile-webhook.md)

* **SMS コンテンツのディープリンク** - URL ヘルパー機能を使用して、SMS コンテンツにディープリンクを追加できるようになりました。 これにより、必要な設定とモバイルアプリの実装手順を完了した場合に、受信者は web ブラウザーやアプリストアを通じてルーティングすることなく、目的のアプリ内コンテンツに直接移動できます。 [詳細情報](../email/deeplinks.md)

### WhatsApp チャネル {#may-26-whatsapp}

このリリースでは、WhatsApp チャネルに次の機能強化が追加されました。

* **WhatsApp ボタンのサポートとトラッキング** - WhatsApp テンプレートは、**クイック返信**、**コールトゥアクション - URL**、**コールトゥアクション - 電話番号**&#x200B;をサポートするようになりました。**コードをコピー**&#x200B;はサポートされていません。 Journey Optimizer は、サポートされているボタンを送信し、他のチャネルのレポートと共にインタラクションを追跡します。

* **WhatsApp チャネルコンテキストデータ** - Journey Optimizer は、WhatsApp チャネルから返される追加のインタラクションデータをキャプチャし、**AJO EmailTrackingExperienceEvent データセット**&#x200B;の `whatsAppChannelContext` フィールドグループに保存するようになりました。 [詳細情報](../whatsapp/send-whatsapp.md#whatsapp-channel-context)

  +++ 次のフィールドがキャプチャされ、オーディエンスの作成や WhatsApp エンゲージメントの分析に使用できます。

   * **`messageType`** - WhatsApp メッセージタイプ（例：`templateBased`、`response`）
   * **`inboundMessage`** - インバウンド返信コンテンツ（例：`stop`、`start`、`subscribe`）
   * **`inboundNumber`** - インバウンドメッセージを受信した送信者 ID
   * **`channelType`** - チャネルカテゴリ （`Utility`、`Marketing` または `Promotional`）
   * **`profileNumber`** - インバウンドメッセージを受信した電話番号
   * **`origTimestamp`** - Meta／WhatsApp の元のタイムスタンプ
   * **`status`** - 標準化されたプロバイダーのフィードバック （`sent`、`delivered`、`bounce`、`error`、`delay`、`duplicate`、`denylist`、`exclude` または `unknown`）と生のプロバイダーのステータスメッセージを含む配信ステータス
   * **`reactionEvent`** - ユーザー応答のコンテンツ：反応の場合は絵文字、特定のメッセージへの返信の場合はメッセージテキスト
   * **`reactionMessageID`** - 応答する元のメッセージの ID
   * **`reactionActionName`** – 応答アクションのタイプ（`react`、`unreact` または `reply`）
   * **`interactiveSelectedTitle`** - WhatsApp インタラクティブメッセージからユーザーが選択したタイトル
   * **`interactiveType`** - インタラクティブ メッセージタイプ（`list reply`、`button reply` または `button`）
   * **`interactiveSelectedDescription`** - 選択した WhatsApp インタラクティブオプションの説明
   * **`interactiveSelectedID`** - WhatsApp から選択したオプションの ID

  +++

### コンテンツと統合 {#may-26-content}

このリリースでは、コンテンツ管理と統合に次の機能と機能強化が追加されました。

<table>
<thead>
<tr>
<th><strong>コンテンツアドバイザーセレクター</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer は、Experience Manager Assets とコンテンツフラグメントの両方を選択するための統合モーダルである<strong>コンテンツアドバイザーセレクター</strong>を使用するようになりました。 新しいセレクターには、以下が含まれます。</p>
<ul>
<li><strong>参照、検索、フィルタリング</strong>：すべてのアセットとフラグメントをまたいで実行できます。</li>
<li><strong>AI セマンティック検索</strong>：例えば、「山の中のコーヒー」のように、必要な内容をプレーンな言葉で記述することで、単なるテキスト一致ではなく、意味とコンテンツに基づいて文脈に沿って関連性の高いアセットを表示できます。 また、多言語クエリもサポートされています。</li>
<li><strong>概要のアップロード</strong>：マーケティングの概要をアップロードすると、そのコンテンツと要件に基づいてキャンペーンのコンテキストに一致するアセットが自動的に表示されます。</li>
<li><strong>Dynamic Media レンディション</strong>：セレクターから離れることなく、動的アセットの画像レンディションを選択して適用できます。</li>
</ul>
<p>詳しくは、 <a href="../integrations/aem-content-advisor.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月19日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><b>統合</b>機能を使用すると、サードパーティのデータソースを Adobe Journey Optimizer に直接接続できます。 この機能により、外部データと<b>構成可能なコンテンツ</b>の取り込み方法が簡素化され、あらゆるチャネルをまたいで、パーソナライズされた動的なメッセージを容易に配信できるようになります。</p>
<p>この機能は、以前はベータ版でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../integrations/integrations.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年5月4日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **アセットセレクターでの組織間のリポジトリへのアクセス** - Adobe Experience Manager アセットセレクター内で、複数の組織をまたいでリポジトリからアセットをシームレスに選択できるようになりました。

<!--
+++ Coming soon — **Information below is subject to change.**

* **Message Feedback Event Dataset moving to batch ingestion** - The `AJO Message Feedback Event Dataset` is transitioning from streaming to batch ingestion mode. This change ensures that data ingestion does not exceed streaming ingestion limits. If you use this dataset in Customer Journey Analytics reports or run queries against it, expect an increase in data latency of up to 2 hours going forward.

  Availability date: June 1, 2026

+++
-->

### 使いやすさの向上 {#may-26-usability}

2026年5月には、次の使いやすさの向上もリリースされました。

#### リスト

* **一括アクション** - **キャンペーン**、**フラグメント**、**テンプレート**&#x200B;のリストで複数の項目を一度に選択し、単一のアクションバーから一括操作を実行できるようになりました。これには、項目のパッケージへの追加、フォルダーへの移動、タグの編集、アクセス権の管理、アーカイブまたは削除が含まれます。 [詳細情報](../start/search-filter-categorize.md#bulk-actions)

  ![](../start/assets/bulk-actions-campaigns.png)

* **並べ替えと列のサイズ変更** - **キャンペーン**、**フラグメント**、**テンプレート**&#x200B;のリストで、任意の列ヘッダーをクリックすることで並べ替えがサポートされるようになりました。 また、キャンペーンフォルダー表示では、**[!UICONTROL 優先度]**&#x200B;と&#x200B;**[!UICONTROL チャネル設定]**&#x200B;による並べ替えとフィルタリングも使用できます。 **フラグメント**&#x200B;と&#x200B;**テンプレート**&#x200B;のリストの列幅もサイズ変更できます。列の境界線をドラッグして、最も関心のあるデータに合わせて調整します。 [詳細情報](../start/search-filter-categorize.md#filter-lists)

#### コンテンツのオーサリング

* **インラインプロファイル属性編集** - E メールデザイナーのインラインプロファイル属性編集は、4月に初めてリリースされました。 5月のリリースの一環として、この機能は AI アシスタントから切り離され、プッシュチャネルエディターに拡張されました。 [詳細情報](../personalization/personalize.md#inline-personalization)

  ![](../personalization/assets/inline-profile-attributes.png)

* **プッシュチャネルエディターのリンク URL ツールチップ** - リンクまたはメディアフィールドの URL が長すぎて表示できない場合、フィールドの横にツールチップアイコンが常に表示されます。アイコンにポインタを合わせると、完全な URL が表示されます。 [詳細情報](../push/design-push.md#on-click-behavior)

  ![](../rn/assets/do-not-localize/push-link-tooltip.png)

<!--
#### Simulation & Preview

* **Redesigned preview experience** - The content preview screen has been redesigned with a side-by-side layout that lets you compare how your content renders across multiple profiles at a glance, enabling quicker and more confident reviews before sending. [Learn more](../test-approve/simulate-sample-input.md#preview)

  ![](../test-approve/assets/simulation-preview-redesign.png)
-->

<!--
+++ Coming soon — **Information below is subject to change.**

* **Folders for journeys and campaigns** - You can now organize your journeys and campaigns into folders to improve navigation and management in the interface.

  Availability date: Early June, 2026

+++
-->

