---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: d98b15b24a21f35703e88d3dce7a990f1aa73ba9
workflow-type: tm+mt
source-wordcount: '2342'
ht-degree: 22%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。


## 2026 年 1 月プレリリースノート {#jan-26-01-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

詳しくは、[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**：2026年1月26日（PT）

### 新機能 {#jan-26-01-features}

<table>
<thead>
<tr>
<th><strong>ジャーニーのアクションアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、新しい汎用 <strong> アクションアクティビティ </strong> をサポートしています。このアクティビティを使用すると、単一のアクションと <strong> 複数アクションのインバウンドアクショングループ </strong> の両方を設定でき、ジャーニーキャンバス内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13290">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-111916"> 製品 JIRA タスクへのリンク </a></p>
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
<p>新しい <strong> モニタリングダッシュボード </strong> と強化されたジャーニーステップイベントデータを使用して、カスタムアクションエンドポイントの正常性とパフォーマンスをより深くinsightできます。 成功した呼び出し、エラー、スループット、応答時間およびキューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13981">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-126869"> 製品 JIRA タスクへのリンク </a></p>
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
<p>通知の少ない時間では、メール、SMS、プッシュおよび WhatsApp チャネルに対して <strong> 時間ベースの除外 </strong> を定義できます。 これにより、特定の期間中にメッセージが送信されないようにし、顧客の好みやコンプライアンスの要件を尊重するのに役立ちます。 クワイエットアワーは、キャンペーンやジャーニー内の個々のアクションに割り当てて、正確な制御を行うことができる<strong>ルールセット</strong>を通じて適用できます。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を使用できます。 この一般提供リリースで、機能に、顧客が非表示時間の完了までキャンペーンアクションをキューに入れる機能と、アクティブ化された非表示時間ルールをプレビューする機能が含まれるようになりました。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13986">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-63912"> 製品 JIRA タスクへのリンク </a></p>
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
<p>以前はキャンペーンに限定されていましたが、<strong> ダイレクトメールチャネル </strong> が <strong> ジャーニーキャンバス </strong> で使用できるようになり、ダイレクトメールをジャーニーに組み込めるようになりました。 ダイレクトメールは、ファイル抽出の設定と時間ベースの頻度設定のサポートにより、バッチと 1 対 1 のジャーニーシナリオの両方で使用できるようになりました。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13543">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-38399"> 製品 JIRA タスクへのリンク </a></p>
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
<p>Adobe Journey Optimizerで <strong>web プッシュ通知 </strong> がサポートされるようになり、プッシュチャネルがモバイル以外にも拡大しました。 モバイルブラウザーとデスクトップブラウザーの両方にシームレスに通知を配信できるので、アプリを使用せずに、デバイス上で直接お客様にリーチできます。 この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、タイムリーでパーソナライズされたメッセージを用いて、リアルタイムでユーザーに関与できるようになります。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13581">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-37866"> 製品 JIRA タスクへのリンク </a></p>
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
<p>プッシュおよび SMS ジャーニーとキャンペーンに <strong> 決定ポリシー </strong> を追加できるようになりました。 決定ポリシーは、配信する最適なコンテンツを各オーディエンスメンバーに応じて動的に返すことを目的に、決定エンジンを活用するオファーのためのコンテナです。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13426">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/DOCAC-13425">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-55817"> 製品 JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-55818"> 製品 JIRA タスクへのリンク </a></p>
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
<p>ダイレクトメールチャネルを調整されたキャンペーンで使用できるようになりました。 <strong> ダイレクトメールアクティビティ </strong> は、1 回限りのメッセージと繰り返しメッセージの両方について、オーケストレートキャンペーン内でのダイレクトメール送信を容易にします。 ダイレクトメールプロバイダーに必要な <strong> 抽出ファイル </strong> の生成プロセスを自動化する役割を果たします。 チャネルアクティビティを調整されたキャンペーンキャンバスに組み合わせて、顧客の行動とデータに基づいてアクションをトリガーできるクロスチャネルキャンペーンを作成できます。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13379">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-82584"> 製品 JIRA タスクへのリンク </a></p>
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
<p>Adobe Experience Platformの Talon.One、Capilary、Kobie の各ロイヤルティアプリで、新しい <strong> ソースコネクタ </strong> が利用できるようになりました。 これらのコネクタを使用すると、ロイヤルティデータを Adobe Experience Platform にシームレスにストリームし、Journey Optimizer でこれらのデータを活用できます。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13372">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メッセージのエクスポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>アーカイブやコンプライアンスの目的で、特定のデータセットに <strong> 送信済み配信を書き出す </strong> ことができるようになりました。 この機能は、メールだけでなく、SMS などの他のチャネルでも使用できます。 メッセージ書き出しデータセットのデータ保持が <strong>7 日 </strong> になりました。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-12915">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-105313"> 製品 JIRA タスクへのリンク </a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>アクションキャンペーンを取得する新しい API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい <strong>Journey Optimizer API</strong> が利用可能になり、詳細、バージョン、設定など、キャンペーン関連のデータをプログラムで取得し、調べることができるようになりました。</p>
<p>詳しくは、<a href="https://developer.adobe.com/journey-optimizer-apis/references/campaigns-retrieve/">詳細なドキュメント</a>を参照してください。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13506">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-96195"> 製品 JIRA タスクへのリンク </a></p>
<p>公開日：2025年11月24日（PT）</p>
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
<p>ジャーニーライフサイクルイベントとカスタムアクションのパフォーマンスの監視と追跡に役立つ、3 つの新しい <strong> ジャーニーアラート </strong> が使用できるようになりました。</p>
<ul>
<li><strong>ジャーニーが公開されました</strong>：ジャーニーキャンバスで実務担当者がジャーニーを公開した際に通知を受信します。</li>
<li><strong>ジャーニーが完了しました</strong>：ジャーニーが完了した際に、ジャーニーのタイプ（オーディエンスを読み取りまたはイベントトリガー）に基づいた特定の定義を使用してアラートを受信します。</li>
<li><strong>カスタムアクションキャップがトリガーされました</strong>：カスタムアクションエンドポイントでキャッピングをアクティブ化した際に通知されます。</li>
</ul>
<p>これらのアラートは、組織レベルまたは特定のジャーニーごとに登録できます。</p>
<p>詳しくは、<a href="../reports/alerts.md#journey-alerts">詳細なドキュメント</a>を参照してください。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13465">DOCAC JIRA タスクへのリンク</a></p>
<p>公開日：2025年11月5日（PT）</p>
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
<p><strong> 事前承認済みのテーマ </strong> を迅速に適用して、すべてのメールでブランドの一貫性を確保し、キャンペーンの作成プロセスを迅速化し、デザイン チームへの依存を減らしながら、高品質のメールを独自に作成できるようになりました。</p>
<p>この機能は、以前はベータ版でリリースされていましたが、現在は一部の組織で使用できるようになりました（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/themes.gif">
<p>詳しくは、<a href="../email/apply-email-themes.md">詳細なドキュメント</a>を参照してください。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-12941">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/NEO-88838"> 製品 JIRA タスクへのリンク </a></p>
<p>公開日：2025年11月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#jan-26-01-improv}

このリリースに含まれる機能強化を以下に示します。

#### AI

* **AI アシスタントのコンテンツ品質チェック** - ブランドの整合性に加えて、全体的な <strong> コンテンツ品質 </strong> を評価して、ブランドガイドラインに依存せずに、読みやすさ、凝集性、有効性に関する潜在的な問題を明らかにできるようになりました。 これらの自動チェックは、メッセージングの不明確、一貫性のないトーン、構造ギャップの特定に役立ちます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13917">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-103238"> 製品 JIRA タスクへのリンク </a>
* **新しい「カラー」タブでブランドを更新** - ブランドガイドラインは、すべてのタッチポイントでブランドを一貫して提示するのに役立ちます。 新しい <strong> カラーセクション </strong> では、エクスペリエンスをまたいでカラーの選択、整理、適用の方法を概説し、ブランドのカラーシステムの標準を定義します。 これにより、プライマリー、セカンダリー、アクセント、ニュートラルカラーの一貫性のある使用が保証され、凝集してアクセス可能で認識可能なブランドアイデンティティがサポートされます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13811">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-121183"> 製品 JIRA タスクへのリンク </a>

#### キャンペーン

* **プロファイルタイムゾーンを使用したキャンペーンのスケジュール設定** - Campaign のスケジュール設定で、各プロファイルの <strong> タイムゾーン </strong> を使用して、目的のローカルタイムでメッセージを配信できるようになりました。

  **注意**：この機能強化は、一連の組織（使用制限あり）でのみ使用できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-11534">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-43782"> 製品 JIRA タスクへのリンク </a>

#### チャネル

* **SMS Webhook：フェーズ II** – 説明を入力します。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13978">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-93914"> 製品 JIRA タスクへのリンク </a>

* **WhatsApp 再販オファー** – 提供する説明。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13669">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-86420"> 製品 JIRA タスクへのリンク </a>

#### E メールデザイナー

* **E メールデザイナーでのインプレース修正** - <strong>AI を活用した自動コンテンツ提案 </strong> は、コンテンツの検証中に違反が検出された場合に、E メールDesignerで使用できるようになりました。 コンテンツにブランドガイドラインとの不一致のフラグが設定されたり、品質基準に失敗した場合、システムはプロアクティブに修正された代替コンテンツを生成し、インラインでレビューおよび適用できるので、コンプライアンスが向上し、生産が迅速化されます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13979">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-95365"> 製品 JIRA タスクへのリンク </a>

#### Experience Decisioning

* **ジャーニーの判別** - <strong> 式と AI モデル </strong> を使用して、顧客プロファイル属性とコンテキスト要因に基づいてジャーニーの優先度スコアを自動的に上げ、顧客が最も関連性の高いジャーニーにエントリできるようにできるようになりました。

  **注意**：この機能強化は、一連の組織（使用制限あり）でのみ使用できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13976">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-78932"> 製品 JIRA タスクへのリンク </a>

* **exd sandbox tooling documentation - update** – 提供される説明。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13596">DOCAC JIRA タスクへのリンク </a>

* **セルフサービス移行ツール API** - オファー管理エンティティを Experience Decisioning に移行するために、新しいセットの <strong> 移行ツール API</strong> を使用できます。 このツールを使用すると、依存関係の解決とロールバック機能により、サンドボックス間をシームレスに移行できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13837">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-109695"> 製品 JIRA タスクへのリンク </a>

* **決定項目にフラグメントを添付** - Journey Optimizerでは、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで利用できる決定項目に <strong> フラグメント </strong> を添付する機能が提供されるようになりました。

  **メモ**：以前に限定提供でリリースされていましたが、この改善をすべての環境で利用できるようになりました（一般提供）。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13418">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-110282"> 製品 JIRA タスクへのリンク </a>

#### ジャーニー

* **ジャーニーのカスタムアクションでのエラー応答ペイロードの活用** - カスタムアクションにオプションの <strong> エラー応答ペイロード </strong> を定義できるようになりました。 呼び出しが失敗すると、エラーペイロードがジャーニーコンテキストで公開され、タイムアウト/エラー分岐で使用して、より豊富なフォールバックロジックとデバッグをサポートできます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13977">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-113125"> 製品 JIRA タスクへのリンク </a>

* **ネイティブメッセージアクションとAdobe Campaign メッセージアクションの組み合わせ** - Journey Optimizerでは、Adobe Campaign v7/v8 メッセージアクションと、ネイティブチャネルアクションを、同じジャーニーで組み合わせることができるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13974">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-113103"> 製品 JIRA タスクへのリンク </a>

* **ジャーニーでのジャーニーのペイロードサイズの検証** - Journey Optimizerで <strong> ペイロードサイズ検証 </strong> が提供されるようになり、最適なパフォーマンスとシステムの安定性を確保できるようになりました。 ジャーニーを作成または公開すると、ペイロードサイズが推奨制限に近づいた、または推奨制限を超えた場合は、明確な警告とエラーが表示され、ジャーニー設定を最適化するための実用的なガイダンスも提供されます。 このプロアクティブな検証は、潜在的な問題を早期に特定し、ジャーニーのパフォーマンスを維持するのに役立ちます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13840">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-122236"> 製品 JIRA タスクへのリンク </a>

* **ジャーニーでの複数のインバウンドアクション** - ジャーニーオーケストレーションを簡素化するために、1 つのジャーニーで <strong> 複数のインバウンドアクション </strong> を定義できるようになりました。 以前はキャンペーンで使用できましたが、この機能を使用すると、複数のコードベースのエクスペリエンス、アプリ内メッセージ、コンテンツカード、web アクションを異なる場所に同時に配信でき、各アクションに特定のコンテンツを含めることができます。

  **メモ**：以前に限定提供でリリースされていましたが、この改善をすべての環境で利用できるようになりました（一般提供）。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13453">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-111916"> 製品 JIRA タスクへのリンク </a>

#### オーケストレーションキャンペーン

* **属性の選択と配分値のコピー** - オーケストレートキャンペーンの値の配分ビューから、値を直接選択またはコピーできるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13973">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-105244"> 製品 JIRA タスクへのリンク </a>

* **オーディエンスのデータ使用ラベルの継承** - <strong>Adobe Experience Platformで適用されたデータ使用ラベル </strong> は、調整されたキャンペーンでオーディエンスを保存する際に自動的に引き継がれるようになり、手動の DULE タグ付けを減らしました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13972">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-120769"> 製品 JIRA タスクへのリンク </a>

* **定義済みのリターゲティングフィルター** – 調整されたキャンペーンのユースケースでより簡単にリターゲティングできるように、このリリースでは新しい <strong> リターゲティングフィルター </strong> を導入しました。 これらのフィルターを使用すると、送信済み、開封のみ、開封済みまたはクリック済み、開封済みおよびクリック済みなどのメッセージエンゲージメントに基づいてオーディエンスを直接ターゲット設定し、再ターゲットする特定のキャンペーンまたは移行中キャンペーンを選択できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13971">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-116701"> 製品 JIRA タスクへのリンク </a>

* **パラメーターを含む定義済みフィルター** - オーケストレートキャンペーンで <strong> パラメーターを含むフィルター </strong> を作成して、再利用可能で編集可能なルールを使用できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13970">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-115431"> 製品 JIRA タスクへのリンク </a>

* **送信前のメッセージ確認** - オーケストレーションされたキャンペーンを送信する前に、<strong> 確認手順 </strong> がデフォルトで有効になり、誤った送信を減らすことができるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13927">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-87219"> 製品 JIRA タスクへのリンク </a>

* **ユーザー生成メタデータのサポート** - <strong>executionMetadata ヘルパー関数 </strong> がオーケストレートキャンペーンのパーソナライゼーションエディターで使用できるようになりました。これにより、任意のネイティブアクションにコンテキスト情報を添付し、外部システムに書き出すためにデータセットに保存できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13923">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-112697"> 製品 JIRA タスクへのリンク </a>

* **再開ボタン** - オーケストレーションされたキャンペーンに <strong> 再開ボタン </strong> が含まれるようになりました。これにより、キャンペーンを公開する前に、必要に応じて素早く実行を再開できます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13920">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-106020"> 製品 JIRA タスクへのリンク </a>

* **レートコントロールのサポート** - オーケストレーションされたキャンペーンで <strong> レートコントロール </strong> がサポートされるようになり、配信のペースを調整し、ボリュームの制約に合わせることができるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13764">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-113254"> 製品 JIRA タスクへのリンク </a>

#### 権限

* **ジャーニーとキャンペーンの自己承認の防止** – 作成者が独自のジャーニーやキャンペーンを承認できないことを承認ワークフローで必須にできるようになり、<strong> 職務の分離 </strong> が改善されました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13472">DOCAC JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-99957"> 製品 JIRA タスクへのリンク </a> <a href="https://jira.corp.adobe.com/browse/CJM-95676"> 製品 JIRA タスクへのリンク </a>

## 近日リリース予定 {#jan-26-01-coming-soon}

今後数日間で、次の機能と機能強化がリリースされる予定です。**情報は変更される場合があります**。更新したリンク、画面、ドキュメントは、これらの更新が実稼動環境で公開すると共有されます。

<table>
<thead>
<tr>
<th><strong>Journey Agent内でのコンテンツの生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform Agent Orchestratorを活用した <strong>Journey Agent</strong> はJourney Optimizerで利用でき、自然言語インターフェイスを通じてジャーニーを分析できます。 また、Journey Agentで直接チャネル固有のコンテンツを生成および管理できるようになりました。メールやプッシュなどのチャネル用のコンテンツの作成、テンプレートの適用とプレビュー、プロンプトによるトーンとスタイルの調整、コンテキスト内編集用のコンテンツをコンテンツDesignerで開くこともできます。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-13980">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-111882"> 製品 JIRA タスクへのリンク </a></p>
<p>公開日：2026年2月2日（PT）</p>
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
<p>ジャーニーキャンバスの専用のコンテンツ決定アクティビティを通じて、ジャーニーに <strong> パーソナライズされたオファー </strong> を含め、それらをジャーニーアクティビティ（条件やカスタムアクションなど）で使用できるようになりました。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-12902">DOCAC JIRA タスクへのリンク </a><a href="https://jira.corp.adobe.com/browse/CJM-99223"> 製品 JIRA タスクへのリンク </a></p>
<p>公開日：2026年2月2日（PT）</p>
</td>
</tr>
</tbody>
</table>
