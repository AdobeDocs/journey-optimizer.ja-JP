---
solution: Journey Optimizer
product: journey optimizer
title: 以前のリリースノート（2021）
description: Journey Optimizer 2021 リリースノート
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hide: true
exl-id: 0e43be98-f471-4860-be84-8f99ab93e983
TQID: https://experienceleague.adobe.com/3i0k1Wzvdf3Z3NccHSFE-nzIrYC45iLqs-ftmQZIeVw
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: b3538224-471e-4c63-a444-9b19d89ae29cid: bb359667-ec7d-4d4b-8663-5850fc219d32id: d556b755-390a-43f0-be32-a08cf6236126id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: b5e335a9-0e5f-4dda-8845-c4ac5dca2be4id: cfba2953-2ce9-4b00-a00c-71cd338ae63fid: dd51b532-b93f-4bcf-8dbf-0d007f593acaid: e5329d1b-e590-4e24-a3fb-ef3fe0f2c721id: ee5bb250-0884-4d71-86eb-d8489e8bcaddid: f550d0f2-143d-4093-9463-467fbec95fccid: fa683eda-48de-4558-af32-2673edcd44feid: fae48155-b23f-40d2-a252-a25bce350b4did: fb9a80eb-bebc-492f-a0e9-584595621ebbid: fdac7813-bd56-47ae-9f6d-fa94ad1c5dee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cc72dcf1-72e1-48cc-b434-e7c27d62d67cid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 2060
ht-degree: 100%

---

# リリースノート 2021 {#release-notes-2021}

このページでは、2021年にリリースされた [!DNL Journey Optimizer] の機能と改善点をすべて一覧表示しています。

## 2021 年 11 月リリース {#november-2021-release}

<table>
<thead>
<tr>
<th><strong>CNAME サブドメインのデリゲーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer で CNAME がサポートされるようになりました。 CNAME（正規名レコード）とは、IP アドレスではなく別のドメインアドレスを指すレコードです。 CNAME サブドメインデリゲーションを使用すると、サブドメインを作成し、CNAME を使用してアドビ固有のレコードを指定できます。 この設定を使用すると、 メールの送信、レンダリング、トラッキングの環境を設定するために、DNS の管理に対する責任を、お客様とアドビで共有します。</p>
<p>組織のポリシーで完全なサブドメインデリゲーションの方法が制限されている場合は、この方法をお勧めします。</p>
<p>CNAME サブドメインデリゲーションについて詳しくは、<a href="../configuration/delegate-subdomain.md#cname-subdomain-setup">詳細ドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


## 2021年10月リリース {#oct-2021-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>意思決定管理 - オファーのシミュレーション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer UI で、特定のプレースメントの場合にテストプロファイルに配信されるオファーをシミュレートできるようになりました。 これにより、本番環境に配置する前に、実施要件の制約やランキングアルゴリズムなどの決定ロジックを容易に検証できます。 この機能を使用すると、技術に詳しいユーザーもそうでないユーザーも意思決定管理を迅速にテストし、潜在的な問題をトラブルシューティングできます。</p>
<p>詳しくは、<a href="../offers/offer-activities/simulation.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定管理 - オファーのパーソナライズ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer UI の随所に用意されている式エディターコンポーネントと同じものを使用して、Adobe Experience Platform のプロファイル属性とオーディエンスでオファーのコンテンツをパーソナライズできるようになりました。 </p>
<p>詳しくは、<a href="../offers/offer-library/creating-personalized-offers.md#custom-text">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


その他の変更点については、[Adobe Experience Platform 10月のリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/2021/october-2021.html?lang=ja){target="_blank"}も参照してください。

### 機能強化

**ジャーニー**

* **式エディター** - パワーユーザーは、関数を使用してマップを操作できるようになりました。 この機能は、サブスクリプションリストで利用できます。 例えば、オーディエンスでは、サブスクリプションリストからメールアドレスを取得できるようになりました。 詳しくは、[このサンプル](../building-journeys/message-to-subscribers-uc.md)を参照してください。

