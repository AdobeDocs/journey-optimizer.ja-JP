---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 7e378cbda6ee2379a8bd795588c328cb14107aa4
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 72%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。


## 2025 年 6 月のリリースノート {#25-6-rn}

<!--
**Early release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.-->

**リリース日**：2025年6月18日（PT）

<!--See also [Adobe Experience Platform Pre Release Notes](https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}.-->

### 新機能 {#25-06-features}

このリリースに含まれる新機能を以下に示します。


<table>
<thead>
<tr>
<th><strong>RCS メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer でリッチコミュニケーションサービス（RCS）メッセージがサポートされるようになり、プロバイダーと通信事業者のサポートに応じて、次の拡張メッセージ機能が有効になります。</p>
<ul>
<li>ブランドおよび検証済みの送信者のサポート：ブランディング要素（ロゴ、送信者名など）を含む検証済みのビジネスプロファイルを使用してメッセージを送信します。</li>
<li>メッセージ配信インサイト：メッセージステータスの更新（送信済み、配信済み、読み取り済みなど）を含む詳細な配信レポートを受信します。</li>
<li>リンクトラッキング：エンゲージメント分析用として、RCS メッセージ内に URL を埋め込んで追跡します。</li>
<li>SMS へのフォールバック：プロファイルのデバイスが RCS をサポートしていない場合や、一時的に RCS 経由で未到達の場合に、SMS に自動的にフォールバックします。</li>
<li>基本的なメッセージ構成：プロバイダーのサポートに応じて、オプションのメディアとリッチ要素を使用した、テキストベースの RCS メッセージを送信します。</li>
</ul>
<p>詳しくは、<a href="../sms/sms-configuration.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>コードベースのエクスペリエンスコンテンツのフォームフィールド</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>JSON または HTML コンテンツテンプレートでは、特定の編集可能なフィールドを定義できるようになりました。これにより、技術ユーザー以外がコードを操作することなく、コードベースのエクスペリエンスチャネルオーサリング内のフォームビューでコンテンツを簡単に編集できます。<br />さらに、コードベースのエクスペリエンスコンテンツテンプレートを定義する際に、テンプレートに決定ポリシーを挿入できるようになり、再利用性と使いやすさが向上します。</p>
<img src="assets/do-not-localize/form-fields.gif">
<p>詳しくは、<a href="../code-based/code-based-form-fields.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Custom delegation method for subdomains</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>In addition to the full delegation and the CNAME method, a new subdomain configuration method is now available: the Custom delegation method, which enables you to fully own controlling and maintaining all aspects of DNS that are required for delivering, rendering and tracking messages.</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>ジャーニー内のコンテンツ決定アクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーキャンバスの専用のコンテンツ決定アクティビティを通じてパーソナライズされたオファーをジャーニーに含め、条件やカスタムアクションなどのジャーニーアクティビティで使用できるようになりました。</p>
<img src="assets/do-not-localize/content-decision.gif">
<p>この機能は、一連の組織でのみ使用でき（限定提供）、今後のリリースでグローバルにロールアウトされる予定です。</p>
<p>詳しくは、<a href="../building-journeys/content-decision.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーのドライラン</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーのドライランは、Adobe Journey Optimizer の特別なジャーニー公開モードで、ジャーニー実務担当者は実際の顧客に連絡したり、プロファイル情報を更新したりすることなく、実際の実稼動データを使用してジャーニーをテストできます。この機能により、ジャーニー実務担当者は、ジャーニーをライブで公開する前に、ジャーニーのデザインとオーディエンスのターゲティングに自身を持つことができます。</p>
<img src="assets/do-not-localize/DryRun.gif">
<p>この機能は、一連の組織でのみ使用でき（限定提供）、今後のリリースでグローバルにロールアウトされる予定です。</p>
<p>詳しくは、<a href="../building-journeys/journey-dry-run.md">詳細なドキュメント</a>を参照してください。</p>

