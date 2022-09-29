---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: cdaa6def25adcb63318c272efbfc6d7c4212a9dc
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 28%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022年9月リリース{#sept-2022-release}

### 新機能{#sept-2022-features}


<!--
<table>
<thead>
<tr>
<th><strong>Dynamic content & new conditional rule builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create dynamic content to adapt the content of your messages based on conditional rules.</p> 
<p>Conditional rules are created using a visual rule builder within the Expression Editor, where you can store them for further reuse across your journeys and campaigns.</p>
<img src="assets/do-not-localize/dynamic-content.gif"/>
<p>For more information, refer to the <a href="../personalization/get-started-dynamic-content.md">detailed documentation</a>.
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>API トリガーキャンペーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>既存のスケジュール済みキャンペーンに加えて、Journey Optimizerで API トリガーキャンペーンを作成し、API を使用して外部システムから呼び出すことができるようになりました。</p>
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
<p>管理者は、属性ベースのアクセス制御を使用して、特定の属性に基づいて特定のオブジェクトへのアクセスを制御できます。 これらの属性は、オブジェクトに追加されるメタデータ（ラベルなど）にすることができます。 このリリース以降、管理者は、特定のフィールドやオブジェクトにのみアクセスできるユーザーの役割、およびこれらのフィールドやオブジェクトに対応するデータを定義することもできます。</p>
<p> 属性ベースのアクセス制御の使用は、現在、選択した顧客に制限されており、将来のリリースですべての環境にデプロイされます。</p>
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
<p>Data Usage Labeling and Enforcement(DULE) ガバナンスフレームワークを使用すると、Journey OptimizerはAdobe Experience Platformガバナンスポリシーを活用して、機密のあるフィールドがカスタムアクションを通じてサードパーティのシステムに書き出されるのを防ぐことができます。 カスタムアクションパラメーターで制限されたフィールドが識別されると、エラーが表示されて、ジャーニーを公開できません。</p>
<p>Data Usage Labeling and Enforcement(DULE) の使用は、現在、選択した顧客に制限されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、<a href="../action/action-privacy.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>自動同意実施（同意ポリシー）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform では、顧客の同意設定に従ってマーケティングポリシーを簡単に採用および実施できます。同意ポリシーは、Adobe Experience Platform で定義されます。Journey Optimizer では、これらの同意ポリシーをカスタムアクションに適用できます。例えば、E メール、プッシュまたは SMS 通信の受信に同意しない顧客を除外する同意ポリシーを定義できます。
<p>自動同意実施は、現在、Healthcare Shield アドオン機能を購入した組織でのみ利用できます。</p>
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
<p>Journey Optimizerは、機能およびオブジェクトの権限を管理するためのユーザーの役割およびアクセスポリシーの定義をサポートしています。 ～ <strong>Adobe Experience Cloud権限</strong>では、役割を作成および管理し、それらの役割に対する必要なリソース権限を割り当てることができます。 また、権限では、特定の役割に関連付けられたラベル、サンドボックス、ユーザーを管理することもできます。</p>
<p> 権限の使用は、現在、選択した顧客に制限されており、将来のリリースですべての環境にデプロイされます。</p>
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
<p>Journey Optimizerのユーザーは、ユーザーインターフェイスを通じてシステムアラートにアクセスし、ジャーニーが期待どおりに動作しなかった場合に通知を受け取れるようになりました。 使用可能なアラートを表示し、購読することができます。 このリリースで使用できる最初のアラートは、「セグメントを読み取り」アクティビティが定義された期間内にプロファイルを処理しなかった場合に警告を表示します。 このワークフローがロック解除されると、さらに多くの情報が表示されます。</p>
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

* この **エンティティデータセット** は、Adobe Journey Optimizerの標準のデータセットとして使用できるようになりました。 このルックアップデータセットには、トラッキングとフィードバックのデータセット情報を強化するメタデータが含まれています。 これにより、より分かりやすいデータを使用して、レポートやクエリを改善できます。 [詳細情報](../start/datasets-query-examples.md#entity-dataset)
* 単一のジャーニー（イベントまたはセグメントの資格で始まる）に新しいガードレールが追加され、同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぎました。 プロファイルの再入口は、デフォルトで 5 分間一時的にブロックされるようになりました。 [詳細情報](../start/guardrails.md#events-g)

**管理**

* 許可リストを有効または無効にする際に、新しい警告が表示されて、各アクションの影響の詳細を確認できるようになりました。 [詳細情報](../configuration/allow-list.md#enable-allow-list)
* チャネルサーフェスの作成、IP プールの作成、抑制リストと許可リストの管理、SMS チャネルの設定をおこなうためのユーザーインターフェイスが更新されました。
<!--* Now when creating the first channel surface for a given subdomain, the processing time will take 10 minutes to 10 days, and only up to 3 hours for subsequent surfaces using that subdomain. Learn more
* Now when downloading the suppression list as a CSV file, you can choose the file that was previously generated, or generate a new file.
* The user interface for creating landing page presets and landing page subdomains has been improved. Learn more -->

**監査制御**

* Journey Optimizerを使用すると、キャンペーン、ジャーニー、メッセージ、ランディングページなど、様々なサービスや機能でシステム内のユーザーが実行したアクションを識別できます。 監査ログリソースに、その他の様々なアクションに対する変更が含まれるようになり、アクティビティの発生時に自動的に記録されます。 詳しくは、[このページ](../privacy/audit-logs.md)を参照してください。

**アーカイブのサポート**

* 新しい **エンティティデータセット** には、アーカイブ目的で送信メッセージの形式と構造をすべてのチャネルにエクスポートできる「テンプレート」フィールドが含まれています。 [詳細情報](../configuration/archiving-support.md)

**ランディングページ**

* 同じランディングページ内の別のページからのコンテキストデータを使用できるようになりました。 例えば、プライマリランディングページの購読リストにチェックボックスをリンクする場合、その購読リストを「ありがとうございました」サブページで使用できます。 [詳細情報](../landing-pages/lp-content.md#use-primary-page-context)

* プライマリページを設定する際に、ランディングページの送信時に情報を保存できるように、追加のデータを作成できるようになりました。 [詳細情報](../landing-pages/lp-content.md#use-additional-data)

<!--* You can now use information that was submitted on a landing page to send communications to your customers. For example, if a user subscribes to a given subscription list, you can leverage that information to send an email recommending other subscription lists to that user.-->

### その他の変更{#sept-2022-other}

* ジャーニーバーストモードは、Campaign の迅速な配信モードに置き換えられました。 詳細情報
* パフォーマンスを向上させるために、「セグメントを読み取り」、「セグメントの選定」、「ビジネスイベント」アクティビティから始まるジャーニーでは、エクスペリエンスイベントフィールドグループを使用できなくなりました。 この変更は、新しいジャーニーにのみ適用されます。 既存のものは、現在の動作を維持します。 [詳細情報](../start/guardrails.md#expression-editor)
* スケジュールされたセグメント読み取りジャーニーの 1 時間の制限が削除されました。 これらのジャーニーを遅延なく実行できるようになりました。

