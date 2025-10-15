---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 1a5f6be689c9e91ee0dc0b5f024dbe8020424337
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 29%

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
<th><strong>ジャーニーのダイレクトメールチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はキャンペーンに限定されていましたが、ダイレクトメールチャネルがジャーニーキャンバスで使用できるようになり、ダイレクトメールをジャーニーに組み込めるようになりました。 ダイレクトメールは、ファイル抽出の設定と時間ベースの頻度設定のサポートにより、バッチと 1 対 1 のジャーニーシナリオの両方で使用できるようになりました。</p>
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
<th><strong>新しい実行メタデータヘルパー関数</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい executionMetadata ヘルパー関数が、パーソナライゼーションエディターで使用できます。 これを使用すると、任意のネイティブアクションにコンテキスト情報を追加し、外部システムに書き出すためにデータセットに取得できます。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>公開日：2025 年 10 月 13 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>実験エージェント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実験エージェントは、Web サイト、メール、プッシュメッセージおよびアプリケーションをまたいでデジタル実験を実行および管理する方法を最新化する、AI を利用したツールです。 Adobe Experience Platform AI プラットフォームと実験ツール上に構築された実験エージェントは、実験をより効率的に実行し、ビジネス目標を整理し、成功した内容、失敗した内容、次に実験する場所に焦点を当てた実用的なインサイトを生成するのに役立ちます。</p>
<p>新しいExperimentation Accelerator機能の一部として、エージェントは次の機能を提供します。</p>
<ul>
<li><strong> パフォーマンス：</strong> 実験で発生したことを明確に把握します</li>
<li><strong> インサイト：</strong> 結果が発生した理由の説明</li>
<li><strong> 機会：</strong> 実行する次のアクションに関するガイダンス</li>
</ul>
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>公開日：2025 年 10 月 9 日（PT）</p>
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
<!--img src="assets/do-not-localize/FILE.gif"-->
<!-- p>For more information, refer to the <a href="../FILE.md">detailed documentation</a>.</p -->
<p>公開日：2025 年 9 月 25 日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

- **キャンペーン、エクスペリエンス決定、ジャーニー**
   - **ターゲティングでの再利用可能なルールの選択** - ジャーニーやキャンペーンでメッセージの最適化機能を使用してターゲティングルールを使用する際に、ルールビルダーを活用できるようになりました。<!-- [Read more](../FILE.md) -->

- **チャネル - WhatsApp**
   - **WhatsApp チャネルの実行フィールド** - メールと SMS に加えて、WhatsApp のデフォルトの実行フィールドを更新できるようになりました。 また、WhatsApp ジャーニーアクティビティの詳細設定パラメーターまたは WhatsApp チャネル設定でグローバルに設定された実行フィールドを上書きすることもできます。<!-- [Read more](../FILE.md) -->

- **権限**
   - **ジャーニー/キャンペーンの作成者が承認できないようにする** – 承認ポリシーを作成または設定する際に、ジャーニー/キャンペーンの作成者が独自のオブジェクトを承認できないようにするオプションを追加しました。<!-- [Read more](../FILE.md) -->

- **チャネル - プッシュ**
   - **モバイルライブアクティビティ – プライベートベータ版** - ライブアクティビティは、モバイルアプリ内でリアルタイムの更新とインタラクティブなエクスペリエンスを提供し、ユーザーが進行中のイベントやタスクに関する情報をデバイスの画面に直接表示できるようにします。 この機能は、ユーザーがアプリを開くことなく、進行状況の追跡、イベントの更新、インタラクティブコンテンツなどのライブ情報を配信することで、エンゲージメントを強化します。<!-- [Read more](../FILE.md) -->

- **ジャーニー**
   - **新しいジャーニーアラート** – 公開日：2025 年 10 月 14 日（PT）
ジャーニーに対して、新しい事前設定されたアラートを使用できます。プロファイル破棄率を超えています（過去 5 分に入力したプロファイルに対するプロファイル破棄の割合がしきい値を超えています）、カスタムアクションエラー率を超えています（過去 5 分に成功した HTTP 呼び出しに対するカスタムアクションエラーの割合がしきい値を超えています）。<!-- [Read more](../FILE.md) -->

- **設定**
   - **ワンクリック登録解除 URL でのカスタム属性のサポート** – 公開日：2025 年 10 月 6 日（PT）
Journey Optimizerを使用すると、Adobe外で同意を管理している場合に、メール設定で独自のワンクリック購読解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が購読解除リンクをクリックすると、Journey Optimizerによって、プロファイル固有のデフォルトのパラメーターが同意更新イベントに追加されます。 登録解除メールアドレスをさらにパーソナライズするために、同意イベントに追加されるカスタム属性を定義できるようになりました。この機能は、8 月 25 日（PT）以降、カスタムのワンクリック購読解除 URL で既に使用できるようになり、限定提供で宛先（登録解除） オプション用にリリースされました。 アクセス権を取得するには、Adobe担当者にお問い合わせください。<!-- [Read more](../FILE.md) -->

- **チャネル - メール**
   - **メールへのPDF添付ファイル** – 公開日：2025 年 9 月 30 日（PT）
Journey Optimizerで送信されるメールメッセージに、静的PDF ファイルを添付できるようになりました。 プロファイルごとに、PDFの添付ファイルを含むメッセージを年間 6 件まで送信できます。 各添付ファイルに許可される最大ファイルサイズは 5 MB です。 その他のサイズまたはボリュームについては、PDF添付ファイルアドオンを購入できます。 詳しくは、アドビ担当者にお問い合わせください。

  >[!AVAILABILITY]
  >
  >以前は限定提供でリリースされていましたが、この改善はすべての環境で利用できるようになりました（一般提供）。

  <!-- [Read more](../FILE.md) -->

