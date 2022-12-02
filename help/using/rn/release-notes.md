---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 3a932747de33ced59d68835a96386b7ac560e4fe
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 100%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。


## 2022年10月リリース {#oct-2022-release}

<!--

### New capability{#oct-2022-features}

<table>
<thead>
<tr>
<th><strong>Direct Mail Channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add direct mail messages in your campaigns and journeys. Direct mail is an offline channel that allows you to personalize and generate the files required by direct mail providers to send mail to your customers.</p>
<p>When you prepare a direct mail delivery, Journey Optimizer generates a file including all the targeted profiles and the chosen contact information (postal address for example). You will then be able to send this file to your direct mail provider who will take care of the actual sending.</p>
</td>
</tr>
</tbody>
</table>

-->

### 機能強化 {#oct-2022-improvements}

**ジャーニー**

* 「**繰り返し時に再エントリを強制**」オプションを、繰り返しのセグメント読み取りスケジュールパラメーターに追加しました。このオプションを使用すると、ジャーニーにまだ存在するすべてのプロファイルを、次回の実行時に自動的に終了させることができます。このオプションを無効にした場合、プロファイルは、別のオカレンスに再エントリする前に、ジャーニーを終了する必要があります。[詳細情報](../building-journeys/read-segment.md#configuring-segment-trigger-activity)

**管理**

* サブドメイン、ランディングページのサブドメイン、PTR レコードおよび IP プールの設定はすべてのサンドボックスに共通であるため、これらの設定のいずれかを変更すると実稼動サンドボックスにも影響することを警告するメッセージをユーザーインターフェイスに追加しました。
* 抑制リストを CSV ファイルとしてユーザーインターフェイスからアップロードする手順を変更しました。[詳細情報](../configuration/manage-suppression-list.md#download-suppression-list)

**キャンペーン**

* 完了したキャンペーンと停止したキャンペーンをアーカイブできるようになりました。[詳細情報](../campaigns/modify-stop-campaign.md#archive)
