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
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: b3538224-471e-4c63-a444-9b19d89ae29c
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: c2beecbb-b93e-4ae3-baa9-72adcdc06781
  - id: cfba2953-2ce9-4b00-a00c-71cd338ae63f
  - id: ee5bb250-0884-4d71-86eb-d8489e8bcadd
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 6e45f1930e70702b3f79449edbe1c73b9cffb8c1
workflow-type: tm+mt
source-wordcount: 1566
ht-degree: 38%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。 これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は継続的配信モデルに従って、アドビが新機能、機能強化、修正を継続的に提供できるようにします。 このアプローチにより、スケーラブルで段階的な機能のロールアウトが可能になり、すべての環境をまたいでパフォーマンスと安定性を確保できます。

このモデルにより、リリースノートは毎月のリリースの間に更新されます。 リリースサイクルと可用性フェーズについて詳しくは、[Journey Optimizer リリースサイクル](releases.md)を参照してください。

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
<th><strong>Content Advisor Selector</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、Experience Manager Assetsとコンテンツフラグメントの両方を選択するための統一モーダルである<strong>Content Advisor セレクター</strong>を使用するようになりました。 新しいセレクターは、すべてのアセットの閲覧、検索、フィルタリングをサポートし、Dynamic Media レンディションを含み、ダイナミックアセットを使用するときに画像レンディションを簡単に追加できる強化されたユーザーインターフェイス機能を組み込んでいます。</p>
<p>以前は制限付き可用性で使用されていましたが、この機能はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
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

#### 決定

* **移行ワークフローAPI** – 依存関係の分析と移行ワークフローを作成するためのAPI コントラクトが更新されました。リクエスト URL （`sandbox`、`offer`または`decision`）に&#x200B;**`request-level`**&#x200B;を&#x200B;**クエリパラメーター**&#x200B;として渡します。 リクエストレベルをJSON本文で送信する必要はありません。 [詳細情報](../experience-decisioning/decisioning-migration-api.md)

  ご利用いただけます：2026年5月6日（PT）

#### SMS

<!--
* **Opt-out and consent at phone number and sender** - For SMS, Journey Optimizer now records marketing consent and opt-out at the level of both the profile's phone number and short code. 

  This capability is currently only available for Sinch SMS configurations. [Read more](../sms/sms-configuration-sinch.md)
-->

* **文字カウント** - Adobe Journey Optimizer では、文字カウントを使用して SMS メッセージの長さをリアルタイムで監視できるようになりました。 メッセージが複数のセグメントに分割されるタイミングを確認できるので、書式設定をより適切に管理し、送信コストの予期しない増加を回避できます。 [詳細情報](../sms/create-sms.md)

* **カスタムデータセットに対する SMS インバウンド** - **SMS API 資格情報**&#x200B;で、デフォルトのトラッキングデータセットだけでなく、選択した&#x200B;**カスタムのプロファイル対応エクスペリエンスイベントデータセット**&#x200B;に&#x200B;**インバウンド SMS** をルーティングします。 [詳細情報](../sms/sms-webhook.md)

* **Webhook インターフェイスの機能強化** - SMS webhook を設定する際に、ユーザーインターフェイスに実用的な例を含む組み込みの設定ガイドが含まれるようになりました。これにより、設定フローを離れることなく、プロバイダーのペイロードを調整し、問題のトラブルシューティングを行うことが簡単になります。 [詳細情報](../sms/sms-webhook.md)

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
<th><strong>ジャーニーシミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを<strong>シミュレーション</strong>に設定できます。 このモードを使用すると、<strong>シミュレートされたユーザー</strong>を使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。 一般公開リリースでは、Journey Agentを使用して、シミュレーションユーザーとイベントをシミュレーションメニューで直接生成できるようになりました。</p>
<p>ご利用いただけます：2026年5月28日（PT）</p>
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
<p>ご利用いただけます：2026年5月28日（PT）</p>
</td>
</tr>
</tbody>
</table>


### 機能強化  {#coming-soon-improvements}

#### ナビゲーション

* ジャーニーとキャンペーンの&#x200B;**フォルダー** - ジャーニーとキャンペーンをフォルダーに整理して、インターフェイスのナビゲーションと管理を改善できるようになりました。

  ご利用いただけます：2026年5月21日（PT）

#### オーケストレーションキャンペーン

* **エンリッチメントアクティビティでリンクを追加** - オーケストレーションされたキャンペーンのエンリッチメントアクティビティで、「リンクを追加」機能を使用できるようになりました。 これにより、作業用テーブルデータと既存のデータベーステーブルとの間に直接関係を作成できます。


  ご利用いただけます：2026年5月26日（PT）

* **関係データのループベースのパーソナライゼーション** - パーソナライゼーションエディターで、注文、アカウント、予約などの関係コレクションを繰り返し処理し、1つのレコードにつき1つのコンテンツブロックを1つの電子メールまたはSMS内にレンダリングするループブロックがサポートされるようになりました。 コレクションは、パーソナライゼーショントークンを使用してデータピッカーを通じて設定され、式の書き込みは必要ありません。


  ご利用いただけます：2026年5月28日（PT）

#### メール

* **受信者とキャンペーンごとにメール送信者の詳細をパーソナライズ** - オーケストレーションされたキャンペーンでは、プロファイル属性またはリレーショナルデータを使用して、名前、送信者アドレス、返信先などのメールヘッダーフィールドのパーソナライズがサポートされるようになりました。 これにより、送信者の詳細では、単一の企業アドレスを介してすべての送信をルーティングするのではなく、各受信者に関連するアドバイザー、場所、またはブランチを反映できます。

  ヘッダー値はチャネルレベルで設定でき、コンテキストデータを使用してキャンペーンごとに上書きすることで、より正確な制御が可能になります。


  ご利用いただけます：2026年5月29日（PT）

  &#x200B;#### 設定

* **メッセージフィードバックイベントデータセットがバッチ取り込みに移行** - `AJO Message Feedback Event Dataset`はストリーミングモードからバッチ取り込みモードに移行中です。 この変更により、データ取り込みがストリーミング取り込み制限を超えないことが保証されます。 このデータセットをCustomer Journey Analytics レポートで使用する場合や、このデータセットに対してクエリを実行する場合は、最大2時間のデータ遅延が発生すると予想されます。

  ご利用いただけます：2026年5月29日（PT）
