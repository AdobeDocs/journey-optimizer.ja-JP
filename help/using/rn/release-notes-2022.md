---
title: リリースノート 2022
description: Journey Optimizer 2022 リリースノート
exl-id: 0997a640-3f89-4460-ba93-ea21a9d4efc5
source-git-commit: b31eb2bcf52bb57aec8e145ad8e94790a1fb44bf
workflow-type: ht
source-wordcount: '1790'
ht-degree: 100%

---

# リリースノート 2022 {#release-notes-2022}

このページは、2022年にリリースされた [!DNL Journey Optimizer] の機能と改善点をすべて一覧表示しています。

## 2022年6月リリース {#june-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ユーザーへの SMS の送信（使用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><b>Sinch</b> または <b>Twilio</b> との統合を使用して、Journey Optimizer で SMS の作成、パーソナライズおよび送信ができるようになりました。</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>SMS チャネルは現在、一連の組織でのみ使用できます（使用制限があります）。 詳しくは、アドビ担当者にお問い合わせください。</p>
<p>SMS の作成および送信方法については、この<a href="../messages/create-sms.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Stock との統合による効果的な画像の迅速な検索</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Stock と Adobe Journey Optimizer 電子メールデザイナーの統合プラグインを使用すると、メッセージオーサリングで使用する画像のナビゲーション、ライセンス取得および保存を簡単に行うことができます。</br> 新しい「<b>類似のストックフォトを検索</b>」オプションを使用すると、画像の内容、カラーおよび構成に一致するストックフォトを見つけることもできます。 </p>
<img src="assets/do-not-localize/stock-rn.gif"/>
<p>詳しくは、<a href="../design/stock.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>すべてのメールでの「BCC で E メールを送信」の使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>BCC（ブラインドカーボンコピー）でメールを送信機能を使用して、Adobe Journey Optimizer から送信されたメールを保存できるようになりました。メールプリセットでこのオプションを有効にして、送信されたすべてのメールが BCC アドレスにブラインドコピーされるようにします。</p>
<img src="assets/do-not-localize/bcc-rn.gif"/>
<p>詳しくは、<a href="../configuration/bcc-email.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the <a href="../offers/ranking/personalized-optimization-model.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>サンドボックス間でのオブジェクトのコピー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer サンドボックスから別のサンドボックスに（例：非実稼動サンドボックスから実稼動サンドボックスに）、エクスペリエンスを再作成できるようになりました。この新しい機能では、ジャーニーが正しく実行されるために必要なオブジェクトを含め、ジャーニー全体が一方の環境からもう一方の環境にコピーされます。ジャーニーに加えて、オファー、メッセージ、スキーマ、データセット、データソース、イベント、アクションなど、他のコンポーネントもコピーできます。</p>
<p>詳しくは、 <a href="../building-journeys/copy-to-sandbox.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content. In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### 機能強化

**意思決定管理**

