---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 181999b096f6f65f25ba5220868aab3aaeafb807
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 86%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。

このモデルにより、リリースノートは毎月のリリースの間に更新されます。専用の [ 最新のアップデート ](#latest-updates) セクションでは、実稼動へのデプロイ時に新機能と改善点がハイライト表示されるので、常にすべての変更がリアルタイムで通知されます。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル ](releases.md) を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

<!--
## Latest updates {#latest-updates}


New capabilities and improvements released in the past weeks are listed below, with their availability date. They will be grouped with the next release notes content at the end of the month. See also the latest [release notes below](#latest-rn).

-->



## 2025年10月リリースノート {#oct-25-10-rn}

### 新機能 {#oct-25-10-features}


<table>
<thead>
<tr>
<th><strong>画像からHTMLへのコンバーター</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>画像からHTMLへのコンバーターは、静的な画像デザインを、完全にカスタマイズ可能なモジュール型のHTML メールコンテンツテンプレートに変換する AI を利用した機能です。 このコードなしのツールにより、マーケターは、技術的な専門知識を必要とせずに、ビジュアルデザインをレスポンシブで編集可能なメールテンプレートに変換でき、プラットフォームの移行、迅速なテンプレート作成、再利用可能なテンプレートライブラリの構築に最適です。</p>
<p><img src="../email/assets/email_designer_converted_img.png"/></p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../email/image-to-html.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 10 月 30 日（PT）</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>カスタムアクションの監視とレポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>この機能により、カスタムアクションエンドポイントの正常性とパフォーマンスがよりわかりやすくなっています。 新しいカスタムアクション監視ダッシュボードと、ジャーニーステップイベントデータセットの対応するフィールドを使用すると、カスタムアクションエンドポイントの成功した呼び出し、エラー、スループット、応答時間、キュー待機時間を監視するのに役立ちます。 カスタムアクションで異常な状況が発生しているタイミング、場所、理由をすばやく把握できるようになりました。</p>
<p>この機能は、現在、お客様に対して限定提供されています。</p>
<p>詳しくは、<a href="../action/reporting.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月28日（PT）</p>
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
<p>[!DNL Journey Optimizer] を使用すると、ランディングページを通じてプロファイル属性を取得できるようになりました。</p>
<p>特定のデータセットに基づいて、ニーズに合わせてカスタマイズされたカスタムフォームを作成、デザイン、管理します。その後、ランディングページでこれらのフォームを活用して、各フォームに定義されたデータセットに選択したプロファイル属性を追加できます。</p>
<p>この機能は、現在、米国およびオーストラリアのお客様向けに限定提供されています。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<p>詳しくは、<a href="../landing-pages/lp-forms.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月23日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>クワイエットアワー／時間ベースの除外</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>クワイエットアワーでは、メール、SMS、プッシュ、WhatsApp の各チャネルについて、時間ベースの除外を定義できます。これにより、特定の期間中にメッセージが送信されなくなり、顧客の環境設定やコンプライアンス要件を適用できます。</p>
<p>クワイエットアワーは、キャンペーンやジャーニー内の個々のアクションに割り当てて、正確な制御を行うことができるルールセットを通じて適用できます。</p>
<p>クワイエットアワールールは現在、一連の組織でのみ使用できます（限定提供）。待機リストに追加するには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/quiet-hour.gif">
<p>詳しくは、<a href="../conflict-prioritization/quiet-hours.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月22日（PT）</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>RCS Basic Messaging</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>With the new RCS Basic add-on offering, you can now deliver basic Rich Communication Services (RCS) messaging in Journey Optimizer, enabling the following enhanced messaging capabilities subject to provider and geographical support:</p>
<ul>
<li><strong>Branded and verified sender support:</strong> Send messages using verified business profiles with branding elements (logo, sender name, etc.).</li>
<li><strong>Message delivery insights:</strong> Receive detailed delivery reports including message status updates (e.g., sent, delivered, read).</li>
<li><strong>Link tracking:</strong> Embed and track URLs within RCS messages for engagement analytics.</li>
<li><strong>Fallback to SMS:</strong> Automatic fallback to SMS when the recipient's device does not support RCS or is temporarily unreachable via RCS.</li>
<li><strong>Basic message composition:</strong> Send basic text-based RCS messages.</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct mail channel in Orchestrated campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Direct mail channel is now available in orchestrated campaigns. The Direct mail activity facilitates direct mail sending within your Orchestrated campaign, for both one-time and recurring messages. It serves to automate the process of generating the extraction file required by direct mail providers. You can combine channel activities into the Orchestrated campaign canvas to create cross-channel campaigns that can trigger actions based on customer behavior and data.</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Direct Mail channel in journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Previously limited to Campaigns, Direct Mail channel is now available on the journey canvas, enabling you to incorporate Direct Mail into your journeys. Direct Mail can now be used in both batch and 1:1 journey scenarios, with support for file extraction configuration and time-based frequency settings.</p>
<p> Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<!--/td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>New API to retrieve Action Campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A new Journey Optimizer API is now available, enabling you to programmatically retrieve and inspect campaign-related data such as details, versions, and configurations.</p>
<p>For more information, refer to the <a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

<!--<table>
<thead>
<tr>
<th><strong>New source connectors for loyalty apps</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>New source connectors are now available in Adobe Experience Platform for the Talon.One, Capillary and Kobie loyalty Apps. These connectors let you seamlessly stream loyalty data into Adobe Experience Platform and leverage these data in Journey Optimizer.</p>
<p>For more information, refer to the <a href="../start/get-started-sources.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table>-->

<!--table>
<thead>
<tr>
<th><strong>Decisioning support in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add Decision policies into email journeys and campaigns. Decision policies are containers for your offers that leverage the Decisioning engine to dynamically return the best content to deliver for each audience member.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<img src="assets/do-not-localize/FILE.gif">
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>API トリガーメールキャンペーンの高スループットメッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>API トリガーキャンペーンで新しい高スループットトランザクションメッセージモードが使用できるようになりました。このモードは、大規模なリアルタイムトランザクションメッセージ向けに設計され、1 秒あたり最大 5,000 トランザクションと高い可用性を実現します。また、このモードでは、ゲストのチェックアウト、注文確認、パスワードリセット、セキュリティ通知、その他のサービス／操作に関する通知など、顧客プロファイルを参照または作成することなく、トランザクションメッセージをサポートします。</p>
<p>この機能は、アドビの高スループットトランザクションメッセージのアドオン機能を購入した組織がメールチャネルでのみ使用できます。詳しくは、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../campaigns/api-triggered-high-throughput.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月22日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>再利用可能なターゲティングルール</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>時間と労力を節約するために、Journey Optimizer では、専用の UI メニューから再利用可能なルールを作成し、キャンペーンやジャーニーの最適化コンテンツの一部として、またはジャーニーを最適化アクティビティのいずれかでターゲティングを作成する際に活用できるようになりました。</p>
<p>ターゲティングルールは現在、限定提供（LA）です。 アクセス権を取得するには、アドビ担当者にお問い合わせください。この機能は、決定アドオン機能を購入した組織のみが利用できます。すべての顧客に段階的にロールアウトされる予定です。</p>
<img src="assets/do-not-localize/targeting-rules.gif">
<p>詳しくは、<a href="../experience-decisioning/rules.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月22日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>新しいジャーニーアラート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーの実行を監視する事前設定済みの新しいアラートが使用可能です。</p>
<ul><li><a href="../reports/alerts.md#alert-discard-rate">プロファイル破棄率超過</a>：しきい値を超えた、過去 5 分間にエントリ済みのプロファイル数に対するプロファイル破棄率。</li>
<li><a href="../reports/alerts.md#alert-custom-action-error-rate">カスタムアクションエラー率超過</a>：しきい値を超えた、過去 5 分間に成功した HTTP 呼び出し数に対するカスタムアクションエラー率。</li>
<li><a href="../reports/alerts.md#alert-profile-error-rate">プロファイルエラー率超過</a>：しきい値を超えた、過去 5 分間にエントリ済みのプロファイル数に対するプロファイルエラー率。</li></ul> <p>しきい値を変更し、グローバルではなく個々のジャーニーレベルのアラートを登録できます。</p>
<p>詳しくは、<a href="../reports/alerts.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月14日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>実行メタデータヘルパー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい「executionMetadata」ヘルパー関数がパーソナライゼーションエディターで使用できます。これを使用すると、任意のネイティブアクションにコンテキスト情報を追加し、データセットにキャプチャして外部システムにエクスポートできます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/execution-metadata.gif">
<p>詳しくは、<a href="../personalization/functions/helpers.md#execution-metadata">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月13日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>実験エージェントを備えた実験アクセラレーター</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer 実験アクセラレーターに、実験、インサイト、機会とやり取りできる AI を活用した対話型ツールである実験エージェントが含まれるようになりました。これにより、Journey Optimizer の実験アクセラレーターのエクスペリエンスが強化され、実験をより効率的に実行し、機能する内容を明らかにし、次に最適化する箇所を見つけるのに役立ちます。</p>
<p>詳しくは、<a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html?lang=ja" target="_blank">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月10日（PT）</p>
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
<li>追加のサイズまたはボリュームについては、PDF 添付ファイルアドオンを購入できます。詳しくは、アドビ担当者にお問い合わせください。</li>
</ul>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/pdf-attachments.gif"/></p>
<p>詳しくは、<a href="../email/pdf-attachments.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年9月30日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーを取得するパブリック API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーと、キャンペーンやサーフェスなどの関連オブジェクトを取得する新しい Journey Optimizer API が利用可能になりました。</p>
<p>詳しくは、<a href="https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve/">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年9月25日（PT）</p>
</td>
</tr>
</tbody>
</table>



### 機能強化 {#updates-improvements}

**WhatsApp チャネルの実行フィールド**

メールと SMS に加えて、サンドボックスレベルで WhatsApp 配信のデフォルトの実行フィールドを更新できるようになりました。また、WhatsApp ジャーニーアクティビティの高度なパラメーターや WhatsApp チャネル設定で変更することで、グローバルに設定された実行フィールドを上書きすることもできます。[詳細情報](../configuration/primary-email-addresses.md)

公開日：2025年10月22日（PT）

**宛先（登録解除）アドレスのカスタム属性サポート**

アドビの外部で同意を管理している場合、Journey Optimizer では、メール設定で独自のワンクリック登録解除リンクとカスタム登録解除用メールアドレスを定義して、外部カスタムエンドポイントを設定できます。受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

ワンクリック登録解除リンクをさらにパーソナライズするため、同意イベントに追加されるカスタム属性も定義できるようになりました。[詳細情報](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>この機能は、8月25日（PT）以降、カスタム&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** で既に使用できるようになり、限定提供の「**[!UICONTROL 宛先（登録解除）]**」オプションでリリースされました。アクセス権を取得するには、アドビ担当者にお問い合わせください。

公開日：2025年10月6日（PT）

<!--
### Coming soon {#oct-25-10-soon}

In the next few days, the following capabilities and enhancements are scheduled for release. **Information is subject to change**. Updated links, screens, and documentation will be shared once these updates are live in production.

#### New capabilities {#oct-25-10-soon-features}

<table>
<thead>
<tr>
<th><strong>Themes in the Email Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now quickly apply pre-approved themes to ensure brand consistency across all emails, speed up your campaign creation process, and independently produce high-quality emails while reducing dependency on design teams.</p>
<p>Previously released in beta version, this capability is now available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<img src="assets/do-not-localize/themes.gif">
<p>For more information, refer to the <a href="../email/apply-email-themes.md">detailed documentation</a>.</p>
<p>Availability date: November 4, 2025</p>
</td>
</tr>
</tbody>
</table>

#### Improvements {#oct-25-10-soon-improvements}

**Decisioning in emails through AI models**

You can now use AI models to optimize the best content in your email through the use of Decisioning. For example, this capability allows you to offer the best content based on custom events such as Purchases, Button Clicks, Add to Cart, etc.
-->

<!--
<table>
<thead>
<tr>
<th><strong>New Web Push notifications channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports Web Push notifications, expanding the push channel beyond mobile. You can seamlessly deliver notifications to both mobile and desktop browsers, enabling you to reach customers directly on their devices without requiring an app.</p>
<p>This enhancement allows you to engage users with timely, personalized messages in real time, leveraging the same authoring workflows and targeting capabilities already available for mobile push.</p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Custom action monitoring and reporting</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Custom action monitoring and reporting is now available. This capability provides better visibility into journey health and execution, including lifecycle status and performance alerts. You can now quickly understand when, where, and why an anomalous situation is occurring in a custom action.</p>
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p>
</td>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>New source connectors for loyalty apps</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>New source connectors are now available in Adobe Experience Platform for the Talon.One, Capillary, and Kobie loyalty apps. These connectors let you seamlessly stream loyalty data into Adobe Experience Platform and leverage these data in Journey Optimizer.</p>
</td>
</tr>
</tbody>
</table>

-->
