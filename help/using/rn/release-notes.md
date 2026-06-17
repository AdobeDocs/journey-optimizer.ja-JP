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
feature_v2: id: a7b2bfc5-be71-4740-b371-76fa6be8df02
subfeature_v2: id: eac3bd2c-b027-4dfa-80d2-0bd752ae4794id: e437f8db-d1f7-44c0-bdc0-b0a361adc4c0id: c4e1378f-bb85-43a2-8b7c-1623ad3b14b5
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: e0a12bd7971c778378f9905cf93653792f38509d
workflow-type: tm+mt
source-wordcount: 2279
ht-degree: 40%

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
>これらのリリースノートに記載されている機能には、各変更がお客様の環境でアクセス可能になるタイミングを示す&#x200B;**公開日**&#x200B;が含まれています。 **近日リリース予定**&#x200B;のアコーディオンへのエントリは、今後数日または数週間以内に予定されています。 次の節の情報は変更される場合があります。

## 26年6月のリリースノート {#june-26-rn}

2026年6月のリリースでは、**ジャーニーシミュレーション**、**ジャーニーパス最適化ターゲティング**、**ジャーニーフラグメント**&#x200B;など、いくつかの主要な機能が一般公開されました。さらに、ジャーニーとコンテンツにおける新しいAIによるオーサリング、ダイレクトメールチャネルに対する意思決定サポートの拡張、セキュリティと管理機能の追加が追加されました。 以下の機能と改善点は、テーマ別に整理されています。 また、追加の変更は今後数日または数週間以内に予定されています。

### ジャーニー {#june-26-journeys}

このリリースでは、ジャーニーに次の機能と機能強化が追加されました。 また、追加の変更は今後数日または数週間以内に予定されています。


<table>
<thead>
<tr>
<th><strong>ジャーニーシミュレーション（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーをシミュレーションに設定できます。 このモードでは、シミュレートされたユーザーを使用してロジックを検証できます。 これらはシミュレーション専用に作成された一時的なプロファイルで、Adobe Experience Platform で永続的なテストプロファイルを管理することなく、自由にテストできます。 </p>
<p>この機能は、ジャーニーシミュレーションは限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました。 この一般提供リリースでは、Journey エージェントを使用して、シミュレーションユーザーとイベントをシミュレーションメニューで直接生成できるようになりました。</p>
<p><img src="assets/do-not-localize/journey-simulation.gif"></p>
<p>詳しくは、<a href="../building-journeys/simulate-journey-gs.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーフラグメント（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer で<strong>ジャーニーフラグメント</strong>を作成できるようになりました。 ジャーニーフラグメントは、一度作成すればサンドボックスをまたいで任意のジャーニーにドロップできる、再利用可能なジャーニーノードのセットです。 実施要件の確認、優先チャネルのルーティングロジック、ウェルカムシーケンスなど、フラグメントを使用することで、チームは毎回同じロジックをゼロから再作成することなく、より迅速に作業を進め、一貫性を維持できます。</p>
<p>作成したフラグメントは、専用の<strong>フラグメント在庫</strong>に保存され、<strong>ジャーニーフラグメント</strong>アクティビティを使用して任意のジャーニーに挿入できます。</p>
<p>以前は制限付き可用性で利用可能でしたが、この機能はすべての顧客で一般に利用可能になりました。 ジャーニーフラグメントは<strong> サンドボックスツール </strong>もサポートしており、サンドボックス間でフラグメントをパッケージ化および書き出すことができます。</p>
<p>詳しくは、<a href="../building-journeys/journey-fragments.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化 – ターゲティング（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong> アクティビティの最適化</strong>では、<strong> ターゲティングルール </strong>がサポートされるようになりました。これにより、オーディエンスセグメントまたはプロファイル属性に基づいて、顧客が特定のジャーニーパスの対象として選定するために満たす必要がある特定の基準を定義できます。</p>
<p>顧客がランダムにパスに割り当てられる実験とは異なり、ターゲティングでは決定論的ロジックを使用して、適切なオーディエンスまたは顧客プロファイルが目的のパスにルーティングされるようにします。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><img src="assets/do-not-localize/optimize.gif"></p>
<p>詳しくは、<a href="../building-journeys/path-targeting.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月8日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー式用 AI アシスタント（パブリックベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、ジャーニーの高度な式エディターで機能して、自然言語プロンプトを有効な式と条件付きロジックに変換するようになりました。 作成したい式を説明すると、AI アシスタントがすぐに適用できる使いやすいコードを生成したり、フォローアッププロンプトを通じて調整したりできます。</p>
<p>この機能は、パブリックベータ版としてすべてのユーザーが使用できます。</p>
<p><img src="assets/do-not-localize/expression-assistant.gif"></p>
<p>詳しくは、<a href="../building-journeys/expression/expression-agent.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月3日（PT）</p> 
</td>
</tr>
</tbody>
</table>

