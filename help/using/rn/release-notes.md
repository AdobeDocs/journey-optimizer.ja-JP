---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 0706cb23bb41aff56984d7723df22c5a07bbe51d
workflow-type: tm+mt
source-wordcount: '1807'
ht-degree: 15%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。

このモデルのため、リリースノートは毎月のリリースの間に更新されます。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2026 年 1 月リリースノート {#latest-rn}

**リリース日**:2026 年 1 月 27～28 日

[&#x200B; 機能 &#x200B;](#jan-26-01-features) および [&#x200B; 改善 &#x200B;](#jan-26-01-improv) の節では、既に使用可能な機能について説明し、[&#x200B; 近日公開 &#x200B;](#jan-26-01-coming-soon) では、後の公開日にスケジュールされている項目を一覧表示しています。

<!-- **The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date. 

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

### 新機能 {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>Journey Agent - ジャーニーの作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Agentの作成時にJourney Optimizer ユーザーが <strong> 自然言語インターフェイス </strong> を使用してマーケティングジャーニーを作成および設定できるようになりました。 実務担当者は、対話型プロンプトで要件を記述することで、ジャーニーを迅速に作成できます。 これにより、ジャーニーの作成プロセスが合理化され、マーケターは技術的な設定ではなく戦略に専念できます。</p>
<p>詳しくは、<a href="../start/ai-features.md#journey-agent">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年1月12日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>アクションキャンペーン取得 API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい API を使用すると、アクションキャンペーンを取得し、主要な属性でフィルタリングして、自動化ワークフローとレポートワークフローをサポートできます。</p>
<p>詳しくは、<a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/" target="_blank">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年11月24日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーアラート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいジャーニーアラートは、主要なジャーニーの正常性シグナルを監視するのに役立ちます。 このリリースでは、プロファイル破棄率、カスタムアクションエラー率、プロファイルエラー率のアラートタイプと、設定可能なしきい値、ジャーニーインベントリからのジャーニーレベルのアラート購読が導入されています。</p>
<p>しきい値は、すべてのジャーニーでグローバルです。</p>
<p>詳しくは、<a href="../reports/alerts.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年10月14日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールDesignerのテーマ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールのコンテンツを作成する際に、再利用可能なテーマを使用して、メールDesignerで一貫したスタイルを適用します。</p>
<p><img src="assets/do-not-localize/themes.gif"/></p>
<p>詳しくは、<a href="../email/apply-email-themes.md">詳細なドキュメント</a>を参照してください。</p>
<p>この機能は、一連の組織を対象に、限定提供で利用できます。 アドビ担当者にお問い合わせください。</p>
<p>公開日：2025年11月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Web プッシュ通知チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerは <strong>web プッシュ通知 </strong> をサポートし、プッシュチャネルをモバイル以外にも拡張します。 モバイルブラウザーとデスクトップブラウザーの両方に通知を配信できるので、アプリを必要とせずに、デバイス上で顧客に直接リーチできます。 この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、パーソナライズされたメッセージをリアルタイムでタイムリーにユーザーに提供できるようになります。</p>
<p>詳しくは、<a href="../push/push-configuration-web.md">詳細なドキュメント</a>を参照してください。</p>
<p>以前にBetaでリリースされたこの機能は、すべての環境で使用できるようになります（一般提供）。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#jan-26-01-improv}

#### Experience Decisioning

* **決定項目にフラグメントを添付** - Journey Optimizerでは、決定項目に <strong> フラグメント </strong> を添付する機能が提供されるようになりました。この機能は、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで利用できます。 [詳細情報](../experience-decisioning/items.md)

  **メモ**：以前に限定提供でリリースされていましたが、この改善をすべての環境で利用できるようになりました（一般提供）。

#### ジャーニー

* **ジャーニーのカスタムアクションでのエラー応答ペイロードの活用** - カスタムアクションにオプションの <strong> エラー応答ペイロード </strong> を定義できるようになりました。 呼び出しが失敗すると、エラーペイロードがジャーニーコンテキストで公開され、タイムアウト/エラー分岐で `jo_status_code` と共に使用して、より豊富なフォールバックロジックとデバッグをサポートできます。 [詳細情報](../action/action-response.md)

* **ネイティブメッセージアクションとAdobe Campaign メッセージアクションの組み合わせ** - Journey Optimizerでは、Adobe Campaign v7/v8 メッセージアクションと、ネイティブチャネルアクションを、同じジャーニーで組み合わせることができるようになりました。 [詳細情報](../building-journeys/using-adobe-campaign-v7-v8.md)

* **ジャーニーでのジャーニーペイロードサイズの検証** - Journey Optimizerは、最適なパフォーマンスとシステムの安定性を確保するために、ジャーニーペイロードサイズを検証するようになりました。 ジャーニーを作成または公開すると、ペイロードサイズが推奨制限に近づいた、または推奨制限を超えた場合は、明確な警告とエラーが表示され、ジャーニー設定を最適化するための実用的なガイダンスも提供されます。 このプロアクティブな検証は、潜在的な問題を早期に特定し、ジャーニーのパフォーマンスを維持するのに役立ちます。 [詳細情報](../start/guardrails.md#message-content-size)

#### オーケストレーションキャンペーン

* **属性の選択と配分値のコピー** - オーケストレートキャンペーンの値の配分ビューから、値を直接選択またはコピーできるようになりました。 [詳細情報](../orchestrated/build-query.md)

* **オーディエンスのデータ使用ラベルの継承** - オーケストレートキャンペーンでオーディエンスを保存する際に、Adobe Experience Platformで適用されたラベルが自動的に引き継がれるようになり、手動の DULE タグ付けが減りました。 [詳細情報](../orchestrated/activities/save-audience.md)

* **定義済みのリターゲティングフィルター** – 調整されたキャンペーンのユースケースでより簡単にリターゲティングできるように、このリリースでは新しい <strong> キャンペーンフィードバックフィルター </strong> を導入しました。 これらのフィルターを使用すると、送信済み、開封のみ、開封済みまたはクリック済み、開封済みおよびクリック済みなどのメッセージエンゲージメントに基づいてオーディエンスを直接ターゲット設定し、再ターゲットする特定のキャンペーンまたは移行中キャンペーンを選択できます。 [詳細情報](../orchestrated/retarget.md)

* **パラメーターを含む定義済みフィルター** - オーケストレートキャンペーンで <strong> パラメーター </strong> を含む定義済みフィルターを作成して、再利用可能で編集可能なルールを実現できるようになりました。 [詳細情報](../orchestrated/predefined-filters.md)

* **送信前のメッセージ確認** - オーケストレーションされたキャンペーンを送信する前に、<strong> 確認手順 </strong> がデフォルトで有効になり、誤った送信を減らすことができるようになりました。 [詳細情報](../orchestrated/activities/channels.md#confirm-message-sending)

* **ユーザー生成メタデータのサポート** - <strong>executionMetadata ヘルパー関数 </strong> がオーケストレートキャンペーン用のパーソナライゼーションエディターで使用できるようになりました。これにより、任意のネイティブアクションにコンテキスト情報を添付し、外部システムに書き出すデータセットに保存できます。 [詳細情報](../personalization/functions/helpers.md#execution-metadata)

* **再開ボタン** - オーケストレーションされたキャンペーンに <strong> 再開ボタン </strong> が含まれるようになりました。これにより、キャンペーンを公開する前に、必要に応じて素早く実行を再開できます。 [詳細情報](../orchestrated/start-monitor-campaigns.md)

* **レートコントロールのサポート** - オーケストレーションされたキャンペーンで <strong> レートコントロール </strong> がサポートされるようになり、配信のペースを調整し、ボリュームの制約に合わせることができるようになりました。 [詳細情報](../orchestrated/activities/channels.md#rate-control)

#### 権限

* **ジャーニーおよびキャンペーンの自己承認を防ぐ** – 承認ポリシーを作成または設定する際に、ジャーニーまたはキャンペーンの作成者が独自のオブジェクトを承認できないようにするオプションを追加しました。 [詳細情報](../test-approve/approval-policies.md)

#### AI アシスタント

* **AI アシスタントのコンテンツ品質チェック** - ブランドの整合性に加えて、全体的な <strong> コンテンツ品質 </strong> を評価し、ブランドガイドラインに依存せずに、読みやすさ、凝集性、有効性に関する潜在的な問題を明らかにすることができます。 これらの自動チェックは、メッセージングの不明確、一貫性のないトーン、または構造的なギャップを特定するのに役立ちます。 公開日：2026 年 1 月 28 日（PT）。

## 近日リリース予定 {#jan-26-01-coming-soon}

今後数日間で、次の機能と機能強化がリリースされる予定です。**情報は変更される場合があります**。更新したリンク、画面、ドキュメントは、これらの更新が実稼動環境で公開すると共有されます。

### 機能

<table>
<thead>
<tr>
<th><strong>メッセージのエクスポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールおよび SMS チャネルで新しい <strong> メッセージエクスポート </strong> 機能が使用できるようになります。 この機能を使用すると、送信されたメッセージコンテンツを専用のExperience Platform データセットに自動的にエクスポートし、次のことが可能になります。</p>
<ul>
<li>コンプライアンス要件（HIPAA など）を満たす</li>
<li>法的請求およびカスタマーケアに関する問い合わせに対するメッセージのアーカイブ</li>
<li>個人に送信されたパーソナライズされたコンテンツのコピーを保持</li>
</ul>
<p>レコードは、取り込みから 7 暦日間、AJO メッセージ書き出しデータセットに保持されます。 この保持期間中に、Experience Platformの宛先を介して独自のストレージにデータを書き出すことができます。 この機能はチャネル設定レベルで有効になり、書き出されるメッセージを詳細に制御できます。</p>
<p>この機能は、メッセージ書き出しアドオン機能を購入した組織のメールおよび SMS チャネルでのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>セルフサービス移行ツール API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> 移行ツール API</strong> は、意思決定管理エンティティを Decisioning にプログラムで移行する際に使用できます。この機能は次のとおりです。</p>
<ul>
<li>柔軟な移行範囲（サンドボックス、オファーまたは決定レベル）</li>
<li>依存関係の自動分析と検証</li>
<li>完了した移行のロールバックサポート</li>
<li>オブジェクトマッピングを使用した詳細な移行レポート</li>
</ul>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>非表示時間（時間ベースの除外）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>通知の少ない時間では、メール、SMS、プッシュおよび WhatsApp チャネルに対して <strong> 時間ベースの除外 </strong> を定義できます。 これにより、特定の期間中にメッセージが送信されることがなくなり、顧客の好みやコンプライアンス要件を尊重するのに役立ちます。 <strong> ルールセット </strong> を通じて待ち時間を適用できます。このルールセットはキャンペーンやジャーニーの個々のアクションに割り当てられて、正確に制御できます。</p>
<p>以前に限定提供でリリースされたこの機能は、すべての環境で使用できます（一般提供）。 この一般提供リリースでは、この機能に、非表示時間が完了するまでキャンペーンアクションをキューに入れる機能と、アクティブ化された非表示時間ルールをプレビューする機能も含まれます。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーのダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はキャンペーンに限定されていましたが、<strong> ダイレクトメールチャネル </strong> をジャーニーキャンバスで使用できるようになり、ダイレクトメールをジャーニーに組み込むことができます。 ダイレクトメールは、ファイル抽出設定と時間ベースの頻度設定を使用して、バッチと 1 対 1 のジャーニーシナリオの両方でサポートされます。</p>
<p>以前に限定提供でリリースされたこの機能は、すべての環境で使用できます（一般提供）。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>調整されたキャンペーンのダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ダイレクトメールチャネルは、調整されたキャンペーンで使用できるようになります。 <strong> ダイレクトメールアクティビティ </strong> を使用すると、1 回限りのメッセージと繰り返しメッセージの両方について、調整されたキャンペーン内でダイレクトメールを簡単に送信できます。 ダイレクトメールプロバイダーに必要な <strong> 抽出ファイル </strong> の生成が自動化されます。 チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーにするクロスチャネルキャンペーンを作成できます。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタムアクションの監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい <strong> モニタリングダッシュボード </strong> と強化されたジャーニーステップイベントデータを使用して、カスタムアクションエンドポイントのヘルスとパフォーマンスについて詳しくinsightできるようになります。 成功した呼び出し、エラー、スループット、応答時間およびキューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
<p>以前に限定提供でリリースされたこの機能は、すべての環境で使用できます（一般提供）。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent内でのコンテンツの生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform Agent Orchestratorを活用し、Journey Optimizerで <strong>Journey Agent</strong> を使用できるようになります。これにより、自然言語インターフェイスを使用してジャーニーを分析できるようになります。 Journey Agentでは、チャネル固有のコンテンツを直接生成および管理し、メールやプッシュなどのチャネルのコンテンツを作成し、テンプレートを適用およびプレビューし、プロンプトを使用してトーンとスタイルを調整し、<strong> コンテンツDesigner</strong> でコンテンツを開いてコンテキスト内編集を行うことができます。</p>
<p>公開日：2026年2月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>プッシュおよび SMS チャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Decisioning</strong> を使用して、プッシュと SMS メッセージのコンテンツをパーソナライズおよび最適化できます。 決定ポリシー、<strong> 優先度スコア </strong>、式または AI モデルを使用して、顧客に最適なコンテンツを表示します。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コンテンツ決定アクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい <strong> コンテンツ決定アクティビティ </strong> は、パーソナライズされたオファーをカスタマージャーニーに直接統合するために、ジャーニーキャンバスで使用できるようになります。 このアクティビティを使用すると、決定ベースのコンテンツを配信し、ジャーニー全体を通じてそれらのオファーを参照できます。実施要件ベースのブランチを作成する条件や、オファーデータを外部システムに渡すカスタムアクションのほか、完全にパーソナライズされた顧客エクスペリエンスを構築するための他のアクティビティも同様です。</p>
<p>この機能は、すべての環境で使用できるようになります（一般提供）。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* **SMS Webhook** - <strong>Webhook</strong> はすべての SMS プロバイダーでサポートされます。 目的に応じて、各 Webhook を設定できます。受信メッセージをキャプチャする受信 Webhook と、配信の受信、ステータスの更新、その他のメッセージ関連イベントを受信するフィードバック Webhook。 公開日：2026 年 1 月 28 日（PT）。

* **プロファイルのタイムゾーンを使用してキャンペーンをスケジュール** - Campaign のスケジュール設定では、各プロファイルの <strong> タイムゾーン </strong> を使用して、目的のローカルタイムでメッセージを配信できます。 **注意**：この機能強化は、一連の組織（使用制限あり）でのみ使用できます。 公開日：2026 年 1 月 28 日（PT）。
