---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizerのプレリリースノート
description: Adobe Journey Optimizerのプレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 3a44111345c1627610a6b026d7b19b281c4538d3
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 46%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下のプレリリースノートは、リリースの公開日まで予告なく変更される場合があります**。 リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。


## 2025 年 8 月のプレリリースノート {#25-7-rn}

**以下のプレリリースノートは、リリースの公開日まで予告なく変更される場合があります**。 リンク、画面、更新済みのドキュメントは、リリース日に公開されます。

[Adobe Experience Platformのプレリリースノート ](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"} も参照してください。

**リリース日**：2025年8月19日（PT）


### 新機能 {#Aug-25-8-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>ジャーニーの一時停止と再開</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを一時停止して再開できるようになりました。この機能により、顧客体験を止めずにライブジャーニーを一時中断できるので、ジャーニー実務担当者はより優れた制御と柔軟性を得ることができます。一時停止すると、通信は送信されず、ジャーニーが再開されるまでプロファイルは中断状態のままになります。</p>
<p>1 つのジャーニーのみを一時停止および再開することや、ジャーニーのグループに対して一括で一時停止および再開の操作を実行することができます。</p>
<p>さらに、一時停止したジャーニーにグローバルフィルターを適用して、属性に基づいてプロファイルを除外できます。</p>
<img src="assets/do-not-localize/PauseResume.gif">
<p>以前は一部のお客様のみが利用できましたが（限定提供）、この機能はすべての環境で利用できるようになりました（一般提供）。</p>
<p>詳しくは、<a href="../building-journeys/journey-pause.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>



<table>
<thead>
<tr>
<th><strong>カレンダー表示</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーとキャンペーンのリストでカレンダー表示を使用できるようになりました。これにより、すべてのジャーニーとキャンペーンのアクティベーションをそれぞれのリストで視覚化できます。</p>
<p>以前は限定提供（LA）で提供されていましたが、現在はすべての環境でこの機能を利用できます。 この一般提供リリースでは、この機能には次のものが含まれます。</p>
<ul>
<li>日付でのナビゲーションのデザインの改善</li>
<li>開始日と終了日を設定した場合に、ドラフトキャンペーンを表示する機能</li>
<li>実行されているカレンダー項目の表示/非表示を長時間切り替える新しい設定</li>
</ul>
<img src="assets/do-not-localize/calendar.gif">
<p>詳しくは、<a href="../building-journeys/journey-ui.md#journeys-calendar"> 詳細ドキュメント </a> を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>E メールデザイナーでのダークモード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey OptimizerのメールDesignerで、ダークモード表示に切り替える機能が追加されました。この機能を使用すると、ダークモードでメールを読む受信者にのみ表示される特定のカスタム設定を定義できます。</p>
<p>次のことに注意してください。</p>
<ul>
<li>ダークモードの最終レンダリングは、受信者のメールクライアントによって異なる場合があります。</li>
<li>すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。さらに、一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードのみが適用されます。どちらの場合も、E メールデザイナーで定義したカスタム設定はレンダリングできません。</li>
</ul>
<P>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>詳しくは、<a href="../email/dark-mode.md">詳細なドキュメント</a>を参照してください。 </p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>キャンペーンの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、ツールを使用して、キャンペーンのオーディエンスにパーソナライズされ最適化されたコンテンツを提供できるようになりました。これにより、コンテンツ実験の実行、ルールベースのターゲティングの作成、および両方の高度な組み合わせの使用が、キャンペーンの効果を最大限に高めることができます。</p>
<p>最適化を使用すると、次のことができます。</p>
<ul>
<li>複数のコンテンツのバリエーションをテストして、最も効果的なメッセージを特定します。</li>
<li>ユーザー属性とコンテキストデータに基づいてパーソナライズされたコンテンツを配信します。</li>
<li>高度なキャンペーン戦略のために、ターゲティングと実験を組み合わせます。</li>
<li>バリアント条件に一致しないユーザーをフィルターで除外します。</li>
<li>ユーザーエンゲージメントを維持するためのフォールバックメカニズムを確認します。</li>
</ul>
<P>キャンペーンがライブになると、プロファイルは定義された条件に照らして評価され、一致条件に基づいて、キャンペーンの適切なエクスペリエンスまたはコンテンツで配信されます。</p>
<p><img src="assets/do-not-localize/campaign-optimization.gif"/></p>
<!--p>For more information, refer to the <a href="../FILE.md">detailed documentation</a></p-->
</td>
</tr>
</tbody>
</table>

### 機能強化 {#Aug-25-8-improv}

このリリースに含まれる機能強化を以下に示します。