* **監視** - ライブジャーニーのステップイベントとテストモードが強化されました。 プロファイルエクスポートジョブに関連する[新規フィールド](../reports/sharing-field-list.md#servicevents-field)が追加されました。 ユーザーエクスペリエンスを向上させるために、ステップイベントフィールドが様々なカテゴリに分類されるようになりました。 以前のステップイベントフィールドはすべて、引き続き [stepEvents](../reports/sharing-legacy-fields.md) カテゴリで使用できます。
* **アクセシビリティ** - ジャーニーにアクセシビリティ機能の強化が実装されました。
* **コレクション** - サブオブジェクトを含んだオブジェクトの配列がサポートされるようになりました。 [詳細情報](../building-journeys/collections.md)
* **リスト** - ジャーニー、イベント、アクション、データソースのリスト画面が改善されました。

**レポーティング**

* **グローバル表示のデータフォーマット** -「**実行**」タブの&#x200B;**グローバル表示**&#x200B;で数値表示とパーセント表示を切り替えられるようになりました。


**管理**

* **メッセージプリセットの編集** - メッセージプリセットを編集し、その更新ステータスを監視できるようになりました。 [詳細情報](../configuration/channel-surfaces.md#edit-channel-surface)
* **PTR レコードの編集** - PTR レコードを編集し、その更新ステータスを監視できるようになりました。 [詳細情報](../configuration/ptr-records.md#edit-ptr-record)

**パーソナライゼーション**

* **日付書式設定用の新しいヘルパー関数** - 日付文字列の表現方法を指定できるようになりました。 [詳細情報](../personalization/functions/dates.md#format-date)


**意思決定管理**

* **評価順序** - 改善された新しい決定作成フローにより、決定オブジェクト間をよりシームレスに移動できるだけでなく、決定エンジンによるオファーコレクションの評価方法を完全に制御できるようにもなりました。 これには、一括で評価されるコレクションと個別に評価されるコレクションの区別や、コレクションの評価順序などが含まれます。 [詳細情報](../offers/offer-activities/create-offer-activities.md#add-decision-scopes)

### 修正点

* ブラウザー言語が英語以外の場合に、ジャーニーリスト、メッセージリストおよび E メールデザイナーが表示されない問題を修正しました。
* E メールデザイナーで式を使用してパーソナライゼーションを追加する際に発生する構文エラーを修正しました。文字が誤ってエスケープされていました。
* **管理**&#x200B;メニュー内を移動すると 404 エラーになる問題を修正しました。
* ビジネスイベントを使用してジャーニーをテストする際に他のライブジャーニーがトリガーされる問題を修正しました。


## 2021年9月リリース {#september-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>レポート - ターゲットオーディエンスに対するインサイトの向上</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>レポートで新しい指標を使用できます。メールおよびプッシュメッセージの「ターゲット」と「除外」がライブレポートとグローバルレポートの両方に表示されます。</br> 最新の指標にアクセスするには、チャネルとレポートのタイプごとに異なるレポートダッシュボードをリセットする必要があります。 ダッシュボードのカスタマイズについて詳しくは、<a href="../reports/live-report.md">詳細ドキュメント</a>を参照してください。</p>
<p>メッセージ実行リストの新しい列に、メッセージ実行ごとのターゲットプロファイル数が表示されます。 </p>
<p>詳しくは、<a href="../reports/report-gs-cja.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>

<th><strong>カスタムアクションを使用したデータリストの動的な受け渡し</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>実行時に動的に入力されるカスタムアクションパラメーターに、コレクションつまりデータのリストを渡すことができるようになりました。 単純なコレクションとオブジェクトコレクションの 2 種類のコレクションがサポートされています。 以前に作成したカスタムアクションは引き続き機能します。 </p>
<p>コレクションについて詳しくは、<a href="../building-journeys/collections.md">詳細なドキュメント</a>を参照してください。 </p>
<p>filter 関数と intersect 関数が、高度な式エディターで使用できる関数のリストに追加されました。 これにより、コレクションのフィルタリングと比較でさらに多くのことを行えるようになります。</p>
<p><a href="../building-journeys/functions/list-functions.md#filter">filter</a> 関数と <a href="../building-journeys/functions/list-functions.md#intersect">intersect</a> 関数のドキュメントを参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* ステップイベントのプロビジョニング時に作成されたシステム生成スキーマおよびデータセットは、読み取り専用モードになり、重要なスキーマへの不用意な変更に対する保護が強化されました。 [詳細情報](../reports/sharing-overview.md)
* 「**待機**」アクティビティのラベルとして、キャンバスに表示されるラベルがはっきりと表示されます。 このラベルは、レポートおよびテストモードのログでも使用され、実行内容がはっきりとわかるようになっています。 [詳細情報](../building-journeys/about-journey-activities.md#best-practices)
* 検索を使用して&#x200B;**イベント**&#x200B;および&#x200B;**アクション**&#x200B;カテゴリの要素をフィルタリングすることで、イベントとアクションをすばやく見つけることができます。 オーケストレーションアクティビティがフィルタリングされなくなりました。 [詳細情報](../building-journeys/using-the-journey-designer.md)
* ルールベースイベントまたはビジネスイベントでイベント ID 条件を定義する際に、「次を含む」演算子を文字列タイプのフィールドで使用できるようになりました。 [詳細情報](../event/about-creating.md)

**メール設定**

* IP プールがメッセージプリセットに関連付けられている場合に IP プールを編集できるようになり、更新は非同期になります。 また、各 IP プールの更新ステータスを確認することもできます。 [詳細情報](../configuration/ip-pools.md#edit-ip-pool)


## 2021年8月リリース {#august-2021-release}

### 新機能

<table>
<thead>
<tr>

<th><strong>最適なタイミングでのメッセージの送信 - 送信時間の最適化</strong><br/></th>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer とのエンゲージメントの対象となる顧客ごとに、最適なタイミングでプッシュ通知またはメールを自動的に送信します。 アドビの AI サービスを活用した送信時間最適化により、メールまたはプッシュメッセージの送信に最適な時間を標準で予測して、過去の開封率やクリック率に基づいてエンゲージメントを最大化できます。</p>
<p>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。</p>
<p>詳しくは、<a href="../building-journeys/send-time-optimization.md">詳細なドキュメント</a>を参照してください。</p>
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
<p>ビジネスイベントの設定時に、スキーマ間の関係を活用できるようになりました。 これに加えて、単一イベントの設定、ジャーニーでの条件の使用、メッセージのパーソナライゼーションおよびカスタムアクションのパーソナライゼーションの際に、リンクされたテーブルのフィールドも活用できます。</p>
<p>詳しくは、<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>パーソナライズされた URL</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライズされた URL は、プロファイル属性に応じて、受信者を web サイトの特定のページに誘導するか、パーソナライズされたマイクロサイトに誘導します。 Adobe Journey Optimizer で、メッセージコンテンツの URL にパーソナライゼーションを追加できるようになりました。 URL のパーソナライゼーションはテキストや画像に適用でき、その際にプロファイルデータやコンテキストデータを使用できます。</p>
<p>詳しくは、<a href="../personalization/personalization-syntax.md#perso-urls">詳細なドキュメント</a>を参照してください。</p>
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
<p>プリセットごとに再試行期間を定義して、不要になったときに再試行がそれ以上実行されないようにすることが可能になりました。 例えば、1 日のみ有効なリンクを含んだパスワードリセット用トランザクションメッセージの場合は、再試行期間を 24 時間に設定できます。 なお、再試行設定はメールチャネルにのみ適用されます。</p>
<p>詳しくは、<a href="../configuration/retries.md#retry-duration">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>送信から除外するアドレスの定義 - 抑制リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールアドレスとドメインを抑制リストに追加する際、1 つずつユーザーインターフェイスから選択、またはCSV ファイルをアップロードした一括モードのいずれかを利用できるようになりました。</p>
<p>詳しくは、 <a href="../configuration/manage-suppression-list.md#add-addresses-and-domains">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


### 機能強化

**ジャーニー**

* **動的ヘッダー** - HTTP ヘッダーパラメーターで動的データを渡せるようになりました。 これらのパラメーターは、ジャーニーアクションの HTTP 呼び出し（タイムスタンプやトラッキング ID など）を受信する統合システムで使用できます。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* **動的 URL パス** - カスタムアクションの動的 URL パスをセットアップできるようになりました。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* 「オーディエンスを読み取り」の全体的なスロットルレートが、1 秒あたり 17,000 メッセージから 20,000 メッセージに変更されました。 [詳細情報](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

**ユーザーインターフェイス**

* **検索** - すべてのページで、Experience Cloud 統合検索フィールドからビジネスオブジェクトやヘルプ記事を直接検索できるようになりました。 [詳細情報](../start/user-interface.md#unified-search)
* **最近使用したもの** - Adobe Journey Optimizer ホームページの最近の情報要素の表示が拡張され、追加のビジネスオブジェクトが含まれるようになりました。 この更新で、最近アクセスしたものへのショートカットに、メッセージ、ジャーニー、オーディエンス、スキーマ、データセット、データソース、イベント、アクション、ソースおよび宛先が含まれるようになりました。 [詳細情報](../action/about-custom-action-configuration.md#passing-collection)

**コンテンツデザイン**

* **背景** - 背景画像がライブプレビューでサポートされるようになりました。 [詳細情報](../content-management/preview-test.md)
  <!--* **One-click opt-out link** - You can insert a new type of link into your email content: the **Opt-out** link allows users to unsubscribe from receiving your communications in just one click, without being redirected to a landing page to confirm opting out. [Learn more](../privacy/opt-out.md#opt-out-personalization)-->

**パーソナライゼーション**

* **式エディター** - パーソナライゼーションを定義する際に、フォールバック値を容易に追加できるようになりました。プロファイルのパーソナライゼーションフィールドが空の場合、フォールバック値が表示されます。 [詳細情報](../personalization/functions/helpers.md)

**メール設定**

* **許可リスト** - API 呼び出しを通じて、非本番稼働用サンドボックスで許可リストを有効および無効にできるようになりました。 [詳細情報](../configuration/allow-list.md#enable-allow-list)
* **ナビゲーション** - 抑制リストは&#x200B;**管理／チャネル／メール設定／一般**&#x200B;メニューでアクセス可能でしたが、新しい&#x200B;**抑制リスト**&#x200B;サブメニューに移動しました。このサブメニューには、関連するすべての機能が集約されているので、アクセスしやすくなっています。 [詳細情報](../configuration/manage-suppression-list.md#access-suppression-list)

**意思決定管理**

* オファーの作成時に表示域を追加および設定する方法が更新され、ユーザーエクスペリエンスが向上しました。 特に、アセットライブラリは、表示域に対して画像タイプのコンテンツを定義する場合にのみ表示されるようになりました。 [詳細情報](../offers/offer-library/creating-personalized-offers.md#representations)

### 修正点

* メッセージタブのナビゲーションにおけるアクセシビリティの問題を修正しました。
* E メールデザイナーのラベルに関するローカライゼーションの問題を修正しました。
* 1 つのジャーニーで複数のノードを選択してプロパティパネルの「削除」をクリックする際の問題を修正しました。
* ジャーニーで使用するアクションに新しいヘッダーを追加できなかった問題を修正しました。
* ユーザーインターフェイスの警告がより明確になったので、メッセージプリセットの作成が失敗した理由を特定できるようになりました。


## 2021年7月リリース {#july-2021-release}

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
<p>Journey Optimizer に読み込んだ参照データを使用して、エクスペリエンスを強化できます。 例えば、エクスペリエンスイベントで予約 ID のメタデータを検索したり、キャンバスで使用するためにエクスペリエンスイベントで SKU から製品情報を検索したりすることができます。 </p>
<p>あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を活用できるようになりました。 その場合、リンクされたテーブルのすべてのフィールドは、単一イベントの設定時、ジャーニーでの条件の使用時、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションに活用できます。</p>
<p>詳しくは、<a href="../event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
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
<p>特定の送信セーフリストをサンドボックスレベルで定義して、テスト目的の安全な環境を構築できるようになりました。 ミスが発生する可能性のある非本番稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。 この機能は、抑制 API を利用することで有効になります。</p>
<p>詳しくは、 <a href="../configuration/allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックスで同時に実行されるすべての「オーディエンスを読み取り」アクティビティの全体的なスロットルレートは、1 秒あたり 17,000 メッセージに制限されています。 [詳細情報](../building-journeys/read-audience.md#configuring-segment-trigger-activity)
* **キャッシュ時間**&#x200B;フィールドがデータソース設定ペインから削除されました。 [詳細情報](../datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数キャップルールが自動的に定義されるようになりました。 [詳細情報](../configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーのプロパティ画面に、ジャーニーの公開日と公開したユーザー名が表示されるようになりました。 [詳細情報](../building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細情報](../start/user-interface.md#filter-lists)
* **[!UICONTROL スロットルレート]**&#x200B;パラメーターが「オーディエンスを読み取り」アクティビティに追加されました。 [詳細情報](../building-journeys/read-audience.md#configuring-segment-trigger-activity)

**プレビューとテスト**

* ID と名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。 [詳細情報](../content-management/preview-test.md#preview-test)
* 配達確認のテストメールの数が 10 個に制限されるようになりました。
* 配達確認の&#x200B;**件名行の接頭辞**&#x200B;に使用できる文字が制限されるようになりました。 [詳細情報](../content-management/preview-test.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前と順序が変更されました。

### 修正点

* 一括メール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が終了した後、メール送信が実行されない場合、それに応じてイベントが生成されるようになりました。
* PTR レコード画面に IP 情報が表示されない問題を修正しました。
* 式エディター内のオファーパネルのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image` プロパティを持つ内部スタイルシートがサポートされていない HTML ファイルをアップロードする際の E メールデザイナーの問題を修正しました。
