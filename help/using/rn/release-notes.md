---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 8def78063b8477eb2eaf0a95602b7d311eb1ad2e
workflow-type: tm+mt
source-wordcount: '1891'
ht-degree: 39%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 9 月リリースノート {#25-9-rn}

**リリース日**:2025 年 9 月 23～24 日

### 新機能 {#sept-25-9-features}

<!-- table>
<thead>
<tr>
<th><strong>Public API to retrieve journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A new Journey Optimizer API is now available to retrieve journeys and their associated objects such as campaigns and surfaces.</p>
<p>For more information, refer to the <a href="https://developer.adobe.com/journey-optimizer-apis/references/journeys-retrieve/">detailed documentation</a></p>
<p>Availability date: Sept 25, 2025</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Journey Optimizer Experimentation Accelerator</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Experimentation Acceleratorは、実験を次のレベルに引き上げるために設計された AI ファーストの製品です。 Adobe Journey OptimizerおよびAdobe Target ユーザー向けに構築されたこのサービスは、実験管理を統合し、AI を活用したインサイトとオポチュニティを提供し、新しい実験エージェントを導入します。</p>
<p>次の点にご期待ください。</p>
<ul>
<li><strong> 統合された実験インベントリ：</strong>Adobe Journey OptimizerとAdobe Targetのすべての実験を 1 つの中央ワークスペースですばやく表示、フィルタリング、管理します。</li>
<li><strong>AI 実験のインサイトと機会：</strong>GenAI によるインサイトと推奨事項を使用して、統計的な読み上げを超えます。 各実験では、根拠を裏付ける完全な、実用的な機会が得られるため、チームは次に何をテストすべきかをより自信を持って決定できます。</li>
<li><strong>Journey Optimizerでのマルチアームバンディット（MAB）のサポート：</strong> マルチアームバンディット実験で無駄になるトラフィックを減らしながら、影響を最大限に高めます。 MAB では、オーディエンスを均等に分割するのではなく、パフォーマンスの最も高いバリエーションにリアルタイムでより多くの訪問者を自動的に割り当てるため、機能を学びながら、より多くの顧客により良いエクスペリエンスを提供できます。</li></ul>
<p><img src="assets/do-not-localize/experimentation-accelerator.gif"/></p>
<p>詳しくは、<a href="../content-management/experiment-accelerator.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 9 月 23 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agentが来ました。</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><a href="https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator" target="_blank">Adobe Experience Platform Agent Orchestrator</a> を活用し、Journey OptimizerでJourney Agentを利用できます。 これにより、自然言語インターフェイスを使用してジャーニーを分析できます。 エージェントは、オーディエンスを検出したり、ジャーニーでの競合やプロファイルのドロップオフをスケジュールしたりして、それらを解決する手順を実行できるようにします。 間もなく、代理店のサポートを受けたジャーニーを作成できるようになります。</p>
<p>詳しくは、<a href="https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent-analyze" target="_blank">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 9 月 24 日（PT）</p>
</td>
</tr>
</tbody>
</table>

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
 <p>公開日：2025年9月16日（PT）</p>
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
<p>公開日：2025年9月4日（PT）</p>
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
<p><img src="assets/do-not-localize/custom-delegation.gif"/></p>
<p>詳しくは、<a href="../configuration/delegate-custom-subdomain.md">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025年9月4日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>パーソナライゼーションと意思決定へのAdobe Experience Platform データの使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はパブリックベータ版でリリースされていましたが、現在はすべての環境でこの機能を利用できます。 このリリースでは、次の機能強化が導入されました。</p>
<ul><li>インバウンドチャネルでのデータセット参照パーソナライゼーションのサポート。</li>
<li>「datasetLookup」ヘルパー関数を式フラグメント内で使用できるようになりました。現時点では、この機能は限定された一連のお客様のみが使用できます。アクセスするには、アドビ担当者にお問い合わせください。</li>
<li>データセット管理インターフェイスのオプションを使用すると、API 呼び出しを実行しなくても、レコードベースのデータセットで参照パーソナライゼーションを有効にできるようになりました。</li>
<li>データ取り込みステータスを追跡し、データセットの検索準備が整ったタイミングを把握する監視を機能強化しました。</li>
<li>最適なパフォーマンスと信頼性を確保することを目的に、使用ガイドラインとガードレールを更新しました。</li>
<li>Adobe Experience Platform データセットを決定キャッピングルールで活用できるようになりました。</li></ul></p>
<p>詳しくは、<a href="../data/lookup-aep-data.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年9月1日（PT）</p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#sept-25-9-improvements}

* **API トリガーキャンペーンの Webhook サポート**\
  API トリガーキャンペーンで Webhook がサポートされるようになりました。 Webhook の URL を設定して、メッセージごとにリアルタイムのステータス更新を受信するようにすると、観測性が向上し、シームレスな監視と自動化が可能になります。 [詳細情報](../configuration/feedback-webhooks.md)

  公開日：2025 年 9 月 29 日（PT）

* **承認ポリシーの権限**
承認ポリシーを作成または設定する際に、ジャーニー/キャンペーン作成者が独自のオブジェクトを承認できないようにするオプションを追加しました。 [ 詳細を読む ](../test-approve/approval-policies.md) – 公開日：2025 年 9 月 23 日（PT）

* **SMS チャネルの mTLS サポート**
カスタム SMS プロバイダーを設定する際に、相互 TLS （mTLS）認証を有効にするオプションが追加されました。この場合、安全な接続が確立される前に、クライアントとサーバーの両方が相互の ID を確認する必要があります。 [ 詳細を読む ](../sms/sms-configuration-custom.md) – 公開日：2025 年 9 月 23 日（PT）

* **モデルベースのスキーマ**\
  モデルベースのスキーマは、で使用して、調整されたキャンペーンでのリレーショナルモデリングのニーズをサポートできるようになりました。 [ 詳細を読む ](../orchestrated/gs-schemas.md) – 公開日：2025 年 9 月 23 日（PT）

* **ジャーニーでのデータセットルックアップのサポート**\
  ジャーニーの新しいアクティビティ **データセットルックアップ** を使用すると、実行時にAdobe Experience Platform レコードデータセットからデータを動的に取得できます。 この機能を活用すると、プロファイルまたはイベントペイロードに存在しない可能性のあるデータにアクセスできるので、顧客とのインタラクションが関連性が高く、タイムリーなものとなります。 [ 詳細を読む ](../building-journeys/dataset-lookup.md) – 公開日：2025 年 9 月 23 日（PT）

  このアクティビティは、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。

* **ジャーニーカスタムアクションでのリダイレクトのサポート**\
  リダイレクト （302）がジャーニーのカスタムアクションでサポートされるようになりました。  – 公開日：2025 年 9 月 23 日（PT）

* **チャネル設定のモニタリングアラート** - カスタムサブドメインデリゲーションタイプを使用したメールチャネル設定エラーが発生した場合に、メールまたは Journey Optimizer 通知センターでシステムアラートを受信するように登録できるようになりました。[ 詳細を読む ](../reports/alerts.md#alert-channel-config-failure) – 公開日：2025 年 9 月 23 日（PT）

* **ワンクリック購読解除リクエスト** - Adobe Managed で設定されたワンクリック購読解除リクエストの処理をさらに強化し、信頼性と一貫性のある処理を確保する機能強化を導入しました。  – 公開日：2025 年 9 月 23 日（PT）

* **カスタム認証でネストされた JSON ボディパラメーターがサポートされるようになりました**\
  カスタムアクションにカスタム認証を設定する場合、ネストされた JSON オブジェクト（`bodyParams` 内のサブオブジェクトなど）がサポートされるようになりました。 [ 詳細を読む ](../datasource/external-data-sources.md#custom-authentication-mode) – 公開日：2025 年 9 月 18 日（PT）

* **時間単位での頻度キャップのリセット** - チャネルルールセットに対して時間単位でキャップを適用できるようになりました。以前は限定提供（LA）で利用できましたが、現在はすべての環境で利用でき、1 時間（以前は 3 時間）を選択できるようになりました。 [ 詳細を読む ](../conflict-prioritization/channel-capping.md) – 公開日：2025 年 9 月 17 日（PT）

* **すべてのインバウンドチャネルのコンテンツバリエーションのシミュレーション**\
  以前は、メール、SMS、プッシュ通知のチャネルでのみ使用できましたが、コンテンツのバリエーションのシミュレーションはすべてのインバウンドチャネルにも適用されるようになりました。 [ 詳細を読む ](../test-approve/simulate-sample-input.md) – 公開日：2025 年 9 月 17 日（PT）

* **決定キャッピングルールの式** - 独自の式を作成して、決定項目のキャッピングルールのしきい値を定義できるようになりました。[ 詳細を読む ](../experience-decisioning/items.md#capping) – 公開日：2025 年 9 月 16 日（PT）

* **動的ドメインのサポート** - Journey Optimizer では、アドビが受け入れた定義済みドメインの完全／ベース URL パーソナライゼーションがサポートされるようになりました。[ 詳細を読む ](../personalization/personalization-build-expressions.md#where) – 公開日：2025 年 9 月 12 日（PT）

  この機能は、一連のお客様に対して限定提供で利用できます。

* **Webhook** – このリリースでは、カスタム SMS プロバイダーを設定する際の Webhook に関する次の機能強化が導入されています。

   * 取得するデータのタイプに応じて、Webhook の目的（インバウンドまたはフィードバック）を定義できるようになりました。 [ 詳細を読む ](../sms/sms-configuration-custom.md#webhook) – 公開日：2025 年 9 月 23 日（PT）

   * 設定を容易にするために、キーワード設定用のインターフェイスを改善しました。 [ 詳細を読む ](../sms/sms-configuration-custom.md#webhook) – 公開日：2025 年 9 月 23 日（PT）

* **SMS**

   * カスタム SMS プロバイダーを設定する際に、受信 SMS に認識できないキーワードが含まれている場合に使用する **デフォルト** キーワードを定義できるようになりました。 特定のアクションに対して **カスタム** キーワードを作成することもできます。 [ 詳細を読む ](../sms/sms-configuration-custom.md) – 公開日：2025 年 9 月 23 日（PT）

   * 設定で明示的に定義されていない入力ミス、単語、文など、SMS メッセージで送信される未定義の受信キーワードの応答にアクセスできるようになりました。 これらは、{InboundMessage} の下の **0}AJO メールトラッキングエクスペリエンスイベント** データセットに 13 か月間保存され **す。** Sinch、Infobip、カスタム SMS プロバイダーでのみ使用できます。  – 公開日：2025 年 9 月 23 日（PT）

* **WhatsApp** - WhatsApp のデフォルトの実行アドレスを使用するか、カスタムアドレスを設定できるようになりました。

### 準備中 {#sept-25-9-soon}

今後数日以内に、次の機能および機能強化のリリースが予定されています。 **情報は変更される場合があります**。 更新されたリンク、画面およびドキュメントは、これらの更新が実稼動環境で公開されると共有されます。

<table>
<thead>
<tr>
<th><strong>新しい Web プッシュ通知チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerで web プッシュ通知がサポートされるようになり、モバイル以外にもプッシュチャネルが拡大されました。 モバイルブラウザーとデスクトップブラウザーの両方にシームレスに通知を配信できるので、アプリを使用せずに、デバイス上で直接お客様にリーチできます。</p>
<p>この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、パーソナライズされたメッセージをリアルタイムでユーザーに提供できます。</p>
<!--p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p-->
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
<p>カスタムアクションの監視とレポートが使用できるようになりました。 この機能により、ライフサイクルステータスやパフォーマンスアラートなど、ジャーニーの正常性と実行がよりわかりやすく表示されます。 カスタムアクションで異常な状況が発生しているタイミング、場所、理由をすばやく理解できるようになりました。</p>
<!--p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p-->
</td>
</td>
</tr>
</tbody>
</table>

<!--table>
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
</table-->


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
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/forms.gif"/></p>
<!--p>For more information, refer to the <a href="../landing-pages/lp-forms.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p-->
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
<li>その他のサイズまたはボリュームについては、PDF添付ファイルアドオンを購入できます。 詳しくは、アドビ担当者にお問い合わせください。</li>
</ul>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/pdf-attachments.gif"/></p>
<!--p>For more information, refer to the <a href="../email/pdf-attachments.md">detailed documentation</a></p>
<p>Availability date: Sept XX, 2025</p-->
</td>
</tr>
</tbody>
</table>



* **新しいジャーニーアラート**\
  ジャーニーには、事前設定済みの新しいアラートを使用できます。

   * プロファイル破棄率の超過：過去 5 分に入力されたプロファイルに対するプロファイル破棄の割合が、しきい値を超えました。
   * カスタムアクションエラー率を超えました：過去 5 分の、成功した HTTP 呼び出しに対するカスタムアクションエラーの割合が、しきい値を超えました。
   * プロファイルエラー率の超過：過去 5 分に入力されたプロファイルに対する、エラーのプロファイルの割合が、しきい値を超えました。
<!--
  * [Profile Discard Rate Exceeded](../reports/alerts.md#profile-discard-rate-exceeded): Ratio of profile discards to entered profiles over the last 5 mins exceeded threshold.  
  * [Custom Action Error Rate Exceeded](../reports/alerts.md#custom-action-error-rate-exceeded): Ratio of custom action errors to successful HTTP calls over the last 5 mins exceeded threshold.  
  * [Profile Error Rate Exceeded](../reports/alerts.md#profile-error-rate-exceeded): Ratio of profiles-in-error to entered profiles over the last 5 mins exceeded threshold.-->

しきい値を変更し、個々のジャーニーレベルのアラートに登録するか、グローバルに登録するかを指定できます。

<!-- Availability date: Sept XX, 2025-->


* **ワンクリック登録解除 URL でのカスタム属性のサポート**\
  Journey Optimizerを使用すると、Adobe外で同意を管理している場合に、メール設定で独自のワンクリック購読解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

  購読解除メールアドレスをさらにパーソナライズするために、同意イベントに追加するカスタム属性を定義できるようになりました。 この機能は、8 月 25 日リリース以降、カスタムのワンクリック購読解除リンクで既に使用されています。

  <!-- Availability date: Sept XX, 2025-->
