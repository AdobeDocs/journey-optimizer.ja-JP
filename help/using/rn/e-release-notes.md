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
source-git-commit: 004eb41b084f32993ec437f589e4e3d2cf7500d3
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2023年10月先行リリースノート {#oct-rn-2023}

**リリース日**：2023年10月25～26日（PT）

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
<p>サンドボックスツールを使用すると、パッケージの書き出しと読み込みを活用して、複数のサンドボックス間でオブジェクトをコピーできます。パッケージは、1 つのオブジェクトまたは複数のオブジェクトで構成できます。パッケージに含まれるオブジェクトは、同じサンドボックスからのものである必要があります。</p>
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
<th><strong>SMS のマルチメディアメッセージサービス（MMS）（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス（MMS）メッセージを送信して通信を強化し、画像、GIF またはビデオを顧客と共有できます。この機能は現在、Sinch のベータ版でのみ使用可能です。</p>
<!--img src="assets/channel-reports.png"/-->
<!--p>For more information, refer to the <a href="../in-app/get-started-in-app.md">detailed documentation</a>.</p-->
</tr>
</tbody>
</table>

### 機能強化 {#oct-2023-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス**

* CSV ファイルからアップロードされたオーディエンスをジャーニーやキャンペーンにターゲットできるようになりました。
* オーディエンスコンポジションを通じて作成されたオーディエンスをターゲットにし、ジャーニーのエンリッチメント属性を活用できるようになりました。

>[!AVAILABILITY]
>
>これらの機能は現在、Private Beta として使用可能です。

<!--
**Spam scoring for emails**

* When simulating an email content, a new option enables you to check how your content performs against inboxes spam filtering. This feature is currently proposed to a set of customers only (Limited Availability), and available for the Email channel.-->

**キャンペーン**

<!--* You can now stop a live one-time campaign, make modifications and resume it again. This improvement is available in Beta.-->
* キャンペーンのいずれかでエラーが発生した場合、キャンペーンのステータスと共に、キャンペーンリストに警告アイコンが表示されるようになりました。

**ジャーニー**

* 待機時間として定義できる最大期間は、30 日ではなく 29 日になりました。これは、以下に適用されます。

   * [待機アクティビティ](../building-journeys/wait-activity.md)の「**時間**」フィールド
   * [ジャーニープロパティ](../building-journeys/journey-gs.md#entrance)の&#x200B;**再エントリ待機期間**
   * [一般](../building-journeys/general-events.md#events-specific-time)イベントと[反応](../building-journeys/reaction-events.md)イベントのタイムアウト定義の「**待機**」フィールド。

**チャネル設定での同意**

* チャネルサーフェスレベルでマーケティングアクションを選択できるようになりました。サーフェスで使用すると、顧客の環境設定に従うために、そのマーケティングアクションに関連付けられたすべての同意ポリシーが活用されます。

**意思決定管理**

* 意思決定管理インターフェイスのオファーキャッピングに関連するいくつかのラベルが更新されました。
