---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: c523783b0984a36f919a581053e994ca131a0115
workflow-type: tm+mt
source-wordcount: '1897'
ht-degree: 81%

---

# リリースノート {#release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

以前のリリースノートは、[このページ](release-notes-2022.md)にあります。 また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。


## 2023 年 4 月の早期リリースノート {#apr-e-rn-2023}

以下の情報は、リリースの公開日まで予告なく変更される場合があります。更新されたドキュメントはリリース日に公開され、ダイレクトリンクがこのページに追加されます。

****&#x200B;リリース日：2023年4月27日（PT）

### 新機能{#apr-2023-features}


<table>
<thead>
<tr>
<th><strong>Web チャネル（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerは、web チャネルのサポートを追加して、クロスチャネル機能を拡張しています。 スマートで直感的なビジュアルインターフェイスを使用して、Web エクスペリエンスをその他のチャネルと同じように作成、変更、プレビューし、エンドユーザーエクスペリエンスをパーソナライズできます。 現在、Journey Optimizerでは、キャンペーンでのみ Web エクスペリエンスを作成できます。</p>
<img src="assets/do-not-localize/create-web-campaign.gif"/>
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>モバイルオンボーディングのクイックスタートワークフロー（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいモバイルオンボーディングクイックスタートワークフローが使用できるようになりました。 この新しい製品機能を使用すると、Mobile SDK をすばやく設定して、モバイルイベントデータの収集と検証を開始し、Adobe Journey Optimizerでモバイルプッシュ通知を送信できます。 この機能には、パブリックベータ版としてデータ収集ホームページからアクセスできます。</p>
<img src="../push/assets/mobile-wf-home.png"/>
<p>詳しくは、<a href="../push/mobile-onboarding-wf.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>新しいジャーニーダッシュボード（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p> ジャーニーダッシュボードが次の 2 つのタブに分割されました。</p>
<ul><li>以下を使用： <strong>概要</strong> タブをクリックして、ジャーニーに関連する主要指標を表示する新しいダッシュボードにアクセスします。</li>
<li>以下を使用： <strong>参照</strong> タブをクリックして、すべてのジャーニーのリストにアクセスします。</li></ul>
<p>この機能は、すべてのジャーニーでパブリックベータ版としてアクセスできます。</p>
<img src="assets/do-not-localize/journey-dashboard.gif"/>
<!--p>For more information, refer to the <a href="../building-journeys/journey-gs.md#journey-access">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Personalized Optimization AI ranking model (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Personalized Optimization AI ranking models are now generally available in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the <a href="../offers/ranking/personalized-optimization-model.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

### 機能強化 {#april-2023-improvements}

**ジャーニー**

* ジャーニーキャンバスに、アクションノードと終了タグのアクティビティ ID が表示されるようになりました。 これにより、レポートとリターゲティングが向上します。
* アクション、データソース、イベント、ジャーニーに表示される設定ペインのレイアウトが改善されました。
* ジャーニーに新しいガードレールが追加されました。
   * ジャーニーのノード数が最大 50 個に制限されるようになりました
   * 1 つの組織内のライブジャーニーの数が、最大 100 に制限されるようになりました。 テストモードのジャーニーは考慮されません。

* ジャーニーに E メール、SMS、またはプッシュアクションを追加する場合、デフォルトでは、そのチャネルで最後に使用したサーフェスと共に、サーフェスが事前入力されるようになりました。
* カスタムアクションで静的クエリパラメーターまたは動的クエリパラメーターを定義できるようになりました。

**レポート**

* Journey OptimizerレポートをPDFとして書き出せるようになりました。

**コンテンツデザイナー**

* Adobe Journey Optimizerコンテンツデザイナーが更新され、デザインスタイルとコンポーネントにアクセスしやすくなりました。 この新しいバージョンでは、ユーザーエクスペリエンスの向上を提案し、パフォーマンスの向上、ダークモードの部分互換性、新しいアクセシビリティ標準のサポートが追加されました。



## 2023 年 3 月リリースノート {#mar-2023}

### 新機能{#mar-2023-features}

<table>
<thead>
<tr>
<th><strong>アプリ内チャネル（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>キャンペーン内で、アプリユーザーにパーソナライズされたアプリ内メッセージを送信できるようになりました。 Journey Optimizer を使用して通知をデザインし、メッセージのレイアウト、表示、テキストおよびボタンをカスタマイズして、シームレスなエクスペリエンスを作成します。</p>
<img src="assets/do-not-localize/in-app.gif"/>
<p>詳しくは、<a href="../in-app/get-started-in-app.md">詳細なドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>SMS のクリックの追跡</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS のクリックの追跡を使用すると、短縮 URL のパフォーマンスを監視し、短縮 URL をクリックしたユーザーを特定し、このデータを使用して、後続のキャンペーンでこれらの顧客を再度ターゲットに設定できます。</p>
<img src="assets/do-not-localize/sms-tracking.gif"/>
<p>詳しくは、<a href="../sms/create-sms.md#sms-content">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーでのタグの使用（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer の実務担当者は、タグを使用してビジネスオブジェクトを整理できるようになりました。タグを使用すると、オブジェクトをすばやく簡単に分類でき、検索が改善されます。この機能は現在ベータ版であり、ジャーニーでのみ使用できます。</p>
<p>詳しくは、 <a href="../building-journeys/tags.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>



### 機能強化 {#mar-2023-improvements}

**ジャーニー**

* 新しい **Throttling API** では、1 秒あたりに送信されるイベントの数に制限を設定して、外部システムや API での過剰なトラフィックのスパイクを防ぐことができます。設定制限に達すると、以降のすべての API 呼び出しは、受け取った順序で、可能な限り早くキューに登録されて処理されます。この機能では、すべてのサンドボックスに対して 1 つのスロットル設定のみがサポートされることに注意してください。[詳細情報](../configuration/external-systems.md)
* ジャーニーキャンバスが強化され、よりシンプルで改善されたユーザーエクスペリエンスが実現しました。キャンバスの各パスの最後に、空のプレースホルダーが削除されています。これで、パスの最後にあるアクティビティをドラッグするだけで、アクティビティを追加できます。
* ジャーニーキャンバスで、**終了**&#x200B;タグは、以前のアクティビティの名前で自動的に設定されなくなりました。必要に応じて、カスタムラベルを手動で追加できます。
* ジャーニープロパティのデフォルトのタイムアウトとエラーの時間が 5 秒から 30 秒に変更されました。[詳細情報](../configuration/external-systems.md#timeout)
* セグメントを読み取りアクティビティのデフォルトのスロットル率が、1 秒あたり 20,000 件から 5,000 件のメッセージに変更されました。 [詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

<!-- 
* When adding an Email, SMS or Push action in a journey, the surface is now pre-filled, by default, with the last used surface for that channel.
* A new type of system alert has been introduced. You can now get notified when a custom action fails. [Learn more](../reports/alerts.md)
* Timeout and error management has been improved in journeys. Timeout and error paths are now always added on the canvas. A new toolbar button is available to show/hide these paths. [Learn more](../building-journeys/journey-gs.md#timeout_and_error)
* The Journey dashboard is now split in two tabs:
    * Use the **Overview** tab to access a new dashboard which displays key metrics related to your journeys.
    * Use the **Browse** tab to access list of all journeys.
-->

**意思決定管理**

* Adobe Experience Platform 全体で最近リリースされたタグ機能との潜在的な混乱を防ぐために、意思決定管理タグの名前を「コレクション修飾子」に変更しました。

   「タグ」という用語は、意思決定管理のユーザーインターフェイスでは使用されなくなりましたが、API やデータセットなどのバックエンドサービスでは引き続き使用します。

* オファーのキャッピングカウンターを日単位、週単位または月単位でリセットできるようになりました。[詳細情報](../offers/offer-library/add-constraints.md#capping)

* また、オファー決定支援キャッピングのために、参照する Adobe Experience Platform イベントを選択することもできます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

* プレースメントの作成画面に追加のパラメーターが追加されました。これを使用すると、1 つのオファーを複数のプレースメントにまたがって複製できるかどうかを制御し、オファーのコンテンツとメタデータを API 応答に含めるかどうかを指定できます。[詳細情報](../offers/offer-library/creating-placements.md)

**パーソナライゼーション**

* 式エディターに文字列ベースのプロファイル属性に対するデフォルトの代替テキストを含めることができるようになりました。これらの値は、選択した属性が結果を返さない場合に表示されます。[詳細情報](../personalization/personalization-build-expressions.md#add)

**レポート**

* レポートウィジェットの機能が改善され、ユーザーによるデータの表示方法をカスタマイズできるようになりました。この改善により、グラフ、表、ドーナツグラフなど、複数のビジュアライゼーションオプションの中から選択できるようになりました。

   最新のウィジェットにアクセスするには、異なるレポートダッシュボードをリセットする必要があることに注意してください。ダッシュボードのカスタマイズについて詳しくは、[詳細ドキュメント](../reports/global-report.md#modify-dashboard)を参照してください。

## 2023 年 2 月リリースノート {#feb-2023}

### 新機能{#feb-2023-features}

<table>
<thead>
<tr>
<th><strong>アプリ内チャネル（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>キャンペーン内で、アプリユーザーにパーソナライズされたアプリ内メッセージを送信できるようになりました。 Journey Optimizer を使用して通知をデザインし、メッセージのレイアウト、表示、テキストおよびボタンをカスタマイズして、シームレスなエクスペリエンスを作成します。</p>
<p><strong>注意</strong> - この機能は現在ベータ版です。ベータ版のユーザーのみがご利用いただけます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。</p>
<img src="assets/do-not-localize/in-app.gif"/>
<p>詳しくは、<a href="../in-app/get-started-in-app.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Optimizer データセットのクラウドストレージへの書き出し（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>データセットの内容を書き出すために、クラウドストレージの場所とのライブ接続を確立できるようになりました。使用可能な宛先は次のとおりです。Amazon S3 Cloud Storage、Azure Blob、Azure Data Lake Gen 2、Data Landing Zone、Google Cloud Storage、SFTP。</p>
<p><strong>注意</strong> - この機能は現在ベータ版です。すべての Adobe Journey Optimizer ユーザーがご利用いただけます。 アクセス権がない場合は、アドビ担当者に相談して、宛先へのアクセス権を取得してください。</p>
<img src="assets/do-not-localize/gif-destinations.gif"/>
<p>詳しくは、 <a href="../data/export-datasets.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--

<table>
<thead>
<tr>
<th><strong>Performance Measurement in campaigns</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now measure the performance of your campaigns across inbound and outbound through dedicated reports. Adobe Journey Optimizer reports can retrieve additional metrics to use in the <strong>Objective</strong> tab of your campaign reports. </p>
<img src="assets/do-not-localize/performance_report.gif"/>
<p>For more information, refer to the <a href="../privacy/data-hygiene.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>

+++ Learn more about Performance Measurement

The **[!UICONTROL Objective]** tab of your Campaign report allows you to better fine-tune your deliveries' reports by targeting one specific metric. With this feature, you can effectively track and analyze your campaign's performance and make informed decisions to improve your results.

The **[!UICONTROL Objectives]** listed are linked to **[!UICONTROL Datasets]** that define a connection to a system in order to retrieve additional information. A list of pre-configured **[!UICONTROL Objectives]** is available, but you can also customize your report by adding new **[!UICONTROL Datasets]** and defining your own objectives. 

By selecting the desired Objectives, the **[!UICONTROL Performance overview]** and **[!UICONTROL Campaign objective]** widgets provide a comprehensive and insightful summary of your delivery performance, allowing you to closely monitor and evaluate the success of your campaign.

With the **[!UICONTROL Campaign objective]** widget, you can also choose to compare your primary objective against another performance metric.

Note that each widget can be resized and deleted as needed.
+++




<table>
<thead>
<tr>
<th><strong>Use Tags in your Journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>As a Journey Optimizer practitioner, you can now organize your business objects using tags. Tags are a quick and easy way of classifying objects to improve search. Tags are currently only available for Journeys.</p>
</td>
</tr>
</tbody>
</table>

-->

### 機能強化 {#feb-2023-improvements}

**ジャーニー**

* ジャーニープロパティに「**再エントリ待機期間**」フィールドが追加されました。このフィールドでは、（イベントまたはセグメントの資格で始まる）単一のジャーニーで、プロファイルがジャーニーに再度エントリできるようにするまでの待機時間を定義できます。これにより、ジャーニーが同じイベントに対して誤って複数回トリガーされるのを防ぎます。デフォルトでは、このフィールドは 5 分に設定されています。[詳細情報](../building-journeys/journey-gs.md#entrance)

* **ジャーニーの開始日と終了日**&#x200B;が改善されました。開始日を指定していない場合は、公開時に自動的に追加されるようになりました。**セグメントの読み取り**&#x200B;ジャーニーで、終了日を追加できるようになりました。その日付に達したプロファイルを自動的に終了できます。[詳細情報](../building-journeys/journey-gs.md#dates)

<!--

* The Journey canvas has been enhanced for a simpler and improved user experience. At the end of each path in the canvas, the empty placeholders have been removed. You can now simply add your activities by dragging them anywhere between nodes. [Learn more](../building-journeys/using-the-journey-designer.md)

* Timeout and error management has been improved in journeys. Timeout and error paths are now always added on the canvas. A new toolbar button is available to show/hide these paths. [Learn more](../building-journeys/journey-gs.md#timeout_and_error)

* A new type of system alert has been introduced. You can now get notified when a custom action fails. [Learn more](../reports/alerts.md)

* The Journey dashboard is now split in two tabs:
    * Use the **Overview** tab to access a new dashboard which displays key metrics related to your journeys.
    * Use the **Browse** tab to access list of all journeys.
-->


**管理**

* **許可リスト** - 許可リストを .csv ファイルとしてダウンロードできるようになりました。[詳細情報](../configuration/allow-list.md#download-allowed-list)

* **メールサーフェス** - メールサーフェスの設定にさらにチェックが追加されました。サブドメインの MX レコードが&#x200B;**返信先（メール）アドレス**&#x200B;または **BCC メールアドレス**&#x200B;が正しく設定されていない場合、メールサーフェスを作成できなくなりました。設定するか、別の設定を使用する必要があります。 [詳細情報](../email/email-settings.md#reply-to-email)

* **メールサーフェス** - メールサーフェス設定の **URLトラッキングパラメーター**&#x200B;セクションで、Adobe Analytics トラッキングとの互換性のために、各&#x200B;**値**&#x200B;フィールドの制限が 255 文字から 5 KB に更新されました。[詳細情報](../email/email-settings.md#url-tracking)

**意思決定管理**

* **プレースメント** - プレースメントの作成画面に追加のパラメーターが追加されました。これを使用すると、1 つのオファーを複数のプレースメントにまたがって複製できるかどうかを制御し、オファーのコンテンツとメタデータを API 応答に含めるかどうかを指定できます。[詳細情報](../offers/offer-library/creating-placements.md)

* **URL のパーソナライゼーション** - オファーの表示域にコンテンツとして URL を追加する場合、式エディターを使用して、これらの URL をパーソナライズできるようになりました。[詳細情報](../offers/offer-library/add-representations.md)

## 2023年1月リリースノート{#jan-2023-release}

### 新機能{#jan-2023-features}

<table>
<thead>
<tr>
<th><strong>データハイジーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform は、消費者レコードとデータセットをプログラムで削除することで、保存されたデータを管理できる、一連のデータハイジーン機能を提供します。この機能は、Adobe Journey Optimizer で使用できるようになりました。 </p>
<p>データストアを管理して、情報が期待どおりに使用され、必要な場合は不適切なデータの修正が更新され、組織のポリシーで必要と判断された場合は削除されるようになります。</p>
<p><strong>注意</strong> - データハイジーン機能は、現在、<strong>Healthcare Shield</strong> および<strong>プライバシーとセキュリティシールド</strong>アドオン機能を購入した組織でのみ利用できます。</p><p>詳しくは、<a href="../privacy/data-hygiene.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールコンテンツテンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーやキャンペーン全体で活用できるスタンドアロンのコンテンツテンプレートを作成し、すばやく再利用できるようになりました。</p> 
</p>
<img src="assets/do-not-localize/content-template.gif"/>
<p>コンテンツテンプレートを作成、編集、使用する方法については<a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/content-templates.html?lang=ja">このビデオ</a>をご覧ください。 詳しくは、 <a href="../email/content-templates.md">詳細なドキュメント</a>を参照してください。
</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#jan-2023-improvements}

**ジャーニー**

* 「**セグメントの選定**」または「**セグメントの読み取り**」をジャーニーに追加すると、名前空間は、最後に使用した名前空間で、デフォルトで事前入力されるようになりました。 詳しくは、[セグメントの選定](../building-journeys/segment-qualification-events.md#about-segment-qualification)および[セグメントの読み取り](../building-journeys/read-segment.md#configuring-segment-trigger-activity)の節を参照してください。

* ジャーニーキャンバスのツールバーに新しいボタンが表示され、ジャーニーのスクリーンショットをダウンロードできます。

**電子メールデザイナー**

* **HTML を書き出し**&#x200B;メニューからメールの内容を書き出せるようになりました。書き出されたファイルは、アーカイブ（.ZIP）ファイルで使用できます。

**管理**

* 新しいサブセクションでは、**返信先（メール）**&#x200B;アドレスを作成し、適切な返信管理を行うための推奨事項を説明します。[詳細情報](../email/email-settings.md#reply-to-email)

* **IP プール**&#x200B;の作成または編集時に、関連付けられている PTR レコードが IP リストに表示され、選択した IP アドレスにカーソルを合わせると表示されるようになりました。[詳細情報](../configuration/ip-pools.md#create-ip-pool)

* チャネルサーフェスで IP プールが選択された後、IP アドレスにカーソルを合わせると、PTR レコード情報が表示されるようになりました。[詳細情報](../email/email-settings.md#subdomains-and-ip-pools)

* [PTR レコード](../configuration/ptr-records.md#edit-ptr-record)および[実行フィールド](../configuration/primary-email-addresses.md)編集用のユーザーインターフェイスが更新されました。 

* サブドメインの作成および編集用のユーザーインターフェイスが改善されました。 [詳細情報](../configuration/delegate-subdomain.md)

* 抑制リストの&#x200B;**最近のアップロード**&#x200B;画面が更新されました。[詳細情報](../configuration/manage-suppression-list.md#recent-uploads)

**キャンペーン**

* API トリガーキャンペーンを実行するためのサンプル cURL リクエストが自動生成され、キャンペーン画面で使用できるようになりました。 [詳細情報](../campaigns/api-triggered-campaigns.md)


**パーソナライゼーション**

* 新しいヘルパー関数（formatCurrency、charCodeAt、stringToDate、toString、formatNumber、toHexString）を使用できます。さらに、toDateTimeOnly 関数では、文字列、日付、長さ、整数の各フィールドタイプを受け入れるようになりました。 [詳細情報](../personalization/functions/functions.md)
