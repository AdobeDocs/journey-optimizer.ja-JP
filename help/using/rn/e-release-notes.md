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
source-git-commit: 16812ed5a3f4a4626387d7f21be91c31530eb7cc
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 23%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024 年 6 月先行リリースノート {#e-2024}

**リリース日**:2024 年 6 月 18～19 日

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
<p>新しい IP アドレスでメールを送信している場合に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。 Adobe Journey Optimizerは、最適な配信品質を得るためのベストプラクティスに従って IP アドレスをウォームアップする、標準化された効率的な方法を提供します。</p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>コンテンツフラグメントのカスタマイズとライフサイクル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>フラグメント内に特定のフィールドを定義できるようになりました。このフィールドは、フラグメントをキャンペーンまたはジャーニーに追加するときに編集できます。 これにより、使用時にコンテンツの部分を調整でき、コンテキスト固有の詳細でデフォルト値を柔軟に上書きできます。</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Journey Optimizerの AI アシスタント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、特定のAdobeのコンセプトをナビゲートして理解し、運用上のインサイトを得るために使用できるユーザーインターフェイス機能です。 Adobe Journey Optimizerを含むAdobe Experience Cloud全体の複数の製品で使用できます。</p>
<p>詳しくは、 <a href="../start/ai-assistant.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Reporting with Customer Journey Analytics (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer reporting is now fully integrated with Customer Journey Analytics capabilities, standardizing reporting across both platforms and improving data consistency and reliability. This seamless integration between Journey Optimizer and Customer Journey Analytics provides a clearer view of performance metrics, enabling users to make more informed decisions.</p>
</td>
</tr>
</tbody>
</table-->


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

* **意思決定管理でのマルチルールのサポート**  – 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

**コンテンツフラグメント**

* フラグメントを編集し、フラグメントが使用されているすべてのライブジャーニーおよびキャンペーンに変更を反映できるようになりました。
* コンテンツフラグメントの新しいステータスが導入されました。 **ドラフト**, **ライブ**, **公開中**、および **アーカイブ済み**.
* ジャーニーまたはキャンペーンでフラグメントを使用するには、フラグメントが次の場所にある必要があります。 **ライブ** ステータス。 フラグメント作成プロセスに新しい手順が追加され、フラグメントを公開して、ジャーニーやキャンペーンで使用できるようになりました。 フラグメントの公開には、新しい権限が必要になります。

  **注意**  – 以降 **ドラフト** および **ライブ** Journey Optimizerの 6 月のリリースでステータスが導入されました。このリリースより前に作成されたすべてのフラグメントには、 **ドラフト** ステータス （ジャーニーやキャンペーンで使用されている場合を含む）。 既存のフラグメントを更新する方法については、この節を参照してください。

**ジャーニー**

* ジャーニーのグローバルタイムアウトが 30 日から 91 日に増えました。
* Adobe Journey Optimizerで、プライバシーに関する削除/アクセスリクエストがサポートされるようになりました。
* ジャーニーインベントリの列のサイズを変更できるようになりました。


**キャンペーン**

* Adobe Journey Optimizerでキャンペーンを作成する際、新しいモーダルでキャンペーンのタイプ（スケジュール済みまたはトリガー済み）を選択できるようになりました。

**メールチャネル**

* **リスト – 登録解除**  – 一括送信者向けの最近の Gmail および Yahoo のお知らせに続いて、Journey Optimizerでは、「投稿/1 クリック」のリスト購読解除オプションをサポートしています。 <!--Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)-->


**SMS チャネル**

* 単一の API 設定で、各サンドボックスに一意のショートコードを追加できるようになり、プロセスの効率と合理化が向上しました。
* 既存の SMS 設定を変更できるようになりました。

**アプリ内チャネル**

* **式フラグメント**  – 式フラグメントを **アプリ内チャネル**. [詳細情報](../personalization/use-expression-fragments.md)


* これで、エッジ配信プラグインを使用して、インバウンド実装を理解し、トラブルシューティングするために必要な情報を取得できます。


