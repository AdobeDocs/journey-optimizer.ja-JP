---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: ca383beea12fe1a4420cd8e4a6cd3bde147ade71
workflow-type: tm+mt
source-wordcount: '3166'
ht-degree: 27%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。

このモデルにより、リリースノートは毎月のリリースの間に更新されます。リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2026 年 3 月プレリリースノート {#march-26-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

詳しくは、[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**:2026 年 3 月 24～25 日

### 新機能 {#march-26-features}

<!--
<table>
<thead>
<tr>
<th><strong>LLM email optimizer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now optimize your email content for deliverability using large language model (LLM) technology. The LLM email optimizer analyzes your email content and provides actionable recommendations to improve sender reputation, avoid spam filters, and enhance overall deliverability performance.</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>画像をメールコンテンツテンプレートに変換する</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで画像をメールコンテンツテンプレートに直接変換できるようになりました。 AI を活用した分析を使用して、視覚的な参照から構造化HTML テンプレートを自動的に生成し、メールの設計時間を大幅に短縮します。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>調整されたキャンペーンでの増分クエリアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい <strong> 増分処理クエリ </strong> アクティビティを、オーケストレートキャンペーンで使用できるようになりました。 このアクティビティは、前回のワークフロー実行以降に新しいレコードまたは更新されたレコードのみをクエリするので、大規模なデータセットをターゲットにした繰り返しキャンペーンの処理時間が大幅に短縮され、効率が向上します。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>調整されたキャンペーンでのトランザクションメッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>調整されたキャンペーンで <strong> トランザクションメッセージ </strong> がサポートされるようになり、注文確認、予約通知、アカウントの更新など、リアルタイムのイベント駆動型メッセージをキャンペーンワークフロー内で直接トリガー化できるようになりました。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>調整されたキャンペーンでのテストアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレートキャンペーンで新しい <strong> テスト </strong> アクティビティを使用できるようになりました。 このアクティビティは、定義された条件に基づいてワークフローの実行を様々なブランチにルーティングするので、ライブ配信をアクティブ化する前にキャンペーンのロジックと設定を検証できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ランディングページのカスタムフォーム</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ランディングページに <strong> カスタムフォーム </strong> を作成して、標準のオプトインフィールドを超えて特定の購読者データを収集できるようになりました。 独自のフォームフィールド、検証ルールおよび送信動作を定義して、購読やプロファイルエンリッチメントのユースケースの範囲を拡大します。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent：オーケストレーションされた Campaign のユースケースの作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform Agent Orchestratorを活用した <strong>Journey Agent</strong> では、自然言語インターフェイスを使用して、完全な <strong> オーケストレーションされたキャンペーン </strong> のユースケースを作成できるようになりました。 キャンペーンの目標と要件を分かりやすく説明すると、Journey Agentでキャンペーンの構造、アクティビティおよびターゲティングを設定できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ランディングページでの新規プロファイル獲得</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ランディングページで <strong> 新しいプロファイルの獲得 </strong> ワークフローがサポートされるようになり、ランディングページエクスペリエンスから新しいオーディエンスメンバーを直接取得してオンボーディングできるようになりました。 取得フォームを設定してプロファイルデータを収集し、Adobe Experience Platformで新しいプロファイルを自動的にプロビジョニングします。</p>
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
<p><strong>ジャーニーパスの最適化 </strong>AI を使用して、過去のジャーニーのパフォーマンスを分析し、各顧客に最適なパスを自動的に選択することで、コンバージョンやエンゲージメントの成果を最大限に高めます。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p><strong> 決定 </strong> を使用して、メールメッセージのコンテンツをパーソナライズおよび最適化できるようになりました。 優先度スコア、数式または AI モデルを活用して、各受信者に最も関連性の高いオファーやコンテンツを表示します。</p>
<p>以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（一般提供）。 この一般提供（GA）リリースで、ミラーページがサポートされるようになりました。</p>
<p>詳しくは、<a href="../experience-decisioning/create-decision-policy.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メッセージインボックス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerで新しい <strong> メッセージインボックス </strong> が使用できるようになり、受信したアプリ内メッセージ、プッシュおよび SMS メッセージを一元的に表示できるようになりました。 受信者は、すべてのメッセージに 1 か所でアクセスして操作できるので、エンゲージメントと再エンゲージメントシナリオを強化できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ネイティブチャネルアクションアクティビティの廃止</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>2026 年 2 月の <strong> アクションアクティビティ </strong> の一般提供に続いて、ジャーニーキャンバスの従来のネイティブチャネルアクションアクティビティ（メール、SMS、プッシュ、アプリ内など）は、非推奨（廃止予定）になりました。 従来のチャネルアクティビティを使用する既存のジャーニーは、変更や移行を必要とせずに引き続き機能します。 詳しくは、<a href="../building-journeys/journey-action.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーでのデータセットルックアップのサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーの新しいアクティビティであるデータセット検索を使用すると、実行時にAdobe Experience Platform レコードデータセットからデータを動的に取得できます。 この機能を活用することで、プロファイルやイベントペイロードに存在しない場合があるデータにアクセスできるので、顧客とのインタラクションの関連性を高め、適切なタイミングで行えるようになります。以前は限定提供でリリースされていましたが、現在はすべての環境でこの機能を利用できます（一般提供）。 詳しくは、<a href="../building-journeys/dataset-lookup.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API を使用して調整されたキャンペーンのトリガー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>API を使用して、オーケストレーションされたキャンペーンをトリガーできるようになりました。 ターゲットキャンペーンを「シグナルによってトリガー」として設定し、公開します。 次に、API 呼び出しを使用してキャンペーンを実行します。 API 呼び出しには、トリガーされたキャンペーンで変数として使用できるパラメーターを含めることができます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールテンプレート用の高度なHTML エディター</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールコンテンツテンプレートの高度なHTML モードを使用すると、メールDesignerでコンテンツのHTML ソースを編集したり、ソースに高度な式（条件など）を追加したり、変更内容を失わずにHTML表示とデスクトップ表示を切り替えたりできます。</p>
<p>この機能は、メールチャネルのコンテンツテンプレートでのみ使用できます。 現在、限定提供です。アクセス権を取得するには、Adobe担当者にお問い合わせください。</p>
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
<th><strong>AI モデルの監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで、Decisioning AI モデルのヘルス、トレーニングのステータス、パフォーマンスを監視できるようになりました。 これにより、AI を使用して各顧客に最適なオファーを選択するために、トレーニングの成功の検証、失敗のトラブルシューティングおよび結果への影響の把握ができます。 この機能は、<strong> 決定 </strong> にのみ使用できます（従来の意思決定管理モデルでは使用できません）。</p>
<p>この機能は、現在、<strong> パーソナライズされた最適化 </strong> モデルでのみ使用できます（自動最適化では使用できません）。</p>
<p><img src="assets/do-not-localize/ai-model-observability.gif"/></p>
<p>詳しくは、<a href="../experience-decisioning/ranking/ai-model-observability.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月9日（PT）</p>
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
<p><strong>Adobe Experience Platform Agent Orchestrator</strong> を活用した <strong>Journey Agent</strong> はJourney Optimizerで利用でき、自然言語インターフェイスを通じてジャーニーを分析できます。 また、Journey Agentで直接チャネル固有のコンテンツを生成および管理したり、メールやプッシュなどのチャネルのコンテンツを作成したり、テンプレートを適用およびプレビューしたり、プロンプトを使用してトーンとスタイルを調整したり、<strong> コンテンツDesigner</strong> でコンテンツを開いてコンテキスト内編集を行ったりできるようになりました。</p>
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
<th><strong>iOSのライブアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey OptimizerのiOS ライブアクティビティを使用すると、顧客の Lock Screensや Dynamic Island に直接リアルタイムエクスペリエンスを提供できます。 ユーザーがアプリを開く必要なく、注文のトラッキングやフライトステータスからイベントのカウント、ライブスコア、配信の進行状況に至るまで、ライブ更新を配信します。 オーディエンスに情報を提供し、正確に適切なタイミング、適切な場所でエンゲージメントを維持します。</p>
<p>以前ベータ版でリリースされていましたが、この機能を、すべての環境で利用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../mobile-live/get-started-mobile-live.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタムのFirefly モデルとサードパーティの画像生成モデルの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>標準およびカスタムのFirefly モデルを承認済みのサードパーティ画像モデルとシームレスに統合して、画像の生成時の柔軟性、コントロール、ブランドの関連付けを強化できます。</p>
<p>ニーズに合った適切なモデルの選択：</p>
<ul><li> 追加のセットアップを必要とせずに即座に画像を生成するための <strong>Adobe モデル </strong> （Firefly Image Model 4を活用）</li><li> <strong> パートナーモデル </strong> （Gemini 2.5 Flash 搭載）により、特殊な機能を実現</li><li><strong> カスタムモデル </strong> （独自のアセットに基づいてトレーニングされたブランド固有のモデル）を使用すると、ブランドアイデンティティ、スタイル、視覚的なガイドラインに正確に合致するオンブランド生成機能を実現できます。</li></ul>
<p>詳しくは、<a href="../content-management/generative-models.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年3月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#march-26-improv}

このリリースに含まれる機能強化を以下に示します。

#### ジャーニー

* **ジャーニーの判別 – AI モデル** - ランキング式に加えて、AI モデルをジャーニーの判別と組み合わせて使用し、機械学習を活用して過去の行動とコンテキストシグナルに基づいて各プロファイルに最も関連性の高いジャーニーを決定することで、顧客のジャーニーエントリを自動的にランク付け、優先順位付けできるようになりました。 この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。

* **ジャーニーでのアウトバウンドメッセージのウェーブ送信** - Journey Optimizer ジャーニーからのメッセージが制御されたバッチで時間をかけて配信されるようにスケジュールできるようになりました。 [詳細情報](../building-journeys/send-using-waves.md)

  以前はジャーニーで使用するための限定提供でリリースされていましたが、この機能は、すべての環境で使用できるようになりました（一般提供）。

  公開日：2026年3月16日（PT）

* **ジャーニーの技術的な詳細の一時停止と再開の詳細** - ジャーニー **技術的な詳細** には、追加の一時停止と再開の情報が含まれるようになりました。最後の一時停止と再開の日時、各アクションを実行したユーザーの表示名と内部識別子、一時停止の動作、最大一時停止時間、自動再開状態など、一時停止されたジャーニー設定の完全なセットです。 [詳細情報](../building-journeys/journey-properties.md)

  公開日：2026年3月2日（PT）

#### レポート

* **メールおよび SMS レポートのボットクリック数の除外** - メールおよび SMS レポートで、クリック指標からボットクリック数が自動的に除外されるようになり、より正確なエンゲージメントデータが提供され、自動トラフィックによってパフォーマンス数値が水増しされるのを防ぎます。

* **送信時間の最適化：更新されたコントロールの場所と新しいリフトレポート** – 送信時間の最適化（STO）コントロールがアクション設定メニューに再配置されました。 さらに、ジャーニーレポートで新しい上昇率レポートを使用して、キャンペーンのパフォーマンス指標に対する STO の影響を測定できるようになりました。

#### E メールデザイナー

* **Dynamic Media （Beta）を使用したオープンタイムパーソナライゼーション** - Adobe Dynamic Media アセットを使用して、メールのコンテンツを公開時にパーソナライズできるようになりました。これにより、メールが開封された時点での各受信者の属性に基づいて、受信者に固有のリアルタイムの画像とビジュアルが動的に生成されます。 この機能は、現在Betaにあります。

* **統合シェルに表示されるメールDesigner** - メールDesignerが統合シェルエクスペリエンス内に表示され、他のAdobe アプリケーションと連携する一貫したナビゲーションおよびヘッダーエクスペリエンスを提供するようになりました。

* **フラグメントでのテキストモードのサポート** - フラグメントでテキストモードの編集がサポートされるようになり、テキストベースのメールワークフローやマルチチャネルシナリオで使用するために、コンテンツフラグメントのプレーンテキストバージョンを作成および管理できるようになりました。

#### 決定

* **Edge Decisioning での式フラグメント参照の変更フィードのサポート** – この機能強化により、フラグメントを参照するすべてのアイテムに、フラグメント参照の変更が自動的に反映され、何も手動で更新する（キャンペーンポリシーまたは決定ポリシーを再公開する）必要がなくなります。

* **決定項目のオプションのフラグメント** – 決定項目に添付されるフラグメントをオプションとして設定できるようになり、すべての決定項目レンダリングで特定のフラグメントが必要ない場合でも、コンテンツ構成をより柔軟に設定できます。

#### 設定

* **URL パラメーターの暗号化** - トラッキングリンクおよびランディングページの URL パラメーターを暗号化できるようになり、機密パラメーターデータのセキュリティがさらに強化されます。 この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。

* **ジャーニーとキャンペーンのフォルダー** - ジャーニーとキャンペーンをフォルダーに整理して、大量のコンテンツを扱うチーム向けに構造化されたナビゲーションと容易な管理を可能にしました。 この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。

* **AJOセカンダリ受信者フィードバックイベントデータセットの変更** - AJO メール BCC フィードバックイベントデータセットは、AJOセカンダリ受信者フィードバックイベントデータセットに名前が変更されます。
   * **既存のユーザー**：表示名のみが変更されます。 基になるテーブル名は変更されません。
   * **新しいユーザーと新しいサンドボックス**：表示名とテーブル名の両方で新しい名前を使用します。
   * **新しいサンドボックスを使用する既存のユーザー/組織**：表示名とテーブル名の両方が新しい名前に変更されます。

  公開日：2026年3月2日（PT）

#### オーケストレーションキャンペーン

* **オーケストレートキャンペーンのグローバル変数** - オーケストレートキャンペーンでは、ワークフロー内のすべてのアクティビティで一度定義して再利用できるグローバル変数をサポートするようになり、設定を簡素化し、動的な値、式、コンテンツのパーソナライゼーションの一貫性を確保します。

* **Orchestrated Campaigns でのターゲットディメンションの簡略化** - Orchestrated Campaigns で適切なターゲティングとセカンダリディメンションを簡単に選択または自動的に推測して、正確で効率的なオーディエンスのアクティベーションを行うことができるようになりました。

## 2026 年 2 月リリースノート {#feb-26-01-rn}

[ 新機能 ](#feb-26-01-features) と [ 改善点 ](#feb-26-01-improv) の節では、既に使用可能な機能について説明しています。 [ 近日公開 ](#coming-soon) のセクションには、2 月下旬にリリースが予定されている機能と改善点の一覧が表示されます。

<!--**The pre-release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published in the release notes, at the release date.

See also [Adobe Experience Platform Pre-release notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

<!--**Release date**: February 17-18, 2026-->

### 新機能 {#feb-26-01-features}


<table>
<thead>
<tr>
<th><strong>ジャーニーの判別</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> ランキング式 </strong> を使用して、顧客プロファイル属性とコンテキスト要因に基づいてジャーニーの優先度スコアを自動的にブーストし、顧客が最も関連性の高いジャーニーにエントリできるようにできるようになりました。</p>
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
<p>Journey Optimizerでは、新しい汎用 <strong> アクションアクティビティ </strong> をサポートしています。このアクティビティを使用すると、単一のアクションと複数のアクションのインバウンドアクショングループの両方を設定でき、ジャーニーキャンバス内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内の簡素化されたネイティブアクション設定。</li>
<li>複数アクションのインバウンドアクショングループを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p><img src="assets/do-not-localize/action-activity.gif"/></p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../building-journeys/journey-action.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月20日（PT）</p>
<p><strong> メモ：</strong> すべてのネイティブチャネルは、アクションジャーニーアクティビティを通じてアクセスできるようになりました。 従来のネイティブチャネルアクティビティは、3 月のリリースで非推奨（廃止予定）になります。 従来のアクションを含む既存のジャーニーは、引き続きそのまま機能します。移行は不要です。</p>
</td>
</tr>
</tbody>
</table>

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

<table>
<thead>
<tr>
<th><strong>カスタムアクションの監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい監視ダッシュボードと強化されたジャーニーステップイベントデータを使用して、カスタムアクションエンドポイントの正常性とパフォーマンスをより深くinsightできます。 成功した呼び出し、エラー、スループット、応答時間、キューの待機時間を追跡して、異常値が発生したタイミング、場所、理由をすばやく把握します。</p>
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
<th><strong>SMS チャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Decisioning を使用して SMS メッセージのコンテンツをパーソナライズおよび最適化できるようになりました。 優先度スコア、数式、AI モデルを使用して、顧客に最適なコンテンツを表示します。</p>
<p>詳しくは、<a href="../experience-decisioning/create-decision.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2026年2月2日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#feb-26-01-improv}

このリリースに含まれる機能強化を以下に示します。

#### 設定

* **ジャーニー式でのエクスペリエンスイベントの使用** - 2026 年 4 月 1 日（PT）以降、ジャーニー式でのエクスペリエンスイベント属性の使用は、過去 90 日間にこの機能を使用していない組織ではサポートされなくなります。 この機能は、2025 年 7 月 8 日（PT）以降、新規のお客様は使用できなくなっています。 代替手段については、[ ジャーニーでのエクスペリエンスイベントの参照 ](../building-journeys/exp-event-lookup.md) を参照してください。

#### コンテンツ管理

<!--
* **Update brands with new color tab** - Brand guidelines help ensure your brand is presented consistently across all touchpoints. The new <strong>Colors</strong> section defines the standards for your brand's color system, outlining how colors are selected, organized, and applied across experiences. It ensures consistent use of primary, secondary, accent, and neutral colors to support a cohesive, accessible, and recognizable brand identity. [Read more](../content-management/brands.md)
-->

* **テーマを使用して画像をメールテンプレートに変換** - Journey Optimizerで画像をメールテンプレートに変換する際に、テーマを入力として使用できるようになり、生成されたHTMLがブランドパラメーターに従うようになりました。 背景色、ボタンの色、フォント、行間、余白、パディングなどのスタイル設定が自動的に適用されるので、手動によるデザイン作業が軽減され、最小限の編集作業で使いやすいテンプレートが配信されます。 [詳細情報](../content-management/image-to-html.md)

  公開日：2026 年 2 月 17 日（PT）。

<!--* **Text mode for fragments** - You can now create and manage text versions of your fragments, supporting workflows that rely on plain text content and providing the same flexibility as in email content. [Read more](../content-management/create-fragments.md)-->

#### E メールデザイナー

* **テキストインデント** - プロパティパネルから直接、テキストコンポーネントの段落の先頭行に、カスタマイズ可能な左インデントを適用できるようになりました。 <!--The new **Indentation** control lets you define indentation in pixels or percentage via a numeric input or slider, with live preview on the canvas. --> これにより、編集者や記事などの長い形式のコンテンツの読みやすさが向上します。 [詳細情報](../email/get-started-email-style.md)

  公開日：2026 年 2 月 18 日（PT）。

#### 決定

* **Decisioning でのEdge データの使用に対するAdobe Experience Platform インバウンドサポート** - Decisioning でのAdobe Experience Platform データの使用で、ジャーニーでのメールおよびカスタムアクションに加えて、エッジインバウンドのユースケースがサポートされるようになりました。 [詳細情報](../experience-decisioning/aep-data-exd.md)

  この機能は、一連の組織でのみ使用できます（限定提供）。アクセス権を取得するには、アドビ担当者にお問い合わせください。


* **フラグメントを決定項目に添付** - Journey Optimizer では、決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できるフラグメントを決定項目に添付できるようになりました。[詳細情報](../experience-decisioning/fragments-decision-policies.md)

  この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。

  公開日：2026 年 2 月 12 日（PT）。

#### パーソナライゼーション

* **実行メタデータヘルパー** - `executionMetadata` ヘルパー関数が、すべてのJourney Optimizer ユーザーが使用できるようになりました。 これを使用すると、任意のネイティブアクションにコンテキスト情報を動的に追加し、外部システムに書き出すためにデータセットに取り込むことができます。 [詳細情報](../personalization/functions/helpers.md#execution-metadata)

  この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。

  公開日：2026 年 2 月 20 日（PT）。

#### SMS

* **SMS Webhook** – すべての SMS プロバイダーで Webhook がサポートされるようになりました。 目的に応じて、各 Webhook を設定できます。受信メッセージをキャプチャする受信 Webhook と、配信の受信、ステータスの更新、その他のメッセージ関連イベントを受信するフィードバック Webhook。 [詳細情報](../sms/sms-webhook.md)

  公開日：2026 年 2 月 2 日（PT）。

<!--## Coming soon {#coming-soon}

The features and improvements below are planned for release later in February. Release dates and scope may change without prior notice.

### Improvements {#coming-soon-improv}

* **Decisioning preview in Code-based Experience channel** - You can now preview decision items when configuring Decisioning with the Code-based Experience channel. Preview is available directly in the authoring interface before going live.

  Availability date: February 18, 2026
-->

