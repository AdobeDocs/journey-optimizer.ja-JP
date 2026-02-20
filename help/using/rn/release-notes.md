---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 6c509ef134c4240b243d255fd1ab7ec6bb062bf0
workflow-type: tm+mt
source-wordcount: '1329'
ht-degree: 33%

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

[&#x200B; 新機能 &#x200B;](#feb-26-01-features) と [&#x200B; 改善点 &#x200B;](#feb-26-01-improv) の節では、既に使用可能な機能について説明しています。 [&#x200B; 近日公開 &#x200B;](#coming-soon) のセクションには、2 月下旬にリリースが予定されている機能と改善点の一覧が表示されます。

<!--**The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

<!--**Release date**: February 17-18, 2026-->

### 新機能 {#feb-26-01-features}


<!--
<table>
<thead>
<tr>
<th><strong>Mobile Live Activities</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Live Activities</strong> provide real-time updates and interactive experiences within mobile apps, allowing users to stay informed about ongoing events or tasks directly on their device's screen. This feature enhances engagement by delivering live information, such as progress tracking, event updates, or interactive content, without requiring users to open the app.</p>
<p>Previously released in beta, this capability is now available to all environments (General Availability).</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>送信メッセージのウェーブ送信</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer キャンペーンまたはジャーニーからのメッセージが制御されたバッチで時間の経過と共に配信されるようにスケジュールできるようになりました。</p>
<p>Wave 送信には、次の利点があります。</p>
<ul>
<li>配信品質の向上 – 送信を時間の経過と共に拡散することで、強力な送信者の評判を維持し、スパムとしてフラグ付けされるリスクを軽減できます。</li>
<li>読み込み制御 – 一度に送信されるメッセージの数を制限することで、ダウンストリームのシステム（コールセンター、ランディングページなど）が過剰になるのを防ぎます。</li>
<li>大量で時間に敏感なユースケース – 大規模なオーディエンスや、タイミングを制御する必要がある場合（コールセンターの処理能力、ランプアップ、時間限定オファーなど）に適しています。</li>
</ul>
<p><img src="assets/do-not-localize/waves.gif"/></p>
<p><strong> キャンペーン </strong> では、この機能はすべての環境で使用できます（一般提供）。 詳しくは、<a href="../campaigns/send-using-waves.md">詳細なドキュメント</a>を参照してください。</p>

<p><strong> ジャーニー </strong> では、この機能は一連の組織（使用制限あり）でのみ使用できます。アクセス権を取得するには、Adobe担当者にお問い合わせください。 詳しくは、<a href="../building-journeys/send-using-waves.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月19日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サブドメインのカスタムデリゲーションへの移行</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>CNAME 委任モードを使用して、サブドメインをインターフェイスから直接カスタムデリゲーションに移行できるようになりました。これにより、チャネル設定を再作成することなく、会社のガイドラインに沿って、より厳しいセキュリティポリシーを満たすことができます。</p>
<p><img src="assets/do-not-localize/subdomain-migration.gif"/></p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../configuration/custom-subdomain-migration.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月19日（PT）</p>
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
<p>Adobe Journey Optimizerで <strong>web プッシュ通知 </strong> がサポートされるようになり、プッシュチャネルがモバイル以外にも拡大しました。 <strong>モバイルブラウザーとデスクトップブラウザー</strong>の両方に通知をシームレスに配信できるので、アプリを必要とせずにデバイス上で直接顧客にリーチできます。この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、タイムリーでパーソナライズされたメッセージを用いて、リアルタイムでユーザーに関与できるようになります。</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>以前にBetaでリリースされたこの機能は、すべての環境で使用できるようになります（一般提供）。</p>
<p>詳しくは、<a href="../push/push-configuration-web.md">詳細なドキュメント</a>を参照してください。</p>
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
<p>ジャーニーキャンバスで新しい <strong> コンテンツ決定アクティビティ </strong> が使用できるようになり、パーソナライズされたオファーをカスタマージャーニーに直接統合できます。 このアクティビティを使用すると、決定ベースのコンテンツを配信し、ジャーニー全体でこれらのオファーを参照できます。実施要件ベースのブランチを作成する条件、外部システムにオファーデータを渡すカスタムアクション、完全にパーソナライズされたカスタマーエクスペリエンスを構築するその他のアクティビティなどです。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/content-decision.gif"/></p>
<p>詳しくは、<a href="../building-journeys/content-decision.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月10日（PT）</p>
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
<p>移行ツール API が、次の機能を備える <strong> 意思決定管理 </strong> エンティティを <strong> 意思決定 </strong> にプログラム的に移行できるようになりました。</p>
<ul>
<li>柔軟な移行範囲（サンドボックス、オファー、決定レベル）</li>
<li>自動化された依存関係分析と検証</li>
<li>完了した移行のロールバックサポート</li>
<li>オブジェクトマッピングを含む詳細な移行レポート</li>
</ul>
<p>詳しくは、<a href="../experience-decisioning/decisioning-migration-api.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#feb-26-01-improv}

このリリースに含まれる機能強化を以下に示します。

#### 設定

* **ジャーニー式でのエクスペリエンスイベントの使用** - 2026 年 4 月 1 日（PT）以降、ジャーニー式でのエクスペリエンスイベント属性の使用は、過去 90 日間にこの機能を使用していない組織ではサポートされなくなります。 この機能は、2025 年 7 月 8 日（PT）以降、新規のお客様は使用できなくなっています。 代替手段については、[&#x200B; ジャーニーでのエクスペリエンスイベントの参照 &#x200B;](../building-journeys/exp-event-lookup.md) を参照してください。

#### E メールデザイナー

* **テキストインデント** - プロパティパネルから直接、テキストコンポーネントの段落の先頭行に、カスタマイズ可能な左インデントを適用できるようになりました。 <!--The new **Indentation** control lets you define indentation in pixels or percentage via a numeric input or slider, with live preview on the canvas. --> これにより、編集者や記事などの長い形式のコンテンツの読みやすさが向上します。

  公開日：2026 年 2 月 18 日（PT）。

#### コンテンツテンプレート

* **テーマを使用して画像をメールテンプレートに変換** - Journey Optimizerで画像をメールテンプレートに変換する際に、テーマを入力として使用できるようになり、生成されたHTMLがブランドパラメーターに従うようになりました。 背景色、ボタンの色、フォント、行間、余白、パディングなどのスタイル設定が自動的に適用されるので、手動によるデザイン作業が軽減され、最小限の編集作業で使いやすいテンプレートが配信されます。 [詳細情報](../content-management/image-to-html.md)

  公開日：2026 年 2 月 17 日（PT）。


#### エクスペリエンス決定

* **Decisioning でのEdge データの使用に対するAdobe Experience Platform インバウンドサポート** - Decisioning でのAdobe Experience Platform データの使用で、ジャーニーでのメールおよびカスタムアクションに加えて、エッジインバウンドのユースケースがサポートされるようになりました。 [詳細情報](../experience-decisioning/aep-data-exd.md)

  **注意**：この機能は一連の組織でのみ使用できます（<strong> 使用制限あり </strong>）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。


* **フラグメントを決定項目に添付** - Journey Optimizer では、決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できるフラグメントを決定項目に添付できるようになりました。[詳細情報](../experience-decisioning/fragments-decision-policies.md)

  **注意**：以前リリースされた限定提供では、この機能はすべての環境で使用できるようになりました（一般提供）。

  公開日：2026 年 2 月 12 日（PT）。

## 近日リリース予定 {#coming-soon}

以下の機能および改善点は、2 月下旬にリリースされる予定です。 リリース日および範囲は、予告なく変更される場合があります。

<table>
<thead>
<tr>
<th><strong>Journey Agent：チャネルコンテンツの作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Adobe Experience Platform Agent Orchestrator</strong> を活用した <strong>Journey Agent</strong> はJourney Optimizerで利用でき、自然言語インターフェイスを通じてジャーニーを分析できます。 また、Journey Agentで直接チャネル固有のコンテンツを生成および管理したり、メールやプッシュなどのチャネルのコンテンツを作成したり、テンプレートを適用およびプレビューしたり、プロンプトを使用してトーンとスタイルを調整したり、<strong> コンテンツDesigner</strong> でコンテンツを開いてコンテキスト内編集を行ったりできるようになりました。</p>
<p>公開日：2026年2月20日（PT）</p>
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
<p><strong> ランキング式 </strong> と <strong>AI モデル </strong> を使用して、顧客プロファイル属性とコンテキスト要因に基づいてジャーニーの優先度スコアを自動的に上げることができるようになり、顧客が最も関連性の高いジャーニーにエントリできるようになりました。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>公開日：2026年2月24日（PT）</p>
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
<p>Journey Optimizerでは、新しい汎用 <strong> アクションアクティビティ </strong> をサポートしています。このアクティビティを使用すると、単一のアクションと複数のアクションのインバウンドアクショングループの両方を設定でき、ジャーニーキャンバス内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>公開日：2026年2月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI モデルの監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで、Decisioning AI モデルのヘルス、トレーニングのステータス、パフォーマンスを監視できるようになりました。 これにより、AI を使用して各顧客に最適なオファーを選択するために、トレーニングの成功の検証、失敗のトラブルシューティングおよび結果への影響の把握ができます。 この機能は、<strong> 決定 </strong> にのみ使用できます（従来の意思決定管理モデルでは使用できません）。</p>
<p>この機能は、現在、<strong> パーソナライズされた最適化 </strong> モデルでのみ使用できます（自動最適化では使用できません）。</p>
<p>公開日：2026年2月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#coming-soon-improv}

* **コードベースのエクスペリエンスチャネルでのエクスペリエンス決定のプレビュー** - コードベースのエクスペリエンスチャネルでエクスペリエンス決定を設定する際に、決定項目をプレビューできるようになりました。 プレビューは、運用開始前に、オーサリングインターフェイスで直接使用できます。

  公開日：2026 年 2 月 20 日（PT）。

* **カスタムのFirefly モデルとサードパーティの画像生成モデルの統合** – 標準およびカスタムのFirefly モデルと、承認済みのサードパーティの画像モデル（NanoBanana など）をシームレスに統合し、画像を生成する際の柔軟性、制御、ブランドの関連付けを向上させることができます。 これにより、一般的なニーズに対応する標準Firefly、ブランドに合わせたカスタム Firefly、専門的または実験的なシナリオに対応する承認済みのサードパーティモデルなど、ユースケースごとに最適なモデルを選択できます。

  公開日：2026 年 2 月 20 日（PT）。

