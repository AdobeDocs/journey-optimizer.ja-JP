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
source-git-commit: 74a4de20ae14923139cf6bf81676819355944ceb
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 24%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2023 年 10 月の早期リリースノート {#oct-rn-2023}

**リリース日**:2023 年 10 月 25～26 日

### 新機能{#oct-2023-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>サンドボックスツール</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>サンドボックスツールを使用すると、パッケージのエクスポートとインポートを活用して、複数のサンドボックスにまたがってオブジェクトをコピーできます。 パッケージは、1 つのオブジェクトまたは複数のオブジェクトで構成できます。 パッケージに含まれるオブジェクトは、同じサンドボックスからのものである必要があります。</p>
<!--img src="../data/assets/dataset-export-setup.png"-->
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<!-- table>
<thead>
<tr>
<th><strong>Composed audiences in journeys</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use audiences created in composition workflows in your journeys to target customers. Once an audience composition is published, and the audience saved, use a Read Audience activity to select this new audience in your journey canvas.</p>
<img src="assets/channel-reports.png"/>
<p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p>
</tr>
</tbody>
</table -->

<table>
<thead>
<tr>
<th><strong>SMS（ベータ版）でのマルチメディアメッセージサービス (MMS)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス (MMS) メッセージを送信して、顧客との画像、GIFまたはビデオの共有を有効にすることで、通信を強化できます。 この機能は、現在、Sinch でベータ版でのみ使用できます。</p>
<!--img src="assets/channel-reports.png"/-->
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>

### 機能強化 {#oct-2023-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス**

* CSV ファイルからジャーニーやキャンペーンにアップロードされたオーディエンスをターゲットに設定できるようになりました。
* オーディエンスの構成を通じて作成されたオーディエンスをターゲットにし、ジャーニーのエンリッチメント属性を活用できるようになりました。

>[!AVAILABILITY]
>
>これらの機能は、現在、非公開ベータ版として使用できます。

<!--
**Spam scoring for emails**

* When simulating an email content, a new option enables you to check how your content performs against inboxes spam filtering. This feature is currently proposed to a set of customers only (Limited Availability), and available for the Email channel.-->

**キャンペーン**

* ライブな 1 回限りのキャンペーンを停止し、変更を加えて再開できるようになりました。 この改善は、ベータ版で利用できます。
* キャンペーンの 1 つ内でエラーが発生した場合、キャンペーンのステータスと共に、キャンペーンリストに警告アイコンが表示されるようになりました。

**ジャーニー**

* 任意の待機時間で定義できる最大期間は、30 日ではなく 29 日になりました。 これは次に当てはまります。

   * の **時間** フィールド [待機アクティビティ](../building-journeys/wait-activity.md)
   * の **再入場待機期間** in [ジャーニーのプロパティ](../building-journeys/journey-gs.md#entrance)
   * の **待機** タイムアウト定義のフィールド [一般](../building-journeys/general-events.md#events-specific-time) および [反応](../building-journeys/reaction-events.md) イベント。

**チャネル設定での同意**

* これで、チャネルサーフェスレベルでマーケティングアクションを選択できます。 表面で使用する場合、顧客の好みを尊重するために、そのマーケティングアクションに関連するすべての同意ポリシーが利用されます。

**意思決定管理**

* 決定管理インターフェイスのオファー制限に関連するいくつかのラベルが更新されました。
