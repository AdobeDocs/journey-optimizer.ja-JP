---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
hide: true
hidefromtoc: true
topic: Content Management
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 6c4e0418776622467e7f5b7bb3d9332d965becf1
workflow-type: ht
source-wordcount: '434'
ht-degree: 100%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年6月先行リリースノート {#e-2024}

**リリース日**：2024年6月18～19日（PT）

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>IP ウォームアップワークフロー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい IP アドレスでメールを送信する際に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。Adobe Journey Optimizer は、標準化された効率的な方法で、最適な配信品質を実現するためのベストプラクティスに従って IP アドレスをウォームアップします。</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<!--<table>
<thead>
<tr>
<th><strong>Content Fragments customization</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define specific fields in a fragment that can be edited when the fragment is added to a campaign or journey. This allows for the adjustment of content portions at the time of use, providing flexibility to override default values with context-specific details.</p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->


<table>
<thead>
<tr>
<th><strong>Adobe Journey Optimizer の AI アシスタント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、アドビのコンセプトをナビゲートして理解し、特定の環境の運用上のインサイトを得るために使用できるユーザーインターフェイス機能です。Adobe Journey Optimizer を含む Adobe Experience Cloud 全体の複数の製品で使用できます。</p>
<p>詳しくは、 <a href="../start/ai-assistant.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>





<!--table>
<thead>
<tr>
<th><strong>Multilingual messages in journeys and campaigns  (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now effortlessly create content in multiple languages within a single campaign or journey. With this feature, you can switch between languages when editing your campaign or your journey, streamlining the entire editing process and improving your capability to efficiently manage multilingual content.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Experimentation in journeys (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Already available in campaigns, Adobe Journey Optimizer now supports experiments in journeys. Experiments are randomized trials, which in the context of online testing, means that you expose some randomly selected users to a given variation of a message, and another randomly selected set of users to some other variation or treatment. After exposure, you can then measure the outcome metrics you are interested in, such as opens of emails, subscriptions, or purchases.</p>
</td>
</tr>
</tbody>
</table-->



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


**意思決定管理**

* **意思決定管理でのマルチルールのサポート** - 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

<!--**Content fragments**

* Fragments can now be edited, and changes can be propagated across all live journeys and campaigns where they are used.
* New statuses for content fragments have been introduced: **Draft**, **Live**, **Publishing**, and **Archived**. 
* To use a fragment in a journey or campaign, it must now be in the **Live** status. A new step has been added to the fragment creation process, allowing the fragment to be published and made available for use in journeys and campaigns. Note that fragment publishing requires a new permission.
   
   **CAUTION** - Since **Draft** and **Live** statuses have been introduced with Journey Optimizer June release, all fragments created before this release have the **Draft** status, even if they are used in a journey or campaign. Learn how to update your existing fragments in this section.-->

**ジャーニー**

* ジャーニーのグローバルタイムアウトが 30 日から 91 日に延長されました。
* Adobe Journey Optimizer は、プライバシーの削除／アクセスリクエストと、データライフサイクル管理リクエストもサポートするようになりました。
* ジャーニーインベントリの列のサイズを変更できるようになりました。
* **イベント設定の高度な式エディター**（GA）- イベントを設定する際に高度な式エディターを活用できるようになり、より複雑な式を定義したり、イベント ID 条件で関数を使用したりできるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。<!--[Read more](../event/about-creating.md)-->
* **結合ポリシー**（GA）- ジャーニーで使用される結合ポリシーがジャーニー全体で表示され、一貫性が保たれるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。<!--[Read more](../building-journeys/journey-gs.md#merge-policies)-->



**キャンペーン**

* Adobe Journey Optimizer でキャンペーンを作成する際、新しいモーダルでキャンペーンのタイプ（スケジュール済みまたはトリガー済み）を選択できるようになりました。

<!--**Email channel**

* **List-unsubscribe** - Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)-->


**SMS チャネル**

* 1 回の API 設定で各サンドボックスに一意のショートコードを追加できるようになりました。これにより、プロセスが合理化され、効率が上がります。
  <!--* You can now modify existing SMS configurations.-->

**アプリ内チャネル**

* **式フラグメント** - 式フラグメントを&#x200B;**アプリ内チャネル**&#x200B;で利用できるようになりました。<!--[Read more](../personalization/use-expression-fragments.md)-->


* これで、Edge Delivery プラグインを使用して、インバウンド実装を理解し、トラブルシューティングに必要な情報を取得できます。