* **HTML および JSON ファイルのサポート** - 外部の HTML ファイルと JSON ファイルを Adobe Experience Cloud アセットライブラリからオファー表示域のコンテンツにドラッグ＆ドロップできるようになりました。[詳細情報](../offers/offer-library/add-representations.md#html-json)


**メール**

* **テンプレートとして保存** - メールコンテンツをテンプレートとして保存し、他のメッセージを作成する際に再利用できるようになりました。[詳細情報](../design/email-templates.md)


**管理**

* **トラッキング URL パラメーターのプレビュー** - メッセージプリセットを設定する際に、URL トラッキングパラメーターを定義すると、結果として生成されるトラッキング URL の動的プレビューが表示されるようになりました。[詳細情報](../configuration/email-settings.md#url-tracking)

* **メッセージプリセットの編集** - メッセージプリセットを更新する際、処理時間は最大 3 時間に制限されるようになりました。[詳細情報](../configuration/channel-surfaces.md#edit-channel-surface)

* **IP プールの編集** - IP プールを更新する際、処理時間は最大 3 時間に制限されるようになりました。[詳細情報](../configuration/ip-pools.md#edit-ip-pool)




## 2022年5月リリース {#may-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージ頻度ルール</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>過度に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルのビジネスルールを設定できるようになりました。</p>
<img src="assets/do-not-localize/frequency-rn.gif"/>
<p>詳しくは、<a href="../configuration/frequency-rules.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定管理 - AI ランキング自動最適化モデル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>意思決定管理で、トレーニング済みモデルシステムを使用できるようになりました。この新しい機能は、特定のプロファイルに対して表示するオファーをランク付けします。</p>
<img src="assets/do-not-localize/optimization.gif"/>
<p>詳しくは、<a href="../offers/offer-activities/configure-offer-selection.md#use-ranking-strategy">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Attribute-based Access Control (ABAC)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Permission management in Journey Optimizer has been extended to data access. You can now manage data access for specific teams or groups of users (i.e. internal, external, 3rd parties) ​and manage access to specific types of data (i.e. Sensitive Personal Data/SPD).</p>
<p>This capability is available for a limited set of customers.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Journey Optimizer 監査ログ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer リソースでユーザーが実行したアクションを監視できるようになりました。</p>
<img src="assets/do-not-localize/audit-rn.gif"/>
<p>詳しくは、 <a href="../privacy/audit-logs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**パーソナライゼーション**

* **文字を非表示にする新しいヘルパー関数** - `mask` ヘルパー関数を使用すると、文字列の一部を「X」文字に置き換えることができます。[詳細情報](../personalization/functions/string.md#mask)

**ランディングページ**

* **フォームのないランディングページ** - フォームを含まず、訪問者のアクションを必要としないランディングページを作成および公開できるようになりました。
* **ランディングページテンプレート** - ランディングページをテンプレートとして保存し、他のランディングページを作成する際に再利用できるようになりました。[詳細情報](../landing-pages/lp-templates.md)
* **プライマリページに戻る** - 同じランディングページ内の任意のサブページからプライマリページへのリンクを追加できるようになりました。
* **カスタム JavaScript のサポート** - ランディングページコンテンツにカスタム JavaScript を追加して、高度なスタイル設定を実行したり、ランディングページにカスタム動作を追加したりできるようになりました。[詳細情報](../landing-pages/lp-custom-js.md)

**ジャーニー**

* **セグメントを読み取り** - 一回限りのセグメントを読み取りジャーニーは、ジャーニーの実行から 30 日後に、完了ステータスに移動するようになりました。スケジュールされた読み取りセグメントの場合、最後の実行から 30 日後になります。[詳細情報](../building-journeys/read-segment.md)
* **式エディター** - [limit](../building-journeys/functions/functionlimit.md) 関数が追加され、リストの項目数を制限できるようになりました。[sort](../building-journeys/functions/functionsort.md) 関数を使用して、リストオブジェクトを並べ替えることができるようになりました。また、listObject のサポートが [discint](../building-journeys/functions/functiondistinct.md) および [distinctWithNull](../building-journeys/functions/functiondistinctwithnull.md) 関数に追加されました。

**管理**

* **ライセンス使用状況ダッシュボードの更新** - [!DNL Adobe Journey Optimizer] でユーザーインターフェイス使用できるライセンス使用状況ダッシュボードに、**ライセンス済み**&#x200B;の平均的なプロファイル充実度の正確な値を反映できるようになりました。この指標表示域にドロップが表示されます。つまり、ライセンス制限が正しくレポートされました。 [詳細情報](../segment/license-usage.md)


## 2022年4月リリース {#april-2022-release}

### 機能強化

**ランディングページ**

* **「オプトイン／オプトアウト」チェックボックスの新しいオプション** - サブスクリプションランディングページにオプトイン／オプトアウト用の単一チェックボックスを挿入できるようになりました。ユーザーは、同意（オプトイン）するにはチェックボックスをオンにし、同意を削除（オプトアウト）するにはオフにする必要があります。[詳細情報](../landing-pages/design-lp.md#define-lp-specific-content)

* **ランディングページのフィールドの事前入力** - ユーザーがランディングページのフィールドにプロファイル情報を事前入力できるようになりました。[詳細情報](../landing-pages/create-lp.md#configure-primary-page)

**意思決定管理**

* **Edge での Decisioning API** - Edge Decisioning API は、Offer Decisioning で管理されるパーソナライズされたオファーを配信およびレンダリングできます。Offer Decisioning ユーザーインターフェイス（UI）または API を使用して、オファーとその他の関連オブジェクトを作成できます。[詳細情報](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md)

**管理**

* **PTR 送信時間** - PTR 編集の有効期間が数時間になりました。[詳細情報](../configuration/ptr-records.md#processing)

**メールデザイン**

* **20 個の新しいメールテンプレート**&#x200B;が Journey Optimizer でメールコンテンツをデザインするために使用できるようになりました。

**ユーザーインターフェイス**

* **Journey Optimizer UI のコンテキストヘルプ** - Journey Optimizer の複数のページにコンテキストヘルプのリンクを追加しました。「i」アイコンが使用可能な場合は、このアイコンをクリックすると、現在の機能の簡単な説明が表示され、関連記事にアクセスできます。

**Adobe Campaign Standard との統合**

Adobe Campaign Standard をご利用のお客様は、Journey Optimizer を使用してメール、プッシュ通知および SMS を送信できるようになりました。新しい組み込みアクションを使用すると、Journey Optimizer への Campaign Standard トランザクションメッセージ機能を活用できます。[詳細情報](../action/acs-action.md)

<!--
### Fixes

* Fixed an issue which caused tracking reports not to be available as the `JourneyActionId` was not properly populated. PLATIR-19854, CJM-26006
* Fixed an error on business events which could block the journey publication. CJM-25931
* Fixed an issue which could prevent images in Email Designer templates from being displayed. PLATIR-18176, CJM-25008
-->

## 2022年3月リリース {#march-2022-release}

### 機能強化

**ジャーニー**

* 統合プロファイルスキーマに不要なフィールドが含まれないようにするために、ジャーニーステップイベントスキーマはプロファイルに対してデフォルトでは有効にならなくなりました。必要に応じて、有効にすることができます。[詳細情報](../reports/sharing-overview.md)
* エクスポートジョブに関連する新しいステップイベントが、Journey Optimizer から Adobe Experience Platform に送信されるようになりました。クエリの例がドキュメントに追加されました。[詳細情報](../reports/query-examples.md)

**意思決定管理**

* すべてのユーザーまたは 1 つの特定のプロファイルに対して、およびすべてのプレースメントまたは各プレースメントに対して、オファーキャッピングを適用するかどうかを指定できるようになりました。[詳細情報](../offers/offer-library/add-constraints.md#capping)
* Batch Decisioning API を使用すると、組織は 1 回の呼び出しで特定のセグメント内のすべてのプロファイルに対して Offer Decisioning 機能を使用できます。セグメント内の各プロファイルのオファーコンテンツは、AEP データセットに配置され、カスタムバッチワークフローで使用できます。[詳細情報](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md)

**管理**

* メールヘッダー内の購読解除リンクをメッセージプリセットレベルで有効／無効にでき、カスタム購読解除 URL をメッセージレベルで設定できるようになりました。[詳細情報](../configuration/channel-surfaces.md#list-unsubscribe)
* 許可リストは、実稼働サンドボックスと非実稼働サンドボックスの [!DNL Journey Optimizer] インターフェイスを介して、有効または無効にできるようになりました。[詳細情報](../configuration/allow-list.md#enable-allow-list)

**パーソナライゼーション**

* 40 を超えるパーソナライゼーション式をライブラリに保存できるようになりました。[詳細情報](../personalization/personalization-library.md)

## 2022年2月リリース {#feb-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>サブスクリプションランディングページ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer でランディングページを作成およびデザインし、ユーザーをオンラインフォームに誘導して、コミュニケーションの受信をオプトインまたはオプトアウトしたり、ニュースレターなどの特定のサービスに購読したりできるようになりました。</p>
<p>詳しくは、<a href="../landing-pages/create-lp.md">詳細なドキュメント</a>および関連する<a href="../landing-pages/lp-use-cases.md">サンプルユースケース</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>新規パーソナライゼーション式ライブラリ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer には、事前定義されたパーソナライゼーション式にアクセスできるライブラリが用意されるようになりました。これらの式は、管理者ユーザーが設定します。</p>
<p>詳しくは、<a href="../personalization/personalization-library.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>API Developer Site and Suppression API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer provide RESTful APIs that allow you to programmatically perform key operations in your applications.
Developer SDK for Journey Optimizer is now available with the Suppression API (beta).</p>
<p>With this API, you can control your outgoing messages using suppression and allow lists.
The suppression list helps you with honoring the ISPs’ feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
<p>See <a href="https://developer.adobe.com/journey-optimizer-apis/">Adobe Journey Optimizer APIs</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>UTM トラッキングパラメーターを使用してメッセージをトラッキングする情報を渡す</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer のメッセージコンテンツで、リンクに UTM パラメーターを追加できるようになりました。これにより、そのリンクに関する追加データが提供され、ユーザーがリンクをクリックした場所と理由を特定するのに役立ちます。</p>
<p>詳しくは、 <a href="../configuration/channel-surfaces.md#configure-email-settings">詳細なドキュメント</a>を参照してください。</p-->
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* パフォーマンスを最適化するために、1 週間トリガーされていないテストモードのすべてのジャーニーが、ドラフトステータスに戻るようになりました。[詳細情報](../building-journeys/testing-the-journey.md#important_notes)
* Journey Optimizer と Adobe Campaign Classic の統合は、パフォーマンスを向上させるために最適化されています。キャッピングのデフォルト設定は、5 分につき呼び出し 4,000 件に変更されました。[詳細情報](../action/acc-action.md#important-notes)

**レポーティング**

* 配信は、ステータスに応じてフィルタリングできるようになりました。
   * メッセージの実行リストで、配信のリストから配達確認を除外できるようになりました。
   * ライブレポートまたはグローバルレポートから、テストイベントの除外を選択できます。

* 即時にメッセージを送信した人の数、1 時間の最適化、2 時間の最適化などでメッセージを送信した人の数などの、送信時間の最適化データに関するレポートにアクセスできるようになりました。

<!--* Offer Decisioning reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**意思決定管理**

* ランキングと AI ランキングが 1 つのタブにグループ化されました。

## 2022年1月リリース {#january-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ジャーニー - プロファイルキャップ条件による IP ランプアップの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーで<strong>条件</strong>アクティビティを設定する際、プロファイルのキャップを定義できるようになりました。この新しい条件タイプを使用すると、ジャーニーパスの最大プロファイル数を設定できます。この制限に到達すると、エントリするプロファイルは代替パスを使用します。これにより、配信の量を増やすことができます（IP ランプアップ）。例えば、1 日目に 1000 通のメッセージ、2 日目に 2000 通というように、ドメインでの実行を分割して配信を増やす場合があります。</p>
<p>詳しくは、<a href="../building-journeys/condition-activity.md#profile_cap">詳細なドキュメント</a>および関連する<a href="../building-journeys/ramp-up-deliveries-uc.md">サンプルユースケース</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー - セグメントの読み取りの向上</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>増分読み取り</strong>オプションが、繰り返しの<strong>セグメントを読み取り</strong>アクティビティに追加されました 。このオプションを使用すると、ジャーニーの最後の実行以降にセグメントにエントリした個人のみをターゲットにすることができます。最初の実行では、常にすべてのセグメントメンバーがターゲットになります。</p>
<p>詳しくは、 <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* Journey Optimizer ステップイベントを、[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) の他のデータセットにリンクできるようになりました。ビルトイン Journey Step Event スキーマの **profileID** フィールドが、ID フィールドとして定義されるようになりました。[詳細情報](../reports/sharing-overview.md#integration-cja)

**Offer Decisioning**

* 公開済みメッセージ内で直接または間接的に参照されるオファー、フォールバックオファー、オファーコレクション、オファー決定を更新すると、その更新は、対応するメッセージに自動的に反映されるようになり、再公開する必要がなくなりました。[詳細情報](../offers/offers-e2e.md#insert-decision-in-email)

* 特定のテストプロファイルに配信するオファーをシミュレートする際に、デフォルトのシミュレーション設定を変更し、トラブルシューティング目的で使用できる、シミュレーションに対応したコードを表示できるようになりました。[詳細情報](../offers/offer-activities/simulation.md#define-simulation-settings)

**管理**

* 管理者は、CNAME を設定したサブドメインを使用して PTR レコードを編集できるようになりました。[詳細情報](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**パーソナライゼーション**

* **お気に入りに追加** - パーソナライゼーションを使用する際の効率を向上させるために、お気に入りを保存するという概念を導入しました。お気に入りメニューに異なる属性を追加すると、最も頻繁に使用する項目にすばやくアクセスできます。[詳細情報](../personalization/personalize.md#fav)