</td>
</tr>
</tbody>
</table>

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
<p>この機能は、一連の組織でのみ使用でき（限定提供）、今後のリリースでグローバルにロールアウトされる予定です。</p>
<p>詳しくは、<a href="../building-journeys/journey-pause.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>実験の勝者を拡大</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>「実験の勝者を拡大」を使用すると、実験の勝利バリエーションをすべてのオーディエンスに自動または手動でロールアウトできます。この機能により、最もパフォーマンスの高い処理が特定されると、手動で常に監視することなく、そのリーチと効果を最大化できます。</p>
<p>詳しくは、<a href="../content-management/content-experiment.md">詳細なドキュメント</a>を参照してください。</p>
<p>リリース日：2025年6月2日（PT）</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>競合と優先順位付け</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、過剰な数のインタラクションで顧客が圧倒されるのを避けるために、キャンペーンとジャーニーの量とタイミングを管理することが不可欠です。Journey Optimizer では、以前は制限付きアクセス（LA）組織でのみ使用できた競合の管理と優先順位付けのためのツールがいくつか提供されるようになりましたが、現在は一般提供（GA）されています。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます。この一般提供リリースでは、次の機能強化が導入されました。</p>
<ul>
<li>サポートの拡張：競合管理ツールでは、オーディエンスを読み取りジャーニーに加えて、単一ジャーニーとオーディエンスの選定ジャーニーの両方がサポートされるようになりました。</li>
<li>トラブルシューティングの改善：クエリサービスで 2 つの新しいステップイベントフィールドが使用できるようになりました。これにより、プロファイルがジャーニーまたはキャンペーンから却下された理由を分析できます。</li>
<li>レポートの強化：レポートには、ジャーニーまたはキャンペーンからプロファイルを除外した特定のルールが示されるようになり、透明性が向上し、実用的なインサイトが提供されます。</li></ul>
<img src="assets/do-not-localize/gif-conflict.gif">
<p>詳しくは、<a href="../conflict-prioritization/gs-conflict-prioritization.md">詳細なドキュメント</a>を参照してください。</p>
<p>リリース日：2025年6月3日（PT）</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>意思決定のAdobe Experience Platform データセット（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前はパーソナライズ機能で使用できましたが、Adobe Experience Platform データセットを意思決定に活用できるようになりました。 これにより、決定属性の定義をデータセット内の追加データに拡張して、定期的に変更される一括更新を行うことができます。属性を 1 つずつ手動で更新する必要はありません。 例えば、可用性、待機時間など。</p>
<p>この機能は現在、パブリックベータ版としてすべてのお客様にご使用いただけます。この機能へのアクセスを希望する場合は、アカウント担当者にお問い合わせください</p>
<p>詳しくは、<a href="../experience-decisioning/aep-data-exd.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 6 月 20 日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#25-06-improv}

このリリースに含まれる機能強化を以下に示します。

* **チャネルルールセット**

   * キャッピングの **カスタム期間ウィンドウ** – 新しい **ごと** フィールドがチャネルルールセット設定画面で使用できるようになり、指定された期間に応じて複数の日、週、月にわたってフリークエンシーキャッピングルールを適用できます。

   * **1 時間ごとのリセットキャッピングの頻度** - チャネルルールセットに対して 1 時間ごとにキャッピングを適用できるようになりました。 この機能は、一連の組織でのみ使用できます（限定提供）。有効にするには、カスタマーケアにお問い合わせください。

   * **毎日の期間** – 以前は限定提供で利用できましたが、チャネルルールセットの「毎日」のフリークエンシーキャップは、すべてのお客様が利用できるようになりました。

  詳しくは、[詳細なドキュメント](../conflict-prioritization/channel-capping.md)を参照してください。

* **コードベースのエクスペリエンス**

   * 決定ポリシーをコードベースのエクスペリエンスコンテンツテンプレートで追加できるようになりました。このテンプレートを使用して、編集可能なフォームフィールドでオファーを活用できます。 [詳細情報](../code-based/code-based-form-fields.md)

   * コードベースのエクスペリエンスジャーニーまたはキャンペーン編集画面から、パーソナライゼーションエディターを開くことなく、決定ポリシーを直接追加できるようになりました。 [詳細情報](../code-based/create-code-based.md#edit-code)

* **E メールデザイナーのカスタム CSS のサポート**

  Journey Optimizerで、メールDesigner内でメールコンテンツに直接カスタム CSS を追加できるようになりました。 [詳細情報](../email/custom-css.md)

* **キャンペーン用の新しいタブ付きナビゲーション**

  新しいナビゲーションパターンにより、コンテンツオーサリングにすばやくアクセスでき、キャンペーン全体でさらに設定を拡張できます。 [詳細情報](../campaigns/create-campaign.md)

* **決定**

   * **サンドボックスのコピーと決定** （公開日：2025 年 6 月 3 日（PT）） – 決定オブジェクトをサンドボックス間でコピーできるようになり、テストおよびデプロイメントワークフローを合理化します。 [詳細情報](../configuration/copy-objects-to-sandbox.md#decisioning)

   * **決定ルール用の決定項目属性のサポート** （公開日：2025 年 6 月 4 日（PT）） – 決定項目属性を活用して決定ルールを作成できるようになりました。 [詳細情報](../experience-decisioning/rules.md#create)

* **インタラクティブメッセージ実行 API の更新** – リリース日：2025年6月6日（PT）

  インタラクティブメッセージ実行 API で、今後のキャンペーン実行のスケジュールを削除できるようになりました。[詳細情報](https://developer.adobe.com/journey-optimizer-apis/references/messaging/){target="_blank"}
