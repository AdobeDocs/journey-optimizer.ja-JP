---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 913104934e78b61b91ea3fca21ee80372050a1fb
workflow-type: tm+mt
source-wordcount: '1209'
ht-degree: 48%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的な配信モデルに従っており、Adobeが新機能、機能強化および修正点を継続的に提供できるようにします。 このアプローチにより、機能をスケーラブルかつ段階的にロールアウトして、すべての環境でパフォーマンスと安定性を確保できます。

このモデルのため、リリースノートは毎月のリリースの間に更新されます。  専用の [ 最新のアップデート ](#updates-rn) セクションでは、実稼動へのデプロイ時に新機能と改善点がハイライト表示されるので、常にすべての変更がリアルタイムで通知されます。<!--For full details about the release cycle and availability phases, see [Journey Optimizer release cycle](#releases.md).-->

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 10 月リリースノート {#oct-25-10-rn}

**リリース日**：2025年10月22日（PT）

### 新機能 {#oct-25-10-features}

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
<th><strong>無表示時間/時間ベースの除外</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>通知の少ない時間帯は、メール、SMS、プッシュおよび WhatsApp チャネルに対する時間ベースの除外を定義できます。 これにより、特定の期間中にメッセージが送信されないようにし、顧客の好みやコンプライアンスの要件を尊重するのに役立ちます。</p>
<p>クワイエットタイムは、キャンペーンやジャーニーの個々のアクションに割り当てて、正確に制御できるルールセットを通じて適用できます。</p>
<p>非表示時間ルールは現在、一連の組織でのみ使用できます（使用制限あり）。 キャンセル待ちに追加するには、Adobeの担当者にお問い合わせください。</p>
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
<th><strong>Custom action monitoring and reporting</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>This capability provides better visibility into journey health and execution, including lifecycle status and performance alerts. You can now quickly understand when, where, and why an anomalous situation is occurring in a custom action.</p>
<img src="assets/do-not-localize/FILE.gif">
<p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p>
<p>Availability date: October 22, 2025</p>
</td>
</tr>
</tbody>
</table-->

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
<th><strong>API トリガーメールキャンペーンに対する高スループットメッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>API トリガーキャンペーンで、新しい高スループットのトランザクションメッセージモードを使用できます。 このモードは、大規模なリアルタイムトランザクションメッセージ用に設計されており、1 秒あたり最大 5,000 個のトランザクションをサポートし、可用性が向上します。 また、このモードでは、ゲストのチェックアウト、注文の確認、パスワードのリセット、セキュリティ通知、その他のサービスや操作に関する通知など、顧客プロファイルを参照または作成することなく、トランザクションメッセージをサポートします。</p>
<p>この機能は、Adobeの高スループットトランザクションメッセージ アドオン機能を購入した組織のメールチャネルでのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。</p>
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
<p>Journey Optimizerでは、時間と労力を節約するために、専用の UI メニューから再利用可能なルールを作成し、キャンペーンやジャーニーのコンテンツ最適化の一部として、またはジャーニーの最適化アクティビティのいずれかでターゲティングを構築する際に活用できるようになりました。</p>
<p>ターゲティングルールは現在、限定提供（LA）になっています。 アクセス権を取得するには、アドビ担当者にお問い合わせください。この機能は、Decisioning アドオン機能を購入した組織のみが利用できます。 すべての顧客に段階的にロールアウトされます。</p>
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
<p>新しい事前設定済みのアラートを使用して、ジャーニーの実行を監視できます。</p>
<ul><li><a href="../reports/alerts.md#alert-discard-rate"> プロファイル破棄率を超過 </a>：過去 5 分に入力されたプロファイルに対するプロファイル破棄の割合が、しきい値を超過しました</li>
<li><a href="../reports/alerts.md#alert-custom-action-error-rate"> カスタムアクションエラー率を超えています </a>：過去 5 分間に成功した HTTP 呼び出しに対するカスタムアクションエラーの割合が、しきい値を超えています</li>
<li><a href="../reports/alerts.md#alert-profile-error-rate"> プロファイルエラー率を超過 </a>：過去 5 分に入力されたプロファイルに対する、エラーのプロファイルの割合が、しきい値を超えました。</li></ul> <p>しきい値を変更し、グローバルではなく個々のジャーニーレベルのアラートを登録できます。</p>
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
<p>新しい「executionMetadata」ヘルパー関数がパーソナライゼーションエディターで使用できます。 これを使用すると、任意のネイティブアクションにコンテキスト情報を追加し、外部システムに書き出すためにデータセットに取得できます。</p>
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
<th><strong>実験エージェントのExperimentation Accelerator</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Experimentation Acceleratorに、実験エージェントが含まれるようになりました。これは、実験、インサイト、機会とやり取りできる、AI を活用した対話型ツールです。 Journey Optimizer Experimentation Acceleratorのエクスペリエンスを向上させ、実験をより効率的に実行し、何が機能するかを明らかにし、次にどこを最適化するかを見つけるのを支援します。</p>
<p>詳しくは、<a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html" target="_blank">詳細なドキュメント</a>を参照してください。</p>
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

<!--
## Latest updates {#updates-rn}

New capabilities and improvements released in the past weeks are listed below, with their availability date. They will be grouped with the next release notes content at the end of the month. See also the latest [release notes below](#latest-rn).
-->

### 機能強化 {#updates-improvements}

<!--Availability date: October 22, 2025-->

**WhatsApp チャネルの実行フィールド**

メールと SMS に加えて、サンドボックスレベルで WhatsApp 配信のデフォルトの実行フィールドを更新することがわかります。 また、WhatsApp ジャーニーアクティビティの詳細設定パラメーターまたは WhatsApp チャネル設定で変更することで、グローバルに設定された実行フィールドを上書きすることもできます。 [詳細情報](../configuration/primary-email-addresses.md)

公開日：2025年10月22日（PT）

**宛先（登録解除）アドレスのカスタム属性サポート**

アドビの外部で同意を管理している場合、Journey Optimizer では、メール設定で独自のワンクリック登録解除リンクとカスタム登録解除用メールアドレスを定義して、外部カスタムエンドポイントを設定できます。受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

ワンクリック登録解除リンクをさらにパーソナライズするため、同意イベントに追加されるカスタム属性も定義できるようになりました。[詳細情報](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>この機能は、8月25日（PT）以降、カスタム&#x200B;**[!UICONTROL ワンクリック登録解除 URL]** で既に使用できるようになり、限定提供の「**[!UICONTROL 宛先（登録解除）]**」オプションでリリースされました。アクセス権を取得するには、アドビ担当者にお問い合わせください。

公開日：2025年10月6日（PT）

### 近日リリース予定 {#oct-25-10-soon}

今後数日間で、次の機能と機能強化がリリースされる予定です。**情報は変更される場合があります**。更新したリンク、画面、ドキュメントは、これらの更新が実稼動環境で公開すると共有されます。

#### 新機能 {#oct-25-10-soon-features}

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
<p>以前ベータ版でリリースされていましたが、この機能は一連の組織で使用できるようになりました（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<!--img src="assets/do-not-localize/themes.gif">
<p>For more information, refer to the <a href="../email/apply-email-themes.md">detailed documentation</a>.</p>
<p>Availability date: November 4, 2025</p-->
</td>
</tr>
</tbody>
</table>

#### 機能強化 {#oct-25-10-soon-improvements}

**AI モデルを通じた E メールの意思決定**

AI モデルを使用して、Decisioning を通じてメールの最適なコンテンツを最適化できるようになりました。 例えば、この機能を使用すると、購入、ボタンクリック数、買い物かごに追加などのカスタムイベントに基づいて最適なコンテンツを提供できます。

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
