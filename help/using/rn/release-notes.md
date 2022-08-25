---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 711fdf1dce0688d2e21d405a4e3e8777612b2f3b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 50%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022年8月リリース {#aug-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>Journey Optimizerでのキャンペーンの作成と管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerキャンペーンを使用すると、様々なチャネルを使用して、特定のセグメントに 1 回限りのコンテンツを配信できます。 ジャーニーを使用する場合、アクションは順番に実行されるように設計されています。 キャンペーンでは、アクションは即座に、または指定したスケジュールに基づいて、同時に実行されます。 </p>
<img src="assets/do-not-localize/campaigns.gif"/>
<p>キャンペーンを作成する方法を学ぶ <a href="../campaigns/get-started-with-campaigns.md">詳細なドキュメント</a>.
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ユーザーに SMS を送信する（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><b>Sinch</b> または <b>Twilio</b> との統合を使用して、Journey Optimizer で SMS の作成、パーソナライズおよび送信ができるようになりました。</p>
<img src="assets/do-not-localize/SMS.gif"/>
<p>SMS の作成および送信方法については、この<a href="../messages/create-sms.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>New Dynamic Expression Builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create conditional content blocks across different authoring services to personalize your content.</p>
<p>In addition to the Personalization Expression Library, the Expression Editor provides a new Conditional Rule Builder to help you design and save your content blocks.</p>
<p>For more information, refer to the <a href="../building-journeys/read-segment.md#configuring-segment-trigger-activity">detailed documentation</a>.
</td>
</tr>
</tbody>
</table-->



### 機能強化

**レポーティング**

* 同意ポリシーのテーブルとグラフがジャーニーのグローバルレポートで使用できるようになりました。 これらのウィジェットを使用すると、カスタムアクションのポリシーから除外されたプロファイルを追跡できます。 [詳細情報](../reports/journey-global-report.md#journey-global)

   最新のウィジェットにアクセスするには、別のレポートダッシュボードをリセットする必要があります。 ダッシュボードのカスタマイズについて詳しくは、 [詳細なドキュメント](../reports/global-report.md).

**管理**

* SMS チャネルで使用するプライマリ電話番号を更新できるようになりました。 [詳細情報](../configuration/primary-email-addresses.md)