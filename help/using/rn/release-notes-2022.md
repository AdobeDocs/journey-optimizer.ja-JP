---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート2022
description: 旅オプティマイザー2022リリースノート
exl-id: 0997a640-3f89-4460-ba93-ea21a9d4efc5
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '3479'
ht-degree: 0%

---

# リリースノート2022 {#release-notes-2022}

このページには、2022でリリースされたすべての機能と機能強化 [!DNL Journey Optimizer] が記載されています。


## 9月2022リリース{#sept-2022-release}

### 新機能{#sept-2022-features}

<table>
<thead>
<tr>
<th><strong>動的コンテンツ &amp; 新規条件付き規則ビルダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>動的コンテンツを作成して、条件付きルールに基づいて、メッセージの内容を調整できるようになりました。</p> 
<p>条件付きルールは、エクスプレッションエディター内で視覚的なルールビルダーを使用して作成されます。これは、journeys およびキャンペーン全体で再利用するために保存しておくことができます。</p>
<img src="assets/do-not-localize/dynamic-content.gif"/>
<p>詳しくは、詳細なマニュアル </a> を <a href="../personalization/get-started-dynamic-content.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API によってトリガーされたキャンペーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在のスケジュールされたキャンペーンの他にも、旅オプティマイザーで API によって生成されたキャンペーンを作成し、Api を使用して外部システムから起動できるようになりました。</p>
<p>これにより、パスワードのリセット、OTP トークンなど、様々な操作上のメッセージングおよびトランザクションのニーズに対応できます。</p>
<img src="assets/do-not-localize/api-triggered.gif"/>
<p>詳しくは、詳細なマニュアル </a> を <a href="../campaigns/api-triggered-campaigns.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>データアクセス制御</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>属性ベースのアクセス制御により、管理者は特定の属性に基づいて特定のオブジェクトへのアクセスを制御できます。 属性には、ラベルなどのオブジェクトに追加されたメタデータを指定できます。 このリリースを開始すると、管理者は、特定のフィールドとオブジェクトにのみアクセスできるユーザーロールと、それらのフィールドまたはオブジェクトに対応するデータだけを定義することもできます。</p>
<p> 属性ベースのアクセス制御は、現在選択されている顧客に制限されているため、将来のリリースではすべての環境にデプロイされます。</p>
<img src="assets/do-not-localize/olac.gif"/>
<p>詳しくは、詳細なマニュアル </a> を <a href="../administration/object-based-access.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>データの管理とプライバシー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>データ使用状況の DULE) ガバナンスフレームワークによって、旅のオプティマイザーは、Adobe エクスペリエンスプラットフォームガバナンスポリシーを使用して、カスタムアクションによって重要なフィールドをサードパーティシステムに書き出されるのを防ぐことができるようになりました。 カスタムアクションパラメーターで制限されているフィールドがシステムによって識別される場合、エラーが表示され、旅を公開できなくなります。</p>
<p>使用するデータは、現在選択されている顧客に制限されているので、今後のリリースでは、すべての環境にデプロイされます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../action/action-privacy.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>自動承認強制 (同意ポリシー)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe エクスペリエンスプラットフォームを使用すると、顧客の同意に関する設定に基づいて、容易にマーケティングポリシーを採用して適用することができます。 承認ポリシーは、Adobe エクスペリエンスプラットフォームで定義されています。 このような同意ポリシーをカスタムアクションに適用するには、旅のオプティマイザーを使用します。 例えば、電子メール、プッシュ、または SMS 通信を consented にしていないお客様を除外するための承認ポリシーを定義することができます。
<p>自動承認強制は、現在、ヘルスケアシールドアドオンオファーリングを購入した組織でのみ使用できます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../action/consent.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>権限の管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このため、ユーザーロールやアクセスポリシーの定義を使用して、機能やオブジェクトのアクセス許可を管理することができます。 Adobe エクスペリエンスクラウドの権限 </strong> を使用 <strong> すると、役割を作成および管理することができます。また、役割に必要なリソースアクセス許可を割り当てることもできます。権限を使用して、特定の役割に関連付けられたラベル、サンドボックス、ユーザーを管理することもできます。</strong></p>
<p> 権限の使用は、現在選択されているユーザーに制限されているため、将来のリリースではすべての環境にデプロイされます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../administration/attribute-based-access.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>アラートと監視</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ユーザーインターフェイスを使用してシステム警告にアクセスすることにより、journeys が期待どおりに機能しない場合は、そのことを示すメッセージが表示されるようになりました。 使用可能なアラートを表示して、サブスクライブすることができます。 このリリースで使用可能な最初のアラートは、セグメント読み取り操作で、定義された時間枠内にどのプロファイルも処理されていない場合に、警告を表示します。 このワークフローのロックを解除すると、さらに多くの機能が提供されます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../reports/alerts.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Data Hygiene</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform provides a suite of data hygiene capabilities that allow you manage your stored data through programmatic deletions of consumer records and datasets. This capability is now available for Adobe Journey Optimizer. </p>
<p>You can manage your data stores to ensure that information is used as expected, is updated when incorrect data needs fixing, and is deleted when organizational policies deem it necessary.</p>
<p><strong>Caution</strong> - Data Hygiene capabilities are currently only available for organizations that have purchased the Healthcare Shield add-on offering.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->

