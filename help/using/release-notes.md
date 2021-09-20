---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 5a21ac0c199bf237972122ac46e58bf9f8d0f8ab
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 86%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。最新の[ドキュメント更新](documentation-updates.md)を参照することもできます。


## 2021 年 8 月リリース {#august-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>最適なタイミングでのメッセージの送信 - 送信時間の最適化</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer とのエンゲージメントの対象となる顧客ごとに、最適なタイミングでプッシュ通知またはメールを自動的に送信します。アドビの AI サービスを活用した送信時間最適化により、メールまたはプッシュメッセージの送信に最適な時間を標準で予測して、過去の開封率やクリック率に基づいてエンゲージメントを最大化できます。</p>
<p>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。</p>
<p>詳しくは、<a href="building-journeys/journeys-message.md#send-time-optimization">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>ビジネスイベントでのスキーマ関係の活用 - ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ビジネスイベントの設定時に、スキーマ間の関係を活用できるようになりました。これに加えて、単一イベントの設定、ジャーニーでの条件の使用、メッセージのパーソナライゼーションおよびカスタムアクションのパーソナライゼーションの際に、リンクされたテーブルのフィールドも活用できます。</p>
<p>詳しくは、<a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>パーソナライズされたURL</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライズされたURLを使用すると、受信者はプロファイル属性に応じて、Webサイトの特定のページや、パーソナライズされたマイクロサイトにアクセスできます。 Adobe Journey Optimizerで、メッセージコンテンツのURLにパーソナライゼーションを追加できるようになりました。 URLのパーソナライゼーションは、テキストや画像に適用し、プロファイルデータやコンテキストデータを使用できます。</p>
<p>詳しくは、<a href="personalization/personalization-syntax.md#perso-urls">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ユーザーへのメールの確実な配信 - メールの再試行</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>プリセットごとに再試行期間を定義して、不要になったときに再試行がそれ以上実行されないようにすることが可能になりました。例えば、1 日のみ有効なリンクを含んだパスワードリセット用トランザクションメッセージの場合は、再試行期間を 24 時間に設定できます。なお、再試行設定はメールチャネルにのみ適用されます。</p>
<p>詳しくは、<a href="configuration/retries.md#retry-duration">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>送信から除外するアドレスの定義 — 抑制リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールアドレスとドメインを抑制リストに追加する際、1 つずつユーザーインターフェイスから選択、またはCSV ファイルをアップロードした一括モードのいずれかを利用できるようになりました。</p>
<p>詳しくは、 <a href="configuration/manage-suppression-list.md#add-addresses-and-domains">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Customer Alerts</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now subscribe to event-based alerts regarding Adobe Journey Optimizer activities. The user interface allows you to view a history of received alerts based on metrics revealed by Adobe Experience Platform Observability Insights. The UI also allows you to view, enable, and disable available alert rules.</p>
<p>This feature is currently in beta version and only available to beta customers. To join the beta program, contact Adobe Customer Care.
</p>
<p>For more information, refer to the <a href="https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html">Adobe Experience Platform documentation</a>.</p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化

**ジャーニー**

