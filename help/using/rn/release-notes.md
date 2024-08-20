---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: d971d857a480868f5ef502f3a3f2c209afc93cca
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 70%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2024年8月早期リリースノート {#e-2024}

**リリース日**：2024年8月20日～21日（PT）

>[!CAUTION]
>
>**以下の早期リリースノートは、リリース日まで予告なく変更される場合があります**。 リンク、画面、更新されたドキュメントは、リリース日に公開されます。
>

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<!--table>
<thead>
<tr>
<th><strong>Guided Channel Setup</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Guided Channel Setup enables you to automate and validate channel setup in a unified experience, speeding up the process of getting started with Journey Optimizer. This new guided setup streamlines rapid channel configuration, ensuring all necessary resources are readily installed and working within Experience Platform, Journey Optimizer, and Data Collection. This enables marketing, product and data engineering teams to quickly begin with campaign and journey creation.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Content Cards</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Content card is a new digital messaging feature in Adobe Journey Optimizer that delivers personalized and engaging content directly within mobile apps and websites. Unlike traditional push notifications, Content Cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.</p>
<p>This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Improved Channel Configurations</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The current channel surface capabilities have been enhanced for a consistent approach across all channels. You can now define, manage, and reuse these configurations for any of your channels, including Web, In-app messaging, or Code-based experience.</p>
<p><ul>
<li>Channel surfaces are now renamed to <strong>Channel configurations</strong></li>
<li>You can attach one or multiple marketing actions to enforce consent and data governance policies</li>
<li>Object level access control (OLAC) is now available for each channel configuration, allowing you to decide which of your users are allowed to create or use specific configurations</li>
<li>For some channels, you can create channel configurations that target multiple platforms. An example here would be an In-app messaging channel configuration that can target a web page, an iOS app and an Android app.</li>
</ul></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>カスタムアクションのMarketo Engage</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer を Adobe Marketo Engage と統合して、B2B ユースケースを作成できるようになりました。新しいカスタムアクションを使用すると、ジャーニーから Marketo にデータを取り込むことができます。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>コンテンツフラグメントの変数</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>フラグメントは、<a href="../personalization/use-expression-fragments.md"> 式フラグメント </a> と <a href="../email/use-visual-fragments.md"> ビジュアルフラグメント </a> の両方で入力変数を使用できるようになりました。 これらの変数を使用して、キャンペーンやジャーニーでメッセージのコンテンツやパラメーターをパーソナライズできます。</p>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>IP ウォームアップワークフロー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>公開日：8月13日（PT）</p>
<p>新しい IP アドレスでメールを送信する際に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。Adobe Journey Optimizer は、標準化された効率的な方法で、最適な配信品質を実現するためのベストプラクティスに従って IP アドレスをウォームアップします。</p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が行われています。

**ジャーニー**

<!--* In the **Condition** activity, by default, the Time condition is now set by hour, from 00:00 to 12:00. [Read more](../building-journeys/condition-activity.md#time_condition)-->
* ジャーニーを作成する際に、キャンペーンアラートと連携して一貫したユーザーエクスペリエンスを実現するために、アラートがドロップダウンリストに表示されるようになりました。 [詳細情報](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* ジャーニーツールバーのズームオプションが改善されました。ズーム率が表示され、ズーム値を 100% に簡単にリセットできるようになりました。

**オーディエンス**

* カスタムアップロード（CSV ファイル）のオーディエンスを、プライバシーとセキュリティシールドのアドオンで使用できるようになりました。
* カスタムアップロード（CSV ファイル）オーディエンスをターゲティングする際に、キャンペーンおよびジャーニーでファイルの属性を使用できるようになりました。 これらの属性は、パーソナライゼーションエディター、メッセージのパーソナライズ、ジャーニーの高度な式エディターで使用できます。

## 2024年7月リリースノート {#24-7-2024}

**リリース日**：2024年7月30～31日（PT）

### 新機能 {#27-4-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>任意のプロバイダーでの SMS チャネル（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>デフォルトのプロバイダーである Sinch、Infobip、Twilio に加えて、Journey Optimizer 内で追加の SMS プロバイダーを設定できるようになりました。</p>
<img src="assets/do-not-localize/byo_sms.gif"/>
<p>詳しくは、<a href="../sms/sms-configuration-custom.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>連合オーディエンス構成（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>連合オーディエンス構成が Adobe Journey Optimizer で使用できるようになりました。これを使用すると、企業は様々なユースケースでの稼動率を高めるデータを作成できます。この新しいアプローチでは、Adobe Real-time Customer Data Platform または Adobe Journey Optimizer のユーザーとして、既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。</p>
<p>詳しくは、 <a href="https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home"  target="_blank">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#27-4-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**ジャーニー**

* （提供日：7月8日（PT）**ジャーニーイベント設定の高度な式エディター** - イベントを設定する際に高度な式エディターを活用できるようになりました。これにより、さらに複雑な式を定義したり、イベント ID 条件で関数を使用したりできます。[詳細情報](../event/about-creating.md#adv-exp-editor)

