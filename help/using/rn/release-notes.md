---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 50dbebcd16631f5df624c962af1a84da0846f53d
workflow-type: tm+mt
source-wordcount: '1849'
ht-degree: 23%

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

<!--**Release date**: January 27-28, 2026-->

[ 機能 ](#jan-26-01-features) および [ 改善 ](#jan-26-01-improv) の節では、既に使用可能な機能について説明し、[ 近日公開 ](#jan-26-01-coming-soon) では、後の公開日にスケジュールされている項目を一覧表示しています。

<!-- **The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date. 

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

### 新機能 {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>メッセージのエクスポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールおよび SMS チャネルで新しい <strong> メッセージエクスポート </strong> 機能が使用できるようになりました。 この機能を使用すると、送信されたメッセージコンテンツを専用のExperience Platform データセットに自動的にエクスポートし、次のことが可能になります。</p>
<ul>
<li>コンプライアンス要件（HIPAA など）を満たす</li>
<li>法的請求およびカスタマーケアに関する問い合わせに対するメッセージのアーカイブ</li>
<li>個人に送信されたパーソナライズされたコンテンツのコピーを保持</li>
</ul>
<p>レコードは、取り込みから 7 暦日間、AJO メッセージ書き出しデータセットに保持されます。 この保持期間中に、Experience Platformの宛先を介して独自のストレージに書き出すことができます。 この機能はチャネル設定レベルで有効になっており、書き出すメッセージを <strong> 詳細に制御 </strong> できます。</p>
<p>この機能は、メッセージ書き出しアドオン機能を購入した組織のメールおよび SMS チャネルでのみ使用できます。 詳しくは、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/message-export.gif"/></p>
<p>詳しくは、<a href="../configuration/message-export.md#message-export">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年1月28日（PT）</p>
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
<p>Adobe Journey Optimizerで <strong>web プッシュ通知 </strong> がサポートされるようになり、プッシュチャネルがモバイル以外にも拡大しました。 <strong> モバイルブラウザーとデスクトップブラウザー </strong> の両方にシームレスに通知を配信できるので、アプリを使用せずに、デバイス上で直接お客様にリーチできます。 この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、タイムリーでパーソナライズされたメッセージを用いて、リアルタイムでユーザーに関与できるようになります。</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>この機能は、以前はベータ版でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../push/push-configuration-web.md">詳細なドキュメント</a>を参照してください。</p>
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
<p>ダイレクトメールチャネルを調整されたキャンペーンで使用できるようになりました。 <strong> ダイレクトメールアクティビティ </strong> は、1 回限りのメッセージと繰り返しメッセージの両方について、オーケストレートキャンペーン内でのダイレクトメール送信を容易にします。 ダイレクトメールプロバイダーに必要な <strong> 抽出ファイル </strong> の生成プロセスを自動化する役割を果たします。 チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。</p>
<p><img src="assets/do-not-localize/dm-oc.gif"/></p>
<p>詳しくは、<a href="../orchestrated/activities/channels.md#channel">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年1月28日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent - ジャーニーの作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Agentの作成時にJourney Optimizer ユーザーが <strong> 自然言語インターフェイス </strong> を使用してマーケティングジャーニーを作成および設定できるようになりました。 これらの新しいスキルを使用すると、実務担当者は、<strong> 対話型プロンプト </strong> で要件を説明するだけで、すばやくジャーニーを作成できます。 このイノベーションにより、ジャーニーの作成プロセスが合理化され、マーケターは技術的な設定ではなく戦略に専念できます。</p>
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
<p>新しいJourney Optimizer API が使用できるようになりました。これにより、詳細、バージョン、設定など、<strong> キャンペーン関連のデータ </strong> をプログラムで取得して調べることができます。</p>
<p>詳しくは、<a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/" target="_blank">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年11月24日（PT）</p>
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
<p><strong> 事前承認済みのテーマ </strong> をすばやく適用して、すべてのメールで <strong> ブランドの一貫性 </strong> を確保し、キャンペーンの作成プロセスを迅速化し、高品質のメールを独自に作成しつつ、デザインチームへの依存を軽減できるようになりました。</p>
<p><img src="assets/do-not-localize/themes.gif"/></p>
<p>この機能は、以前はベータ版でリリースされていましたが、現在は一部の組織で使用できるようになりました（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../email/apply-email-themes.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年11月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#jan-26-01-improv}

#### AI

* **AI アシスタントコンテンツ品質チェック** - ブランドの整合性に加えて、全体的な <strong> コンテンツ品質 </strong> を評価して、ブランドガイドラインに依存せずに、<strong> 読みやすさ </strong>、凝集性、有効性に関する潜在的な問題を明らかにできるようになりました。 これらの自動チェックは、メッセージングの不明確、一貫性のないトーン、構造ギャップの特定に役立ちます。 [ 詳細情報 ](../content-management/brands-score.md#validate-quality)。 [ ビデオでこの機能を確認する ](https://video.tv.adobe.com/v/3470544/?learn=on)。

#### Experience Decisioning

#### ジャーニー

* **ネイティブメッセージアクションとAdobe Campaign メッセージアクションの組み合わせ** - Journey Optimizerでは、<strong>Adobe Campaign v7/v8</strong> メッセージアクションと <strong> ネイティブチャネルアクション </strong> を同じジャーニーで組み合わせることができるようになりました。 [詳細情報](../building-journeys/using-adobe-campaign-v7-v8.md)

  公開日：2026 年 1 月 27 日（PT）。

* **カスタムアクションエラー応答ペイロード** - カスタムアクションにオプションの <strong> エラー応答ペイロード </strong> を定義できるようになりました。 呼び出しが失敗すると、エラーペイロードがジャーニーコンテキスト（アクションの errorResponse ノードの下）で公開され、<strong> タイムアウト/エラー分岐 </strong> で `jo_status_code` と共に使用して、より豊富なフォールバックロジックとデバッグをサポートできます。 [詳細情報](../action/action-response.md)

  公開日：2026 年 1 月 27 日（PT）。

* **ジャーニーでのジャーニーのペイロードサイズの検証** - Journey Optimizerで <strong> ペイロードサイズ </strong> が検証され、最適なパフォーマンスとシステムの安定性が確保されるようになりました。 ジャーニーを作成または公開すると、ペイロードサイズが推奨制限に近づいた場合や推奨制限を超えた場合は、明確な <strong> 警告とエラー </strong> が表示され、ジャーニー設定を最適化するための実用的なガイダンスも示されます。 このプロアクティブな検証は、潜在的な問題を早期に特定し、ジャーニーのパフォーマンスを維持するのに役立ちます。 [詳細情報](../start/guardrails.md#journey-payload-size)

  公開日：2026 年 1 月 27 日（PT）。


* **ジャーニーアラート** – 新しい <strong> 事前設定済みのアラート </strong> をジャーニーで使用できます。
   * <strong> プロファイル破棄率を超えています </strong> – 過去 5 分に入力されたプロファイルに対するプロファイル破棄の割合が、しきい値を超えています
   * <strong> カスタムアクションエラー率を超えました </strong> – 過去 5 分に成功した HTTP 呼び出しに対するカスタムアクションエラーの割合が、しきい値を超えました
   * <strong> プロファイルエラー率を超えています </strong> – 過去 5 分に入力されたプロファイルに対する、エラーのプロファイルの割合が、しきい値を超えています

  詳しくは、[詳細なドキュメント](../reports/alerts.md)を参照してください。

  公開日：2025 年 10 月 14 日（PT）。

#### オーケストレーションキャンペーン

* **オーディエンスのデータ使用ラベルの継承** - Adobe Experience Platformで適用されたラベルは、調整されたキャンペーンで <strong> オーディエンス </strong> を保存する際に自動的に引き継がれるようになり、手動の <strong>DULE タグ付け </strong> を減らしました。 [詳細情報](../orchestrated/activities/save-audience.md)

* **パラメーターを含む定義済みフィルター** - オーケストレートキャンペーンで <strong> パラメーター </strong> を含む <strong> 定義済みフィルター </strong> を作成して、再利用可能で編集可能なルールを使用できるようになりました。 [詳細情報](../orchestrated/predefined-filters.md)

* **属性の選択と配分値のコピー** - オーケストレートキャンペーンの <strong> 値の配分 </strong> ビューから直接値を選択またはコピー <strong> できるようになりました </strong>。 [詳細情報](../orchestrated/build-query.md)

* **送信前のメッセージ確認** - オーケストレーションされたキャンペーンを送信する前に、<strong> 確認手順 </strong> がデフォルトで有効になり、誤った送信を減らすことができるようになりました。 [詳細情報](../orchestrated/activities/channels.md#confirm-message-sending)

* **定義済みのリターゲティングフィルター** – 調整されたキャンペーンのユースケースでより簡単にリターゲティングできるように、このリリースでは新しい <strong> キャンペーンフィードバックフィルター </strong> を導入しました。 これらのフィルターを使用すると、送信済み、開封のみ、開封済みまたはクリック済み、開封済みおよびクリック済みなどの <strong> メッセージエンゲージメント </strong> に基づいてオーディエンスを直接ターゲット設定し、再ターゲットする特定のキャンペーンまたは移行中キャンペーンを選択できます。 [詳細情報](../orchestrated/retarget.md)

* **レートコントロールのサポート** - オーケストレーションされたキャンペーンで <strong> レートコントロール </strong> がサポートされるようになり、配信のペースを調整し、<strong> ボリュームの制約 </strong> に合わせることができるようになりました。 [詳細情報](../orchestrated/activities/channels.md#rate-control)

* **再起動ボタン** - オーケストレーションされたキャンペーンに <strong> 再起動ボタン </strong> が含まれるようになりました。キャンペーンを公開する前に、必要に応じて <strong> 実行を素早く </strong> 再起動）できます。 [詳細情報](../orchestrated/start-monitor-campaigns.md)

* **ユーザー生成メタデータのサポート** - <strong>executionMetadata ヘルパー関数 </strong> がオーケストレートキャンペーン用のパーソナライゼーションエディターで使用できるようになりました。これにより、任意のネイティブアクションにコンテキスト情報を添付し、外部システムに書き出すデータセットに保存できます。 [詳細情報](../personalization/functions/helpers.md#execution-metadata)

  公開日：2026 年 1 月 27 日（PT）。

#### キャンペーン

* **プロファイルタイムゾーンを使用したキャンペーンのスケジュール設定** - Campaign のスケジュール設定で、各プロファイルの <strong> タイムゾーン </strong> を使用して、目的のローカルタイムでメッセージを配信できるようになりました。 [詳細情報](../campaigns/campaign-schedule.md)

  **注意**：この機能強化は、一連の組織（使用制限あり）でのみ使用できます。

  公開日：2026 年 1 月 27 日（PT）。

#### 権限

* **ジャーニーおよびキャンペーンの自己承認を防ぐ** - <strong> 承認ポリシー </strong> を作成または設定する際に、ジャーニーまたはキャンペーンの作成者が <strong> 独自のオブジェクトを承認 </strong> できないようにするオプションを追加しました。 [詳細情報](../test-approve/approval-policies.md)

  公開日：2026 年 1 月 27 日（PT）。

## 近日リリース予定 {#jan-26-01-coming-soon}

今後数日間で、次の機能と機能強化がリリースされる予定です。**情報は変更される場合があります**。更新したリンク、画面、ドキュメントは、これらの更新が実稼動環境で公開すると共有されます。

### 機能

<table>
<thead>
<tr>
<th><strong>ジャーニーのダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はキャンペーンに限定されていましたが、<strong> ダイレクトメール </strong> チャネルがジャーニーキャンバスで使用できるようになり、ダイレクトメールをジャーニーに組み込めるようになりました。 ダイレクトメールは、ファイル抽出の設定と時間ベースの頻度設定をサポートし、<strong> バッチと 1:1 のジャーニーシナリオ </strong> の両方で使用できるようになりました。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p><strong> 無表示時間 </strong> では、メール、SMS、プッシュ、WhatsApp の各チャネルに対して、時間ベースの除外を定義できます。 これにより、特定の期間中にメッセージが送信されないようにし、顧客の好みやコンプライアンスの要件を尊重するのに役立ちます。 クワイエットアワーは、キャンペーンやジャーニー内の個々のアクションに割り当てて、正確な制御を行うことができる<strong>ルールセット</strong>を通じて適用できます。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を使用できます。 この一般提供リリースで、機能に、顧客が非表示時間の完了までキャンペーンアクションをキューに入れる機能と、アクティブ化された非表示時間ルールをプレビューする機能が含まれるようになりました。</p>
<p>公開日：2026年1月29日（PT）</p>
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
<p><strong> 移行ツール API</strong> が、意思決定管理エンティティを Decisioning にプログラムで移行する際に使用できるようになりました。この機能は次のとおりです。</p>
<ul>
<li>柔軟な移行範囲（サンドボックス、オファーまたは決定レベル）</li>
<li>依存関係の自動分析と検証</li>
<li>完了した移行のロールバックサポート</li>
<li>オブジェクトマッピングを使用した詳細な移行レポート</li>
</ul>
<p>公開日：2026年1月29日（PT）</p>
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
<p>新しい監視ダッシュボードと強化されたジャーニーステップイベントデータを使用して、<strong> カスタムアクションエンドポイント </strong> の正常性とパフォーマンスをより深くinsightできます。 成功した呼び出し、エラー、スループット、応答時間およびキューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>公開日：2026年1月29日（PT）</p>
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
<p>Adobe Experience Platform Agent Orchestratorを活用した <strong>Journey Agent</strong> はJourney Optimizerで利用でき、自然言語インターフェイスを通じてジャーニーを分析できます。 また、Journey Agentで直接 <strong> コンテンツを生成および管理 </strong>、メールやプッシュなどのチャネルのコンテンツを作成、テンプレートを適用およびプレビュー、プロンプトによるトーンとスタイルの調整、コンテキスト内編集用にコンテンツDesignerで開くこともできます。</p>
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
<p><strong>Decisioning</strong> を使用して、<strong> プッシュと SMS</strong> メッセージのコンテンツをパーソナライズおよび最適化できるようになりました。 優先度スコア、式または AI モデルを使用して、顧客に最適なコンテンツを表示します。</p>
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
<p>ジャーニーキャンバスで新しい <strong> コンテンツ決定アクティビティ </strong> が使用できるようになり、<strong> パーソナライズされたオファー </strong> をカスタマージャーニーに直接統合できます。 このアクティビティを使用すると、決定ベースのコンテンツを配信し、ジャーニー全体でこれらのオファーを参照できます。実施要件ベースのブランチを作成する条件、外部システムにオファーデータを渡すカスタムアクション、完全にパーソナライズされたカスタマーエクスペリエンスを構築するその他のアクティビティなどです。</p>
<p>この機能は、すべての環境で使用できるようになります（一般提供）。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* **SMS Webhook** - <strong>Webhook</strong> がすべての SMS プロバイダーでサポートされるようになりました。 目的に応じて各 Webhook を設定できます。受信メッセージをキャプチャする受信 Webhook および配信の受信、ステータスの更新、その他のメッセージ関連イベントを受信するフィードバック Webhook。

  公開日：2026 年 1 月 30 日（PT）。

* **決定項目にフラグメントを添付** - Journey Optimizerでは、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できる <strong> フラグメント </strong> を <strong> 決定項目 </strong> に添付する機能が提供されるようになりました。

  公開日：2026 年 1 月 30 日（PT）。
