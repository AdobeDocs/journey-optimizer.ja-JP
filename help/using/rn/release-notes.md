---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: ee33923ff5bfb73974935864c7e241ea4b0353c5
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 74%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2024年2月リリースノート {#feb-2024}

**リリース日**：2024年2月21～22日（PT）

### 新機能{#feb-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>Web アプリ内メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい web アプリ内メッセージ機能を使用して、モーダルオーバーレイメッセージを通じてパーソナライズされたコンテンツを web サイトに直接表示できるようになりました。この機能により、web 訪問者と効果的に関わり、ユーザーインタラクション、定着率およびコンバージョン率を向上させることができます。<br/><br/></p>
<p>詳しくは、<a href="../in-app/create-in-app-web.md">詳細なドキュメント</a>を参照してください。<br></br></p>
<img src="assets/do-not-localize/web_inapp.gif">
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>マルチチャネルコンテンツテンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>E メールに加え、コンテンツテンプレートが、プッシュ、アプリ内、SMS、ダイレクトメールの各チャネルで利用できるようになりました。各チャネルには専用のテンプレートタイプがあります。 E メールの場合は、コンテンツタイプを選択できるようになりました。これにより、件名行を E メールテンプレートの一部として保存できます。 <br/><br/></p>
<p>詳しくは、 <a href="../content-management/content-templates.md">詳細なドキュメント</a>を参照してください。<br></br></p>
<img src="assets/do-not-localize/multi-chan-templates.gif">
</tr>
</tbody>
</table>


### 機能強化 {#feb-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス**

* **シードリスト** - **シードリスト**&#x200B;の使用時にバリアントがサポートされるようになりました。シードアドレスには、同じメッセージのすべてのバリアントのコピーが届きます（コンテンツ実験の様々な処理など）。 [詳細情報](../configuration/seed-lists.md)

以前はベータ版として提供されていましたが、現在は次の機能強化がすべてのユーザーに提供されています。

* **オーディエンスコンポジションを通じて作成されたオーディエンス**&#x200B;をターゲットにし、ジャーニーのエンリッチメント属性を活用できるようになりました。[詳細情報](../building-journeys/read-audience.md)

* **CSV ファイルからアップロードされたオーディエンス**&#x200B;を、ジャーニーやキャンペーンにターゲットできるようになりました。[詳細情報](../audience/about-audiences.md#segments-in-journey-optimizer)

  >[!AVAILABILITY]
  >
  >* オーディエンス構成とカスタムアップロード（CSV ファイル）からのオーディエンスと属性の使用は、現在、Healthcare Shield または Privacy and Security Shield では使用できません。
  >* The **CSV ファイルからのオーディエンスのアップロード** 最初のリリースの後、数日間で徐々に改善が進んでいます。 一部のユーザーは即時にアクセスできますが、他のユーザーの環境で使用できるようになるまでに遅延が生じる場合があります。

**ジャーニー**

* **ジャーニーをフィルタリング** - 既存の定義済み日付フィルターに加えて、**カスタム日付を使用してジャーニーインベントリをフィルタリング**&#x200B;できるようになりました。これにより、特定の日付に作成または公開されたジャーニーを、特定の月内、1 年を通じて、または指定した期間内に表示することで、リストを細かく設定できます。 [詳細情報](../building-journeys/journey-gs.md#filter)
* **カスタムアクション**  — これで、 **content-type** ヘッダー。 この新しい **content-type** は JSON コンテンツを参照する必要があります。 [詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* **設定** - stepEvents のidentityMap 属性が事前に入力されるようになりました。プライマリ ID は「primary = true」と定義されます。 [詳細情報](../reports/sharing-field-list.md)
* **ユーザーインターフェイス** - エクスペリエンスを向上させるために、ジャーニー画面の上部バーが再編成されました。様々な更新の中で、ジャーニーのプロパティにアクセスできる「鉛筆」アイコンが、上部のバーの左側、ジャーニーの名前の横に表示されるようになりました。 [詳細情報](../building-journeys/journey-gs.md#change-properties)

**SMS チャネル**

* **オプトイン／オプトアウトのキーワード** - SMS チャネルを設定する際に、環境設定に従って&#x200B;**オプトインおよびオプトアウトキーワード**&#x200B;をカスタマイズできるようになりました。Journey Optimizerトリガーは、指定されたこれらのキーワードに基づいて応答を送信します。 [詳細情報](../sms/sms-configuration.md#create-api)

**キャンペーン**

* **API トリガーキャンペーン** - API トリガーのキャンペーンをアクティブ化した後に生成される cURL コードが強化されました。メッセージで使用されるすべてのパーソナライゼーション（プロファイルとコンテキスト）変数が含まれるようになりました。 [詳細情報](../campaigns/api-triggered-campaigns.md#execute)

**頻度ルール**

* E メールとプッシュに加えて、SMS チャネルとダイレクトメールチャネル用の頻度ルールを作成できるようになりました。 頻度ルールは、頻度キャップに達した場合に、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外します。 [詳細情報](../configuration/frequency-rules.md)

<!--**Decision management**

* **Capping rules** - You can now add **multiple capping rules** for one offer. This allows you to increase the level of control over the way offers are sent.-->

<!--
**Content templates**

* **Thumbnails** - A **Grid view** is now available for content templates for improved visual access.

   >[!AVAILABILITY]
   >
   >This capability is released in Limited Availability (LA) for a small set of customers.
-->


## 2024年1月リリースノート {#jan-2024}

**リリース日**：2024年1月30～31日（PT）

### 新機能{#jan24-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>配信品質のアップデート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer は、DMARC 認証テクノロジーをサポートするようになりました。</p>
<p>2024年2月1日（PT）以降、Google と Yahoo! は、メールの送信に使用するドメインの DMARC レコードを要求します。Journey Optimizer でアドビにデリゲートしたすべてのサブドメインや、デリゲート中のすべてのサブドメインに対して、DMARC レコードが設定されていることを確認してください。</p>
<p>詳しくは、<a href="../configuration/dmarc-record-update.md">詳細なドキュメント</a>を参照してください。</p>
<br/><img src="assets/do-not-localize/dmarc.gif"/>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ユースケースプレイブック</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-Time CDPとJourney Optimizerの業界固有のユースケースプレイブックのカタログを活用して、Adobe Experience PlatformとAdobe Journey Optimizerを使用して実行できる一般的な使用例に対処します。</p><p>ニーズに最適なプレイブックを選択したら、それを有効にして、ジャーニー、メッセージ、スキーマ、セグメントなどのユースケースをサポートするために必要なアセットを生成し、スキーマに合わせてカスタマイズして価値実現までの時間を短縮できます。</p>
<p>詳しくは、 <a href="../start/playbooks.md">詳細なドキュメント</a>を参照してください。</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
</tr>
</tbody>
</table>

### 機能強化 {#jan24-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**レポート**

* **新しいドメインベースの分類ウィジェット** - キャンペーンレポートとジャーニーレポートを強化するための新しいウィジェットが追加されました。**ドメイン別のバウンス理由**、**ドメイン別に送信および配信済み**、**ドメイン別の開封数およびクリック数**&#x200B;および&#x200B;**ドメイン別のバウンス数およびエラー数**&#x200B;ウィジェットは、主なメール配信とトラッキング指標のドメインレベルでの詳細な分類を提供します。[詳細情報](../reports/channel-report.md)

**SMS チャネル**

* **ダブルオプトイン** - SMS のダブルオプトインワークフローでは、デバイスからリクエストが開始された際に、ユーザーがメッセージの受信を明示的にオプトインすることが保証されます。ユーザーは、インバウンド SMS メッセージを送信して同意プロセスを開始します。同意を確認すると、最終検証をリクエストするフォローアップメッセージが送信されます。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。[詳細情報](../sms/sms-configuration.md#create-api)

  この機能は、Sinch および Infobip の SMS プロバイダーで使用できます。

**ジャーニー**

* **反応イベントの期間** - **反応イベント**&#x200B;で定義できる最大期間は、30 日ではなく 29 日になりました。[詳細情報](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **オーディエンスを読み取り** - 「**オーディエンスを読み取り**」アクティビティは、バッチセグメントのプロファイルスナップショットデータセットに依存するようになりました。このデータセットは、スケジュールされた日次バッチジョブの実行後に 1 日に 1 回のみ生成されます。そのため、データは前回の日次バッチジョブの時点での最新になります。[詳細情報](../building-journeys/read-audience.md)

* **フィールドグループ** - このリリースでは、特定の場合にフィールドグループの保存がブロックされていた問題が修正されています。

* `<listObject>` のサポートは、複数の機能で変更されました。

**頻度ルール**

* **週別および日別のフリークエンシーキャップ** - 1 か月に加え、1 週間または 1 日に顧客プロファイルに送信するメッセージを指定できるようになりました。フリークエンシーキャップは、選択したカレンダー期間に基づき、対応する時間枠の開始時にリセットされます。[詳細情報](../configuration/frequency-rules.md#create-new-rule)


**意思決定管理**

* **Edge でのフリークエンシーキャップ** - フリークエンシーキャップカウンターが更新され、3 秒未満で Edge Decisioning API の決定で使用できるようになりました。[詳細情報](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
