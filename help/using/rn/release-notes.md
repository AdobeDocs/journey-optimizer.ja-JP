---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b53f9279a8698e99683cd6e75a7e746102e3e094
workflow-type: tm+mt
source-wordcount: '1534'
ht-degree: 29%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。

このモデルにより、リリースノートは毎月のリリースの間に更新されます。リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2026 年 2 月リリースノート {#feb-26-01-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

詳しくは、[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**：2026年2月17日（PT）

### 新機能 {#feb-26-01-features}

<table>
<thead>
<tr>
<th><strong>送信メッセージのウェーブ送信</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> キャンペーン </strong> または <strong> ジャーニー </strong> からのアウトバウンドメッセージを、制御された <strong> バッチ </strong> で時間をかけて配信するようにスケジュールできます。</p>
<p>Wave 送信には、次の利点があります。</p>
<ul>
<li><strong> 配信品質 </strong> の向上 – 送信を時間の経過と共に拡散して、強力な <strong> 送信者の評判 </strong> を維持し、スパムとしてフラグが立てられるリスクを軽減します。</li>
<li><strong> 読み込み制御 </strong> – 一度に送信するメッセージの数を制限して、ダウンストリームのシステム（コールセンター、ランディングページなど）が多くなりすぎないようにします。</li>
<li>大量で時間に敏感なユースケース – 大規模なオーディエンスや、タイミングを制御する必要がある場合（コールセンターの処理能力、ランプアップ、時間限定オファーなど）に適しています。</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーの判別</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> 式 </strong> と <strong>AI モデル </strong> を使用して、顧客プロファイル属性とコンテキスト要因に基づいて <strong> ジャーニー優先度スコア </strong> を自動的にブーストし、顧客が最も関連性の高いジャーニーにエントリできるようになりました。</p>
<p>この機能は、一連の組織でのみ使用できます（<strong> 限定提供 </strong>）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent：チャネルコンテンツの作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Adobe Experience Platform Agent Orchestrator</strong> を活用した <strong>Journey Agent</strong> はJourney Optimizerで利用でき、<strong> 自然言語インターフェイス </strong> を通じてジャーニーを分析できます。 また、Journey Agentで直接チャネル固有のコンテンツを生成および管理したり、メールやプッシュなどのチャネルのコンテンツを作成したり、テンプレートを適用およびプレビューしたり、プロンプトを使用してトーンとスタイルを調整したり、<strong> コンテンツDesigner</strong> でコンテンツを開いてコンテキスト内編集を行ったりできるようになりました。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>モバイルライブアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> ライブアクティビティ </strong> モバイルアプリ内に <strong> リアルタイムの更新 </strong> とインタラクティブなエクスペリエンスを提供し、ユーザーが進行中のイベントやタスクに関する情報をデバイスの画面に直接表示できるようにします。 この機能は、ユーザーがアプリを開かなくても、進行状況のトラッキング、イベントの更新、インタラクティブコンテンツなどのライブ情報を配信することで、エンゲージメントを強化します。</p>
<p>以前ベータ版でリリースされていましたが、この機能を、すべての環境で利用できるようになりました（<strong> 一般提供 </strong>）。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーのアクションアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、新しい汎用 <strong> アクションアクティビティ </strong> をサポートしています。これにより、単一のアクションと <strong> 複数アクションのインバウンドアクショングループ </strong> の両方を設定でき、<strong> ジャーニーキャンバス </strong> 内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>ビルトインのチャネルアクションに <strong> 最適化 </strong> を追加する機能。</li>
<li>任意のアクションに <strong> 実験 </strong> オプションと <strong> 多言語 </strong> オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p>Adobe Journey Optimizer は <strong>web プッシュ通知</strong>をサポートするようになり、プッシュチャネルがモバイル以外にも拡張されました。モバイルブラウザーとデスクトップブラウザーの両方に通知をシームレスに配信できるので、アプリを必要とせずにデバイス上で直接顧客にリーチできます。この機能強化により、既にモバイルプッシュで使用できるのと同じ <strong> オーサリングワークフロー </strong> ターゲティング機能 <strong> を活用して、パーソナライズされたメッセージをリアルタイムでタイムリーにユーザーに提供 </strong> きます。</p>
<p>以前ベータ版でリリースされていましたが、この機能を、すべての環境で利用できるようになりました（<strong> 一般提供 </strong>）。</p>
<p>公開日：2026年2月13日（PT）</p>
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
<p><strong> パーソナライズされたオファー </strong> をカスタマージャーニーに直接統合するために、<strong> ジャーニーキャンバス </strong> で新しい <strong> コンテンツ決定アクティビティ </strong> が使用できるようになりました。 このアクティビティを使用すると、決定ベースのコンテンツを配信し、ジャーニー全体でこれらのオファーを参照できます。実施要件ベースのブランチを作成する条件、外部システムにオファーデータを渡すカスタムアクション、完全にパーソナライズされたカスタマーエクスペリエンスを構築するその他のアクティビティなどです。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（<strong> 一般提供 </strong>）。</p>
<p><img src="assets/do-not-localize/content-decision.gif"/></p>
<p>詳しくは、<a href="../building-journeys/content-decision.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月11日（PT）</p>
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
<p><strong> 移行ツール API</strong> が、<strong> 意思決定管理 </strong> エンティティを <strong>Decisioning</strong> にプログラムで移行できるようになりました。その特徴は次のとおりです。</p>
<ul>
<li>柔軟な移行範囲（<strong> サンドボックス </strong>、<strong> オファー </strong>、または <strong> 決定 </strong> レベル）</li>
<li>自動 <strong> 依存関係分析 </strong> および検証</li>
<li>完了した移行の <strong> ロールバックサポート </strong></li>
<li>オブジェクトマッピングを含む詳細な移行レポート</li>
</ul>
<p>詳しくは、<a href="../experience-decisioning/decisioning-migration-api.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月3日（PT）</p>
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
<p>新しい <strong> モニタリングダッシュボード </strong> と強化された <strong> ジャーニーステップイベントデータ </strong> を使用して、<strong> カスタムアクションエンドポイント </strong> の正常性とパフォーマンスをより深くinsightできます。 成功した呼び出し、エラー、スループット、応答時間、キューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（<strong> 一般提供 </strong>）。</p>
<p>詳しくは、<a href="../action/reporting.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>SMS チャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Decisioning</strong> を使用して、<strong>SMS メッセージ </strong> のコンテンツをパーソナライズおよび最適化できるようになりました。 <strong> 優先度スコア </strong>、<strong> 式 </strong> または <strong>AI モデル </strong> を使用して、顧客に最適なコンテンツを表示します。</p>
<p>詳しくは、<a href="../experience-decisioning/create-decision.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#feb-26-01-improv}

このリリースに含まれる機能強化を以下に示します。

#### 設定

* **ジャーニー式でのエクスペリエンスイベントの使用** - 2026 年 4 月 1 日（PT）以降、ジャーニー式でのエクスペリエンスイベント属性の使用は、過去 90 日間にこの機能を使用していない組織ではサポートされなくなります。 この機能は、2025 年 7 月 8 日（PT）以降、新規のお客様は使用できなくなっています。 代替手段については、[&#x200B; ジャーニーでのエクスペリエンスイベントの参照 &#x200B;](../building-journeys/exp-event-lookup.md) を参照してください。


* **サブドメインデリゲーション方法の切り替え** - <strong> サブドメインデリゲーション </strong> 方法を別の方法に切り替えられるようになりました。 これにより、<strong>CNAME デリゲーション </strong> モードを使用してドメインを <strong> カスタムデリゲーション </strong> メソッドに移行して、会社のセキュリティポリシーに準拠することができます。

  **注意**：この機能は一連の組織でのみ使用できます（<strong> 使用制限あり </strong>）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。


#### E メールデザイナー

* **ブランドテーマを使用して画像をメールテンプレートに変換** - Journey Optimizerで画像をメールテンプレートに変換する際に、<strong> テーマ </strong> を入力として使用して、生成されたHTMLが <strong> ブランドパラメーターに従うようになりました </strong>。 背景色、ボタンの色、フォント、行間、余白、パディングなどのスタイル設定が自動的に適用されるので、手動によるデザイン作業が軽減され、最小限の編集作業で使いやすいテンプレートが配信されます。


* **新しい「カラー」タブでブランドを更新** - <strong> ブランドガイドライン </strong> を使用すると、すべてのタッチポイントにわたってブランドを一貫して提示できます。 新しい<strong>「カラー」セクション</strong>では、ブランドのカラーシステムの標準を定義し、エクスペリエンスをまたいでカラーを選択、整理、適用する方法の概要を示します。これにより、プライマリカラー、セカンダリカラー、アクセントカラー、ニュートラルカラーの一貫性のある使用が確保され、まとまりのあるアクセス可能で認識可能なブランドアイデンティティがサポートされます。


#### AI

* **カスタムのFirefly モデルとサードパーティの画像生成モデルの統合** – 標準およびカスタムの <strong>Firefly モデル </strong> と、承認済みの <strong> サードパーティの画像モデル </strong> （NanoBanana など）をシームレスに統合し、画像を生成する際の柔軟性、制御、ブランドの整合性を向上させることができます。 これにより、一般的なニーズに対応する標準Firefly、ブランドに合わせたカスタム Firefly、専門的または実験的なシナリオに対応する承認済みのサードパーティモデルなど、ユースケースごとに最適なモデルを選択できます。


#### エクスペリエンス決定

* **Decisioning でのEdge データの使用に対するAdobe Experience Platform インバウンドサポート** - <strong>Experience Platform データルックアップの意思決定サポートに </strong>、&lbrace;edge インバウンド <strong> チャネルのユースケースが含まれ </strong> ようになりました。 この機能は引き続き限定提供です。基になるデータルックアップ機能の一般提供はまだ発表されていません（AEP/製品の依存関係）。

  **注意**：この機能は一連の組織でのみ使用できます（<strong> 使用制限あり </strong>）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。


* **コードベースのエクスペリエンスチャネルでのエクスペリエンス決定のプレビュー** - <strong> コードベースのエクスペリエンス </strong> チャネルを使用して <strong> エクスペリエンス決定 </strong> を設定する際に <strong> 決定項目 </strong> をプレビューできるようになりました。 プレビューは、運用開始前に、オーサリングインターフェイスで直接使用できます。


* **オファーランキング AI モデルの可観測性** - Journey Optimizerでは、Decisioning で <strong>AI モデル </strong> の <strong> ヘルス </strong>、<strong> トレーニングステータス </strong> および <strong> パフォーマンス </strong> を監視できるようになりました。これにより、トレーニングの成功を検証し、失敗をトラブルシューティングして、結果に与える影響を理解できます。 この機能は、パーソナライズされた最適化モデルでのみ使用できます（自動最適化では使用できません）。


* **決定項目にフラグメントを添付** - Journey Optimizerでは、<strong> 決定ポリシー </strong> を通じてコードベースのエクスペリエンスキャンペーンで利用できる <strong> フラグメント </strong> を <strong> 決定項目に添付する機能を提供 </strong> ました。

  **注意**：以前リリースされた限定提供では、この機能はすべての環境で使用できるようになりました（一般提供）。

  公開日：2026 年 2 月 12 日（PT）。


#### ジャーニー

* **ジャーニーでの複数のインバウンドアクション** - ジャーニーオーケストレーションを簡素化するために、1 つのジャーニーで複数の <strong> インバウンドアクション </strong> を定義できるようになりました。 以前はキャンペーンで使用できましたが、この機能を使用すると、特定のコンテンツを含んだ複数の <strong> コードベースのエクスペリエンス </strong>、<strong> アプリ内メッセージ </strong>、<strong> コンテンツカード </strong>、または <strong>web アクション </strong> を異なる場所に同時に配信できます。

  **注意**：以前リリースされた限定提供では、この機能はすべての環境で使用できるようになりました（一般提供）。


* **SMS Webhook** - <strong>Webhook</strong> がすべての SMS プロバイダーでサポートされるようになりました。目的に応じて、各 Webhook を設定できます。<strong> インバウンド Webhook</strong> は受信メッセージをキャプチャし、<strong> フィードバック Webhook</strong> は配信の受信、ステータスの更新およびその他のメッセージ関連イベントを受信します。 [詳細情報](../sms/sms-webhook.md)

  公開日：2026 年 2 月 2 日（PT）。