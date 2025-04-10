---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 315cd1df52018497c24da29d1b899c9662bfa576
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 75%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート ](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"} を参照してください。

## 2025年4月の更新

### 機能強化 {#25-04-improv}


* **サンドボックスツール** – 公開日：2025 年 4 月 3 日（PT）

  パッケージのエクスポート機能とインポート機能を使用して、複数のサンドボックスにわたってキャンペーンをコピーできるようになりました。 キャンペーンが、プロファイル、オーディエンス、スキーマ、インラインメッセージおよび依存オブジェクトに関連するすべての項目と共にコピーされます。 決定項目、データ使用ラベル、言語設定など、一部の項目はコピーされません。 [詳細情報](../configuration/copy-objects-to-sandbox.md)

* **Personalization** – 公開日：2025 年 4 月 2 日（PT）

  パーソナライゼーションエディターの属性ペインに、デフォルトで入力された属性のみが表示されるようになりました。 すべての属性を表示するには、「設定」ボタンを使用して「**[!UICONTROL 入力された属性のみを表示]**」オプションをオフにします。 [詳細情報](../personalization/personalization-build-expressions.md)

* **コンテンツ管理** – 公開日：2025 年 4 月 2 日（PT）

  コンテンツテンプレートとフラグメントを簡単に管理するために、フォルダーを使用して、より効果的に構造化された階層に整理できるようになりました。 詳しくは、[コンテンツテンプレート](../content-management/access-content-templates.md#folders)および[フラグメント](../content-management/manage-fragments.md#folders)の節を参照してください。

  >[!AVAILABILITY]
  >
  >この機能強化は、一連の組織のみが使用できます（限定提供）。

* **メールDesigner** – 公開日：2025 年 4 月 1 日（PT）

  Journey Optimizerのアクセシビリティを強化するために、メールDesignerで 2 つの新しいフィールドが使用できるようになりました。これらは、メールコンテンツの `<title>` 要素および `<html>` 要素の `lang` 属性に対応しています。 これらの設定は、「**[!UICONTROL プリヘッダー]**」フィールドに加えて、「メール **[!UICONTROL 本文]**」セクションで定義できます。 [詳細情報](../email/email-metadata.md)


## 2025年3月リリースノート {#25-3-rn}


### 新機能 {#25-03-features}

このリリースに含まれる新機能を以下に示します。

<!--table>
<thead>
<tr>
<th><strong>Integration with Adobe Express (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Adobe Express integration in Adobe Journey Optimizer lets you use Adobe Express's editing tools directly during content creation, enabling you to resize, remove backgrounds, crop, and convert assets to JPEG or PNG.<p>
<p>Adobe Express integration in Adobe Journey Optimizer is currently only available for a set of organizations (Limited Availability). It cannot be deployed for use with Healthcare Shield or Privacy and Security Shield.</p>
<p>For more information, refer to the <a href="../integrations/express.md">detailed documentation</a>.</p>
</br>
<img src="assets/do-not-localize/express_resize.gif"/>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Journey metrics</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey metrics are now available, allowing you to measure the impact of your activities across the key metrics of your business and to provide clearer insights into your performance.</p>
<p>For more information, refer to the <a href="../building-journeys/success-metrics.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/success-metric.gif"/>
</td>
</tr>
</tbody>
</table-->

<!-- table>
<thead>
<tr>
<th><strong>Calendar view for journeys (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A calendar view is now available in Journey Optimizer to visualize all journeys activations. From this view, you can browse your journeys and check details and properties.<p>
<p>This change is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../configuration/rule-sets.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Dynamic Media との統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Dynamic Media アセットが Journey Optimizer で直接使用可能になり、アクセスできるようになりました。この統合により、次のことを実行できます。
<ul>
<li>リアルタイム更新でアセットを一元管理</li>
<li>幅や高さなどのアセット設定を即座に変更</li>
<li>コンテンツを更新し、パーソナライゼーションフィールドを追加して、Dynamic Media テンプレートをカスタマイズ</li>
</ul>
<p>
<p>この統合は、一連の組織のみが使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../integrations/aem-dynamic.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Adobe GenStudio との統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>マーケティング効率を高め、ブランドの一貫性を維持するために、パフォーマンスマーケティングエクスペリエンス用の GenStudio を Journey Optimizer とシームレスに統合できるようになりました。これにより、GenStudio の AI を活用したコンテンツ作成と Journey Optimizer の高度なオーケストレーション機能を活用できるようになります。<p>
<p>Journey Optimizer での GenStudio 統合は、現在、Healthcare Shield またはプライバシーとセキュリティシールド（限定提供）では使用できません。</p>
<p>詳しくは、 <a href="../integrations/genstudio.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/genstudio.gif"/>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>LINE channel (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer has expanded its cross-channel capabilities to include support for the LINE channel. This enhancement allows you to create, edit, and preview LINE experiences enabling more personalized and engaging interactions. With LINE, you can connect with more customers, send relevant content, and improve your engagement.<p>
<p>This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../configuration/rule-sets.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


### 機能強化 {#25-03-improv}

**パーソナライゼーションエディター**（公開日：3月12日（PT））

Journey Optimizer パーソナライゼーションエディターが更新され、新しい機能が追加されました。
* **コードエディターのデザインの更新** - 操作性と焦点を向上させる、よりクリーンで最新のインターフェイス。
* **検索と置換** - エディター内でコンテンツをすばやく検索して置換する機能が追加されました。
* **取り消しとやり直しのサポート** - 変更を簡単に元に戻したり、再適用したりできます。
* **カスタマイズ可能なフォントサイズ** - 読みやすくなるように、エディターのフォントサイズを調整できます。
* **インライン JSON 検証** - エラー検出を高速化するには、JSON コンテンツに対してリアルタイムのクライアントサイド検証を提供します。
* **プロファイル属性とコンテキスト属性のオートコンプリート** - コンテンツ作成を効率化するスマートな候補を表示します。
* **構文のハイライト表示の強化** - コード構造をより視覚的に区別することで、読みやすさを向上します。

![パーソナライゼーションエディターの新機能を示すビデオ](assets/do-not-localize/personalization-editor.gif)

詳しくは、[詳細なドキュメント](../personalization/personalization-build-expressions.md)を参照してください。

**承認**

承認ポリシーの条件を定義する際に、タグやオブジェクトカテゴリでフィルタリングするオプションが追加されました。

詳しくは、[詳細なドキュメント](../test-approve/approval-policies.md)を参照してください。

**設定**

* Adobe Experience Platform 統合タグをチャネル設定に割り当てることができるようになりました。これにより、簡単に分類し、すべてのリストでの検索とナビゲーションを改善できます。[詳細情報](../configuration/channel-surfaces.md#channel-config-tags)

* Journey Optimizer でメールサブドメインを設定または編集する際に、親ドメインで使用可能な場合は、関連付けられた DMARC レコードを独自に管理することを選択できるようになりました。[詳細情報](../configuration/dmarc-record.md#set-up-dmarc)

**ビジネスルール**

バッチセグメント化を使用したジャーニーとキャンペーンで、毎日のフリークエンシーキャップを使用できるようになりました。毎日のフリークエンシーキャップルールの正確性を確保するには、キャンペーンまたはジャーニーを作成する際に、最も優先度の高い名前空間を選択します。名前空間の優先度について詳しくは、[Platform ID サービスガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"} を参照してください

ルールセットでの毎日のフリークエンシーキャップは、一連の組織のみが使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。

ビジネスルールについて詳しくは、[詳細なドキュメント](../configuration/rule-sets.md)を参照してください。

<!--**Deliverability**

You can now choose to have your emails relayed to your SMTP servers instead of being sent directly from Journey Optimizer to ISPs. This allows you to route final email deliveries through your own Mail Transfer Agents and IPs, or to perform final validations on the emails before sending them to your recipients. The SMTP relay capacity is available on demand - contact your Adobe representative.-->


