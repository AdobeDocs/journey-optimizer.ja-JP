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
workflow-type: ht
source-wordcount: '558'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年1月早期リリースノート {#e-2024}

**リリース日**：2024年1月20～31日（PT）

### 新機能{#e-features}

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
<p>Real-Time CDP と Journey Optimizer における業界固有のユースケースプレイブックのカタログを活用し、Adobe Experience Platform と Adobe Journey Optimizer を使用して実行できる一般的なユースケースに対処します。</p><p>ニーズに最適なプレイブックを選択したら、それを有効にして、ジャーニー、メッセージ、スキーマ、セグメントなどのユースケースをサポートするために必要なアセットを生成し、スキーマに合わせてカスタマイズして価値実現までの時間を短縮できます。</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
<!--<p>For more information, refer to the <a href="../start/playbooks.md">detailed documentation</a>.</p>-->
</tr>
</tbody>
</table>

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**レポート**

* **新しいドメインベースの分類ウィジェット** - キャンペーンレポートとジャーニーレポートを強化するための新しいウィジェットが追加されました。**ドメイン別のバウンス理由**、**ドメイン別に送信および配信済み**、**ドメイン別の開封数およびクリック数**&#x200B;および&#x200B;**ドメイン別のバウンス数およびエラー数**&#x200B;ウィジェットは、主なメール配信とトラッキング指標のドメインレベルでの詳細な分類を提供します。[詳細情報](../reports/channel-report.md)

**SMS チャネル**

* **ダブルオプトイン** - SMS のダブルオプトインワークフローでは、デバイスからリクエストが開始された際に、ユーザーがメッセージの受信を明示的にオプトインすることが保証されます。ユーザーは、インバウンド SMS メッセージを送信して同意プロセスを開始します。同意を確認すると、最終検証をリクエストするフォローアップメッセージが送信されます。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。[詳細情報](../sms/sms-configuration.md#create-api)

  これは、Sinch および Infobip の SMS プロバイダーにのみ適用されます。

**ジャーニー**

* **反応イベントの期間** - **反応イベント**&#x200B;で定義できる最大期間は、30 日ではなく 29 日になりました。[詳細情報](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **オーディエンスを読み取り** - 「オーディエンスを読み取り」アクティビティは、バッチセグメントのプロファイルスナップショットデータセットに依存するようになりました。このデータセットは、スケジュールされた毎日のバッチジョブの実行後に 1 日に 1 回のみ生成されるので、データは最後の毎日のバッチジョブまで最新になります。

* **フィールドグループ** - 特定の場合にフィールドグループの保存をブロックする問題を修正しました。

* **式エディター** - すべての式と追加関数で、listObject データタイプをサポートするようになりました。[詳細情報](../building-journeys/expression/functions.md)

**頻度ルール**

* **週別および日別のフリークエンシーキャップ** - 1 か月に加え、1 週間または 1 日に顧客プロファイルに送信するメッセージを指定できるようになりました。フリークエンシーキャップは、選択したカレンダー期間に基づき、対応する時間枠の開始時にリセットされます。[詳細情報](../configuration/frequency-rules.md#create-new-rule)

**意思決定管理**

* **Edge でのフリークエンシーキャップ** - フリークエンシーキャップカウンターが新しくなり、3 秒未満の Edge Decisioning API の決定で使用できるようになりました。