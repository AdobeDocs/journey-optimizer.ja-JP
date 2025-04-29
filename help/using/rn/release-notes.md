---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 0f3191a3d7c5c78e1d8fac2e587e26522f02f8f5
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 52%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。


## 2025 年 4 月リリースノート {#25-4-rn}


**リリース日**:2025 年 4 月 29～30 日


### 新機能 {#25-04-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>Adobe Expressの統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey OptimizerはAdobe Expressと統合され、クリエイティブアセットを journey orchestration とシームレスに接続できるようになりました。 この統合により、キャンペーン全体でパーソナライズされたコンテンツを設計およびデプロイするプロセスが簡素化されます。 </p>
<p>この機能は現在、限定提供（LA）になっています。</p>
<img src="assets/do-not-localize/express_resize.gif">
<p>詳しくは、<a href="../integrations/express.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Calendar view for campaign and journey inventory (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>A new calendar view is now available for campaigns and journey activations. This feature provides a visual representation of scheduled activities, allowing you to view and manage your campaigns and journeys more effectively. Selecting a calendar item opens a right rail with detailed information. This feature is currently in Limited Availability.</p>
<img src="assets/do-not-localize/calendar.gif">
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>Adobe Experience Manager as a Cloud Serviceの統合（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey OptimizerとAdobe Experience Manager as a Cloud Service間の統合の一般提供。 この統合により、パーソナライズされたカスタマージャーニーに対するシームレスなコンテンツのソーシングと管理が可能になります。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Personalization エディター – 実践で学ぶ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライゼーション式を試すことができる、パーソナライゼーションプレイグラウンドが使用できるようになりました。 これを使用すると、開始して独自のパーソナライゼーション式を試すのに役立つサンプルテンプレートとペイロードを調べることができます。</p>
<p>詳しくは、<a href="../personalization/personalize.md#playground">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年4月24日（PT）</p>
<img src="assets/do-not-localize/templating-playground.gif"/>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>トリガーの毎日のジャーニーがバッチセグメント化の完了後に実行される（使用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>毎日スケジュールされたジャーニーの場合、新しいオプションを使用すると、バッチセグメント化ジョブからのオーディエンスデータを待機する最大 6 時間の時間枠を定義でき、ジャーニーが最新のデータで実行されるか、準備ができていない場合はスキップされるようになります。 「バッチオーディエンス評価後にトリガー」オプションは、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../building-journeys/read-audience.md#schedule">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Simulate content variations (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Previously available in beta, content variations simulation is now generally available (GA). It allows you to preview different variations of your content using sample input data uploaded from a CSV or JSON file or added manually. All the attributes used in your content for personalization are automatically detected by the system and can be used for your tests to create multiple variants.</p>
<p>With the General Availability release, the feature now includes support for multilingual content and content experiments, enabling you to test variations across different languages and treatments. Additionally, it now supports contextual attributes (in addition to profile attributes), allowing for even more dynamic and situational content testing.</p>
<img src="assets/do-not-localize/variants.gif">
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>ブランドの整合性スコア（Beta）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ブランドのアラインメントスコア機能は、電子メールデザイナーで直接フィードバックを明確に提供し、コンテンツがブランドのトーン、スタイル、ガイドラインに従っているかどうかを確認するのに役立ちます。</p>
<p>詳しくは、<a href="../content-management/brands-score.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Line channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer has expanded its cross-channel capabilities to include support for the LINE channel. This enhancement allows you to create, edit, and preview LINE experiences enabling more personalized and engaging interactions. With LINE, you can connect with more customers, send relevant content, and improve your engagement.</p>
<p>For more information, refer to the <a href="../sms/sms-configuration-custom.md">detailed documentation</a>.</p></td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Custom SMS provider (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports custom SMS providers, allowing you to integrate your preferred SMS services for enhanced communication flexibility.</p>
<p>For more information, refer to the <a href="../sms/sms-configuration-custom.md">detailed documentation</a>.</p></td>
</tr>
</tbody>
</table-->


<table>
<thead>
<tr>
<th><strong>ジャーニー指標</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニー指標が使用可能になり、ビジネスの主要指標をまたいでアクティビティの影響を測定し、パフォーマンスに関するより明確なインサイトを得ることができるようになりました。</p>
<p>詳しくは、<a href="../building-journeys/success-metrics.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年4月9日（PT）</p>
</br>
<img src="assets/do-not-localize/success-metric.gif"/>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Decisioning - New ranking formula builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create specific Decisioning ranking formulas by defining and combining criteria from a new improved interface. Ranking formulas allow you to define rules that will determine which decision items should be presented first, rather than taking into account the priority scores.  </p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化 {#25-04-improv}

**メールチャネル**

<!--* **Personalized URL tracking**

  For increased flexibility and control over your email settings, you can now personalize all your URL tracking parameters at once at the email channel configuration level, instead of doing it in the Email designer for each link in your content. -->

* **E メールデザイナー** - 公開日：2025年4月1日（PT）

  Journey Optimizer のアクセシビリティを強化するために、E メールデザイナーで 2 つの新しいフィールドが使用できるようになりました。これらは、メールコンテンツの `<html>` 要素の `<title>` 要素と `lang` 属性に対応しています。これらの設定は、メールの「**[!UICONTROL 本文]**」セクションの「**[!UICONTROL プリヘッダー]**」フィールドに加えて定義できます。[詳細情報](../email/email-metadata.md)

<!--- **Email designer themes** (Beta) - Availability date: May 5, 2025

  You can now quickly apply pre-approved styling themes to your email content to ensure brand consistency across all emails, speed up your campaign creation process and independently produce hight-quality emails while reducing dependency on design teams. -->

**サンドボックスツール**

<!--- **Decisioning sandbox copy**

  Decisioning objects can now be copied between sandboxes, streamlining testing and deployment workflows.-->

- **カスタムアクション用のサンドボックスツール**

  カスタムアクションが、サンドボックスツール機能を使用してコピーできるAdobe Journey Optimizer オブジェクトのリストに含まれるようになりました。これにより、テストとデプロイメントを合理化できます。 [詳細情報](../configuration/copy-objects-to-sandbox.md)

- **キャンペーン用サンドボックスツール** – 公開日：2025 年 4 月 3 日（PT）

  パッケージのエクスポート機能とインポート機能を使用して、複数のサンドボックス間でキャンペーンをコピーできるようになりました。キャンペーンは、プロファイル、オーディエンス、スキーマ、インラインメッセージおよび依存オブジェクトに関連するすべての項目と共にコピーされます。決定項目、データ使用ラベル、言語設定など、一部の項目はコピーされません。[詳細情報](../configuration/copy-objects-to-sandbox.md#custom-actions)

**パーソナライゼーション**

<!--- **Pills activation**  

  A new "Pills" button has been to the personalization editor. When enabled, profile and contextual attributes display as pills, enhancing the readability of your code.-->

- **属性ペインに表示される属性** – 公開日：2025 年 4 月 2 日（PT）

  パーソナライゼーションエディターの属性パネルには、デフォルトで入力した属性のみが表示されるようになりました。すべての属性を表示するには、設定ボタンを使用して「**[!UICONTROL 入力した属性のみを表示]**」オプションをオフに切り替えます。[詳細情報](../personalization/personalization-build-expressions.md)


- **新しいコンテキスト属性**

  新しいコンテキスト属性 **メッセージプロファイル ID** が、パーソナライゼーションエディターから選択できるようになりました。 これは、配信内の各ターゲットプロファイルに送信される各メッセージを一意に識別するメッセージ指向属性です。 この一意の識別子は、例えば、受信者が開いた、またはクリックした各リンクを区別するための URL トラッキングパラメーターとして使用できます。

**ナビゲーション**

* **コンテンツ管理** - 公開日：2025年4月2日（PT）

  コンテンツテンプレートとフラグメントを簡単に管理することを目的に、フォルダーを使用して、より効果的に構造化された階層に整理できるようになりました。詳しくは、[コンテンツテンプレート](../content-management/access-content-templates.md#folders)および[フラグメント](../content-management/manage-fragments.md#folders)の節を参照してください。

  >[!AVAILABILITY]
  >
  >この機能強化は、一連の組織のみが使用できます（限定提供）。

<!--- **Folders for content templates and fragments** - Availability date: May 5, 2025

  Previously available for a set of organizations (LA), folders are now available to all users (GA) to manage their content templates and fragments. Folders let you organize your content templates and fragments more easily and effectively into a structured hierarchy.

- **Folders for landing pages** - Availability date: May 5, 2025

  To easily manage your landing pages, you can now also use folders to organize them more effectively into a streamlined hierarchy.  -->

<!--- **Right rail in campaigns list**  

  A right rail has been added to the campaigns list, providing detailed information when a campaign is selected.-->

<!--**Playbooks**

- **Create your own playbooks (Beta)**
  
  You can now create your own playbooks in Adobe Journey Optimizer, enabling greater customization and flexibility in journey planning.-->




