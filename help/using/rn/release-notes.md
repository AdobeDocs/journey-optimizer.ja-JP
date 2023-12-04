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
source-git-commit: 299b34dec2e864fff5eb874b3fd491da80bc0c16
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 100%

---

# リリースノート {#release-notes}


>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

以前のリリースノートは、[このページ](release-notes-2023.md)にあります。 また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2023年10月リリースノート {#oct-rn-2023}

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
<p>詳しくは、<a href="../building-journeys/copy-to-sandbox.md">詳細なドキュメント</a>を参照してください。</p>
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
<th><strong>SMS のマルチメディアメッセージサービス（MMS）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス（MMS）メッセージを送信して通信を強化し、画像、GIF またはビデオを顧客と共有できます。この機能は現在、Sinch でのみ使用可能です。</p>
<img src="assets/do-not-localize/mms.gif"/>
<p>詳しくは、 <a href="../sms/create-sms.md#mms-content">詳細なドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>

### 機能強化 {#oct-2023-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス**

* CSV ファイルからアップロードされたオーディエンスを、ジャーニーやキャンペーンにターゲットできるようになりました。[詳細情報](../audience/about-audiences.md#segments-in-journey-optimizer)
* オーディエンスコンポジションを通じて作成されたオーディエンスをターゲットにし、ジャーニーのエンリッチメント属性を活用できるようになりました。[詳細情報](../building-journeys/read-audience.md)

>[!AVAILABILITY]
>
>これらの機能は現在、Private Beta として使用可能です。

<!--
**Spam scoring for emails**

* When simulating an email content, a new option enables you to check how your content performs against inboxes spam filtering. This feature is currently proposed to a set of customers only (Limited Availability), and available for the Email channel.-->

**キャンペーン**

<!--* You can now stop a live one-time campaign, make modifications and resume it again. This improvement is available in Beta.-->
* キャンペーンのいずれかでエラーが発生した場合、キャンペーンのステータスと共に、キャンペーンリストに警告アイコンが表示されるようになりました。[詳細情報](../campaigns/modify-stop-campaign.md#statuses)

**ジャーニー**

* 待機時間として定義できる最大期間は、30 日ではなく 29 日になりました。この改善は、待機時間がジャーニーの 30 日間を超えるのを防ぐために導入されました。これは、以下に適用されます。

   * [待機アクティビティ](../building-journeys/wait-activity.md)の「**時間**」フィールド
   * [ジャーニープロパティ](../building-journeys/journey-gs.md#entrance)の&#x200B;**再エントリ待機期間**
   * [イベントアクティビティ](../building-journeys/general-events.md#events-specific-time)のタイムアウト定義の「**待機**」フィールド。

<!--
**Consent in channel configuration**

* You can now select a marketing action at the channel surface level. When used in a surface, all consent policies associated with that marketing action are leveraged in order to respect the preferences of your customers.-->

**意思決定管理**

* 意思決定管理インターフェイスのオファーキャッピングに関連するいくつかのラベルが更新されました。[詳細情報](../offers/offer-library/add-constraints.md#capping)

