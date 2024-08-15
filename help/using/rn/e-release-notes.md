---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 128a56b543f470bf967fd195fde73ff7b32b2a17
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 33%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年8月早期リリースノート {#e-2024}

**リリース日**:2024 年 8 月 20～21 日

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>ガイド付きチャネル設定</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ガイド付きチャネル設定を使用すると、統合されたエクスペリエンスでモバイルチャネルの設定手順を自動化して、Journey Optimizerをより迅速に開始できます。 この設定により、マーケティングチャネルの迅速な設定が容易になり、必要なすべてのリソースがExperience Platform、Journey Optimizerおよびデータ収集ですぐに使用できるようになります。 これにより、マーケティングチームはキャンペーンとジャーニーの作成をすぐに開始できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コンテンツカード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>コンテンツカードは、Adobe Journey Optimizerの新しいデジタルメッセージ機能であり、パーソナライズされた魅力的なコンテンツをモバイルアプリや web サイト内で直接配信します。 従来のプッシュ通知とは異なり、コンテンツカードはユーザーインターフェイスにシームレスに統合され、ユーザーインタラクションとエクスペリエンスを向上させる、永続的で非割り込み型のアップデートを提供します。</p>
<p>この機能を使用すると、マーケターは、関連性の高いリッチメディアコンテンツをユーザーに提示できるため、ユーザージャーニーを中断することなくエンゲージメントを向上させ、重要なメッセージを確実に確認できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>チャネル設定の改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在のチャネルサーフェス機能が強化され、すべてのチャネルで一貫したアプローチが可能になりました。 任意のチャネルでこれらの設定を定義、管理および再利用できるようになりました。</p>
<p><ul>
<li>チャネルサーフェスの名前が <strong> チャネル設定 </strong> に変更されました</li>
<li>チャネル設定インベントリから、web、アプリ内メッセージ、コードベースのエクスペリエンスなど、すべてのチャネルに対して再利用可能なチャネル設定を作成できるようになりました</li>
<li>オブジェクトレベルのアクセス制御（OLAC）がチャネル設定ごとに使用できるようになり、特定の設定を作成または使用できるユーザーを決定できるようになりました</li>
<li>一部のチャネルでは、複数のプラットフォームをターゲットとするチャネル設定を作成できます。 例えば、web ページ、iOS アプリ、Android アプリをターゲットにできるアプリ内メッセージチャネル設定が考えられます。</li>
</ul></p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


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
<p>フラグメントは、<a href="../personalization/use-expression-fragments.md"> 式フラグメント </a> と <a href="../email/use-visual-fragments.md"> ビジュアルフラグメント </a> の両方で入力変数を使用できるようになりました。 これらの変数を使用して、キャンペーンやジャーニーでメッセージのコンテンツやパラメーターをパーソナライズできます。</p>
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
<p>公開日：8 月 13 日（PT）</p>
<p>新しい IP アドレスでメールを送信する際に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。Adobe Journey Optimizer は、標準化された効率的な方法で、最適な配信品質を実現するためのベストプラクティスに従って IP アドレスをウォームアップします。</p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Extended personalization data - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now lookup and fetch data values within Adobe Experience Platform datasets, and use these values to build conditions in Adobe Journey Optimizer. You can leverage data from a lookup dataset when a relationship has been defined using an attribute inside of an array of objects. You can specify non-profile enabled datasets for lookup. Once enabled, you can use a profile attribute as a join key to the specified dataset to retrive further data for personalization.</p>
<p>This capability is currently available as a public beta.</p>
</td>
</tr>
</tbody>
</table-->

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**ジャーニー**

* **条件** アクティビティでは、デフォルトで、時間条件が 00:00 から 12:00 の時間別に設定されるようになりました。 [詳細情報](../building-journeys/condition-activity.md#time_condition)
* ジャーニーを作成する際に、キャンペーンアラートと連携して一貫したユーザーエクスペリエンスを実現するために、アラートがドロップダウンリストに表示されるようになりました。 [詳細情報](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* ジャーニーツールバーのズームオプションが改善されました。ズーム率が表示され、ズーム値を 100% に簡単にリセットできるようになりました。

**オーディエンス**

* カスタムアップロード（CSV ファイル）からのオーディエンスを、プライバシーとセキュリティシールドで使用できるようになりました。
* カスタムアップロード（CSV ファイル）オーディエンスをターゲティングする際に、キャンペーンおよびジャーニーでファイルの属性を使用できるようになりました。 これらの属性は、パーソナライゼーションエディター、メッセージのパーソナライズ、ジャーニーの高度な式エディターで使用できます。

<!--
**Push channel**

* You can now add your mobile application push credentials inside Adobe Journey Optimizer channel configuration settings. Creating an App surface in Adobe Experience Platform Data Collection is no longer required.-->

<!--* The `event-id` condition is now automatically filled during test mode. -->

<!--**SMS channel**

* You can now modify existing SMS configurations.-->

<!--
**In-app channel**

* Expression fragments are now available for the In-app channel.-->
