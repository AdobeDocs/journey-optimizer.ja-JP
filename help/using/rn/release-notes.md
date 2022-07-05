---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: ac3c49c16a2496b3d5bc9b803589644b69c6565c
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 78%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022年6月リリース {#june-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>ユーザーへの SMS の送信（使用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><b>Sinch</b> または <b>Twilio</b> との統合を使用して、Journey Optimizer で SMS の作成、パーソナライズおよび送信ができるようになりました。</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>SMS チャネルは現在、一連の組織でのみ使用できます（使用制限があります）。 詳しくは、アドビ担当者にお問い合わせください。</p>
<p>SMS の作成および送信方法については、この<a href="../messages/create-sms.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Stock との統合による効果的な画像の迅速な検索</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Stock と Adobe Journey Optimizer 電子メールデザイナーの統合プラグインを使用すると、メッセージオーサリングで使用する画像のナビゲーション、ライセンス取得および保存を簡単に行うことができます。</br> 新しい「<b>類似のストックフォトを検索</b>」オプションを使用すると、画像の内容、カラーおよび構成に一致するストックフォトを見つけることもできます。 </p>
<img src="assets/do-not-localize/stock-rn.gif"/>
<p>詳しくは、<a href="../design/stock.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>すべてのメールでの「BCC で E メールを送信」の使用</strong><br/></th>
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

<table>
<thead>
<tr>
<th><strong>サンドボックス間でのオブジェクトのコピー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerサンドボックスから別のサンドボックスに、例えば非実稼動サンドボックスから実稼動サンドボックスに、エクスペリエンスを再作成できるようになりました。 この新しい機能は、ジャーニー全体をコピーします。ジャーニーが正しく実行するために使用するオブジェクトも含まれます。ある環境から別の環境にコピーされます。 ジャーニーに加えて、オファー、メッセージ、スキーマ、データセット、データソース、イベント、アクションなど、他のコンポーネントをコピーすることもできます。</p>
<p>詳しくは、 <a href="../building-journeys/copy-to-sandbox.md">詳細なドキュメント</a>を参照してください。
</td>
</tr>
</tbody>
</table>

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

* **HTML および JSON ファイルのサポート** - 外部の HTML ファイルと JSON ファイルを Adobe Experience Cloud アセットライブラリからオファー表示域のコンテンツにドラッグ＆ドロップできるようになりました。[詳細情報](../offers/offer-library/add-representations.md#html-json)


**メール**

* **テンプレートとして保存** - メールコンテンツをテンプレートとして保存し、他のメッセージを作成する際に再利用できるようになりました。[詳細情報](../design/email-templates.md)

<!--
**Journeys**

* **Ending a journey** - In the journey canvas, the **End** activity has been removed from the palette. End tags are now added by default at the end of each path and cannot be removed. This improvement allows better reporting of where a customer dropped out of the journey, without any action from the user.

-->

**管理**

<!--* **Allowed list in the UI** - You can now use the Journey Optimizer user interface to add new email addresses or domains to the allowed list.-->

* **トラッキング URL パラメーターのプレビュー** - メッセージプリセットを設定する際に、URL トラッキングパラメーターを定義すると、結果として生成されるトラッキング URL の動的プレビューが表示されるようになりました。[詳細情報](../configuration/email-settings.md#url-tracking)

* **メッセージプリセットの編集**  — メッセージプリセットを更新する際、処理時間は最大 3 時間に制限されるようになりました。 [詳細情報](../configuration/message-presets.md#edit-message-preset)

* **IP プールのエディション** - IP プールを更新する際、処理時間は最大 3 時間に制限されるようになりました。 [詳細情報](../configuration/ip-pools.md#edit-ip-pool)

<!--* **Personalize tracking URL parameters** - You can now use the Expression Editor to configure URL tracking parameters in your message presets. [Learn more](../configuration/email-settings.md#url-tracking)-->

<!--
**Reporting**

* **Performance measurement** - A new **Reporting** tab is now available in the Administration > Configurations menu to set up reporting data sources.
-->
