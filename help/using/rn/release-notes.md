---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: bd30bbd6ac1230bdb02e1b5a4f9eba19c1fa2ccc
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 47%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022 年 6 月リリース {#june-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ユーザーに SMS を送信する（使用を制限）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>使用可能な日付： <b>6 月 27 日</b></p>
<p></p>
<p>Journey Optimizerで、 <b>シンチ</b> または <b>Twilio</b>.</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>SMS チャネルは現在、一連の組織でのみ使用できます（使用が制限されています）。 詳しくは、Adobe担当者にお問い合わせください。</p>
<p>SMS を作成して送信する方法を説明します <a href="../messages/create-sms.md">詳細なドキュメント</a>.</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Stockとの統合により、より効果的な画像をより迅速に見つける</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>使用可能な日付： <b>6 月 27 日</b></p>
<p></p>
<p>Adobe StockとAdobe Journey Optimizerの Email Designer 統合プラグインを使用すると、メッセージのオーサリングで使用するために、画像のナビゲーション、ライセンス、保存を簡単におこなうことができます。 </br> 新しい <b>類似の写真を検索</b> また、画像のコンテンツ、色、構成に一致する Stock 写真を探すこともできます。 </p>
<img src="assets/do-not-localize/stock-rn.gif"/>
<p>詳しくは、<a href="../design/stock.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>すべてのメールで BCC で E メールを使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>BCC（ブラインドカーボンコピー）でメールを送信機能を使用して、Adobe Journey Optimizer から送信されたメールを保存できるようになりました。メールプリセットでこのオプションを有効にして、送信されたすべてのメールが BCC アドレスにブラインドコピーされるようにします。</p>
<img src="assets/do-not-localize/bcc-rn.gif"/>
<p>詳しくは、<a href="../configuration/bcc-email.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the <a href="../offers/ranking/personalized-optimization-model.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

<!--table>
<thead>
<tr>
<th><strong>Copy objects between sandboxes</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now re-create the experiences from a Journey Optimizer sandbox to another, for example from a non-production sandbox to a production sandbox. This new capability copies an entire Journey, including any objects the Journey depends on to run correctly, from one environment to another. In addition to Journeys, you can also copy other components, such as Offers, Messages, Schemas, Datasets, Data Sources, Events, and Actions.</p>
<p>This feature is currently in beta version and only available to beta customers. To join the beta program, contact Adobe Customer Care.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content. In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->


### 機能強化

**意思決定管理**

* **HTMLと JSON ファイルのサポート**  — 外部HTMLファイルと JSON ファイルをAdobe Experience Cloud Asset ライブラリからオファー表示域のコンテンツにドラッグ&amp;ドロップできるようになりました。 [詳細情報](../offers/offer-library/add-representations.md#html-json)

<!--
**Email**

* **Save as template** - You can now save an email content as a template and reuse it when creating other messages.

**Journeys**

* **Ending a journey** - In the journey canvas, the **End** activity has been removed from the palette. End tags are now added by default at the end of each path and cannot be removed. This improvement allows better reporting of where a customer dropped out of the journey, without any action from the user.

-->

**管理**

<!--* **Allowed list in the UI** - You can now use the Journey Optimizer user interface to add new email addresses or domains to the allowed list.-->

* **トラッキング URL パラメーターのプレビュー**  — メッセージプリセットを設定する際に、URL トラッキングパラメーターを定義すると、結果として生成されるトラッキング URL の動的プレビューが表示されるようになりました。 [詳細情報](../configuration/email-settings.md#url-tracking)

<!--* **Personalize tracking URL parameters** - You can now use the Expression Editor to configure URL tracking parameters in your message presets. [Learn more](../configuration/email-settings.md#url-tracking)-->

<!--
**Reporting**

* **Performance measurement** - A new **Reporting** tab is now available in the Administration > Configurations menu to set up reporting data sources.
-->
