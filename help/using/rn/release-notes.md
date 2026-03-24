---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 4c2785d580e28bb7645b61edaef48929bf9f4ff3
workflow-type: tm+mt
source-wordcount: '2839'
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

## 26年3月プレリリースノート {#march-26-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

[Adobe Experience Platform プレリリースノート ](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**: 2026年3月24日～25日

### 新機能 {#march-26-features}



<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンのトランザクションメッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションキャンペーンで<strong> トランザクションメッセージ </strong>がサポートされるようになりました。これにより、注文の確認、トリガー通知、アカウントの更新など、リアルタイムのイベント駆動型メッセージをキャンペーンワークフロー内で直接通知できるようになりました。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>APIを使用したトリガーオーケストレーションされたキャンペーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>API経由でオーケストレーションされたキャンペーンをトリガーできるようになりました。 ターゲットキャンペーンを「シグナルによってトリガー」として設定し、公開します。 そして、API呼び出しを使用してキャンペーンを実行します。 API呼び出しには、トリガーされたキャンペーンで変数として使用できるパラメーターを含めることができます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンでのアクティビティのテスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい<strong> テスト </strong> アクティビティが、オーケストレーションされたキャンペーンで利用できるようになりました。 このアクティビティにより、定義された条件に基づいてワークフローの実行を異なるブランチにルーティングし、ライブ配信をアクティブ化する前にキャンペーンロジックと設定を検証できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>URL パラメーターの暗号化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>トラッキングリンクやランディングページのURL パラメーターを暗号化できるようになり、機密性の高いパラメーターデータにさらなるセキュリティレイヤーを提供します。</p>
<ul>
<li>専用の<strong>管理</strong> レジストリに暗号化キーを登録して管理します。</li>
<li>式で新しい暗号化ヘルパーを使用して、レンダリング時に保護するクエリパラメーターのトラッキングリンクおよびランディングページ URLの機密データを暗号化します。</li>
</ul>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
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
<p>新しい「最適化」ノードを使用して、特定のオーディエンスをターゲットにしたり、A/B テストを実行して、ビジネス中心のKPIを満たすのに最適なパスを決定したりできます。
このツールを使用すると、コミュニケーション、シーケンス、タイミングをテスト、調整、カスタマイズし、顧客に最も効果的にリーチできます。
</p>
<p>以前は制限付き可用性でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。 <a href="../building-journeys/optimize.md">詳細情報</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーでのデータセット検索のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーの新しいアクティビティであるデータセット検索を使用すると、実行時にAdobe Experience Platform レコードデータセットからデータを動的に取得できます。 この機能を活用することで、プロファイルやイベントペイロードに存在しない場合があるデータにアクセスできるので、顧客とのインタラクションの関連性を高め、適切なタイミングで行えるようになります。以前は制限付き可用性でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。 詳しくは、<a href="../building-journeys/dataset-lookup.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ネイティブチャネルアクションアクティビティの非推奨（廃止予定）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>2026年2月の<strong> アクションアクティビティ </strong>の一般提供に続いて、ジャーニーキャンバス内の従来のネイティブチャネルアクティビティ（メール、プッシュ、SMS、アプリ内、Web、コードベースのエクスペリエンス、コンテンツカード）が非推奨になりました。</p>
<p>これで、単一の<strong> アクションアクティビティ </strong>を使用してすべてのチャネルアクションを設定し、チャネル固有のノードを個別に作成する必要がなくなりました。</p>
従来のチャネルアクティビティを使用している既存のジャーニーは、変更や移行が必要なく、引き続き機能します。
<p>詳しくは、<a href="../building-journeys/journey-action.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールチャネルにおける意思決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Decisioning</strong>を使用して、メールメッセージのコンテンツをパーソナライズおよび最適化できるようになりました。 優先順位のスコア、数式、AI モデルを活用して、各受信者に最も関連性の高いオファーやコンテンツを表示します。</p>
<p>以前は制限付き可用性でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。 この一般提供リリースでは、ミラーページがサポートされるようになりました。</p>
<p>詳しくは、<a href="../experience-decisioning/create-decision-policy.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>画像をメールコンテンツテンプレートに変換</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerから直接、画像をメールコンテンツテンプレートに変換できるようになりました。 AIを活用した分析により、ビジュアルリファレンスから構造化されたHTMLテンプレートを自動的に生成し、メールのデザイン時間を大幅に短縮できます。</p>
<p>以前は制限付き可用性でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。 <a href="../content-management/image-to-html.md">詳細情報</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>インボックス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>受信トレイ </strong>は、コンテンツカードで利用できるモバイル機能で、ユーザーがアプリまたはweb サイト内で一元的な場所を作成して、ユーザーに送信されるメッセージを表示できるようにします。 これにより、メッセージが却下された後もアクセスできるようになり、マーケティングコミュニケーションの有効期間を延長できます。</p>
<p>公開日：2026年3月31日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールテンプレート用の高度なHTMLエディター</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>電子メールコンテンツテンプレートの高度なHTML モードを使用すると、電子メールDesignerでコンテンツのHTML ソースを編集したり、ソースに高度な式（条件など）を追加したり、変更内容を失うことなくHTML ビューとデスクトップビューを切り替えたりできます。</p>
<p>この機能は、メールチャネルのコンテンツテンプレートでのみ使用できます。 現在、利用制限があります。アクセスするには、Adobe担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/expert-mode.gif"/></p>
<p>詳しくは、<a href="../content-management/email-template-expert-mode.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月10日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタム Firefly モデルとサードパーティの画像生成モデルの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>標準Fireflyモデルとカスタム Adobe Target モデルを、承認済みのサードパーティ画像モデルとシームレスに統合することで、画像を生成する際の柔軟性、コントロール、ブランドの整合性を向上できます。</p>
<p>ニーズに適したモデルの選択：</p>
<ul><li> <strong>Adobe モデル </strong> （Firefly Image Model 4を利用）は、追加設定なしで即座に画像を生成できます</li><li> <strong> パートナーモデル </strong> （Gemini 2.5 Flashを搭載）を使用した特殊機能</li><li>ブランドに即した生成を可能にする<strong> カスタムモデル </strong> （独自のアセットでトレーニングされたブランド固有のモデル）は、ブランドアイデンティティ、スタイル、ビジュアルガイドラインに正確に一致します。</li></ul>
<p>詳しくは、<a href="../content-management/generative-models.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>IOSのライブアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey OptimizerのiOS Live Activityを利用して、顧客のロックScreensやダイナミックアイランドにリアルタイムの体験を直接提供できます。 ユーザーがアプリを開かなくても、注文追跡やフライト状況からイベントカウントダウン、ライブスコア、配信の進捗状況に至るまで、ライブアップデートを配信できます。 オーディエンスがどこにいても、適切なタイミングで情報を提供し、エンゲージメントを維持しましょう。</p>
<p>以前はベータ版でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../mobile-live/get-started-mobile-live.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent:Channel content create</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>Adobe Experience Platform Agent Orchestrator</strong>を搭載した<strong>Journey Agent</strong>は、Journey Optimizerで利用でき、自然言語インターフェイスを通じてジャーニーを分析できます。 また、Journey Agentでチャネル固有のコンテンツを直接生成および管理し、電子メールやプッシュ通知などのチャネル用のコンテンツを作成したり、テンプレートを適用およびプレビューしたり、プロンプトを通じてトーンやスタイルを調整したり、コンテキストに沿った編集のために<strong>Content Designer</strong>でコンテンツを開いたりすることもできます。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="https://experienceleague.adobe.com/docs/experience-cloud-ai/experience-cloud-ai/agents/ajo-agent.html">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月4日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI モデル監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、Decisioning AI モデルの健全性、トレーニング状況、パフォーマンスをモニタリングできるようになりました。 これにより、AIを活用する各顧客に最適なオファーを選択するために、トレーニングの成功を検証し、失敗のトラブルシューティングを行い、結果への影響を把握することができます。 この機能は、<strong>Decisioning</strong>でのみ使用できます（従来の意思決定管理モデルでは使用できません）。</p>
<p>この機能は現在、<strong> パーソナライズされた最適化</strong> モデルでのみ使用できます（自動最適化ではありません）。</p>
<p><img src="assets/do-not-localize/ai-model-observability.gif"/></p>
<p>詳しくは、<a href="../experience-decisioning/ranking/ai-model-observability.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月9日（PT）</p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#march-26-improv}

このリリースに含まれる機能強化を以下に示します。


#### レポート

* **電子メールとSMS レポートのボットクリックを除外** - メールとSMS レポートでは、クリック指標からボットクリックが自動的に除外されるようになりました。これにより、より正確なエンゲージメントデータが提供され、自動トラフィックがパフォーマンスの数値を低下させるのを防ぐことができます。

* **送信時間の最適化：更新されたコントロールの場所と新しい上昇率レポート** – 送信時間の最適化（STO）コントロールがアクション設定メニューに再配置されました。 さらに、ジャーニーレポートで新しいリフトレポートを使用できるようになりました。このレポートを使用して、キャンペーンのパフォーマンス指標に対するSTOの影響を測定できます。
<!--
#### Email Designer

* **Email Designer displayed in Unified Shell** - The Email Designer is now displayed within the Unified Shell experience, providing a consistent navigation and header experience that aligns with other Adobe applications.

* **Text mode support in fragments** - To support text-based email workflows, you can now create and manage text versions of your visual fragments for optimal use in the plain text version of emails that include that fragment.

  **Caution:** When using a fragment that was created before the current release, the fragment text version may be incorrectly rendered—both in the Email Designer and in the final email delivered to your recipients. For best results with older fragments, edit, save and republish each fragment.-->

#### 決定

* **決定項目のオプションのフラグメント** – 決定項目でフラグメントを使用する場合、Edgeで一時的に利用できない場合はフラグメントをスキップし、ジャーニーまたはキャンペーンが失敗せずにレンダリングを続行するように、フラグメントをオプションにできるようになりました。

#### 設定

* ジャーニーとキャンペーン用の&#x200B;**フォルダー** - ジャーニーとキャンペーンをフォルダーに整理し、大量のコンテンツを扱うチームの構造化されたナビゲーションと管理を容易にできるようになりました。 この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。

* **AJO セカンダリ Recipient Feedback Event Dataset rename** - `AJO Email BCC Feedback Event` データセットの名前が`AJO Secondary Recipient Feedback Event` Datasetに変更されました。 影響は、状況によって異なります。

   * **既存のユーザー**：表示名のみが更新されます。 基になるテーブル名は変更されません。
   * **新しいユーザーとサンドボックス**：表示名とテーブル名の両方に新しい名前が反映されます。
   * **新しいサンドボックスを持つ既存のユーザー**：表示名とテーブル名の両方が新しい名前に更新されます。

  公開日：2026年3月2日（PT）

#### オーケストレーションキャンペーン

* **オーケストレーションされたキャンペーンのグローバル変数** - オーケストレーションされたキャンペーンは、ワークフロー内のすべてのアクティビティで一度定義して再利用できるグローバル変数をサポートするようになり、設定を簡素化し、動的な値、式、コンテンツのパーソナライゼーションで一貫性を確保します。

* **オーケストレーションされたキャンペーンのターゲットディメンションの簡素化** - オーケストレーションされたキャンペーンの適切なターゲティングとセカンダリディメンションを簡単に選択または自動的に推測できるようになり、正確で効率的なオーディエンスのアクティベーションが可能になりました。

#### ジャーニー

* **ジャーニー内のアウトバウンドメッセージの送信を開始** - Journey Optimizer ジャーニーからのメッセージを、管理されたバッチで配信するようにスケジュールできるようになりました。 [詳細情報](../building-journeys/send-using-waves.md)

  以前は、ジャーニーで使用するための限定可用性でリリースされていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。

  公開日：2026年3月16日（PT）

* **ジャーニーの技術的な詳細**&#x200B;の一時停止と再開の詳細 – ジャーニー&#x200B;**の技術的な詳細**&#x200B;には、追加の一時停止と再開の情報（最後の一時停止と再開の日時、各アクションを実行したユーザーの表示名と内部識別子、一時停止の動作、最大一時停止の時間、自動再開の状態など）が含まれるようになりました。 [詳細情報](../building-journeys/journey-properties.md)

  公開日：2026年3月2日（PT）


## 26年2月のリリースノート {#feb-26-01-rn}

[新機能](#feb-26-01-features)および[改善点](#feb-26-01-improv)のセクションでは、既に使用可能な機能について説明しています。<!--The [Coming soon](#coming-soon) section lists features and improvements scheduled for release later in February.-->

<!--**The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

<!--**Release date**: February 17-18, 2026-->

### 新機能 {#feb-26-01-features}


<table>
<thead>
<tr>
<th><strong>ジャーニー調停</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> ランキング式</strong>を使用して、顧客プロファイル属性と文脈要因に基づいてジャーニーの優先順位スコアを自動的に高め、顧客が最も関連性の高いジャーニーに確実に入れるようにできるようになりました。</p>
<p><img src="assets/do-not-localize/journey-arbitration-formulas.gif"/></p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../conflict-prioritization/journey-ranking-formulas.md">詳細なドキュメント</a>を参照してください。</p>
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
<p>Journey Optimizerでは、新しい汎用<strong> アクションアクティビティ </strong>をサポートしています。これにより、シングルアクションとマルチアクションのインバウンドアクショングループの両方を設定でき、ジャーニーキャンバス内で効率的なアクション設定が可能になります。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>あらゆるアクションに実験と多言語オプションの両方を追加できる機能。</li>
</ul>
<p><img src="assets/do-not-localize/action-activity.gif"/></p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../building-journeys/journey-action.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月20日（PT）</p>
<p><strong> メモ：</strong>すべてのネイティブチャネルにアクションジャーニーアクティビティからアクセスできるようになりました。 従来のネイティブチャネルアクティビティは、3月リリースで非推奨（廃止予定）となります。 従来のアクションを含む既存のジャーニーは、そのまま機能し続けます。移行は必要ありません。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>アウトバウンドメッセージのウェーブ送信</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerのキャンペーンやジャーニーからのメッセージを、管理されたバッチで経時的に配信するようにスケジュールできるようになりました。</p>
<p>Wave sendingには、次のような利点があります。</p>
<ul>
<li>配信品質の向上：スプレッド配信を長期的に実施することで、送信者としてのレピュテーションを維持し、迷惑メールとしてフラグを立てるリスクを低減できます。</li>
<li>負荷制御 – 1回に送信するメッセージの数を制限することで、下流のシステム（コールセンター、ランディングページなど）での負担を回避します。</li>
<li>大量のコンテンツと時間的制約のあるユースケース – 大規模なオーディエンスに適している場合や、タイミングを制御する必要がある場合（コールセンターのキャパシティ、ランプアップ、タイムバウンドのオファーなど）に適しています。</li>
</ul>
<p><img src="assets/do-not-localize/waves.gif"/></p>
<p><strong> キャンペーン </strong>では、この機能はすべての環境で使用できます（一般提供）。 詳しくは、<a href="../campaigns/send-using-waves.md">詳細なドキュメント</a>を参照してください。</p>

<p><strong> ジャーニー</strong>では、この機能は一連の組織でのみ使用できます（利用制限あり） – アクセスを取得するには、Adobe担当者にお問い合わせください。 詳しくは、<a href="../building-journeys/send-using-waves.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月19日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サブドメインをカスタム委任に移行する</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>CNAME委任モードを使用してサブドメインをインターフェイスから直接カスタムデリゲーションに移行できるようになりました。これにより、チャネル設定を再作成することなく、会社のガイドラインに沿ってより厳格なセキュリティポリシーに対応できます。</p>
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
<th><strong>web プッシュ通知チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerは<strong>Web プッシュ通知</strong>をサポートするようになり、プッシュチャネルをモバイル以外にも拡張します。 <strong>モバイルブラウザーとデスクトップブラウザー</strong>の両方に通知をシームレスに配信できるので、アプリを必要とせずにデバイス上で直接顧客にリーチできます。この機能強化により、モバイルプッシュで既に使用可能なものと同じオーサリングワークフローとターゲティング機能を活用して、タイムリーでパーソナライズされたメッセージを用いて、リアルタイムでユーザーに関与できるようになります。</p>
<p><img src="assets/do-not-localize/web-push.gif"/></p>
<p>以前はBetaでリリースされていましたが、この機能はすべての環境で使用できます（一般提供）。</p>
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
<p>新しい<strong> コンテンツ決定アクティビティ </strong>がジャーニーキャンバスで利用できるようになりました。パーソナライズされたオファーをカスタマージャーニーに直接統合できます。 このアクティビティを使用すると、適格性ベースの分岐を作成するための条件、オファーデータを外部システムに渡すためのカスタムアクション、完全にパーソナライズされた顧客体験を構築するためのその他のアクティビティなど、ジャーニー全体を通じて、意思決定ベースのコンテンツを配信し、それらのオファーを参照できます。</p>
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
<p>移行ツール APIを使用して、<strong>意思決定管理</strong> エンティティを<strong>Decisioning</strong>にプログラムで移行できるようになりました。機能は次のとおりです。</p>
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

<table>
<thead>
<tr>
<th><strong>カスタムアクションの監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいモニタリングダッシュボードと強化されたジャーニーステップイベントデータにより、insightでカスタムアクションエンドポイントの健全性とパフォーマンスをより詳細に把握できます。 成功した呼び出し、エラー、スループット、応答時間、キューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../action/reporting.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>SMS チャネルでの意思決定サポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>決定機能を使用して、SMS メッセージのコンテンツをパーソナライズおよび最適化できるようになりました。 優先度スコア、数式、AI モデルを使用して、顧客に最適なコンテンツを表示します。</p>
<p>詳しくは、<a href="../experience-decisioning/create-decision.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#feb-26-01-improv}

このリリースに含まれる機能強化を以下に示します。

#### 設定

* **ジャーニー式でのエクスペリエンスイベントの使用** - 2026年4月1日以降、ジャーニー式でのエクスペリエンスイベント属性の使用は、過去90日間にこの機能を使用していない組織ではサポートされなくなります。 この機能は、2025年7月8日以降、新規顧客組織では既に使用できません。 代替案については、「[ ジャーニー内のエクスペリエンスイベントの検索](../building-journeys/exp-event-lookup.md)」を参照してください。

#### コンテンツ管理

<!--
* **Update brands with new color tab** - Brand guidelines help ensure your brand is presented consistently across all touchpoints. The new <strong>Colors</strong> section defines the standards for your brand's color system, outlining how colors are selected, organized, and applied across experiences. It ensures consistent use of primary, secondary, accent, and neutral colors to support a cohesive, accessible, and recognizable brand identity. [Read more](../content-management/brands.md)
-->

* **テーマを使用して画像をメールテンプレートに変換する** - Journey Optimizerで画像をメールテンプレートに変換する際に、生成されたHTMLがブランドパラメーターに従うように、テーマを入力として使用できるようになりました。 背景色、ボタン色、フォント、行間、余白、パディングなどのスタイル設定が自動的に適用されるため、手作業によるデザイン作業が減り、最小限の編集ですぐに利用できるテンプレートを提供できます。 [詳細情報](../content-management/image-to-html.md)

  ご利用いただけます。2026年2月17日

<!--* **Text mode for fragments** - You can now create and manage text versions of your fragments, supporting workflows that rely on plain text content and providing the same flexibility as in email content. [Read more](../content-management/create-fragments.md)-->

#### E メールデザイナー

* **テキストインデント** - テキストコンポーネントの最初の段落に、プロパティパネルから直接、カスタマイズ可能な左インデントを適用できるようになりました。 <!--The new **Indentation** control lets you define indentation in pixels or percentage via a numeric input or slider, with live preview on the canvas. -->これは、エディトリアルや記事などの長文コンテンツの読みやすさを向上させます。 [詳細情報](../email/get-started-email-style.md)

  ご利用いただけます。2026年2月18日

#### 決定

* **DecisioningでAdobe Experience Platform データを使用するためのEdge インバウンドサポート** - DecisioningでのAdobe Experience Platform データの使用は、ジャーニーでのメールとカスタムアクションに加えて、エッジインバウンドユースケースをサポートするようになりました。 [詳細情報](../experience-decisioning/aep-data-exd.md)

  この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。


* **フラグメントを決定項目に添付** - Journey Optimizer では、決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できるフラグメントを決定項目に添付できるようになりました。[詳細情報](../experience-decisioning/fragments-decision-policies.md)

  この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。

  ご利用いただけます。2026年2月12日

#### パーソナライゼーション

* **実行メタデータヘルパー** - `executionMetadata` ヘルパー関数は、すべてのJourney Optimizer ユーザーが利用できるようになりました。 このツールを使用すると、コンテキスト情報を任意のネイティブアクションに動的に追加し、データセットに取り込んで外部システムに書き出すことができます。 [詳細情報](../personalization/functions/helpers.md#execution-metadata)

  この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。

  ご利用いただけます。2026年2月20日

#### SMS

* **SMS Webhook** - WebhookがすべてのSMS プロバイダーでサポートされるようになりました。 インバウンド Webhookは、受信メッセージを取得する受信Webhookと、配信レシート、ステータス更新、その他のメッセージ関連イベントを受信するフィードバック webhookを設定できます。 [詳細情報](../sms/sms-webhook.md)

  ご利用いただけます。2026年2月2日

<!--## Coming soon {#coming-soon}

The features and improvements below are planned for release later in February. Release dates and scope may change without prior notice.

### Improvements {#coming-soon-improv}

* **Decisioning preview in Code-based Experience channel** - You can now preview decision items when configuring Decisioning with the Code-based Experience channel. Preview is available directly in the authoring interface before going live.

  Availability date: February 18, 2026
-->

