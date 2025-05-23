---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 6628f1a9700f126e23c8e6c21b24973f239805c0
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 36%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 5 月のリリースノート {#25-5-rn}

**リリース日**:2025 年 5 月 20～21 日（PT）

### 新機能 {#25-05-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>Adobe Experience Manager コンテンツフラグメントの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience ManagerとJourney Optimizerの統合により、Adobe Journey Optimizer コンテンツ内でAdobe Experience Manager コンテンツフラグメントを簡単に使用できるようになりました。 このシームレスな接続により、Journey Optimizer内のAEM コンテンツに直接アクセスして使用しやすくなります。</p>
<p>以前は一部の組織（LA）で利用できましたが、この機能は現在は GA であり、次の機能強化が行われています。</p>
<ul>
<!--li>Create offers by directly selecting an AEM Content Fragment.</li-->
<li>エディターモードを使用して、プレースホルダーを定義し、フラグメント署名内のパーソナライゼーション値をマッピングします。</li>
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
<th><strong>Adobe Experience Manager Dynamic Media との統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dynamic Media アセットが Journey Optimizer で直接使用可能になり、アクセスできるようになりました。この統合により、次のことを実行できます。</p>
<ul>
<li>リアルタイムのアップデートでアセットを一元管理します。</li>
<li>幅や高さなどのアセット設定を即座に変更します。</li>
<li>コンテンツを更新し、パーソナライゼーションフィールドを追加して、Dynamic Media テンプレートをカスタマイズします。</li>
</ul>
</br>
<img src="assets/do-not-localize/dynamic_media_template_html.gif">
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（一般提供）。</p>
<p>詳しくは、<a href="../integrations/aem-dynamic.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールDesignerのテーマ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>事前承認済みのテーマをすばやく適用して、すべてのメールでブランドの一貫性を確保し、キャンペーンの作成プロセスを迅速化し、高品質のメールを独自に作成できると同時に、デザインチームへの依存を軽減することができます。</p>
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
<th><strong>意思決定 – 新しい AI 式ビルダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しく改善されたインターフェイスから条件を定義および組み合わせることで、特定の決定ランキング式を作成できるようになりました。静的なオファーの優先度のみに依存するのではなく、ガイド付きインターフェイスを介して AI モデルスコア、オファーの優先度、プロファイル属性、オファー属性、コンテキストシグナルを組み合わせるカスタムランキング式を定義できます。</p>
<img src="assets/do-not-localize/formula-builder.gif">
<p>詳しくは、<a href="../experience-decisioning/exd-ranking-formulas.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月14日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーディエンスを読み取りスケジュールをバッチセグメント化ジョブと同期</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>バッチセグメント化の完了後に毎日のジャーニー実行をトリガーできるようになりました。 すべてのお客様が、毎日スケジュールされるジャーニーでこのオプションを利用できるようになりました。 これにより、最大 6 時間の時間枠を定義して、バッチセグメント化ジョブからのオーディエンスデータを待機し、ジャーニーが最新のデータで実行されるか、準備ができていない場合はスキップされるようにします。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（一般提供）。</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
<p>詳しくは、<a href="../building-journeys/read-audience.md#schedule">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Calendar View for Campaign and Journey inventory</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A calendar view is now available in the journeys and campaigns lists. It allows you to visualize all journeys and campaigns activations in the respective lists.</p>
<p>This change is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<img src="assets/do-not-localize/calendar.gif">
<p>For more information, refer to these sections: <a href="../building-journeys/journey-ui.md">Browse & filter your journeys</a>, <a href="../campaigns/modify-stop-campaign.md">Access campaigns</a>.</p>
</td>
</tr>
</tbody>
</table>-->

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

<table>
<thead>
<tr>
<th><strong>コンテンツのバリエーションをシミュレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はベータ版で提供されていましたが、コンテンツバリエーションのシミュレーションが一般提供（GA）されるようになりました。これを使用すると、CSV ファイルまたは JSON ファイルからアップロードした、または手動で追加したサンプル入力データを使用して、コンテンツの様々なバリエーションをプレビューできます。パーソナライゼーションのコンテンツで使用されるすべての属性は、システムによって自動的に検出され、複数のバリアントを作成するテストに使用できます。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を使用できます。 この一般提供リリースで、この機能に多言語コンテンツとコンテンツ実験のサポートが含まれるようになり、様々な言語や処理でのバリエーションをテストできます。 さらに、（プロファイル属性に加えて）コンテキスト属性もサポートされるようになり、より動的で状況に応じたコンテンツテストが可能になりました。</p>
<img src="assets/do-not-localize/variants.gif">
<p>詳しくは、<a href="../test-approve/simulate-sample-input.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年5月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Scale your Experimentation winner</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Scale the Winner enables you to automatically or manually roll out the winning variation of an experiment to your full audience. This feature ensures that, once a top performer is identified, you can maximize its reach and effectiveness without constant manual oversight.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>カスタム SMS プロバイダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、デフォルトのオプション（Sinch、Infobip および Twilio）以外にも、追加の SMS プロバイダーを設定できるようになりました。 カスタムの SMS プロバイダー設定を使用すると、サードパーティプロバイダーを直接統合し、動的メッセージ用の高度なペイロードカスタマイズを活用し、同意設定（オプトイン/オプトアウト）を管理してコンプライアンスを確保できます。</p>
<p>詳しくは、<a href="../sms/sms-configuration-custom.md">詳細なドキュメント</a>を参照してください。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（一般提供）。</p></td>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Supplemental ID for event-triggered journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now trigger journeys using a profile ID along with another identifier, such as an order ID, subscription ID, or prescription ID, allowing the same profile to be in the same journey multiple times at once. This enables scenarios like managing multiple orders or subscriptions in parallel, with each instance following its own path through the journey.</p>
<p>This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化 {#25-05-improv}

このリリースに含まれる機能強化を以下に示します。


* **サンドボックスコピーで新規オブジェクトがサポートされるようになりました**

   * **キャンペーン** – 公開日：2025 年 5 月 15 日（PT）

     パッケージのエクスポートおよびインポート機能を使用して、複数のサンドボックス間でキャンペーンをコピーする場合、チャネル設定、実験のバリアントと設定、決定ポリシーと項目の依存関係もコピーされるようになりました。 [詳細情報](../configuration/copy-objects-to-sandbox.md)

   * **決定** – 公開日：2025 年 5 月 16 日（PT）

     サンドボックス間で決定オブジェクトをコピーできるようになり、テストおよびデプロイメントワークフローを合理化します。 [詳細情報](../configuration/copy-objects-to-sandbox.md#decisioning)

* **ランディングページのフォルダー** – 公開日：2025 年 5 月 9 日（PT）

  ランディングページを簡単に管理するために、フォルダーを使用して、より効果的に構造化階層に整理できるようになりました。 [詳細情報](../landing-pages/manage-lp.md)

* **ダイレクトメール：SFTP 接続用の SSH キーのサポート** – 公開日：2025 年 5 月 5 日（PT）

  ダイレクトメールファイルのルーティング設定で、パスワード認証タイプの既存の SFTP に加えて、SSH キー認証を使用してダイレクトメールファイルを SFTP サーバーに書き出すことができるようになりました。 [詳細情報](../direct-mail/direct-mail-configuration.md)

* **パーソナライゼーションのための錠剤のアクティベーション** – 公開日：2025 年 5 月 5 日（PT）

  パーソナライゼーションエディターに新しい「ピル」ボタンが追加されました。有効にすると、プロファイルとコンテキスト属性がピルとして表示され、コードの読みやすさが向上します。[詳細情報](../personalization/personalization-build-expressions.md#options)

  >[!AVAILABILITY]
  >
  >この機能は、今後 30 日間にわたってすべての環境に段階的にロールアウトされます。

* Web チャネルでの **URL にリダイレクト」のサポート**

  Journey Optimizer web チャネルで、ビジュアルエディターで新しいバリエーションを作成するのではなく、別の既存の URL に訪問者をリダイレクトできるようになりました。 この機能を使用すると、ページ内のいくつかの要素を変更するだけで済むわけではなく、2 つの完全に異なるページを比較する実験を実行できます。 [詳細情報](../web/create-web.md#web-redirect-to-url)

* **テンプレートとフラグメントのフォルダー**

  フォルダーを使用すると、オブジェクトをより簡単かつ効果的に構造化された階層に整理できます。 以前は一連の組織（LA）に対して提供されていましたが、すべてのユーザー（GA）に対してコンテンツテンプレートとフラグメントを管理できるようになりました。詳しくは、[ コンテンツテンプレート ](../content-management/access-content-templates.md#folders) および [ フラグメント ](../content-management/manage-fragments.md#folders) の節を参照してください。

* **E メールテンプレートでのクリックトラッキング**

  メールコンテンツ `<area>` 画像マップ内の要素のクリックトラッキングが、[!DNL Journey Optimizer] でネイティブにサポートされるようになりました。 これは、画像マップ領域が、標準のハイパーリンクと同じトラッキングラッピング、トラッキングデータおよび追加されたパラメーターを確実に受け取るためです。 [ メッセージトラッキングの詳細情報 ](../email/message-tracking.md#manage-tracking)

<!--
* **Decisioning - Leverage Adobe Experience Platform datasets** 
  
  Journey Optimizer now allows you to leverage Adobe Experience Platform datasets in the following Decisioning objects: eligibility rules, ranking formulas, and capping rules.

* **Right rail in campaigns list**

  In the campaign list, selecting a campaign now opens a pane displaying its details.

* **Form fields in code-based experience content**

  In content templates, you can now define specific JSON or HTML fields which enable non-technical users to easily edit content in code-based experiences without the need to manipulate code.

* **Decision item attribute support for decisioning rules**
  
  You can now leverage decision item attributes to create decisioning rules.

* **Subdomains - 'Custom delegation' method**  
  In addition to the full delegation and the CNAME method, a new subdomain configuration method is now available: the Custom delegation method, which enables you to fully own controlling and maintaining all aspects of DNS that are required for delivering, rendering, and tracking messages.
  -->

