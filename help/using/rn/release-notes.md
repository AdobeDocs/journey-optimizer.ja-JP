---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 4df89a36705fb53984ba04ba1ae2f45554e47f77
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 17%

---

# リリースノート {#release-notes}

[!DNL Adobe Journey Optimizer] 新機能、既存機能の機能強化、バグ修正を継続的に提供します。 すべての変更は、リリースノートの各月の最後の週に統合されます。

以前のリリースノートは、 [このページ](release-notes-2022.md). また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点の詳細： [Adobe Experience Platformリリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}.

![ニュースレター](../assets/do-not-localize/nl-icon.png) 新規登録 [Adobe Journey Optimizer四半期ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} 今日は、最新の製品アップデート、魅力的なストーリー、使用例、ヒントなどを四半期ごとにインボックスに直接配信します。


## 2023年1月リリース {#jan-2023-release}

### 新機能{#jan-2023-features}


<table>
<thead>
<tr>
<th><strong>データハイジーン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platformには、消費者レコードとデータセットをプログラム的に削除することで、保存されたデータを管理できる、一連のデータ衛生機能が用意されています。 この機能は、Adobe Journey Optimizerで使用できるようになりました。 </p>
<p>データストアを管理して、情報が期待どおりに使用され、不適切なデータ修正が必要な場合は更新され、組織のポリシーで必要と判断される場合は削除されるようにします。</p>
<p><strong>注意</strong>  — データ衛生機能は、現在、 <strong>医療用盾</strong> および <strong>プライバシーとセキュリティシールド</strong> アドオンサービス</p><p>詳しくは、<a href="../privacy/data-hygiene.md">詳細なドキュメント</a>を参照してください。

</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールコンテンツテンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーやキャンペーンをまたいで活用して、すばやく再利用できる、スタンドアロンのコンテンツテンプレートを作成できるようになりました。</p> 
</p>
<!--img src="assets/do-not-localize/"/-->
<p>でコンテンツテンプレートを作成、編集、使用する方法について説明します。 <a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/content-templates.html">このビデオ</a>.
<p>詳しくは、 <a href="../email/content-templates.md">詳細なドキュメント</a>を参照してください。
</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#jan-2023-improvements}

**ジャーニー**

<!--
* The **Re-entrance wait period** field has been added to the journey properties. This field allows you to define the time to wait before allowing a profile to enter the journey again in unitary journeys (starting with an event or a segment qualification). This prevents journeys from being erroneously triggered multiple times for the same event. By default the field is set to 5 minutes. [Learn more](../building-journeys/journey-gs.md#entrance)

* Improvements have been made for **journey start and end dates**. If you have not specified a start date, it is now automatically added at publication time. For **Read segment** journeys, you can now add an end date. This allows profiles to exit automatically when the date is reached. [Learn more](../building-journeys/journey-gs.md#dates)
-->

* を追加する場合 **セグメントの選定** または **セグメントを読み取り** ジャーニーでは、名前空間は、最後に使用した名前空間で、デフォルトで事前入力されるようになりました。 詳しくは、 [セグメントの選定](../building-journeys/segment-qualification-events.md#about-segment-qualification) および [セグメントを読み取り](../building-journeys/read-segment.md#configuring-segment-trigger-activity) セクション。

* ジャーニーキャンバスで、ツールバーに新しいボタンが表示され、ジャーニーのスクリーンショットをダウンロードできます。

**E メールデザイナー**

* これで、E メールコンテンツを **書き出しHTML** メニュー 書き出されたファイルは、アーカイブ (.ZIP) ファイルで使用できます。

**管理**

* 新しい節では、 **返信先（E メール）** 適切な返信管理を行う ([詳細情報](../email/email-settings.md#reply-to-email))

* 作成または編集時 **IP プール**&#x200B;に設定すると、関連付けられている PTR レコードが IP リストに表示され、選択した IP アドレスにカーソルを合わせたときに表示されるようになります。 ([詳細情報](../configuration/ip-pools.md#create-ip-pool))

* チャネルサーフェスで IP プールが選択されると、IP アドレスにカーソルを合わせたときに PTR レコード情報が表示されるようになりました。 ([詳細情報](../email/email-settings.md#subdomains-and-ip-pools))

* 編集用のユーザーインターフェイス [PTR レコード](../configuration/ptr-records.md#edit-ptr-record) および [実行フィールド](../configuration/primary-email-addresses.md) が更新されました。

* サブドメインを作成および編集する際のユーザーインターフェイスが改善されました。 ([詳細情報](../configuration/delegate-subdomain.md))

* 抑制リスト **最近のアップロード** 画面が更新されました。 [詳細情報](../configuration/manage-suppression-list.md#recent-uploads)

**キャンペーン**

* API トリガーキャンペーンを実行するためのサンプル cURL リクエストが自動的に生成され、キャンペーン画面で使用できるようになりました。 [詳細情報](../campaigns/api-triggered-campaigns.md)

<!--
**Decision management**

* Additional parameters have been added in placements creation screen. They allow you to control whether an offer can be duplicated across multiple placements, and to specify if the offer's content and metadata should be included in the API response. [Learn more](../offers/offer-library/creating-placements.md)-->

<!--* It is now possible to reset the offer capping counter on a daily, weekly or monthly basis. [Learn more](../offers/offer-library/add-constraints.md#capping)-->

**パーソナライゼーション**

* 次の新しいヘルパー関数を使用できます。formatCurrency、charCodeAt、stringToDate、toString、formatNumber、toHexString。 また、toDateTimeOnly 関数では、文字列、日付、長さ、整数の各フィールドタイプを受け入れるようになりました。 ([詳細情報](../personalization/functions/functions.md))
