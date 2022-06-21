---
title: リリースノート 2022
description: Journey Optimizer 2022 リリースノート
exl-id: 0997a640-3f89-4460-ba93-ea21a9d4efc5
source-git-commit: 0ca491315e214e3c12bec11a93da1a2b98b493b6
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# リリースノート 2022 {#release-notes-2022}

このページは、2022年にリリースされた [!DNL Journey Optimizer] の機能と改善点をすべて一覧表示しています。

最新のリリースノートが[このページ](release-notes.md)で確認できます。

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

* メールヘッダー内の購読解除リンクをメッセージプリセットレベルで有効／無効にでき、カスタム購読解除 URL をメッセージレベルで設定できるようになりました。[詳細情報](../configuration/message-presets.md#list-unsubscribe)
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
<p>詳しくは、 <a href="../configuration/message-presets.md#configure-email-settings">詳細なドキュメント</a>を参照してください。</p-->
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
