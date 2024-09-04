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
source-git-commit: 428e08ca712724cb0b3453681bee1c7e86ce49dc
workflow-type: ht
source-wordcount: '325'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年8月早期リリースノート {#e-2024}

**リリース日**：2024年8月20日～21日（PT）

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>コンテンツフラグメントの変数</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>フラグメントは、<a href="../personalization/use-expression-fragments.md">式フラグメント</a>と<a href="../email/use-visual-fragments.md">ビジュアルフラグメント</a>の両方で入力変数を使用できるようになりました。これらの変数を使用すると、キャンペーンとジャーニーで、メッセージのコンテンツとパラメーターをパーソナライズできます。</p>
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
<p>公開日：8月13日（PT）</p>
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

* **条件**&#x200B;アクティビティでは、デフォルトで、時間条件が 00:00 から 12:00 までの時間単位で設定されるようになりました。[詳細情報](../building-journeys/condition-activity.md#time_condition)
* ジャーニーを作成する際に、アラートがドロップダウンリストに表示されるようになり、キャンペーンアラートに合わせて一貫したユーザーエクスペリエンスを実現します。[詳細情報](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* ジャーニーツールバーのズームオプションが改善されました。ズームの割合が表示され、ズーム値を簡単に 100％にリセットできるようになりました。

**オーディエンス**

* カスタムアップロード（CSV ファイル）からのオーディエンスを、プライバシーとセキュリティシールドで使用できるようになりました。
* カスタムアップロード（CSV ファイル）オーディエンスをターゲティングする際に、キャンペーンとジャーニーでファイルの属性を使用できるようになりました。これらの属性は、メッセージをパーソナライズするためのパーソナライゼーションエディターと、ジャーニーの高度な式エディターで使用できます。


<!--
**Push channel**

* You can now add your mobile application push credentials inside Adobe Journey Optimizer channel configuration settings. Creating an App surface in Adobe Experience Platform Data Collection is no longer required.-->

<!--* The `event-id` condition is now automatically filled during test mode. -->

<!--**SMS channel**

* You can now modify existing SMS configurations.-->

<!--
**In-app channel**

* Expression fragments are now available for the In-app channel.-->
