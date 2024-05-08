---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 61%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## を更新 {#may-updates}

**実施可能日**: 2024 年 5 月 7 日（PT）

<table>
<thead>
<tr>
<th><strong>エクスペリエンス決定 – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experience Decisioning は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。</p>
<p>これらの決定項目は、新しいコードベースのエクスペリエンスチャネルを通じて様々なインバウンドサーフェスにシームレスに統合され、Journey Optimizer キャンペーン内でアクセスできるようになりました。 エクスペリエンス決定決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。</p>
<p>エクスペリエンス決定は、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/gif-exd.gif"/>
<p>詳しくは、<a href="../experience-decisioning/gs-experience-decisioning.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

ベータ版から LA まで、次の改善が追加されました。

* **Experience Decisioning + コードベースエクスペリエンス（LA）**:Experience Decisioning 機能を活用して、コードベースのキャンペーンで決定項目を使用できるようになりました。 メモ：Adobeの Healthcare Shield およびプライバシーとセキュリティシールド アドオン機能を購入した組織では、コードベースのエクスペリエンスチャネルとエクスペリエンス決定は使用できません。 [詳細情報](../code-based/get-started-code-based.md)
* 決定ルールとランキング式で、Adobe Experience Platformのコンテキストデータを活用できるようになりました。 [詳細情報](../experience-decisioning/context-data.md)
* 意思決定管理リソースで、新しい「エクスペリエンス決定の管理」権限を利用できるようになりました。Experience Decisioning に関連する権限を管理できます。 [詳細情報](../experience-decisioning/gs-experience-decisioning.md)
* エクスペリエンス決定で特定の決定項目に対して、複数のキャッピングルールを追加できるようになりました。これにより、オファーの送信方法に対する制御レベルを高めることができます。 [詳細情報](../experience-decisioning/items.md#capping)
* を使用して、Experience Decisioning キャンペーンのカスタムレポートダッシュボードを作成できるようになりました [!DNL Customer Journey Analytics]. [詳細情報](../experience-decisioning/cja-reporting.md)

## 2024年4月リリースノート {#apr-2024}

**リリース日**：2024年5月2日（PT）

### 新機能 {#apr-features}

<!--table>
<thead>
<tr>
<th><strong>Business rules - Private Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>It is now possible to create and apply rule sets to your marketing communications.  </p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Personalization - Local Lookups - Multi-Entity Support - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>TBD</p>
</td>
</tr>
</tbody>
</table-->

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>マルチメディアメッセージサービス（MMS）- すべてのプロバイダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス（MMS）メッセージを送信して通信を強化し、画像、GIF またはビデオを顧客と共有できます。当初は Sinch でのみ利用可能でしたが、MMS は Infobip と Twilio でも利用できるようになりました。</p>
<img src="assets/do-not-localize/mms.gif"/>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーデザイナーとライブレポートの改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このリリースでは、ジャーニーのキャンバスユーザーインターフェイスが改善され、より直感的で効率的なユーザーエクスペリエンスを実現します。クリック数を減らすことで、ジャーニーキャンバスでアクティビティがより明確になり、より多くの情報が表示されます。</p>
<img src="assets/new-canvas3.gif"/>
<p>ジャーニーキャンバスデザインの改善に加えて、過去 24 時間のレポート指標をジャーニーキャンバスで直接確認できる機能を導入します。 </p>
<img src="assets/new-canvas6bis.png"/>
<p><strong>メモ</strong>：これらの変更は、4 月のリリース以降、すべての環境に徐々に展開されます。</p>
<p>詳しくは、 <a href="new-canvas.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!-- table>
<thead>
<tr>
<th><strong>AI Assistant - Experience Variant Generation - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Once you have created and personalized your message, take your content to the next level with the AI assistant. You can now use the AI assistant to optimize your message's impact by experimenting with different main titles, and images. Each variant is managed as a unique Treatment, to measure and compare which title effectively generates more clicks.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>IP Warmup Workflow - LA</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now easily perform IP warmup workflows directly from the Journey Optimizer interface in a standardized and efficient way that follows the best practices for optimal deliverability.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Email Surface Personalization - Private beta </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define dynamic subdomains and personalized header parameters when creating email channel surfaces, for increased flexibility and control over your email settings.</p>
</td>
</tr>
</tbody>
</table-->

### 機能強化 {#apr-improvements}

このリリースでは、以下に示す機能強化が含まれています。

<!--
* **Expression Fragments supported for Web and In-App**: Expression fragments are now available for the Web and In-app channels. 
-->


<!--
* **DULE for AJO Channel Surface**: It is now possible to apply a label on certain profile attributes to restrict their usage inside a channel surface through marketing actions.
-->


<!--
* **List-Unsubscribe updates**: Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. 
-->

**設定**

* チャネルサーフェスレベルでマーケティングアクションを選択できるようになりました。サーフェスで使用する場合、顧客の環境設定に従って、そのマーケティングアクションに関連するすべての同意ポリシーが活用されます。 [詳細情報](../action/consent.md#surface-marketing-actions)
* チャネルサーフェスでオブジェクトレベルのアクセス制御を使用できるようになりました。 [詳細情報](../configuration/channel-surfaces.md#create-channel-surface)
* チャネルサーフェスでリストの購読解除を有効にする際に、他のすべてのソースからの同意の管理方法に合わせて同意レベルを定義できるようになりました。 [詳細情報](../email/email-settings.md#list-unsubscribe)

**コンテンツ管理**

* すべてのチャネルのコンテンツテンプレートをシミュレートできるようになりました。 [詳細情報](../content-management/content-templates.md#test-templates)

**パーソナライゼーション**

* 新しい **toInt** ヘルパー関数は、式エディターで使用できます。 これらの型（number、double、int、long、float、short、byte、boolean、string）を整数に変換できます。 [詳細情報](../personalization/functions/math.md#to-int)
