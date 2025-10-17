---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 1ecf54bbcb2cc62b5f13434cfbf1e369cd145d93
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 44%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。


## 2025 年 10 月プレリリースノート {#oct-25-10-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**：2025年10月22日（PT）

### 新機能 {#oct-25-10-features}



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
<p>クワイエットタイムは、キャンペーンやジャーニーの個々のアクションに割り当てて、正確に制御できるルールセットを通じて適用できます。 これらのプロセスを合理化することによって。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
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
<p>この機能により、ライフサイクルステータスやパフォーマンスアラートなど、ジャーニーの健全性と実行がよりわかりやすく表示されます。カスタムアクションで異常な状況が発生しているタイミング、場所、理由をすばやく把握できるようになりました。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
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

<table>
<thead>
<tr>
<th><strong>アクションキャンペーンを取得する新しい API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいJourney Optimizer API が使用できるようになりました。これにより、詳細、バージョン、設定など、キャンペーン関連のデータをプログラムで取得し、調べることができます。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ロイヤルティアプリ用の新しいソースコネクタ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platformで Talon.One、Capilary、Kobie の各ロイヤルティアプリ用に新しいソースコネクタが利用可能になりました。 これらのコネクタを使用すると、ロイヤルティデータをAdobe Experience Platformにシームレスにストリーミングし、これらのデータをJourney Optimizerで活用できます。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールチャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールジャーニーとキャンペーンに決定ポリシーを追加できるようになりました。決定ポリシーは、配信する最適なコンテンツを各オーディエンスメンバーに応じて動的に返すことを目的に、決定エンジンを活用するオファーのためのコンテナです。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API トリガーメールキャンペーンの高スループットモード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>API トリガーキャンペーンで新しい高スループットモードが使用できるようになりました。このモードは、大規模なリアルタイムメッセージ（1 秒あたり最大 5000 トランザクション）向けに設計され、少ない待ち時間でより高い可用性を実現します。</p>
<p>この機能は、Adobe 高スループットトランザクションメッセージのアドオン機能を購入した組織がメールチャネルでのみ使用できます。詳しくは、アドビ担当者にお問い合わせください。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
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
<p>Journey Optimizerでは、専用の UI メニューからルールを作成し、キャンペーンまたはジャーニーのコンテンツ最適化の一部として、またはジャーニーの最適化アクティビティでターゲティングを構築する際に活用できるようになりました。</p>
<p>ターゲティングルールは現在、限定提供（LA）になっています。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>この機能は、Decisioning アドオン機能を購入した組織のみが利用できます。 すべての顧客に段階的にロールアウトされます。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
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
<p>以前ベータ版でリリースされていましたが、この機能は一連の組織で使用できるようになりました（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/themes.gif">
<p>詳しくは、<a href="../email/apply-email-themes.md">詳細なドキュメント</a>を参照してください。</p>
<!--p>Availability date: October 22, 2025</p-->
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
<p>公開日：2025 年 10 月 14 日（PT）</p>
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
<p>詳しくは、<a href="../personalization/functions/helpers.md#execution-metadata">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025 年 10 月 13 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>実験エージェントが登場！</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><a href="https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator.html" target="_blank">Adobe Experience Platform Agent Orchestrator</a> を活用し、Journey Optimizerで実験エージェントを利用できます。 </p>
<p>実験エージェントは、Web サイト、メール、プッシュメッセージおよびアプリケーションをまたいでデジタル実験を実行および管理する方法を最新化する、AI を利用したツールです。 これにより、実験をより効率的に実行し、ビジネス目標を整理し、うまくいったこと、うまくいかなかったこと、次に実験する場所を強調表示した、実用的なインサイトを生成できます。</p>
<p>詳しくは、<a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html" target="_blank">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 10 月 10 日（PT）</p>
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
<p>公開日：2025 年 9 月 30 日（PT）</p>
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
<p>ジャーニーと、キャンペーンやサーフェスなどの関連オブジェクトを取得する新しいJourney Optimizer API が使用できるようになりました。</p>
<p>詳しくは、<a href="https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve/">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 9 月 25 日（PT）</p>
</td>
</tr>
</tbody>
</table>


### 機能強化

**WhatsApp チャネルの実行フィールド**

メールと SMS に加えて、サンドボックスレベルで WhatsApp 配信のデフォルトの実行フィールドを更新することがわかります。 また、WhatsApp ジャーニーアクティビティの詳細設定パラメーターまたは WhatsApp チャネル設定で変更することで、グローバルに設定された実行フィールドを上書きすることもできます。<!-- [Read more](../FILE.md) -->

**Mailto （登録解除）アドレスのカスタム属性のサポート**

Journey Optimizerを使用すると、Adobe外で同意を管理している場合に、独自のワンクリック購読解除リンクとカスタム購読解除メールアドレスをメール設定に定義することで、外部カスタムエンドポイントを設定できます。 受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

カスタムエンドポイントをさらにパーソナライズするために、同意イベントにも追加されるカスタム属性を定義できるようになりました。 [詳細情報](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>この機能は、8 月 25 日（PT）以降、カスタム **[!UICONTROL ワンクリック登録解除 URL]** で既に使用できるようになり、限定提供の **[!UICONTROL 宛先（登録解除）]** オプションでリリースされました。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

公開日：2025 年 10 月 6 日（PT）