### 実現{#sept-2022-improvements}

**Journeys**

* **これで、Entity dataset** は Adobe の旅のデータセットとして使用できるようになりました。このルックアップデータセットには、トラッキングおよびフィードバックのデータセット情報を強化するメタデータが含まれています。 これを使用すると、より多くの comprehensible データを含むレポートやクエリーを改善することができます。 [詳細情報](../data/datasets-query-examples.md#entity-dataset)
* 同じイベントに対して journeys が誤って複数回トリガーされるのを防ぐために、新しい guardrail が (イベントまたはセグメント認定で開始される) ユニタリ journeys に追加されています。 プロファイルの再入り口は、初期設定では5分間禁止されるようになりました。 [詳細情報](../start/guardrails.md#events-g)

**管理**

* 許可リストをアクティブまたは非アクティブにすると、新しい警告が表示されるようになりました。これで、各アクションの影響が詳述されます。 [詳細情報](../configuration/allow-list.md#enable-allow-list)
* チャネルサーフェスを作成し、IP プールを作成し、抑制リストと許可リストを管理し、SMS チャンネルを設定するためのユーザーインターフェイスが更新されました。
* これにより、指定されたサブドメインの最初のチャンネルサーフェスを作成するときに、処理時間は 10 ~ 10 日になり、そのサブドメインを使用している以降のサーフェスでは最大3時間しか消費されません。 [詳細情報](../configuration/channel-surfaces.md#create-channel-surface)
* ランディングページのプリセットとランディングページのサブドメインを作成するためのユーザーインターフェイスが更新されました。 [詳細情報](../landing-pages/lp-subdomains.md)

**監査制御**

* このような旅により、システムのユーザーが実行した操作は、キャンペーン、journeys、メッセージ、ランディングページなど、様々なサービスと機能によって識別できます。 監査ログリソースには、他の様々なアクションに対する変更が含まれるようになりました。また、アクティビティの実行時に自動的に記録されます。 詳しく [ は、このページ ](../privacy/audit-logs.md) を参照してください。

**アーカイブのサポート**

* 新しい **エンティティデータセット** には、送信されたメッセージの形式を、アーカイブ目的ですべてのチャネルに書き出すことができるテンプレートフィールドが含まれています。 [詳細情報](../configuration/archiving-support.md)

**ランディングページ**

* 同一のランディングページ内の別のページにある文脈データを使用できるようになりました。 例えば、1つのリンクをクリックすると、その購読リストに「お礼」というサブページが表示されます。 [詳細情報](../landing-pages/lp-content.md#use-primary-page-context)

<!--* When configuring the primary page, you can now create additional data to enable storing information when the landing page is being submitted. [Learn more](../landing-pages/lp-content.md#use-additional-data)-->

<!--* You can now use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.-->

### その他の変更{#sept-2022-other}

* 旅のバーストモードは、キャンペーンラピッドデリバリモードに置き換えられました。 [詳細情報](../campaigns/create-campaign.md#rapid-delivery)
* パフォーマンスを改善するために、経験イベントフィールドグループは読み取りセグメント、セグメント認定、またはビジネスイベントアクティビティから開始する journeys では使用できなくなりました。 この変更は、新しい journeys にのみ適用されます。 既存の動作を維持することができます。 [詳細情報](../start/guardrails.md#expression-editor)
* 「予約された読み取りセグメント journeys の1時間制限が削除されました。 これらの journeys は、遅れずに実行できるようになりました。




## 8月2022リリース {#aug-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>旅のオプティマイザーでのキャンペーンの作成と管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>旅のオプティマイザーキャンペーンを使用して、様々なチャネルを使用して、特定のセグメントに1回限りのコンテンツを配信することができます。 Journeys を使用している場合、アクションは順番に実行されるように設計されています。 キャンペーンを使用すると、直ちにアクションが実行されるか、または指定されたスケジュールに基づいてアクションが実行されます。 </p>
<img src="assets/do-not-localize/campaigns.gif"/>
<p>詳しくは、 <a href="../campaigns/get-started-with-campaigns.md"> 詳細なドキュメント </a> と <a href="https://video.tv.adobe.com/v/346680"> 機能のビデオ </a> でキャンペーンを作成する方法を説明しています。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ユーザーに SMS を送信します (ga)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>では <b> 、Twilio </b> との <b> </b> 統合により、旅のオプティマイザーで SMS を作成、パーソナライズ、送信できるようになりました。</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>この <a href="../sms/create-sms.md"> 詳細なドキュメント </a> に SMS を作成して送信する方法について説明します。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>New Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content.</p>
<p>In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### 実現

**書**

* 同意ポリシーテーブルとグラフが、グローバルレポートに表示されるようになりました。 これらの widget を使用すると、カスタムアクションのポリシーから、除外されたプロファイルを追跡できます。 [詳細情報](../reports/journey-global-report.md#journey-global)

   最新の widget にアクセスするには、異なるレポートダッシュボードを再設定する必要があることに注意してください。 ダッシュボードのカスタマイズについて詳しくは、詳しくはマニュアル ](../reports/global-report.md) を [ 参照してください。

**管理**

* SMS チャンネルに使用する1つの基本の電話番号を更新できるようになりました。 [詳細情報](../configuration/primary-email-addresses.md)


## 2022年7月リリース {#july-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>インラインメッセージフローの新規作成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>旅のオプティマイザーにより、Journeys でのメッセージ作成のための新しいフローが提供されます。 インラインメッセージによって、ユーザーの作業時間が大幅に短縮され、電子メール、プッシュ通知、SMS を作成して、旅オプティマイザーに SMS を作成することができます。 メッセージを別のステップとして削除して、進行中の Canvas のアクションの一部としてインラインで編集可能にすることにより、ユーザーは1つのボタンをクリックして、画面を切り替えるだけで、コンテンツをデザインおよび編集することができます。</p>
<img src="assets/do-not-localize/inline.gif"/>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>属性ベースのアクセス制御 (利用制限)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>組織またはデータの使用範囲を定義するラベルを使用して、スキーマフィールドを識別できるようになりました。 管理者は、アクセス権のインターフェイスを使用して、XDM スキーマフィールドに関するアクセスポリシーを定義して、ユーザーまたはユーザーグループ (社内、社外、サードパーティユーザー) に対するアクセスを管理することができます。また、特定の種類のデータ (機密性の高い個人用データ/SPD など) へのアクセスを管理することもできます。</p>
<p>属性ベースのアクセス制御は、現在選択されているユーザーに制限されているため、将来のリリースではすべての環境にデプロイされます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../administration/attribute-based-access.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Decisioning ジョブのバッチ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ユーザーインターフェイスから batch decisioning ジョブを実行できるようになりました。そのため、開発者がバッチ api ジョブを実行する必要はなく、マーケティングに要する時間を短縮することができます。 この新しいインターフェイスでは、ジョブを作成して、最新または過去のジョブを管理することができます。</p>
<img src="assets/do-not-localize/batch.gif"/>
<p>詳しくは、詳細なマニュアルを <a href="../offers/batch-delivery.md"> 参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定に最適な特典を自動的に使用する (可用性制限)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>意思決定管理で、パーソナライズされた最適化モデルシステムを使用できるようになりました。 この新しいタイプのモデルを使用すると、セグメントに基づいてサービスを最適化してカスタマイズし、パフォーマンスを向上させることができます。</p>
<p>パーソナライズされた最適化 AI モデルは、現在選択されているユーザーに制限されているため、将来のリリースではすべての環境にデプロイされます。</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>詳しくは、詳細なマニュアル </a> を <a href="../offers/ranking/personalized-optimization-model.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

### 実現

**Journeys**

* **旅** を終了する-旅の canvas **では、終了** アクティビティーはパレットから削除されています。 終了タグは、各パスの最後にデフォルトで追加されるようになりました。削除することはできません。 この機能強化により、旅において必要な行動をかけることなく、お客様が外出中に脱落させることができます。 「製品について」と [ いうビデオ ](https://video.tv.adobe.com/v/345376) については、 [ ](../building-journeys/end-journey.md) 「ターゲット = &quot;_blank&quot;}」を参照してください。


* プロファイルのタイムゾーン **オプションは、デフォルトでは、** 旅のプロパティについてはオフになっています。[詳細情報](../building-journeys/timezone-management.md#timezone-from-profiles)

**受信**

* メッセージプリセットがチャンネルサーフェス **になりました** 。[詳細情報](../configuration/channel-surfaces.md)

**管理**

* **PTR レコード版** -ptr レコードを更新したときに、処理時間が最大3時間に短縮されます。 [詳細情報](../configuration/ptr-records.md#processing)

* **使用可能なリスト UI** : 現在のユーザーインターフェイスを使用して、新しい電子メールアドレスまたはドメインを許可リストに追加できるようになりました。 [詳細情報](../configuration/allow-list.md)

* **許可されたリストロジックアップデート** -これで、リストが空であっても、その機能が有効になったときに許可されるリストロジックが適用されるようになりました。 [詳細情報](../configuration/allow-list.md#logic)

* **URL 追跡パラメーター** -エクスプレッションエディターを使用して、電子メールのサーフェス (プリセット) 内の url トラッキングパラメーターを設定できるようになりました。 [詳細情報](../email/email-settings.md#url-tracking)

**意思決定管理**

* **対象ユーザーサイズ** -決定ルールを作成すると、決定ルールを作成する場合、または特典スコープにセグメントまたはルールを追加する場合に、ユーザーインターフェイスに新しい対象ユーザー数の予測コンポーネントが表示されるようになりました。


## 2022年6月リリース {#june-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ユーザーへの SMS の送信 (可用性制限)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>では <b> 、Twilio </b> との <b> </b> 統合により、旅のオプティマイザーで SMS を作成、パーソナライズ、送信できるようになりました。</p>
<!--img src="assets/do-not-localize/SMS.gif"/-->
<p>SMS チャネルは、現在のところ、組織のセットでのみ使用できます (利用可能な機能が制限されます)。 詳しくは、アドビの担当者にお問い合わせください。</p>
<p>この <a href="../sms/create-sms.md"> 詳細なドキュメント </a> に SMS を作成して送信する方法について説明します。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Stock との統合により、より impactful 画像をさらにすばやく検索</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Stock および Adobe Aioptimizer の電子メールデザイナー統合プラグインは、メッセージオーサリングで使用する画像を簡単にナビゲート、ライセンス、保存します。 </br> 「新しい <b> 同様の写真写真 </b> を検索」オプションを使用すると、画像のコンテンツ、色、コンポジションに一致する銘柄写真を検索することもできます。 </p>
<!--img src="assets/do-not-localize/stock-rn.gif"/-->
<p>詳しくは、詳細なマニュアル </a> を <a href="../email/stock.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>すべての電子メールに BCC BCC を使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>電子メールの BCC (ブラインドカーボンコピー) 機能を使用して、Adobe の旅オプティマイザーによって送信された電子メールを保存できるようになりました。 電子メールのプリセットでこのオプションをオンにすると、送信された電子メールはすべて BCC アドレスにブラインドコピーされます。</p>
<!--img src="assets/do-not-localize/bcc-rn.gif"/-->
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/archiving-support.md#bcc-email"> 参照してください。</a></p>
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
<p>これにより、例えば、製作サンドボックスから実稼働サンドボックスに向けて、旅のオプティマイザーサンドボックスから別の環境に体験を再現できます。 この新機能により、他の環境にとって、旅が適切に実行されるために必要なオブジェクトを含む、旅全体がコピーされます。 Journeys の他にも、オファー、メッセージ、スキーマ、データセット、データソース、イベント、アクションなどのその他のコンポーネントをコピーすることもできます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../building-journeys/copy-to-sandbox.md"> 参照してください。
</a></td>
</tr>
</tbody>
</table>




### 実現

**意思決定管理**

* **HTML ファイルおよび JSON ファイルのサポート** -Adobe エクスペリエンスクラウドアセットライブラリから、外部 HTML ファイルおよび json ファイルをオファー表現のコンテンツにドラッグ &amp; ドロップできるようになりました。 [詳細情報](../offers/offer-library/add-representations.md#html-json)


**電子メール**

* **テンプレート** として保存: 電子メールコンテンツをテンプレートとして保存し、他のメッセージを作成するときに再利用できます。 [詳細情報](../email/email-templates.md)


**管理**

* **「トラッキング URL パラメーター** のプレビュー」: メッセージプリセットを設定すると、追跡 url のプレビューが表示されるようになりました。 [詳細情報](../email/email-settings.md#url-tracking)

* **メッセージプリセットエディション** -現在、メッセージプリセットを更新する場合、処理時間は最大で3時間になります。 [詳細情報](../configuration/channel-surfaces.md#edit-channel-surface)

* **IP プールエディション** -現在、ip プールを更新する場合、処理時間は最大3時間にしかかかることができません。 [詳細情報](../configuration/ip-pools.md#edit-ip-pool)




## リリース 2022 5 月 {#may-2022-release}

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
<p>クロスチャネルビジネスルールを設定することで、メッセージやアクションから、超過要請プロファイルが自動的に除外されるようになりました。</p>
<!--img src="assets/do-not-localize/frequency-rn.gif"/-->
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/frequency-rules.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>意思決定管理-AI ランク付け自動最適化モデル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>意思決定管理で、認定されたモデルシステムを使用できるようになりました。 この新しい機能のランク付けは、特定のプロファイルについて表示するために用意されています。</p>
<!--img src="assets/do-not-localize/optimization.gif"/-->
<p>詳しくは、詳細なマニュアル </a> を <a href="../offers/offer-activities/configure-offer-selection.md#use-ranking-strategy"> 参照してください。</a></p>
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
<th><strong>「旅のオプティマイザー監査ログ」</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ユーザーが実行したアクションを、アドビシステムズ社の Optimizer リソース上で監視できるようになりました。</p>
<!--img src="assets/do-not-localize/audit-rn.gif"/-->
<p>詳しくは、詳細なマニュアル </a> を <a href="../privacy/audit-logs.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

### 実現

**パーソナライゼーション**

* **文字を非表示** `mask` にするための新しいヘルパー関数。このヘルパー関数を使用すると、ストリングの一部を「X」文字に置き換えることができます。 [詳細情報](../personalization/functions/string.md#mask)

**ランディングページ**

* **フォーム** を使用しないランディングページ-フォームが含まれていないランディングページを作成してパブリッシュすることができます。また、訪問者がアクションを実行する必要はありません。
* **ランディングページテンプレート** -ランディングページをテンプレートとして保存し、他のランディングページを作成するときに再利用できるようになりました。 [詳細情報](../landing-pages/lp-templates.md)
* **プライマリページ** に戻る-同一のランディングページ内の任意のサブページに、プライマリページへのリンクを追加できるようになりました。
* **カスタム JavaScript サポート** : カスタム javascript をランディングページのコンテンツに追加して、高度なスタイルを実行したり、ランディングページにカスタムビヘイビアーを追加することができるようになりました。    [詳細情報](../landing-pages/lp-custom-js.md)

**Journeys**

* **セグメント** の読み取り: ワンショット読み取りセグメント journeys を、旅実行後30日後に移動するようになりました。 予約された読み取りセグメントについては、最後の発生が実行された30日後になります。 [詳細情報](../building-journeys/read-segment.md)
* **式エディター** - [ limit ](../building-journeys/functions/functionlimit.md) 関数が追加されました。これを使用すると、リストの項目数を制限することができます。 [この並べ替え ](../building-journeys/functions/functionsort.md) 関数では、list オブジェクトを並べ替えることができるようになりました。ListObject のサポートは、disctinct ](../building-journeys/functions/functiondistinct.md) および [ distinctWithNull ](../building-journeys/functions/functiondistinctwithnull.md) 関数に [ も追加されました。

**管理**

* **ライセンス使用状況ダッシュボードのアップデート** –ユーザーインターフェイスに表示されるライセンス使用状況のダッシュボードには、ライセンス **された「豊富な機能」 [!DNL Adobe Journey Optimizer] の正確な** 値が反映されています。このメトリック表現にドロップが表示されます。これは、ライセンス上限が正しく報告されるようになったことを示しています。 [詳細情報](../segment/license-usage.md)


## 4月2022リリース {#april-2022-release}

### 実現

**ランディングページ**

* **「オプトイン」および「オプトアウト」チェックボックス** の新しいオプション-「購読」ランディングページにオプトイン/オプトアウト用の1つのチェックボックスを挿入できるようになりました。 ユーザーが同意 (オプトイン) する場合は、このチェックボックスをオンにして、その同意を削除するかどうかを確認する必要があります (オプトアウト)。 [詳細情報](../landing-pages/design-lp.md#define-lp-specific-content)

* **「あらかじめ設定されているランディングページ」フィールド** では、ユーザーがプロファイル情報を使用してランディングページのフィールドに事前にデータを入力できるようになりました。 [詳細情報](../landing-pages/create-lp.md#configure-primary-page)

**意思決定管理**

* **Decisioning API** を使用して、意志決定管理で管理されているパーソナライズされた機能を提供することができます。 意志決定管理ユーザーインターフェイス (UI) または Api を使用して、オファーやその他の関連オブジェクトを作成することができます。 [詳細情報](../offers/api-reference/offer-delivery-api/edge-decisioning-api.md)

**管理**

* **PTR 送信継続時間** : ptr 編集を有効にする期間は、数時間になりました。 [詳細情報](../configuration/ptr-records.md#processing)

**電子メールデザイン**

* **現在、新しい電子メールテンプレート** を使用して、旅のオプティマイザーに電子メールのコンテンツをデザインできるようになりました。

**ユーザーインターフェイス**

* **旅のオプティマイザー** の状況に応じたヘルプが、複数のページに追加されています。 使用可能な場合は、「i」アイコンをクリックして、現在の機能の簡単な説明を表示し、関連する記事にアクセスします。

**Adobe キャンペーン規格との統合**

Adobe キャンペーン標準ユーザーは、旅のオプティマイザーを使用して電子メール、プッシュ通知、SMS を送信することができます。 新しい組み込みアクションを使用して、キャンペーン標準のトランザクションメッセージ機能を、旅のオプティマイザーに活用してください。  [詳細情報](../action/acs-action.md)

<!--
### Fixes

* Fixed an issue which caused tracking reports not to be available as the `JourneyActionId` was not properly populated. PLATIR-19854, CJM-26006
* Fixed an error on business events which could block the journey publication. CJM-25931
* Fixed an issue which could prevent images in Email Designer templates from being displayed. PLATIR-18176, CJM-25008
-->

## 2022年3月リリース {#march-2022-release}

### 実現

**Journeys**

* 統一されたプロファイルスキーマに不要なフィールドがないようにするため、デフォルトでは、段階的なイベントスキーマがプロファイルに対して有効になっていません。 必要に応じて、アクティブにすることができます。 [詳細情報](../reports/sharing-overview.md)
* 輸出ジョブに関する新しいステップイベントは、旅オプティマイザーによって Adobe エクスペリエンスプラットフォームに送信されるようになりました。 ドキュメントには、クエリーの例が追加されています。 [詳細情報](../reports/query-examples.md)

**意思決定管理**

* すべてのユーザーに対して、または1つの特定のプロファイルに対して、すべての位置または配置のすべてに対して、「上限」を適用するかどうかを指定できるようになりました。 [詳細情報](../offers/offer-library/add-constraints.md#capping)
* Batch Decisioning API を使用すると、特定のセグメントに含まれるすべてのプロファイルについて、1回の呼び出しで意思決定管理機能を使用できます。 セグメント内の各プロファイルの offer コンテンツは、AEP データセット内に配置され、カスタムバッチワークフローで利用できるようになります。 [詳細情報](../offers/api-reference/offer-delivery-api/batch-decisioning-api.md)

**管理**

* メッセージプリセットレベルの電子メールヘッダーにあるサブスクライブ解除リンクを有効または無効にしたり、メッセージレベルのカスタム登録解除 URL を設定できるようになりました。 [詳細情報](../configuration/channel-surfaces.md#list-unsubscribe)
* 許可されたリストは、実務サンドボックスと非プロダクションサンドボックスのインターフェイスを [!DNL Journey Optimizer] 使用して有効または無効にすることができます。 [詳細情報](../configuration/allow-list.md#enable-allow-list)

**パーソナライゼーション**

* ライブラリには、40を超えるパーソナル化式を保存できるようになりました。 [詳細情報](../personalization/personalization-library.md)

## 2022年2月リリース {#feb-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>購読ランディングページ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ここで、旅オプティマイザーのランディングページを作成してデザインし、ユーザーがオプトインまたはオプトアウトされている情報をオンラインフォームに直接伝達したり、ニュースレターのような特定のサービスを利用できるようになりました。</p>
<p>詳しくは、詳細なマニュアル </a> および関連 <a href="../landing-pages/lp-use-cases.md"> するサンプルユースケース </a> を <a href="../landing-pages/create-lp.md"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>新規のパーソナル化式ライブラリ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>事前に定義されたパーソナル化式にアクセスできるライブラリが、旅オプティマイザーによって提供されるようになりました。 これらの式は、管理者ユーザーによって設定されます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../personalization/personalization-library.md"> 参照してください。</a></p>
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
The suppression list helps you with honoring the ISPs' feedback to preserve sending IP reputation. The allow list helps you ensure that you send only to those email addresses which are in the allowed list, and typically to ensure that you don't send mails to customers from your development sandbox.</p>
<p>See <a href="https://developer.adobe.com/journey-optimizer-apis/">Adobe Journey Optimizer APIs</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>UTM トラッキングパラメーターを使用してメッセージを追跡するための情報の渡し方</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ここで、UTM パラメーターをリンクに追加できるようになりました。また、リンクに関する追加のデータを提供することができます。また、リンクをクリックした場所と理由を確認するのに役立ちます。</p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../configuration/channel-surfaces.md#configure-email-settings"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

### 実現

**Journeys**

* パフォーマンスを最適化するために、1週間にトリガーされていないテストモードのすべての journeys は、下書き状態に戻るようになりました。 [詳細を読む](../building-journeys/testing-the-journey.md#important_notes)
* 旅オプティマイザーと Adobe キャンペーンの統合は、パフォーマンスを向上させるために最適化されています。 上限デフォルト設定が4000呼び出し (5 分間) に変更されました。    [詳細を読む](../action/acc-action.md#important-notes)

**書**

* 配信はそのステータスに応じて、フィルター処理されるようになりました。
   * 「メッセージ実行」リストから、「配達」リストからの校正を除外できるようになりました。
   * ライブレポートまたはグローバルレポートから、テストイベントを除外することを選択できます。

* これで、送信時の最適化データのレポートにアクセスできるようになりました。これによって、メッセージの送信先は、すぐにメッセージだった人物の数と、1時間の最適化、2時間の最適化、その他の messaged を使用して作成された人物の数の合計になります。

<!--* decision management reports are now available in Journey Optimizer. You can access the following metrics: Offers sent - Offers' impression rate - Offers' click rate - Breakdown report on Offers' sent.-->

**意思決定管理**

* ランキングと AI のランクは、1つのタブにグループ化されました。

## 2022年1月リリース {#january-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>Journeys-IP ランプをプロファイルキャップ条件に合わせて最適化します。</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>1つの過程で Condition </strong> アクティビティーを設定 <strong> するときは、プロファイルキャップを定義できるようになりました。この新しい条件タイプを使用して、旅のパスの最大プロファイル数を設定することができます。 この制限に達した場合は、入力プロファイルによって代替パスが採用されます。 このようにすると、配信量 (IP ランプアップ) が増加します。 例えば、実行を分割することによって、ドメインでの送信を分離することもできます。1000のメッセージを1日目に送信すると、2000のメッセージが表示されます。</strong></p>
<p>詳しくは、詳細なマニュアル </a> および関連 <a href="../building-journeys/ramp-up-deliveries-uc.md"> するサンプルユースケース </a> を <a href="../building-journeys/condition-activity.md#profile_cap"> 参照してください。</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journeys-「セグメントの改善」を読む</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>「インクリメンタル読み取り </strong> 」オプションは、 <strong> 定期的 <strong> に読み取られる「セグメント </strong> 」アクティビティーに追加されました。このオプションを使用すると、最後に行った旅以降にセグメントに入った人物のみを対象とすることができます。 最初の実行では、常にすべてのセグメントメンバーが対象となります。</strong></p>
<p>詳しくは、詳細なマニュアル </a> を <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity"> 参照してください。
</a></td>
</tr>
</tbody>
</table>

### 実現

**Journeys**

* Adobe お客様の旅解析 ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) におい [ て、旅のオプティマイザーステップのイベントが他のデータセットにリンクできるようになりました。**ProfileID** フィールドは、組み込まれている旅のステップイベントスキーマで、id フィールドとして定義されるようになりました。[詳細情報](../reports/sharing-overview.md#integration-cja)

**意思決定管理**

* パブリッシュされたメッセージで直接または間接的に参照されるオファー、フォールバックオファー、オファーコレクション、またはオファーによる決定を更新すると、更新は自動的に対応するメッセージに反映されるようになりました。 [詳細情報](../offers/offers-e2e.md#insert-decision-in-email)

* 特定のテストプロファイルについて、どのオファーが配信されるかをシミュレートする場合は、初期設定のシミュレーション設定を変更して、トラブルシューティング目的に使用できるシミュレーションに対応するコードを表示できるようになりました。 [詳細情報](../offers/offer-activities/simulation.md#define-simulation-settings)

**管理**

* 管理者は、CNAME がサブドメインに設定されている PTR レコードを編集できるようになりました。 [詳細情報](../configuration/ptr-records.md#edit-ptr-subdomains-cname)

**パーソナライゼーション**

* **お気に入り** に追加-パーソナル化を行う際の効率性を高めるために、「お気に入りを保存する」という概念が導入されました。 別の属性を「お気に入り」メニューに追加することで、使用頻度の高いアイテムにすばやくアクセスできます。 [詳細情報](../personalization/personalize.md#fav)
