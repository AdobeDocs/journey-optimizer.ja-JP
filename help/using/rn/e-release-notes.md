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
source-git-commit: f0b08b9cb9c12f7920e5a26a565b34b4bec8c84a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 32%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年7月早期リリースノート {#e-2024}

**リリース日**:2024 年 7 月 30～31 日

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>IP ウォームアップワークフロー（GA）</strong><br/></th>
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


<table>
<thead>
<tr>
<th><strong>任意のプロバイダーを使用した SMS チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>デフォルトのプロバイダーである Sinch、Infobip、Twilio に加え、Journey Optimizer内で追加の SMS プロバイダーを設定できるようになりました。</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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
<p>Adobe Journey OptimizerとAdobe Marketo Engageを統合して、B2B ユースケースを作成できるようになりました。 新しいカスタムアクションを使用すると、ジャーニーからMarketoにデータを取り込むことができます。</p>
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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
<!--p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p-->
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

* （利用可能：7 月 8 日（PT））イベントの設定時に高度な式エディターを利用できるようになり、より複雑な式を定義したり、イベント ID 条件で関数を使用したりできるようになりました。 [詳細情報](../event/about-creating.md#adv-exp-editor)

<!--* The `event-id` condition is now automatically filled during test mode. -->

**SMS チャネル**

* 既存の SMS 設定を変更できるようになりました。

**アプリ内チャネル**

* アプリ内チャネルで式フラグメントを使用できるようになりました。

**プッシュチャネル**

* モバイルアプリケーションのプッシュ資格情報をAdobe Journey Optimizer チャンネル設定内に追加できるようになりました。 Adobe Experience Platform Data Collection でのアプリサーフェスの作成は不要になりました。

**オーディエンス**

* オーディエンスコンポジションとカスタムアップロード（CSV ファイル）のオーディエンスと属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。