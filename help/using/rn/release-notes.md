---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 428e08ca712724cb0b3453681bee1c7e86ce49dc
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 53%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2024年8月リリースノート {#8-2024}

**リリース日**：2024年8月20日～21日（PT）

<!--
>[!CAUTION]
>
>**Early release notes below are subject to change without prior notice until the release date**. Links, screens and updated documentation are published at the release date.
>
-->

### 新機能 {#8-features}

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
<th><strong>Content Cards (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Content cards are a new digital messaging feature in Adobe Journey Optimizer that delivers personalized and engaging content directly within mobile apps and websites. Unlike traditional push notifications, Content Cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.</p>
<p>This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.</p>
</br>
<p>Content card are currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
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
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
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
<p>詳しくは、<a href="../action/marketo-engage.md">詳細なドキュメント</a>を参照してください。</p>
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
<p>フラグメントのグローバル変数は、既存のフラグメント機能を強化して、コンテンツの再利用性とスクリプトのユースケースの効率を向上させます。 フラグメントで入力変数を使用し、キャンペーンおよびジャーニーコンテンツで使用できる出力変数を作成できるようになりました。 フラグメントは、<a href="../personalization/use-expression-fragments.md"> 式フラグメント </a> と <a href="../email/use-visual-fragments.md"> ビジュアルフラグメント </a> の両方で入力変数を使用できます。 これらの変数を使用して、キャンペーンやジャーニーでメッセージのコンテンツやパラメーターをパーソナライズできます。</p>
<p>詳しくは、<a href="../personalization/use-expression-fragments.md">詳細なドキュメント</a>を参照してください。</p>
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


### 機能強化 {#8-improvements}

このリリースでは、以下に示す機能強化が行われています。

**ジャーニー**

* **条件** アクティビティでは、デフォルトで **[!UICONTROL 時間条件]** が時間単位で 00:00 から 12:00 に設定されるようになりました。 [詳細情報](../building-journeys/condition-activity.md#time_condition)
* ジャーニーを作成する際に、他のアラートと連携して一貫性のあるユーザーエクスペリエンスを提供するために、「**アラート**」ボタンからアラートが表示されるようになりました。 [詳細情報](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* ジャーニーツールバーのズームオプションが改善されました。ズーム率が表示され、ズーム値をより簡単にリセットできるようになりました。

<!--**Audiences and Profiles**-->

<!--* The use of audiences from custom upload (CSV file) is now available for use with Privacy and Security Shield add-on.-->
<!--* When targeting a custom upload (CSV file) audience, you can now use attributes from the file in your campaigns and journeys. These attributes are available in the personalization editor, to personalize your messages, and the journey advanced expression editor.-->
<!--* The License usage dashboard now shows the count of Engageable Profiles. [Read more](../audience/license-usage.md)-->


**プッシュチャネル**

* モバイルアプリケーションのプッシュ資格情報をAdobe Journey Optimizer チャンネル設定内に追加できるようになりました。 Adobe Experience Platform Data Collection でのアプリサーフェスの作成は不要になりました。

### その他の変更 {#changes}

**レポート**

* 現在のレポートエクスペリエンスは、10 月リリースの時点で廃止されます。 この日以降、新しいレポートエクスペリエンスが標準となります。 スムーズな移行を確実に行うために、新機能を理解しておくことをお勧めします。

[Journey Optimizerの新しいレポートインターフェイスの概要](../reports/report-gs-cja.md)
