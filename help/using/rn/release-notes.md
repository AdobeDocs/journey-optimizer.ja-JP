---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 0c428b18469eb98392fe6c49d5892a4699477457
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 27%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2024 年 1 月の早期リリースノート {#jan-2024}

**リリース日**:2024 年 1 月 30 日～31 日

### 新機能{#jan24-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>配信品質の更新</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerは、DMARC 認証テクノロジーをサポートするようになりました。</p>
<p>2024 年 2 月 1 日より、Googleと Yahoo! は、電子メールを送信する際に使用するドメインの DMARC レコードを持っている必要があります。 Journey OptimizerでデリゲートしたすべてのサブドメインまたはAdobeへのデリゲート中のサブドメインに対して DMARC レコードが設定されていることを確認します。</p>
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
<p>Real-Time CDPとJourney Optimizerの業界固有のユースケースプレイブックのカタログを活用して、Adobe Experience PlatformとAdobeジャーニーOptimizer を使用して実行できる一般的なユースケースに対処します。</p><p>ニーズに最適なプレイブックを選択したら、ジャーニー、メッセージ、スキーマ、セグメントなどのユースケースをサポートするために必要なアセットを生成し、それらをスキーマにカスタマイズして、価値の創出に要する時間を短縮できます。</p>
<p>詳しくは、 <a href="../start/playbooks.md">詳細なドキュメント</a>を参照してください。</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
</tr>
</tbody>
</table>

### 機能強化 {#jan24-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**レポート**

* **新しいドメインベースの分類ウィジェット**  — キャンペーンおよびジャーニーレポートを強化するための新しいウィジェットが追加されました。 The **ドメイン別のバウンス理由**, **ドメイン別に送信および配信**, **ドメイン別の開封数およびクリック数** および **ドメイン別のバウンスとエラー** ウィジェットは、主要な e メール配信およびトラッキング指標に対して、ドメインレベルで詳細な分類を提供します。 [詳細情報](../reports/channel-report.md)

**SMS チャネル**

* **ダブルオプトイン** - SMS のダブルオプトインワークフローでは、デバイスから要求が開始されたときに、ユーザーがメッセージの受信を明示的にオプトインしていることが保証されます。 ユーザーはインバウンド SMS メッセージを送信して、同意プロセスを開始します。 同意を確認すると、最終検証をリクエストするフォローアップメッセージが送信されます。 ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。 [詳細情報](../sms/sms-configuration.md#create-api)

  この機能は、Sinch および Infobip の SMS プロバイダーで利用できます。

**ジャーニー**

* **反応イベントの期間**  — 定義できる最大期間 ( **反応イベント** は 30 日ではなく 29 日になりました。 [詳細情報](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **オーディエンスの閲覧**  - **オーディエンスの閲覧** アクティビティは、バッチセグメントでプロファイルスナップショットデータセットを使用するようになりました。このデータセットは、スケジュールされた日次バッチジョブの実行後 1 日に 1 回のみ生成されるので、最後の日次バッチジョブまでデータが更新されます。

* **フィールドグループ**  — このリリースでは、特定の場合にフィールドグループが保存されない問題が修正されました。

**頻度ルール**

* **週別および日別の頻度の上限** ：月に加えて、1 週間または 1 日に顧客プロファイルに送信されるメッセージの最大数を指定できるようになりました。 頻度キャップは、選択したカレンダー期間に基づき、対応する期間の初めにリセットされます。 [詳細情報](../configuration/frequency-rules.md#create-new-rule)

**意思決定管理**

* **エッジでの頻度キャップ**  — 頻度キャップカウンターが更新され、3 秒未満で Edge 判定 API の決定で使用できるようになりました。