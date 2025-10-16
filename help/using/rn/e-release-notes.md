---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: c2b990a413762dccc71e4152cbb145a51a5d073e
workflow-type: tm+mt
source-wordcount: '1142'
ht-degree: 42%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。


## 2025 年 10 月プレリリースノート {#25-10-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**:2025 年 10 月 21～22 日

### 新機能 {#oct-25-10-features}



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

<table>
<thead>
<tr>
<th><strong>RCS の基本メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい RCS 基本アドオン機能により、Journey Optimizerで基本的な RCS （Rich Communication Services）メッセージングを提供できるようになりました。これにより、プロバイダや地理的なサポートに応じて、以下の強化されたメッセージング機能が可能になります。</p>
<ul>
<li><strong> ブランド化および検証済みの送信者のサポート：</strong> ブランド要素（ロゴ、送信者名など）を含む検証済みのビジネスプロファイルを使用してメッセージを送信します。</li>
<li><strong> メッセージ配信インサイト：</strong> メッセージのステータス更新（送信済み、配信済み、読み取りなど）を含む詳細な配信レポートを受信します。</li>
<li><strong> リンクトラッキング：</strong> エンゲージメント分析のために、RCS メッセージ内に URL を埋め込んで追跡します。</li>
<li><strong>SMS へのフォールバック：</strong> 受信者のデバイスが RCS をサポートしていない場合や、RCS 経由で一時的に到達できない場合に SMS に自動的にフォールバックします。</li>
<li><strong> 基本的なメッセージ構成：</strong> 基本的なテキストベースの RCS メッセージを送信します。</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーケストレートキャンペーンのダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ダイレクトメールチャネルを調整されたキャンペーンで使用できるようになりました。 ダイレクトメールアクティビティでは、調整されたキャンペーン内でのダイレクトメール送信が促進され、1 回限りのメッセージと繰り返しメッセージの両方を送信できます。これは、ダイレクトメールプロバイダーが必要とする抽出ファイルを生成するプロセスを自動化するのに役立ちます。チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
</td>
</tr>
</tbody>
</table>

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
<p> この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p>詳しくは、<a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-experiment.html?lang=ja" target="_blank">詳細なドキュメント</a>を参照してください。</p>
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

**ターゲティングでの再利用可能なルールを選択**

ジャーニーやキャンペーンで、メッセージの最適化機能を使用してターゲティングルールを使用する際に、ルールビルダーを活用できるようになりました。<!-- [Read more](../FILE.md) -->

**WhatsApp チャネルの実行フィールド**

メールと SMS に加えて、WhatsApp のデフォルトの実行フィールドを更新できるようになりました。 また、WhatsApp ジャーニーアクティビティの詳細設定パラメーターまたは WhatsApp チャネル設定でグローバルに設定された実行フィールドを上書きすることもできます。<!-- [Read more](../FILE.md) -->

**権限**

**新しいジャーニーアラート**

[&#x200B; プロファイル破棄率を超過 &#x200B;](../reports/alerts.md#alert-discard-rate) （過去 5 分に入力したプロファイルに対するプロファイル破棄の割合がしきい値を超えています）、[&#x200B; カスタムアクションエラー率を超過 &#x200B;](../reports/alerts.md#alert-custom-action-error-rate) （過去 5 分に成功した HTTP 呼び出しに対するカスタムアクションエラーの割合がしきい値を超えています）、[&#x200B; プロファイルエラー率を超過 &#x200B;](../reports/alerts.md#alert-profile-error-rate) （過去 5 分に入力したプロファイルに対するエラーの割合）のジャーニーに使用できます。 しきい値を変更し、グローバルではなく個々のジャーニーレベルのアラートを登録できます。

公開日：2025 年 10 月 14 日（PT）

**Mailto （登録解除）アドレスのカスタム属性のサポート**

Journey Optimizerを使用すると、Adobe外で同意を管理している場合に、独自のワンクリック購読解除リンクとカスタム購読解除メールアドレスをメール設定に定義することで、外部カスタムエンドポイントを設定できます。 受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

カスタムエンドポイントをさらにパーソナライズするために、同意イベントにも追加されるカスタム属性を定義できるようになりました。 [詳細情報](../email/list-unsubscribe.md#custom-attributes)

>[!AVAILABILITY]
>
>この機能は、8 月 25 日（PT）以降、カスタム **[!UICONTROL ワンクリック登録解除 URL]** で既に使用できるようになり、限定提供の **[!UICONTROL 宛先（登録解除）]** オプションでリリースされました。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

公開日：2025 年 10 月 6 日（PT）