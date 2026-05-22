---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
role: User
level: Beginner, Intermediate
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
TQID: https://experienceleague.adobe.com/YJKQFYUi8Kw7yZZKm8blcM-1G9uYsqcsEsopH0hOMhA
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: df64005d-8f9a-422e-ba4d-c6f6dc3454b4id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: c2beecbb-b93e-4ae3-baa9-72adcdc06781id: cfba2953-2ce9-4b00-a00c-71cd338ae63fid: ee5bb250-0884-4d71-86eb-d8489e8bcadd
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: f7524e295032c5ac4bb230a0f4c4965a764ee2c8
workflow-type: tm+mt
source-wordcount: 2581
ht-degree: 25%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。 これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。 このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。 このモデルにより、リリースノートは毎月のリリースの間に更新されます。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

>[!NOTE]
>
>これらのリリースノートに記載されている機能には、各変更がいつ環境でアクセスできるようになったかを示す&#x200B;**利用可能日**&#x200B;が含まれています。 このページの下部にある「**近日リリース予定**」セクションには、今後数日以内にリリース予定の機能と機能強化が一覧表示されます。 情報は変更される場合があります。

## 26年5月のリリースノート {#may-26-rn}

### 新機能 {#may-26-features}

2026年5月にリリースされた機能は次のとおりです。

<table>
<thead>
<tr>
<th><strong>新しいモバイルメッセージチャネルと強化されたRCS メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS、MMS、およびRCSは、Adobe Journey Optimizerで1つの<strong> モバイルメッセージ </strong> アクションに統合されるようになりました。これにより、1か所からすべてのモバイルメッセージタイプを簡単に管理できるようになりました。 このアップデートの一環として、新しいネイティブオーサリングエクスペリエンスを通じて、画像、カルーセル、推奨アクションなどのリッチメディア RCS メッセージをJourney Optimizerで直接作成できるようになりました。</p>
<p>詳しくは、 <a href="../mobile/get-started-mobile.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>キャンペーンを連携</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションされたキャンペーンを、別のオーケストレーションされたキャンペーンの<strong>終了アクティビティ </strong>から直接、オーケストレーションされたキャンペーンをトリガーすることで、リンクできるようになりました。</p>
<p>これにより、複雑なオーケストレーションロジックを、毎回再構築するのではなく、複数の親キャンペーンから呼び出すことができる、小さく再利用可能なフローに分割することができます。 実行時に渡されたペイロードは、ダウンストリームキャンペーンでセグメント化とパーソナライゼーションに使用できるため、リンクされた各キャンペーンは、受信したコンテキストに基づいて動作できます。</p>
<p><img src="assets/do-not-localize/oc-trigger.gif"></p>
<p>詳しくは、 <a href="../orchestrated/trigger-orchestrated-campaign.md#signal-end">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月20日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Content Advisor Selector</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、Experience Manager Assetsとコンテンツフラグメントの両方を選択するための統一モーダルである<strong>Content Advisor セレクター</strong>を使用するようになりました。 新しいセレクターには次のものが含まれます。</p>
<ul>
<li><strong>すべてのアセットとフラグメントで</strong>を参照、検索、フィルタリングします。</li>
<li><strong>AI セマンティック検索</strong>：テキストの一致だけでなく、意味や内容に基づいてコンテキストに即したアセットを表示するために、「山の中のコーヒー」など、平易な言語で必要なものを記述します。 多言語クエリもサポートされています。</li>
<li><strong> ブリーフのアップロード </strong>: マーケティングブリーフをアップロードすると、コンテンツと要件にもとづいてキャンペーンコンテキストに沿ったアセットが自動的に表示されます。</li>
<li><strong>Dynamic Media レンディション </strong>：セレクターを離れることなく、ダイナミックアセットの画像レンディションを選択して適用します。</li>
</ul>
<p>詳しくは、 <a href="../integrations/aem-content-advisor.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月19日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーフラグ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerで<strong>ジャーニーフラグメント </strong>を作成できるようになりました。 ジャーニーフラグメントは、再利用可能なジャーニーノードのセットです。一度構築すれば、サンドボックスをまたいであらゆるジャーニーにドロップできます。 実施要件のチェック、好みのチャネルルーティングロジック、ウェルカムシーケンスなど、フラグメントは、同じロジックを毎回ゼロから再構築することなく、より迅速に作業し、一貫性を維持するのに役立ちます。</p>
<p>フラグメントを作成すると、専用の<strong> フラグメントインベントリ </strong>に保存され、<strong>ジャーニーフラグメント </strong> アクティビティを使用して、任意のジャーニーに挿入できます。</p>
<!--<p><img src="assets/do-not-localize/journey-fragments.gif"></p>-->
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、 <a href="../building-journeys/journey-fragments.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月13日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールデザイナーのディープリンク</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>E メールデザイナーの専用オプションを使用して、メールコンテンツにディープリンクを追加できるようになりました。</p><p>これにより、ユーザーはブラウザーやアプリストアにリダイレクトされずに、アプリ内の適切なコンテンツに直接アクセスでき、コンテキストとエンゲージメントが維持されます。</p>
<p><img src="assets/do-not-localize/deeplinks.gif"></p>
<p>詳しくは、 <a href="../email/deeplinks.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月12日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーシミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを<strong>シミュレーション</strong>に設定できます。 このモードを使用すると、<strong>シミュレートされたユーザー</strong>を使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。</p>
<p>この機能は現在、基本機能を備えた限定提供として、すべてのお客様にご利用いただけます。</p>
<p><img src="assets/do-not-localize/simulate-user.gif"></p>
<p>詳しくは、 <a href="../building-journeys/simulate-journey.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>決定ルールとランキング式AI最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>[!DNL Adobe Journey Optimizer] aiを使用して、簡素化できる決定ルールとランキング式を検出できるようになりました。 インベントリでは、AIが最適化機会を特定したルールに赤いインジケーターが表示されます。 インジケーターをクリックすると、AIが提案したバージョンと一緒に元のエクスプレッションが表示されます。 そこから、ファイルをダウンロードして、シミュレートされたプロファイルが各バージョンでどのように評価されるかを確認し、それらが同じように動作することを確認してから、式を最適化された式に置き換えることができます。</p>
<p><img src="assets/do-not-localize/rule-ai.gif"></p>
<p>詳しくは、 <a href="../start/ai-features.md#decisioning-optimization">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月5日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><b>統合</b>機能を使用すると、サードパーティのデータソースを Adobe Journey Optimizer に直接接続できます。 この機能により、外部データと<b>構成可能なコンテンツ</b>の取り込み方法が簡素化され、あらゆるチャネルをまたいで、パーソナライズされた動的なメッセージを容易に配信できるようになります。</p>
<p>この機能は、以前はベータ版でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../integrations/integrations.md">詳細なドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年5月4日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#may-26-improv}

