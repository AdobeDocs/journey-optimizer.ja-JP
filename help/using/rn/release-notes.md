---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: d160baac2eb454cfd10097e29147562f83c1cd50
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 59%

---

# リリースノート {#release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

以前のリリースノートは、[このページ](release-notes-2022.md)にあります。 また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。


## 2023 年 2 月の早期リリースノート {#feb-2023}

この節では、プレリリース情報について説明します。 リリース日、機能などの情報は、予告なく変更されることがあります。詳細なドキュメントは、リリース日に提供される予定です。

可用性： **2023 年 2 月 23 日**

### 機能強化 {#feb-2023-improvements}

**ジャーニー**

* この **再入場待機期間** フィールドがジャーニープロパティに追加されました。 このフィールドでは、プロファイルが単一のジャーニー（イベントまたはセグメントの資格で始まる）でジャーニーに再度エントリできるようにするまでの待機時間を定義できます。 これにより、同じイベントに対してジャーニーが誤って複数回トリガーされるのを防ぎます。 デフォルトでは、このフィールドは 5 分に設定されています。

* 向けに改善が加えられました。 **ジャーニーの開始日と終了日**. 開始日を指定しなかった場合、公開時に自動的に追加されるようになりました。 の場合 **セグメントを読み取り** ジャーニーに追加する終了日を追加できるようになりました。 これにより、日付に達したプロファイルは自動的に終了します。 

* ジャーニーキャンバスが強化され、よりシンプルで改善されたユーザーエクスペリエンスが実現しました。 キャンバスの各パスの最後に、空のプレースホルダーが削除されています。 ノード間の任意の場所にアクティビティをドラッグすることで、単にアクティビティを追加できるようになりました。

* ジャーニーのタイムアウトとエラー管理が改善されました。 タイムアウトとエラーパスがキャンバスに常に追加されるようになりました。 これらのパスの表示/非表示を切り替える新しいツールバーボタンを使用できます。

* 新しいタイプのシステムアラートが導入されました。 カスタムアクションが失敗した場合に通知を受け取れるようになりました。


**管理**

* **許可リスト**  — これで、許可リストを.csv ファイルとしてダウンロードできます。

* **E メールサーフェス** - E メールの表面設定に追加のチェックが追加されました。( **返信先（E メール）アドレス** または **BCC 電子メールアドレス** が正しく設定されていない場合、e メールサーフェスを作成できなくなりました。 設定するか、別の設定を使用する必要があります。

* **E メールサーフェス** - E メールサーフェス設定の「 URL トラッキングパラメーター」セクションで、各 **値** フィールドが 255 文字から 5 KB に更新され、Adobe Analyticsのトラッキングとの互換性が確保されました。

**意思決定管理**

* **配置**  — 配置の作成画面に追加のパラメーターが追加されました。 これを使用すると、1 つのオファーを複数の配置にまたがって複製できるかどうかを制御し、オファーのコンテンツとメタデータを API 応答に含めるかどうかを指定できます。

* **URL のパーソナライゼーション** - URL をコンテンツとしてオファーの表示域に追加する場合、式エディターを使用して、これらの URL をパーソナライズできるようになりました。



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
<p>Adobe Experience Platform は、消費者レコードとデータセットをプログラムで削除することで、保存されたデータを管理できる、一連のデータハイジーン機能を提供します。この機能は、Adobe Journey Optimizer で使用できるようになりました。 </p>
<p>データストアを管理して、情報が期待どおりに使用され、必要な場合は不適切なデータの修正が更新され、組織のポリシーで必要と判断された場合は削除されるようになります。</p>
<p><strong>注意</strong> - データハイジーン機能は、現在、<strong>Healthcare Shield</strong> および<strong>プライバシーとセキュリティシールド</strong>アドオン機能を購入した組織でのみ利用できます。</p><p>詳しくは、<a href="../privacy/data-hygiene.md">詳細なドキュメント</a>を参照してください。

</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールコンテンツテンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーやキャンペーン全体で活用できるスタンドアロンのコンテンツテンプレートを作成し、すばやく再利用できるようになりました。</p> 
</p>
<img src="assets/do-not-localize/content-template.gif"/>
<p>コンテンツテンプレートを作成、編集、使用する方法については<a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/content-templates.html?lang=ja">このビデオ</a>をご覧ください。 詳しくは、 <a href="../email/content-templates.md">詳細なドキュメント</a>を参照してください。
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

* 「**セグメントの選定**」または「**セグメントの読み取り**」をジャーニーに追加すると、名前空間は、最後に使用した名前空間で、デフォルトで事前入力されるようになりました。 詳しくは、[セグメントの選定](../building-journeys/segment-qualification-events.md#about-segment-qualification)および[セグメントの読み取り](../building-journeys/read-segment.md#configuring-segment-trigger-activity)の節を参照してください。

* ジャーニーキャンバスのツールバーに新しいボタンが表示され、ジャーニーのスクリーンショットをダウンロードできます。

**電子メールデザイナー**

* **HTML を書き出し**&#x200B;メニューからメールの内容を書き出せるようになりました。書き出されたファイルは、アーカイブ（.ZIP）ファイルで使用できます。

**管理**

* 新しいサブセクションでは、**返信先（メール）**&#x200B;アドレスを作成し、適切な返信管理を行うための推奨事項を説明します。[詳細情報](../email/email-settings.md#reply-to-email)

* **IP プール**&#x200B;の作成または編集時に、関連付けられている PTR レコードが IP リストに表示され、選択した IP アドレスにカーソルを合わせると表示されるようになりました。[詳細情報](../configuration/ip-pools.md#create-ip-pool)

* チャネルサーフェスで IP プールが選択された後、IP アドレスにカーソルを合わせると、PTR レコード情報が表示されるようになりました。[詳細情報](../email/email-settings.md#subdomains-and-ip-pools)

* [PTR レコード](../configuration/ptr-records.md#edit-ptr-record)および[実行フィールド](../configuration/primary-email-addresses.md)編集用のユーザーインターフェイスが更新されました。 

* サブドメインの作成および編集用のユーザーインターフェイスが改善されました。 [詳細情報](../configuration/delegate-subdomain.md)

* 抑制リストの&#x200B;**最近のアップロード**&#x200B;画面が更新されました。[詳細情報](../configuration/manage-suppression-list.md#recent-uploads)

**キャンペーン**

* API トリガーキャンペーンを実行するためのサンプル cURL リクエストが自動生成され、キャンペーン画面で使用できるようになりました。 [詳細情報](../campaigns/api-triggered-campaigns.md)

<!--
**Decision management**

* Additional parameters have been added in placements creation screen. They allow you to control whether an offer can be duplicated across multiple placements, and to specify if the offer's content and metadata should be included in the API response. [Learn more](../offers/offer-library/creating-placements.md)-->

<!--* It is now possible to reset the offer capping counter on a daily, weekly or monthly basis. [Learn more](../offers/offer-library/add-constraints.md#capping)-->

**パーソナライゼーション**

* 新しいヘルパー関数（formatCurrency、charCodeAt、stringToDate、toString、formatNumber、toHexString）を使用できます。さらに、toDateTimeOnly 関数では、文字列、日付、長さ、整数の各フィールドタイプを受け入れるようになりました。 [詳細情報](../personalization/functions/functions.md)
