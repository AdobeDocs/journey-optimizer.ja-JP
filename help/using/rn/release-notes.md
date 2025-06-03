---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 348a1c0bfaca1abe7fd5705b36879af30da18e54
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 88%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 6 月の更新 {#25-6-rn}


<table>
<thead>
<tr>
<th><strong>実験の勝者を拡大</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実験の勝者をスケーリングすると、実験の勝者バリエーションを自動または手動でオーディエンス全体にロールアウトできます。 この機能により、最もパフォーマンスの高い処理が特定されると、手動で常に監視することなく、そのリーチと効果を最大化できます。</p>
<p>詳しくは、<a href="../content-management/content-experiment.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 6 月 2 日（PT）</p></td>
</tr>
</tbody>
</table>


## 2025年5月リリースノート {#25-5-rn}

<!--**Release date**: May 20-21, 2025-->

### 新機能 {#25-05-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>キャンペーンとジャーニーインベントリのカレンダー表示</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーとキャンペーンのリストでカレンダー表示を使用できるようになりました。これにより、すべてのジャーニーとキャンペーンのアクティベーションをそれぞれのリストで視覚化できます。</p>
<p>この変更は現在、一連の組織でのみ使用できます（使用制限あり）。 アクセスをリクエストするには、<a href="https://forms.cloud.microsoft/r/FC49afuJVi" target="_blank"> このフォーム </a> を使用します。</p>
<img src="assets/do-not-localize/calendar.gif">
<p>詳しくは、次の節を参照してください。<a href="../building-journeys/journey-ui.md"> ジャーニーの参照とフィルタリング </a>、<a href="../campaigns/modify-stop-campaign.md"> キャンペーンへのアクセス </a>。</p>
<p>公開日：2025年5月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Adobe Experience Manager コンテンツフラグメントの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Manager と Adobe Journey Optimizer の統合により、Journey Optimizer コンテンツ内で Adobe Experience Manager コンテンツフラグメントを簡単に使用できるようになりました。このシームレスな接続により、Journey Optimizer で AEM コンテンツに直接アクセスして使用することが簡単になります。</p>
<p>以前は限られた組織のセット（LA）で使用できましたが、この機能は次の機能強化を伴って GA になりました。エディターモードを使用して、プレースホルダーを定義し、フラグメント署名内でパーソナライゼーション値をマッピングできるようになりました。</p>
<ul>
<!--li>Create offers by directly selecting an AEM Content Fragment.</li>
<li>Define placeholders and map personalization values within the fragment signature using the Editor mode.</li-->
</ul>
</br>
<img src="assets/do-not-localize/content-fragment.gif">
<p>詳しくは、<a href="../integrations/aem-fragments.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Adobe Experience Manager Dynamic Media の統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dynamic Media アセットが Journey Optimizer で直接使用可能になり、アクセスできるようになりました。この統合により、次のことを実行できます。</p>
<ul>
<li>リアルタイム更新でアセットを一元管理。</li>
<li>幅や高さなどのアセット設定を即座に変更。</li>
<li>コンテンツを更新し、パーソナライゼーションフィールドを追加して、Dynamic Media テンプレートをカスタマイズ。</li>
</ul>
</br>
<img src="assets/do-not-localize/dynamic_media_template_html.gif">
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます（一般提供）。</p>
<p>詳しくは、<a href="../integrations/aem-dynamic.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>イベントトリガージャーニーの補足 ID</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プロファイル ID と、注文 ID、サブスクリプション ID、処方箋 ID などの別の識別子を使用してジャーニーをトリガーできるようになりました。これにより、同じプロファイルを同じジャーニーに複数回同時に含めることができます。これにより、各インスタンスがジャーニーを通じて独自のパスに従いながら、複数の注文やサブスクリプションを並行して管理するなどのシナリオが可能になります。</p>
<p>詳しくは、<a href="../building-journeys/supplemental-identifier.md">詳細なドキュメント</a>を参照してください。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コンテンツのバリエーションをシミュレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<!--p>Previously available in beta, content variations simulation is now generally available (GA). It allows you to preview different variations of your content using sample input data uploaded from a CSV or JSON file or added manually. All the attributes used in your content for personalization are automatically detected by the system and can be used for your tests to create multiple variants.</p-->
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます。この一般提供リリースでは、この機能に多言語コンテンツとコンテンツ実験のサポートが含まれるようになり、様々な言語や処理でのバリエーションをテストできるようになりました。さらに、（プロファイル属性に加えて）コンテキスト属性もサポートされるようになり、より動的で状況に応じたコンテンツテストが可能になりました。</p>
<img src="assets/do-not-localize/variants.gif">
<p>詳しくは、<a href="../test-approve/simulate-sample-input.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーディエンスを読み取りスケジュールのバッチセグメント化ジョブとの同期</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>バッチセグメント化完了後に毎日のジャーニー実行をトリガーできるようになりました。このオプションは、すべてのお客様に対して毎日スケジュールされているジャーニーで使用できるようになりました。これを使用すると、バッチセグメント化ジョブからのオーディエンスデータを待機する時間枠を最大 6 時間まで定義できます。これにより、ジャーニーは最新のデータで実行されるか、準備が整っていない場合はスキップされます。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます（一般提供）。</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
<p>詳しくは、<a href="../building-journeys/read-audience.md#schedule">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタム SMS プロバイダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、デフォルトのオプションに加えて、Sinch、Infobip、Twilio などの追加の SMS プロバイダーを設定できるようになりました。カスタム SMS プロバイダー設定を使用すると、サードパーティプロバイダーを直接統合し、動的メッセージ用の高度なペイロードカスタマイズを活用し、同意設定（オプトイン／オプトアウト）を管理してコンプライアンスを確保できます。</p>
<p>詳しくは、<a href="../sms/sms-configuration-custom.md">詳細なドキュメント</a>を参照してください。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます（一般提供）。</p>
<p>公開日：2025年5月20日（PT）</p>
</td>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールデザイナーのテーマ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>事前承認済みのテーマをすばやく適用して、すべてのメールにわたってブランドの一貫性を確保し、キャンペーン作成プロセスを高速化し、デザインチームへの依存を減らしながら高品質のメールを独自に作成できるようになりました。</p>
<p>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/themes.gif">
<p>詳しくは、<a href="../email/apply-email-themes.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月14日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>決定 - 新しい AI 式ビルダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しく改善されたインターフェイスから条件を定義および組み合わせることで、特定の決定ランキング式を作成できるようになりました。静的なオファーの優先度のみに依存するのではなく、ガイド付きインターフェイスを通じて、AI モデルスコア、オファーの優先度、プロファイル属性、オファー属性、コンテキストシグナルを組み合わせたカスタムランキング式を定義できます。</p>
<img src="assets/do-not-localize/formula-builder.gif">
<p>詳しくは、<a href="../experience-decisioning/exd-ranking-formulas.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月14日（PT）</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Conflict & prioritization</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In Journey Optimizer, managing the volume and timing of campaigns and journeys is essential to avoid overwhelming customers with too many interactions. Journey Optimizer now offers several tools for conflict management and prioritization - previously available only to limited-access (LA) organizations - that are now generally available (GA).</p>
<p>Previously released in Limited Availability, this capability is now available to all environments. With this General Availability release, the following enhancements have been introduced:</p>
<ul>
<li>Expanded Support: Conflict management tools now support both Unitary Journeys and Audience Qualification Journeys, in addition to Read audience journeys.</li>
<li>Improved Troubleshooting: Two new step event fields are now available in the Query Service, enabling you to analyze why a profile was rejected from a journey or campaign.</li>
<li>Enhanced Reporting: Reports now indicate which specific rule excluded a profile from a journey or campaign, providing greater transparency and actionable insights.</li></ul>
<img src="assets/do-not-localize/gif-conflict.gif">
<p>For more information, refer to the <a href="../conflict-prioritization/gs-conflict-prioritization.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->



### 機能強化 {#25-05-improv}

このリリースに含まれる機能強化を以下に示します。


* **サンドボックスコピーをサポートする新しいキャンペーンオブジェクト** – 公開日：2025 年 5 月 15 日（PT）

  パッケージの書き出しと読み込み機能を使用して、複数のサンドボックス間でキャンペーンをコピーすると、チャネル設定、実験のバリアントと設定、決定ポリシーと項目などの依存関係もコピーされるようになりました。[詳細情報](../configuration/copy-objects-to-sandbox.md)

  <!--* **Decisioning** - Availability date: May 16, 2025

    Decisioning objects can now be copied between sandboxes, streamlining testing and deployment workflows. [Read more](../configuration/copy-objects-to-sandbox.md#decisioning)-->

* **ランディングページのフォルダー** - 公開日：2025年5月9日（PT）

  ランディングページを簡単に管理することを目的に、フォルダーを使用して、より効果的に効率化された階層に整理できるようになりました。[詳細情報](../landing-pages/manage-lp.md)

* **ダイレクトメール：SFTP 接続用の SSH キーのサポート** - 公開日：2025年5月5日（PT）

  ダイレクトメールファイルのルーティング設定では、パスワード認証タイプの既存の SFTP に加えて、SSH キー認証を使用してダイレクトメールファイルを SFTP サーバーに書き出すことができるようになりました。[詳細情報](../direct-mail/direct-mail-configuration.md)

* **パーソナライゼーション用のピルのアクティベーション** - 公開日：2025年5月5日（PT）

  パーソナライゼーションエディターに新しい「ピル」ボタンが追加されました。有効にすると、プロファイルとコンテキスト属性がピルとして表示され、コードの読みやすさが向上します。[詳細情報](../personalization/personalization-build-expressions.md#options)

  >[!AVAILABILITY]
  >
  >この機能は、今後 30 日間にわたってすべての環境に段階的にロールアウトされます。

* Web チャネルでの **「URL にリダイレクト」のサポート** – 公開日：2025 年 5 月 20 日（PT）

  Journey Optimizer web チャネルでは、ビジュアルエディターで新しいバリエーションを作成するのではなく、訪問者を別の既存の URL にリダイレクトできるようになりました。この機能を使用すると、ページ内のいくつかの要素を変更するだけでなく、完全に異なる 2 つのページを比較する実験を実行できます。[詳細情報](../web/create-web.md#web-redirect-to-url)

* **テンプレートおよびフラグメントのフォルダー** – 公開日：2025 年 5 月 20 日（PT）

  フォルダーを使用すると、オブジェクトを構造化された階層に簡単かつ効果的に整理できます。以前は一連の組織（LA）に対して提供されていましたが、すべてのユーザー（GA）に対してコンテンツテンプレートとフラグメントを管理できるようになりました。詳しくは、[コンテンツテンプレート](../content-management/access-content-templates.md#folders)および[フラグメント](../content-management/manage-fragments.md#folders)の節を参照してください。

* **メールテンプレートでのクリックトラッキング** – 公開日：2025 年 5 月 20 日（PT）

  メールコンテンツの画像マップ内の `<area>` 要素のクリックの追跡が [!DNL Journey Optimizer] でネイティブにサポートされるようになりました。これは、画像マップ領域が標準のハイパーリンクと同じトラッキングラッピング、トラッキングデータおよび追加されたパラメーターを確実に受け取るようにするためです。[メッセージトラッキングの詳細情報](../email/message-tracking.md#manage-tracking)

<!--
* **Decisioning - Leverage Adobe Experience Platform datasets** 
  
  Journey Optimizer now allows you to leverage Adobe Experience Platform datasets in the following Decisioning objects: eligibility rules, ranking formulas, and capping rules.-->

* **キャンペーンリストの右側のパネル** – 公開日：2025 年 5 月 20 日（PT）

  キャンペーンリストでキャンペーンを選択すると、詳細を表示するパネルが開くようになりました。

<!--* **Form fields in code-based experience content**

  In content templates, you can now define specific JSON or HTML fields which enable non-technical users to easily edit content in code-based experiences without the need to manipulate code.

* **Decision item attribute support for decisioning rules**
  
  You can now leverage decision item attributes to create decisioning rules.

* **Subdomains - 'Custom delegation' method**  
  In addition to the full delegation and the CNAME method, a new subdomain configuration method is now available: the Custom delegation method, which enables you to fully own controlling and maintaining all aspects of DNS that are required for delivering, rendering, and tracking messages.
  -->