* **動的ヘッダー** - HTTP ヘッダーパラメーターで動的データを渡せるようになりました。これらのパラメーターは、ジャーニーアクションの HTTP 呼び出し（タイムスタンプやトラッキング ID など）を受け取る統合システムで使用できます。 [詳細情報](action/about-custom-action-configuration.md#url-configuration)
* **動的 URL パス** - カスタムアクションの動的 URL パスを設定できるようになりました。[詳細情報](action/about-custom-action-configuration.md#url-configuration)
* 読み取りセグメントの全体的なスロットル率が、1 秒あたり17,000 メッセージから 20,000 メッセージに変更されました。[詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**ユーザーインターフェイス**

* **検索** - すべてのページで、Experience Cloud 統合検索フィールドからビジネスオブジェクトやヘルプ記事を直接検索できるようになりました。[詳細情報](user-interface.md#unified-search)
* **最近の情報** - Adobe Journey Optimizer ホームページの最近の情報要素の表示が拡張され、追加のビジネスオブジェクトが含まれるようになりました。この更新で、最近アクセスしたものへのショートカットに、メッセージ、ジャーニー、セグメント、スキーマ、データセット、データソース、イベント、アクション、ソースおよび宛先が含まれるようになりました。[詳細情報](action/about-custom-action-configuration.md#passing-collection)

**コンテンツデザイン**

* **背景** - 背景画像がライブプレビューでサポートされるようになりました。[詳細情報](preview.md)
* **ワンクリックオプトアウトリンク** - メールコンテンツに新しいタイプのリンクを挿入できます。この&#x200B;**オプトアウト**&#x200B;リンクを使用すると、ユーザーがワンクリックでコミュニケーションの受信登録を解除でき、オプトアウトを確認するためにランディングページにリダイレクトされることはありません。[詳細情報](message-tracking.md#one-click-opt-out-link)

**パーソナライズ機能**

* **式エディター**  — パーソナライゼーションを定義する際に、フォールバック値を簡単に追加できるようになりました。プロファイルのパーソナライゼーションフィールドが空の場合、フォールバック値が表示されます。[詳細情報](personalization/functions/helpers.md)

**メール設定**

* **許可リスト** - API 呼び出しを通じて、実稼動以外のサンドボックスで許可リストを有効および無効にできるようになりました。[詳細情報](allow-list.md#enable-allow-list)
* **ナビゲーション**  -  **管理/チャネル/Eメール設定/一般メニューでアクセス可能な抑制リストが、新しい** 抑制リストサブメニューに移動しまし **** た。このサブメニューでは、アクセスしやすいように、関連するすべての機能が収集されます。[詳細情報](configuration/manage-suppression-list.md#access-suppression-list)

**決定管理**

* オファーの作成時に表示域を追加および設定する方法が更新され、ユーザーエクスペリエンスが向上しました。 特に、アセットライブラリは、表現の画像タイプコンテンツを定義する場合にのみ表示されるようになりました。 [詳細情報](offers/offer-library/creating-personalized-offers.md#representations)

### 修正点

* メッセージタブのナビゲーションにおけるアクセシビリティの問題を修正しました。
* 電子メールデザイナーのラベルに関するローカライゼーションの問題を修正しました。
* 1 つのジャーニーで複数のノードを選択してプロパティパネルの「削除」をクリックする際の問題を修正しました。
* ジャーニーで使用するアクションに新しいヘッダーを追加できなかった問題を修正しました。
* ユーザーインターフェイスの警告がより明確になったので、メッセージプリセットの作成が失敗した理由を特定できるようになりました。


## 2021 年 7 月リリース {#july-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージでのメタデータの使用 - ルックアップテーブルの管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer に読み込んだ参照データを使用して、エクスペリエンスを強化できます。例えば、エクスペリエンスイベントで予約 ID のメタデータを検索したり、キャンバスで使用するためにエクスペリエンスイベントで SKU から製品情報を検索したりすることができます。 </p>
<p>あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を活用できるようになりました。その場合、リンクされたテーブルのすべてのフィールドは、単一イベントの設定時、ジャーニーでの条件の使用時、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションに活用できます。</p>
<p>詳しくは、<a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>許可リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>特定の送信セーフリストをサンドボックスレベルで定義して、テスト目的の安全な環境を構築できるようになりました。 ミスが発生する可能性のある非実稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。この機能は、抑制 API を利用することで有効になります。</p>
<p>詳しくは、 <a href="allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックスで同時に実行されるすべての「セグメントを読み取り」アクティビティの全体的なスロットルレートは、1 秒あたり 17,000 メッセージに制限されています。[詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* 「**キャッシュ時間**」フィールドがデータソース設定ペインから削除されました。[詳細情報](datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数制限（キャッピング）ルールが自動的に定義されるようになりました。 [詳細を読む](configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーを公開した日付とユーザーの名前がジャーニープロパティ画面に表示されるようになりました。 [詳細を読む](building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細を読む](user-interface.md#section_lgm_hpz_pgb)
* **[!UICONTROL スロットルレート]**&#x200B;パラメーターが「セグメントを読み取り」アクティビティに追加されました。 [詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**メッセージのプレビューとテスト**

* ID と名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。[詳細情報](preview.md#preview-your-messages)
* 配達確認のテストメールの数が 10 個に制限されるようになりました。
* 配達確認の&#x200B;**件名行のプレフィックス**&#x200B;に使用できる文字が制限されるようになりました。 [詳細情報](preview.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前と順序が変更されました。

### 修正点

* 一括メール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が終了した後、メール送信が実行されない場合、それに応じてイベントが生成されるようになりました。
* PTR レコード画面に IP 情報が表示されない問題を修正しました。
* 式エディター内のオファーパネルのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image` プロパティを持つ内部スタイルシートがサポートされていない HTML ファイルをアップロードする際の電子メールデザイナーの問題を修正しました。