* **外部オーディエンス向けの補助識別子サポート** - ジャーニーの補助識別子は、CSVファイルからインポートされたオーディエンスや、連合オーディエンス構成で作成されたオーディエンスなど、外部オーディエンスに対してサポートされるようになりました。 オーディエンスから ID 以外の属性またはユーザー ID 以外の属性を補助 ID として指定できます。スキーマのラベル付けは不要です。 [詳細情報](../building-journeys/supplemental-identifier.md)

  ご利用いただけます：2026年6月11日（PT）

* **非繰り返しの読み取りオーディエンスジャーニー**&#x200B;の自動停止 – 繰り返しの&#x200B;**読み取りオーディエンス** ジャーニーが、最後にアクティブなプロファイルが終了すると、自動的に&#x200B;**停止** ステータスに移行するようになりました。 以前は、これらのジャーニーは、プロファイルが流れなくなった場合でも、91 日間のグローバルタイムアウトが期限切れになるまで&#x200B;**ライブ**&#x200B;のままになっていました。 この機能強化により、ジャーニーステータスは完了するとすぐに実際の実行状態を反映するので、手動介入なしでジャーニーインベントリの正確性を維持できます。

  この動作は、待機ノード、反応ノード、イベントトリガーのトランジションなど、待機時間を発生させるノードを含むジャーニーには適用されません。 これらのジャーニーは、標準の 91 日間のグローバルタイムアウトの対象のままです。 [詳細情報](../building-journeys/end-journey.md#auto-stop-non-recurring)

  ご利用いただけます：2026年6月9日（PT）

* **カスタムアクションでの証明書ベースのカスタム認証** - カスタムアクションで、証明書ベースのカスタム認証がサポートされるようになりました。 Journey Optimizer は、カスタム認証設定に `subType: "certificateCredential"` を追加することで、アドビが管理する証明書を使用して JWT クライアントアサーションに署名し、アクセストークンと交換します。クライアント秘密鍵は不要です。 Microsoft Entra IDなど、証明書ベースのID確認を強制するエンタープライズ API向けに設計されています。 [詳細情報](../datasource/external-data-sources.md#certificate-credential)

  ご利用いただけます：2026年6月4日（PT）

### オーケストレーションキャンペーン {#june-26-oc}

このリリースのオーケストレーション済みキャンペーンには、次の機能と機能強化が導入されています。

+++ 近日リリース予定 – **以下の情報は変更される可能性があります。**

<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンでのファイルベースのターゲティング</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションされたキャンペーンでは、最初にAdobe Experience Platformにファイルを取り込むことなく、<strong>CSVまたはTXT ファイル </strong>をターゲットオーディエンスとしてキャンペーンキャンバスに直接読み込むことがサポートされるようになりました。 ファイルデータは実行時に消費され、Adobe Experience Platform データセットとして保持されません。 ファイルの設定時に、列のマッピング、データタイプ、NULL処理、列ごとのエラーポリシーを定義できます。 検証に失敗した行は、キャンペーンが実行される前に却下され、ログに記録されます。これにより、手作業による事前処理なしでオーディエンスをクリーンに保つことができます。 これは、完全な取り込みパイプラインの構築が実用的ではないアドホック送信やパートナーリストキャンペーンに特に適しています。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p> ご利用いただけます：2026年6月30日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **関係データのループベースのパーソナライゼーション** - パーソナライゼーションエディターで、注文、アカウント、予約などの関係コレクションを繰り返し処理し、1つのレコードにつき1つのコンテンツブロックを1つの電子メールまたはSMS内にレンダリングするループブロックがサポートされるようになりました。 コレクションは、パーソナライゼーショントークンを使用してデータピッカーを通じて設定され、式の書き込みは必要ありません。 [詳細情報](../orchestrated/add-personalization.md#enrichment-collections)

  利用可能日：2026年6月末

+++

### 決定 {#june-26-decisioning}

このリリースでは、決定に次の機能と機能強化が追加されました。

<table>
<thead>
<tr>
<th><strong>ダイレクトメールチャネルでの決定のサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ダイレクトメールジャーニーとキャンペーンに決定ポリシーを追加できるようになりました。 決定ポリシーは、各オーディエンスメンバーに最適なコンテンツを動的に返すことを目的に、決定エンジンを活用するオファーのコンテナです。 また、ダイレクトメール決定は、バッチ決定のユースケースもサポートし、特定の Adobe Experience Platform オーディエンスのすべてのプロファイルに対応するオファー項目をエクスポートできます。 </p>
<p><img src="assets/do-not-localize/exd-dm.gif"></p>
<p>詳しくは、<a href="../experience-decisioning/use-decision-policy.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月3日（PT）</p>
</td>
</tr>
</tbody>
</table>

+++ 近日リリース予定 – **以下の情報は変更される可能性があります。**

* **動的なアイテム属性** – 決定項目のカスタム属性を、プロファイル、コンテキスト、オーディエンスのデータを使用して、配信時にパーソナライズできるようになりました。 これにより、コンテンツのバリエーションを作成するために、重複するオファーを管理する必要がなくなり、マーケターはより少ない項目で柔軟に意思決定をおこなえるようになります。

+++

### コンテンツ管理 {#june-26-content}

このリリースでは、コンテンツ管理に次の機能と機能強化が追加されました。

<table>
<thead>
<tr>
<th><strong>コンテンツのバリエーションをシミュレート：エクスペリエンスの更新とAI バリエーションの生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>2つの更新プログラムが、<strong> コンテンツをシミュレート </strong> ワークフローで利用できるようになりました。</p>
<ul>
<li><strong>新しいデフォルトパス </strong> – 「<strong> コンテンツをシミュレート </strong>」をクリックすると、デフォルトで<strong> コンテンツのバリエーションをシミュレート </strong> エクスペリエンスが開くようになりました。 1つの画面から、手動またはCSV/JSON ファイルからサンプル入力を追加し、シミュレートされたユーザーを再利用し、レンダリングをプレビューし、プルーフを送信できます。 Adobe Experience Platform テストプロファイルを使用してプレビューするには、テストプロファイルデータを使用してプルーフを送信するか、メール受信トレイのレンダリングとスパムレポートを確認するには、<strong> コンテンツをシミュレート </strong>をクリックし、ドロップダウンから<strong> コンテンツをシミュレート（AEP プロファイル） </strong>を選択します。</li>
<li><strong>AIで生成されたコンテンツのバリエーション </strong> — <strong> コンテンツのバリエーションをシミュレート </strong> エクスペリエンスで、<strong>生成</strong>をクリックすると、AIを使用してコンテンツのバリエーションを自動的に作成できます。 メッセージの分析、パーソナライゼーションフィールドと条件付き分岐の検出、現実的な値の入力を可能にし、あらゆるバリエーションを手作業で作成することなくレンダリングを検証できます。</li>
</ul>
<p>詳しくは、<a href="../test-approve/simulate-sample-input.md">詳細ドキュメント</a>を参照してください。</p>
<p>ご利用いただけます：2026年6月9日（PT）</p>
</td>
</tr>
</tbody>
</table>

### メールチャネル {#june-26-email}

このリリースでは、メールチャネルに次の機能強化が追加されました。

* **URL パラメーターの暗号化** - メールメッセージに追加されたトラッキングリンクやランディングページリンクの URL パラメーターを暗号化できるようになりました。 これにより、機密性の高いパラメーターデータのセキュリティレイヤーが追加されます。 この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。 [詳細情報](../personalization/url-parameter-encryption.md)

  公開日：2026年6月1日（PT）

* **キーレジストリの新しい権限** - URL パラメーターの暗号化に必要なキーにアクセスして管理するには、新しい 2 つの権限（**キーレジストリを管理**&#x200B;と&#x200B;**キーレジストリを表示**）が必要になりました。 [詳細情報](../administration/high-low-permissions.md#administration-permissions)

  公開日：2026年6月1日（PT）

+++ 近日リリース予定 - **以下の情報は変更される場合があります。**

<table>
<thead>
<tr>
<th><strong>E メールDesignerでのコンテンツ品質チェック</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、電子メールのDesignerで自動的に技術的な検証を直接実行できるようになりました。これにより、送信前にHTMLとCSSの問題を把握できます。</p>
<p><code>&lt;script&gt;</code>および<code>&lt;base&gt;</code> タグ、Microsoft Outlookのレイアウトを解除できる空のdiv、HTML metaの更新タグ、Gmailでトリガーレンダリングが失敗するCSSまたはHTML サイズのしきい値など、サポートされていない要素をチェックします。</p>
<p>結果は、オーサリングパネルで直接エラー、警告、または情報通知として表示され、コンテキストの詳細とワンクリック修正が可能な場合は表示されるので、エディターを離れることなく問題を解決できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>電子メールサイズの縮小を有効にする</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、電子メールのレンダリング方法に影響を与えることなく、不要な空白、コメント、冗長なコードを削除して、電子メールのHTMLのサイズを縮小するオプションが追加されました。</p>
<p>これにより、一部のメールプロバイダーがメッセージのフラグを立てたり却下したりするためのしきい値を回避することで、配信品質を向上させることができます。また、受信者の読み込み時間を短縮することもできます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>フラグメントの編集可能フィールドのリッチテキスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールコンテンツで使用される、カスタマイズ可能なフラグメントにリッチテキストを追加できるようになりました。</p>
<p>例えば、電子メールDesignerでテキストコンポーネントを編集可能フィールドとして使用する場合、コンテンツの書式（太字や斜体など）を直接設定し、ハイパーリンクを挿入できます。</p>
</td>
</tr>
</tbody>
</table>

+++

### コンテンツと統合 {#june-26-integration}

このリリースでは、コンテンツ管理と統合に次の機能と機能強化が導入されています。

+++ 近日リリース予定 – **以下の情報は変更される可能性があります。**

<table>
<thead>
<tr>
<th><strong>Journey OptimizerでのAdobe Experience Manager コンテンツフラグメントの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このリリースでは、Journey Optimizer オーサリングワークフロー内で<strong>Adobe Experience Manager コンテンツフラグメント </strong>をより使いやすく、より制御しやすく、より実稼動対応にするための機能強化がいくつか追加されました。</p>
<ul>
<li>Journey Optimizerでは、オーサー、パブリッシュ、認証済みパブリッシュ層など、複数のAdobe Experience Manager設定からコンテンツフラグメントを取得できるようになりました。</li>
<li>フラグメントを選択すると、そのコンテキストはメッセージ全体を通じて保持されるので、作成者は再選択することなく、コンテンツブロック間でフラグメントフィールドを再利用できます。</li>
<li>新しい専用のコンテンツフラグメントリストページがJourney Optimizerに導入され、ライフサイクル管理が向上しました。同期されていないフラグメントを特定し、手動で同期をトリガーして最新の状態を維持できます。</li>
<li>ロケールとバリエーションのサポートにより、マーケターは同じコンテンツフラグメントの代替バージョンをより慎重に操作できるようになりました。</li>
<li>Adobe Journey OptimizerからAdobe Experience Manager コンテンツへのアクセス方法を柔軟に設定できるようになりました。 このリリースでは、ジャーニーとキャンペーンで使用するコンテンツフラグメントのソースリポジトリ </strong>を<strong>切り替える機能が導入されました。</li>
<li><b>Managed Services</b>との互換性を持つようになり、Adobe Experience Manager コンテンツフラグメントをJourney Optimizerで直接表示、アクセス、使用してパーソナライズできるようになりました。 Adobe Experience Manager Managed Servicesのリポジトリ URLを、1回限りの設定として設定に追加するだけです。</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ADOBE EXPERIENCE MANAGER Asset EssentialsのAI アシスタントとの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントが、メール、Web ページ、プッシュ通知を生成する際に、Adobe Experience Manager Assetsから<b> ブランド承認済み画像</b>を直接自動的に取得するようになりました。 これにより、Assetsを手動で検索したり、汎用的なAI フォールバックを利用したりする必要がなくなり、あらゆるビジュアルが完全に正確で、ブランドに準拠したものになります。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コンテンツ生成向けAI アシスタントの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このリリースでは、より強力な画像編集、より信頼性の高いブランド抽出、画像フローでのコンテンツ信憑性のサポートにより、<strong>AI アシスタント </strong>のコンテンツ生成エクスペリエンスが向上しました。</p>
<ul>
<li>Firefly サードパーティモデルのサポートを含む、画像の生成フローで<strong>AI画像編集</strong>を使用できるようになりました。これにより、アシスタントを終了することなくソース画像を絞り込むことができます。</li>
<li><strong> ブランドシグナル抽出</strong>は、より高品質な結果を提供します。 選択したページに十分なシグナルがない場合、改善されたフォールバックによって、色、タイポグラフィ、ガイドラインなどのブランド属性が設定されるようになりました。</li>
<li><strong>Web ベースのブランド抽出</strong>は信頼性が高くなります。 タイムアウト処理の改善により、ページ、ポップアップ、Cookie バナーが抽出をブロックするのを防ぐことができます。</li>
<li><strong> コンテンツの信頼性（CAI） </strong>が画像フローでサポートされるようになりました。 このリリースでは、参照画像のアップロードの問題も修正され、既存のC2PA マニフェストを持たない画像の処理も改善されています。</li>
</ul>
</td>
</tr>
</tbody>
</table>

+++

### 管理 {#june-26-administration}

このリリースでは、管理とデータ管理に次の機能強化が追加されました。

* [!BADGE 重要]{type=Informative} **AJO Message Feedback Event Dataset moving to batch ingestion** - **AJO Message Feedback Event Dataset**&#x200B;は、ストリーミング取り込みからバッチ取り込みに移行しています。 その結果、このデータセットに対して最大2時間のデータ待ち時間が期待されます。 Customer Journey Analyticsでレポートを作成している場合や、このデータセットを使用してクエリを実行している場合は、今後この遅延が増加することを考慮してください。 [詳細情報](../data/datasets-query-examples.md#message-feedback-event-dataset)

  ご利用いただけます：2026年6月10日（PT）

* **キャンペーンライフサイクルイベントに関する顧客アラート** - 新しいシステムアラートにより、アクションおよび API トリガーキャンペーンの主要なライフサイクルイベントが通知されるようになりました。 サンドボックスレベルで登録してください。 [詳細情報](../reports/alerts.md)

  公開日：2026年6月1日（PT）

<!--
+++ Coming soon — **Information below is subject to change.**

* **Override the default execution field in campaigns** - Previously available at the journey level, you can now override the default execution field set globally for your Email, SMS and WhatsApp deliveries in the campaign parameters.

  Availability date: Early June, 2026

+++
-->