2026年5月には以下の改善もリリースされました。

#### E メールデザイナー

* **フラグメントの継承の改ざんを制限** - フラグメントを作成または編集する際に、メールで使用するときに変更できるかどうかを選択できるようになりました。 フラグメントをロックすることで、ファイルが表示されるあらゆる場所で同期を維持し、ブランド基準やコンプライアンス要件に違反する可能性のあるローカル編集を防ぐことができます。 この設定は後で更新でき、今後の使用に適用されます。 [詳細情報](../content-management/create-fragments.md#lock-visual-fragment)

  ご利用いただけます：2026年5月21日（PT）

#### オーケストレーションキャンペーン

* **エンリッチメントアクティビティでリンクを追加** - オーケストレーションされたキャンペーンのエンリッチメントアクティビティで、「リンクを追加」機能を使用できるようになりました。 これにより、作業用テーブルデータと既存のデータベーステーブルとの間に直接関係を作成できます。


  ご利用いただけます：2026年5月20日（PT）

#### 決定

* **移行ワークフローAPI** – 依存関係の分析と移行ワークフローを作成するためのAPI コントラクトが更新されました。リクエスト URL （`sandbox`、`offer`または`decision`）に&#x200B;**`request-level`**&#x200B;を&#x200B;**クエリパラメーター**&#x200B;として渡します。 リクエストレベルをJSON本文で送信する必要はありません。 [詳細情報](../experience-decisioning/decisioning-migration-api.md)

  ご利用いただけます：2026年5月6日（PT）

* **DecisioningのAdobe Experience Manager コンテンツフラグメント** - Adobe Experience Manager コンテンツフラグメントをDecisioningの決定項目にマッピングし、意思決定ポリシー内でそれらを活用して、適切なフラグメントを適切な顧客に的確なタイミングで配信できるようになりました。 [詳細情報](../integrations/aem-fragments.md#aem-decisioning)

  この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

  ご利用いただけます：2026年5月20日（PT）

#### 統合

* **Adobe Experience Managerセレクターでの組織間のリポジトリアクセス** - Assetsアセットセレクター内で、複数の組織のリポジトリから直接アセットをシームレスに選択できるようになりました。

#### SMS

<!--
* **Opt-out and consent at phone number and sender** - For SMS, Journey Optimizer now records marketing consent and opt-out at the level of both the profile's phone number and short code. 

  This capability is currently only available for Sinch SMS configurations. [Read more](../mobile/mobile-configuration-sinch.md)
-->

* **文字カウント** - Adobe Journey Optimizer では、文字カウントを使用して SMS メッセージの長さをリアルタイムで監視できるようになりました。 メッセージが複数のセグメントに分割されるタイミングを確認できるので、書式設定をより適切に管理し、送信コストの予期しない増加を回避できます。 [詳細情報](../mobile/create-mobile-message.md)

* **カスタムデータセットに対する SMS インバウンド** - **SMS API 資格情報**&#x200B;で、デフォルトのトラッキングデータセットだけでなく、選択した&#x200B;**カスタムのプロファイル対応エクスペリエンスイベントデータセット**&#x200B;に&#x200B;**インバウンド SMS** をルーティングします。 [詳細情報](../mobile/mobile-webhook.md)

* **Webhook インターフェイスの機能強化** - SMS webhook を設定する際に、ユーザーインターフェイスに実用的な例を含む組み込みの設定ガイドが含まれるようになりました。これにより、設定フローを離れることなく、プロバイダーのペイロードを調整し、問題のトラブルシューティングを行うことが簡単になります。 [詳細情報](../mobile/mobile-webhook.md)

#### WhatsApp

* **WhatsApp ボタンのサポートとトラッキング** - WhatsApp テンプレートは&#x200B;**クイック返信**、**Call to action - URL**、**Call to action - phone**、**コピーコード**&#x200B;をサポートしていません。 Journey Optimizerは、サポートされているボタンを送信し、インタラクションを他のチャネルレポートと並行して追跡します。

* **WhatsApp チャネルコンテキストデータ** - Journey Optimizerは、WhatsApp チャネルから返された追加のインタラクションデータを取得し、`whatsAppChannelContext` フィールドグループの&#x200B;**AJO EmailTrackingExperienceEvent データセット**&#x200B;に保存するようになりました。

  +++ 次のフィールドがキャプチャされ、オーディエンスの構築やWhatsApp エンゲージメントの分析に使用できます

   * **`messageType`** - WhatsApp メッセージの種類（例：`templateBased`、`response`）
   * **`inboundMessage`** - インバウンド返信コンテンツ （例：`stop`、`start`、`subscribe`）
   * **`inboundNumber`** – 受信メッセージを受信した送信者ID
   * **`channelType`** - チャネルカテゴリ （`Utility`、`Marketing`または`Promotional`）
   * **`profileNumber`** – 受信メッセージを受信した電話番号
   * **`origTimestamp`** - Meta / WhatsAppの元のタイムスタンプ
   * **`status`** – 標準化されたプロバイダーのフィードバック （`sent`、`delivered`、`bounce`、`error`、`delay`、`duplicate`、`denylist`、`exclude`または`unknown`）と生のプロバイダーのステータスメッセージを含む配信ステータス
   * **`reactionEvent`** - ユーザー応答のコンテンツ：反応の絵文字、または特定のメッセージへの返信のメッセージテキスト
   * **`reactionMessageID`** – 応答する元のメッセージのID
   * **`reactionActionName`** – 応答アクションの種類（`react`、`unreact`または`reply`）
   * **`interactiveSelectedTitle`** - WhatsApp インタラクティブメッセージからユーザーが選択したタイトル
   * **`interactiveType`** - インタラクティブ メッセージの種類（`list reply`、`button reply`、または`button`）
   * **`interactiveSelectedDescription`** – 選択したWhatsApp インタラクティブオプションの説明
   * **`interactiveSelectedID`** - WhatsAppから選択したオプションのID

  +++


## 近日リリース予定 {#coming-soon}

以下の機能と機能強化は、5月後半にリリース予定です。 **情報は変更される場合があります**。 更新したリンク、画面、ドキュメントは、これらの更新が実稼動環境で公開すると共有されます。

### 新機能 {#coming-soon-features}

<table>
<thead>
<tr>
<th><strong>ジャーニー式のためのAI アシスタント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントがジャーニーの高度な式エディターで動作し、自然言語プロンプトを有効な式や条件付きロジックに変換できるようになりました。 構築したい式を記述すると、AI アシスタントがすぐに適用できる使いやすいコードを生成したり、フォローアッププロンプトで微調整したりできます。</p>
<p>この機能は、パブリック Betaとしてすべてのお客様が利用できます。</p>
<!--<p><img src="assets/do-not-localize/expression-assistant.gif"></p>-->
<p>ご利用いただけます：2026年5月22日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>非繰り返しオーディエンス読み取りジャーニーの自動補完</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>最後にアクティブなプロファイルが終了すると、非繰り返しの<strong> オーディエンスの読み取り</strong> ジャーニーが自動的に<strong>停止</strong> ステータスに移行するようになりました。 以前は、これらのジャーニーは、プロファイルがフローしなくなった場合でも、91日間のグローバルタイムアウトが期限切れになるまで<strong> ライブ </strong>のままでした。 この改善により、ジャーニーのステータスは、完了するとすぐに実際の実行ステータスを反映するようになり、手作業なしでジャーニーインベントリを正確に保つことができます。</p>
<p>この動作は、待機期間を引き起こすノード（待機ノード、リアクションノード、イベントトリガーのトランジションなど）を含むジャーニーには適用されません。 これらのジャーニーは、標準の91日間のグローバルタイムアウトの対象のままです。</p>
<p>ご利用いただけます：2026年5月22日（PT）</p>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ダイレクトメールチャネルでの意思決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>決定ポリシーをダイレクトメールジャーニーおよびキャンペーンに追加できるようになりました。 決定ポリシーは、決定エンジンを活用して、各オーディエンスメンバーに最適なコンテンツを動的に返すオファーのコンテナです。 ダイレクトメール決定は、バッチ決定のユースケースもサポートしており、特定のAdobe Experience Platform オーディエンス内の各プロファイルに対応するオファー項目を書き出すことができます。</p>
<!--<p><img src="assets/do-not-localize/exd-dm.gif"></p>-->
<p>ご利用いただけます：2026年6月1日</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化 – ターゲティング</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい<strong>Optimize</strong> ノードを使用して、特定のオーディエンスをターゲットにして、ビジネス中心のKPIを満たすのに最適なパスを決定します。</p>
<p>このツールを活用すれば、一対一のレベルで共感を呼ぶ可能性が高い、より効果的なマーケティング施策を策定し、顧客のマーケティングパーソナライゼーション活動を改善して、コンバージョンや収益などの重要な顧客エンゲージメント KPIを強化できます。</p>
<p>以前は制限付き可用性で使用されていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。</p>
<p>ご利用いただけます：2026年6月1日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー仲裁 – ランキング式</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>式を使用して、顧客プロファイルの属性と文脈要因にもとづいて、ジャーニーの優先順位スコアを自動的に高め、顧客が最も関連性の高いジャーニーに確実に参入できるようにしました。</p>
<p>以前は制限付き可用性で使用されていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。</p>
<p>ご利用いただけます：2026年6月1日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーシミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを<strong>シミュレーション</strong>に設定できます。 このモードを使用すると、<strong>シミュレートされたユーザー</strong>を使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。 一般公開リリースでは、Journey Agentを使用して、シミュレーションユーザーとイベントをシミュレーションメニューで直接生成できるようになりました。</p>
<p>利用開始日：2026年6月上旬</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンのファイルベースのターゲティング</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションされたキャンペーンでは、最初にAdobe Experience Platformにファイルを取り込むことなく、CSV ファイルまたはTXT ファイルをターゲットオーディエンスとしてキャンペーンキャンバスに直接読み込むことがサポートされるようになりました。 ファイルデータは実行時に消費され、Adobe Experience Platform データセットとして保持されません。 ファイルの設定時に、列のマッピング、データタイプ、NULL処理、列ごとのエラーポリシーを定義できます。 これは、完全な取り込みパイプラインの構築が実用的ではないアドホック送信やパートナーリストキャンペーンをサポートしています。 </p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>ご利用いただけます：2026年6月1日（PT）</p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#coming-soon-improvements}

#### ナビゲーション

* ジャーニーとキャンペーンの&#x200B;**フォルダー** - ジャーニーとキャンペーンをフォルダーに整理して、インターフェイスのナビゲーションと管理を改善できるようになりました。

  ご利用いただけます：2026年6月2日（PT）

#### ジャーニー

* **カスタムアクションでの証明書ベースのカスタム認証** - カスタムアクションで、証明書ベースのカスタム認証がサポートされるようになりました。 カスタム認証コンフィギュレーションにsubType: &quot;certificateCredential&quot;を追加することで、Journey OptimizerはAdobeのマネージド証明書を使用してJWT クライアントアサーションに署名し、アクセストークンと交換します。クライアントシークレットは必要ありません。 Azure Entra IDなど、証明書ベースのID確認を強制するエンタープライズ API向けに設計されています。

  ご利用いただけます：2026年5月22日（PT）

* **外部オーディエンスの補足識別子のサポート** - ジャーニーの補足識別子が、CSV ファイルから読み込まれたオーディエンスやFederated Audience Compositionで作成されたオーディエンスなど、外部オーディエンスでサポートされるようになりました。 オーディエンスからID以外の属性または個人ではないID属性を補足IDとして指定できます。スキーマのラベル付けは必要ありません。

  ご利用いただけます：2026年6月1日

#### オーケストレーションキャンペーン

* **関係データのループベースのパーソナライゼーション** - パーソナライゼーションエディターで、注文、アカウント、予約などの関係コレクションを繰り返し処理し、1つのレコードにつき1つのコンテンツブロックを1つの電子メールまたはSMS内にレンダリングするループブロックがサポートされるようになりました。 コレクションは、パーソナライゼーショントークンを使用してデータピッカーを通じて設定され、式の書き込みは必要ありません。

  ご利用いただけます：2026年6月1日

<!--

#### Email Designer

* **Rich text in editable fragment fields** - You can now add rich text to customizable fragments that are used in your email content. For example, when using the Text component as an editable field in the Email Designer, you can directly format the content (for example, bold and italics) and insert hyperlinks.

  Availability date: June 1, 2026
  
-->

#### キャンペーン

* **キャンペーンライフサイクルイベントに関する顧客アラート** – 新しいシステムアラートにより、アクションおよびAPI トリガーキャンペーンの主要なライフサイクルイベントが通知されるようになりました。 サンドボックスレベルでの購入。

  ご利用いただけます：2026年6月1日

* **キャンペーンのデフォルトの実行フィールドを上書き** – 以前はジャーニーレベルで使用されていましたが、キャンペーンのパラメーターで、メール、SMS、WhatsApp配信にグローバルに設定されているデフォルトの実行フィールドを上書きできるようになりました。

  ご利用いただけます：2026年6月1日（PT）

#### メール

* **受信者とキャンペーンごとにメール送信者の詳細をパーソナライズ** - オーケストレーションされたキャンペーンでは、プロファイル属性またはリレーショナルデータを使用して、名前、送信者アドレス、返信先などのメールヘッダーフィールドのパーソナライズがサポートされるようになりました。 これにより、送信者の詳細では、単一の企業アドレスを介してすべての送信をルーティングするのではなく、各受信者に関連するアドバイザー、場所、またはブランチを反映できます。

  ヘッダー値はチャネルレベルで設定でき、コンテキストデータを使用してキャンペーンごとに上書きすることで、より正確な制御が可能になります。

  ご利用いただけます：2026年6月1日（PT）

#### 設定

* **メッセージフィードバックイベントデータセットがバッチ取り込みに移行** - `AJO Message Feedback Event Dataset`はストリーミングモードからバッチ取り込みモードに移行中です。 この変更により、データ取り込みがストリーミング取り込み制限を超えないことが保証されます。 このデータセットをCustomer Journey Analytics レポートで使用する場合や、このデータセットに対してクエリを実行する場合は、最大2時間のデータ遅延が発生すると予想されます。

  ご利用いただけます：2026年6月1日（PT）

#### レポート

* **電子メールとSMS レポートのボットクリックを除外** – 電子メールとSMS レポートから人間ではない（ボット）インタラクションを除外するための新しい見積もり指標が利用可能になりました。 これには、推定クリック数、クリックスルー率（CTR）、クリックして開く率（CTOR）などが含まれ、実際の顧客エンゲージメントをより正確に把握することができます。 既存の指標は変更されず、これらの新しい指標を現在のレポートと併用することで、分析を改善できます。

  ご利用いただけます：2026年6月1日（PT）
