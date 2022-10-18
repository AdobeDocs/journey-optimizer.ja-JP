---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 63c52f04da9fd1a5fafc36ffb5079380229f885e
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 89%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。


## 2022年10月 {#oct-2022-release}

### 機能強化{#oct-2022-improvements}

**ジャーニー**

* この **繰り返し時に再入力を強制** オプションが、繰り返しのセグメント読み取りスケジュールパラメーターに追加されました。 このオプションを使用すると、ジャーニーに存在するすべてのプロファイルを、次回の実行時に自動的に終了させることができます。 このオプションを無効にした場合、プロファイルは、別のオカレンスに再入場する前にジャーニーを完了する必要があります。 [詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

## 2022年9月リリース{#sept-2022-release}

### 新機能{#sept-2022-features}

<table>
<thead>
<tr>
<th><strong>動的コンテンツおよび新しい条件付きルールビルダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>動的コンテンツを作成して、条件ルールに基づいてメッセージのコンテンツを適応させることができるようになりました。</p> 
<p>条件ルールは、式エディター内のビジュアルなルールビルダーを使用して作成されます。このビジュアルなルールを保存することで、ジャーニーやキャンペーンでさらに再利用できます。</p>
<img src="assets/do-not-localize/dynamic-content.gif"/>
<p>詳しくは、<a href="../personalization/get-started-dynamic-content.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>API トリガーキャンペーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>既存のスケジュール済みキャンペーンに加えて、Journey Optimizer で API トリガーキャンペーンを作成し、API を使用して外部システムから呼び出すことができるようになりました。</p>
<p>これにより、パスワードのリセットや OTP トークンなど、運用上のメッセージおよびトランザクションメッセージの様々なニーズに対応できます。</p>
<img src="assets/do-not-localize/api-triggered.gif"/>
<p>詳しくは、<a href="../campaigns/api-triggered-campaigns.md">詳細なドキュメント</a>を参照してください。
</td>
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
<p>属性ベースのアクセス制御により、管理者は特定の属性に基づいて、特定のオブジェクトへのアクセスを制御できます。 これらの属性は、オブジェクトに追加されるメタデータ（ラベルなど）にすることができます。 このリリース以降、管理者は、特定のフィールドやオブジェクト、およびそれらのフィールドやオブジェクトに対応するデータのみにアクセスできるユーザーの役割を定義することもできます。</p>
<p> 属性ベースのアクセス制御の使用は、現在、選択した顧客に限定されており、将来のリリースですべての環境にデプロイされます。</p>
<img src="assets/do-not-localize/olac.gif"/>
<p>詳しくは、<a href="../administration/object-based-access.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>データガバナンスとプライバシー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Data Usage Labeling and Enforcement（DULE）ガバナンスフレームワークにより、Journey Optimizer は Adobe Experience Platform ガバナンスポリシーを活用して、機密フィールドがカスタムアクションを通じてサードパーティのシステムにエクスポートされるのを防ぐことができるようになりました。制限されたフィールドがカスタムアクションパラメーターで特定されると、エラーが表示され、ジャーニーの公開ができなくなります。</p>
<p>Data Usage Labeling and Enforcement（DULE）の使用は、現在、選択した顧客に限定されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、<a href="../action/action-privacy.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>自動同意適用（同意ポリシー）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform では、顧客の同意設定に従ってマーケティングポリシーを簡単に採用および実施できます。同意ポリシーは、Adobe Experience Platform で定義されます。Journey Optimizer では、これらの同意ポリシーをカスタムアクションに適用できます。例えば、メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外する同意ポリシーを定義できます。
<p>自動同意適用は、現在、Healthcare Shield アドオン機能を購入した組織でのみ利用できます。</p>
<p>詳しくは、<a href="../action/consent.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>権限管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、機能およびオブジェクトの権限を管理するためのユーザーの役割およびアクセスポリシーの定義をサポートしています。<strong>Adobe Experience Cloud の権限</strong>を通じて、役割を作成および管理すると共に、それらの役割に対して必要なリソース権限を割り当てることができます。また、権限では、特定の役割に関連付けられたラベル、サンドボックス、ユーザーを管理することもできます。</p>
<p> 権限の使用は、現在、選択したユーザーに限定されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、<a href="../administration/attribute-based-access.md">詳細なドキュメント</a>を参照してください。
</td>
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
<p>Journey Optimizer のユーザーは、ユーザーインターフェイスを通じてシステムアラートにアクセスして、ジャーニーが想定どおりに動作しない場合に通知を受け取れるようになりました。使用可能なアラートを確認し、購読できます。このリリースで使用できる最初のアラートは、定義された時間枠内にセグメントを読み取りアクティビティがプロファイルを処理しなかった場合に警告します。このワークフローのロックが解除されると、さらに多くの情報が表示されます。</p>
<p>詳しくは、 <a href="../reports/alerts.md">詳細なドキュメント</a>を参照してください。
</td>
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

### 機能強化{#sept-2022-improvements}

**ジャーニー**

* この&#x200B;**エンティティデータセット**&#x200B;は、Adobe Journey Optimizer の標準のデータセットとして使用できるようになりました。この参照データセットには、トラッキングとフィードバックのデータセット情報を強化するメタデータが含まれています。これにより、より分かりやすいデータを使用して、レポートやクエリを改善できます。 [詳細情報](../start/datasets-query-examples.md#entity-dataset)
* 同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぐために、新しいガードレールが（イベントまたはセグメントの選定で始まる）単一のジャーニーに追加されました。プロファイルの再エントリは、デフォルトで 5 分間一時的にブロックされるようになりました。[詳細情報](../start/guardrails.md#events-g)

**管理**

* 許可リストをアクティブ化または非アクティブ化する際に、新しい警告が表示されて、各アクションの影響の詳細を確認できます。 [詳細情報](../configuration/allow-list.md#enable-allow-list)
* チャネルサーフェスの作成、IP プールの作成、抑制リストと許可リストの管理、SMS チャネルの設定を行うためのユーザーインターフェイスが更新されました。
* 指定したサブドメインに対して最初のチャネルサーフェスを作成する場合、処理時間は 10 分から 10 日かかり、そのサブドメインを使用する後続のサーフェスに対しては最大 3 時間かかります。[詳細情報](../configuration/channel-surfaces.md#create-channel-surface)

<!--* Now when downloading the suppression list as a CSV file, you can choose the file that was previously generated, or generate a new file.-->
* ランディングページプリセットとランディングページサブドメインの作成を行うためのユーザーインターフェイスが更新されました。[詳細情報](../configuration/lp-subdomains.md)

**監査制御**

* Journey Optimizer を使用すると、キャンペーン、ジャーニー、メッセージ、ランディングページなど、様々なサービスや機能に対してシステム内のユーザーが実行したアクションを識別できます。監査ログリソースには、その他の様々なアクションに対する変更が含まれるようになり、アクティビティが発生すると自動的に記録されます。詳しくは、[このページ](../privacy/audit-logs.md)を参照してください。

**アーカイブのサポート**

* 新しい&#x200B;**エンティティデータセット**&#x200B;には、アーカイブ目的で、すべてのチャネルにおける送信済みメッセージのフォーマット広告構造を書き出すことができるテンプレートフィールドが含まれています。[詳細情報](../configuration/archiving-support.md)

**ランディングページ**

* 同じランディングページ内の別のページから取得したコンテキストデータを使用できるようになりました。例えば、チェックボックスをプライマリランディングページのサブスクリプションリストにリンクさせた場合は、「ありがとうございました」サブページでそのサブスクリプションリストを使用できます。[詳細情報](../landing-pages/lp-content.md#use-primary-page-context)

<!--* When configuring the primary page, you can now create additional data to enable storing information when the landing page is being submitted. [Learn more](../landing-pages/lp-content.md#use-additional-data)-->

<!--* You can now use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.-->

### その他の変更{#sept-2022-other}

* ジャーニーバーストモードは、Campaign 迅速配信モードに置き換えられました。[詳細情報](../campaigns/create-campaign.md#rapid-delivery)
* パフォーマンスを向上させるために、セグメントの読み取り、セグメントの選定、ビジネスイベントアクティビティで開始されるジャーニーでは、エクスペリエンスイベントフィールドグループを使用できなくなりました。この変更は、新しいジャーニーにのみ適用されます。既存のジャーニーは、現在の動作を維持します。[詳細情報](../start/guardrails.md#expression-editor)
* スケジュールされたセグメントの読み取りジャーニーの 1 時間の制限が削除されました。これらのジャーニーは遅延なく実行できるようになりました。

