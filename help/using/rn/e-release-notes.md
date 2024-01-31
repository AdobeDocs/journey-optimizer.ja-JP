---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 97967e8043df9b75d3120e4a7bfccff700f5d57f
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 16%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、 [リリースノート](release-notes.md)、リリース日。

## 2024 年 1 月の早期リリースノート {#e-2024}

**リリース日**:2024 年 1 月 20 日～31 日

### 新機能{#e-features}

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
<!--img src="assets/channel-reports.png"/-->
<p>詳しくは、<a href="../configuration/dmarc-record.md">詳細なドキュメント</a>を参照してください。</p>
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
<br/><img src="assets/do-not-localize/playbooks.gif"/>
<!--<p>For more information, refer to the <a href="../start/playbooks.md">detailed documentation</a>.</p>-->
</tr>
</tbody>
</table>

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**レポート**

* **新しいドメインベースの分類ウィジェット**  — キャンペーンおよびジャーニーレポートを強化するための新しいウィジェットが追加されました。 The **ドメイン別のバウンス理由**, **ドメイン別に送信および配信**, **ドメイン別の開封数およびクリック数** および **ドメイン別のバウンスとエラー** ウィジェットは、主要な e メール配信およびトラッキング指標に対して、ドメインレベルで詳細な分類を提供します。 [詳細情報](../reports/channel-report.md)

**SMS チャネル**

* **ダブルオプトイン** - SMS のダブルオプトインワークフローでは、デバイスから要求が開始されたときに、ユーザーがメッセージの受信を明示的にオプトインしていることが保証されます。 ユーザーはインバウンド SMS メッセージを送信して、同意プロセスを開始します。 同意を確認すると、最終検証をリクエストするフォローアップメッセージが送信されます。 ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。 [詳細情報](../sms/sms-configuration.md#create-api)

  これは、Sinch および Infobip SMS プロバイダーにのみ適用されます。

**ジャーニー**

* **反応イベントの期間**  — 定義できる最大期間 ( **反応イベント** は 30 日ではなく 29 日になりました。 [詳細情報](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **オーディエンスの閲覧**   — 「オーディエンスの読み取り」アクティビティは、バッチセグメントのプロファイルスナップショットデータセットを使用するようになりました。このデータセットは、スケジュールされた日次バッチジョブの実行後 1 日に 1 回のみ生成されるので、最後の日次バッチジョブまでデータが更新されます。

* **フィールドグループ**  — 特定の場合にフィールドグループが保存されない問題を修正しました。

* **式エディター**  — すべての式と追加の関数で、 listObject データ型をサポートするようになりました。 [詳細情報](../building-journeys/expression/functions.md)

**頻度ルール**

* **週別および日別の頻度の上限** ：月に加えて、1 週間または 1 日に顧客プロファイルに送信されるメッセージの最大数を指定できるようになりました。 頻度キャップは、選択したカレンダー期間に基づき、対応する期間の初めにリセットされます。 [詳細情報](../configuration/frequency-rules.md#create-new-rule)

**意思決定管理**

* **エッジでの頻度キャップ**  — 頻度キャップカウンターが更新され、3 秒未満で Edge 判定 API の決定で使用できるようになりました。