---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
hide: true
hidefromtoc: true
source-git-commit: 0ed72b947c176b54220b5e00cdae6ccf91aac9a8
workflow-type: ht
source-wordcount: '343'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、すべての変更が各月の最終週にまとめられます。

以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2023年8月早期リリースノート {#aug-rn-2023}

**リリース日**：2023年8月23～24日（PT）

### 新機能{#aug-2023-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>ジャーニーでのアプリ内メッセージを送信</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニー内で、アプリユーザーにパーソナライズされたアプリ内メッセージを送信できるようになりました。Journey Optimizer を使用して通知をデザインし、メッセージのレイアウト、表示、テキストおよびボタンをカスタマイズして、シームレスなエクスペリエンスを作成します。</p>
<img src="assets/in_app_journey_1.png"/>
<p>詳しくは、<a href="../in-app/get-started-in-app.md">詳細なドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>シードリストを使用したメールの検証</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer でシードリストを作成および管理できるようになりました。シードリストに含む内部アドレスは、配信の実行時に実際のオーディエンスに追加でき、対象プロファイルとまったく同じメッセージを受け取ることができます。この機能を使用して、送信したやりとりを監視し、すべての表示形式、URL、画像、リンクが正しいことを確認します。</p>
<img src="../configuration/assets/seed-list-details.png">
<!--p>For more information, refer to the <a href="../audience/get-started-audience-orchestration.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Generate text and images with the Content assistant</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Once you have created and personalized your message, take your content to the next level with the Content assistant. You can now use the Content assistant to optimize your message's impact by experimenting with different main titles, and images. Each variant is managed as a unique Treatment, to measure and compare which title effectively generates more clicks.</p>
<p>This capability is currently available as a private beta.</p>
<img src="assets/gen-ai-image-2.png"/>
<p>For more information, refer to the <a href="../start/search-filter-categorize.md#tags">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->



### 機能強化 {#aug-2023-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**API**

コンテンツフラグメントを作成および管理するための新しい API が使用可能になりました。[詳細情報](https://developer.adobe.com/journey-optimizer-apis/references/content-templates/#tag/Content-fragment-API){target="_blank"}。

**メールチャネル**

メールサーフェス設定で、スパムの苦情により抑制されたメールアドレスをトランザクションメッセージオーディエンスに含める新しいオプションが使用可能になりました。マーケティングメッセージをスパムとしてマークした場合でも、これらのプロファイルは、パスワードのリセットやアカウントステートメントなどのトランザクションメッセージを受信する可能性があります。このオプションはデフォルトでは無効です。

**ジャーニー**

* カスタムアクションで API 呼び出し応答を活用し、これらの応答に基づいてジャーニーを調整できるようになりました。この機能は現在、Private Beta として使用可能です。
<!--* A new type of system alert has been introduced. You can now get notified when a custom action fails.
* When duplicating a journey, you can now define the name of the journey copy.-->


**ダイレクトメール**

* ファイルルーティング設定で、サーバーの種類として Azure を選択できるようになりました。
* ダイレクトメールのサーフェス設定で、列区切り記号フィールドとして、アンパサンド（&amp;）を使用できるようになりました。