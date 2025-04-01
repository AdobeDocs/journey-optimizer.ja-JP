---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 48ef8d42057ffe51c27221c2176192d4e637fb96
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 41%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。


## 2025 年 3 月リリースノート {#25-3-rn}


### 新機能 {#25-03-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>Adobe Expressとの統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey OptimizerのAdobe Express統合により、コンテンツの作成時に直接Adobe Expressの編集ツールを使用して、アセットのサイズ変更、背景の削除、切り抜き、JPEGまたは PNG への変換を行うことができます。<p>
<p>Adobe Journey OptimizerのAdobe Express統合は現在、一連の組織でのみ使用できます（使用制限あり）。 Healthcare Shield またはプライバシーとセキュリティシールドで使用するためにデプロイすることはできません。</p>
<p>詳しくは、<a href="../integrations/express.md">詳細なドキュメント</a>を参照してください。</p>
</br>
<img src="assets/do-not-localize/express_resize.gif"/>
</td>
</tr>
</tbody>
</table>


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
<p>Dynamic Media アセットをJourney Optimizerで直接使用およびアクセスできるようになりました。 この統合により、次のことが可能になります。
<ul>
<li>リアルタイムのアップデートによるアセットの一元管理</li>
<li>幅や高さなどのアセット設定を即座に変更</li>
<li>コンテンツを更新し、パーソナライゼーションフィールドを追加して、Dynamic Media テンプレートをカスタマイズします</li>
</ul>
<p>
<p>この統合は、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../integrations/aem-dynamic.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>Adobe GenStudioとの統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>GenStudio for Performance MarketingのエクスペリエンスをJourney Optimizerとシームレスに統合して、マーケティング効率を高め、ブランドの一貫性を保つことができるようになりました。 これにより、GenStudioの高度なオーケストレーション機能と共に、Journey Optimizerの AI 機能を活用してコンテンツを作成できます。<p>
<p>Journey OptimizerのGenStudio統合は、現在、Healthcare Shield または Privacy and Security Shield （限定提供）で使用できません。</p>
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

**Personalization エディター** （公開日：3 月 12 日（PT））

Journey Optimizer パーソナライゼーションエディターが更新され、新しい機能が追加されました。
* **コードエディターのデザインの更新** - 操作性と焦点を向上させる、よりクリーンで最新のインターフェイス。
* **検索と置換** - エディター内でコンテンツをすばやく検索して置換する機能が追加されました。
* **取り消しとやり直しのサポート** - 変更を簡単に元に戻したり、再適用したりできます。
* **カスタマイズ可能なフォントサイズ** - 読みやすくなるように、エディターのフォントサイズを調整できます。
* **インライン JSON 検証** - エラー検出を高速化するには、JSON コンテンツに対してリアルタイムのクライアントサイド検証を提供します。
* **プロファイル属性とコンテキスト属性のオートコンプリート** - コンテンツ作成を効率化するスマートな候補を表示します。
* **構文のハイライト表示の強化** - コード構造をより視覚的に区別することで、読みやすさを向上します。

![Personalization エディターの新機能を示すビデオ ](assets/do-not-localize/personalization-editor.gif)

詳しくは、[詳細なドキュメント](../personalization/personalization-build-expressions.md)を参照してください。

**承認**

承認ポリシーの条件を定義する際に、タグまたはオブジェクトカテゴリ（あるいはその両方）でフィルタリングできるようになりました。

詳しくは、[詳細なドキュメント](../test-approve/approval-policies.md)を参照してください。

**設定**

* Adobe Experience Platform統合タグをチャネル設定に割り当てることができるようになりました。 これにより、アセットを簡単に分類し、すべてのリストで検索とナビゲーションを改善できます。 [詳細情報](../configuration/channel-surfaces.md#channel-config-tags)

* Journey Optimizerでメールサブドメインを設定または編集する際に、関連するDMARC レコードを親ドメインで利用できる場合、自分で管理できるようになりました。 [詳細情報](../configuration/dmarc-record.md#set-up-dmarc)

**業務方法書**

バッチセグメント化を使用したジャーニーとキャンペーンで、毎日のフリークエンシーキャップを使用できるようになりました。 毎日のフリークエンシーキャッピングルールの精度を確保するには、キャンペーンまたはジャーニーのオーサリング時に、最も優先度の高い名前空間を選択してください。 名前空間の優先度について詳しくは、[Platform ID サービスガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/namespace-priority){target="_blank"} を参照してください

ルールセットの 1 日のフリークエンシーキャップは、一連の組織（使用制限あり）でのみ使用できます。 アクセスするには、アドビ担当者にお問い合わせください。

ビジネスルールについて詳しくは、[ 詳細ドキュメント ](../configuration/rule-sets.md) を参照してください。

<!--**Content management**

To easily manage your fragments and your content templates, you can now use folders to organize them more effectively into a structured hierarchy. This improvement is only available for a set of organizations (Limited Availability). <!--To gain access, contact your Adobe representative.

**Deliverability**

You can now choose to have your emails relayed to your SMTP servers instead of being sent directly from Journey Optimizer to ISPs. This allows you to route final email deliveries through your own Mail Transfer Agents and IPs, or to perform final validations on the emails before sending them to your recipients. The SMTP relay capacity is available on demand - contact your Adobe representative.-->


