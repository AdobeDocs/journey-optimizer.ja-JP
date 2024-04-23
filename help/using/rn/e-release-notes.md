---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
hide: true
hidefromtoc: true
source-git-commit: 63dfe9a27f8a24a1c78968fa60252e16c87abebd
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 47%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年4月先行リリースノート {#e-2024}

****&#x200B;リリース日：2024年4月30日（PT）

### 新機能 {#e-features}

このリリースでは、以下に説明する新機能が提供されています。

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

<table>
<thead>
<tr>
<th><strong>Experience Decisioning – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Experience Decisioning は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。</p>
<p>これらの決定項目は、Journey Optimizer キャンペーン内でアクセス可能になった新しいコードベースのエクスペリエンスチャネルを通じて、幅広いインバウンドサーフェスにシームレスに統合されます。</p>
<p>Experience Decisioning は現在、一連の組織でのみ使用できます（使用制限あり）。 アクセス権を取得するには、Adobe担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>

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

<table>
<thead>
<tr>
<th><strong>Infobip を使用したマルチメディアメッセージサービス（MMS）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス（MMS）メッセージを送信して通信を強化し、画像、GIF またはビデオを顧客と共有できます。この機能は、以前は Sinch でのみ使用できましたが、Infobip でも使用できるようになりました。</p>
<img src="assets/do-not-localize/mms.gif"/>
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

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

<!--
* **ExD reporting in AEP**: TBD
-->

**オーディエンス**

* Healthcare Shield およびプライバシーとセキュリティシールドで、オーディエンスコンポジションのオーディエンスと属性を使用できるようになりました。
* Healthcare Shield およびプライバシーとセキュリティシールドで、カスタムアップロード（CSV ファイル）を使用できるようになりました。

<!--
* **Experience Decisioning + Code-based experiences (LA)**: You can now leverage the Experience decisioning feature to use decision items in your code-based campaigns. Note: The Code-based experience channel and Experience decisioning are not available for organizations that have purchased the Adobe Healthcare Shield and Privacy and Security Shield add-on offerings.
-->
<!--
* **Expression Fragments supported for Web and In-App**: Expression fragments are now available for the Web and In-app channels. 
-->


<!--
* **DULE for AJO Channel Surface**: It is now possible to apply a label on certain profile attributes to restrict their usage inside a channel surface through marketing actions.
-->


<!--
* **List-Unsubscribe updates**: Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. 
-->

**意思決定管理**

* この **変更ログ** タブを使用すると、オファーまたは決定に加えられたすべての変更が表示されます。 オファーと決定に関連する変更がに表示されるようになりました **監査** メニュー。

**エクスペリエンス決定**

ベータ版から LA 版に至るまで、改善された機能を以下に示します。

* 次を使用して、決定ルールでAdobe Experience Platformのコンテキストデータを活用できるようになりました **コンテキストデータ** タブ。
* 意思決定管理リソースで、新しい「エクスペリエンス決定の管理」権限が使用できるようになりました。 Experience Decisioning に関連する権限を管理できます。
* 1 つのオファーに対して複数のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを向上させることができます。
* Experience Decisioning で特定の決定項目に対して複数のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを向上させることができます。

**ジャーニー**

* **ジャーニーデザイナーの改善**:

   * キャンバス UI が改善され、より直感的で効率的なユーザーエクスペリエンスが提供されるようになりました。
   * アクティビティは、クリック数を減らすことで、ジャーニーキャンバスをより明確に表示し、より多くの情報を提供します。

* **新しいライブレポート**：ジャーニーのレポートにアプリケーションのライブレポートからアクセスできるようになりました。 これは、ジャーニーの実行に対して多くのインサイトを提供するアプリケーションです。

**設定**

* チャネルサーフェスレベルでマーケティングアクションを選択できるようになりました。サーフェスで使用すると、顧客の環境設定に従うために、そのマーケティングアクションに関連付けられたすべての同意ポリシーが活用されます。
* チャネルサーフェスでオブジェクトレベルのアクセス制御を使用できるようになりました。

