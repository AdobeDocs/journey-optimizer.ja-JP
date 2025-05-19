---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 2f7c620a712cfc104418bc985bd74e81da12147c
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 67%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新機能"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025年5月の更新 {#25-5-rn}

* **メールDesigner（Beta）のテーマ** – 公開日：2025 年 5 月 14 日（PT）

  事前承認済みのスタイルテーマをメールコンテンツにすばやく適用して、すべてのメールでブランドの一貫性を確保し、キャンペーンの作成プロセスを高速化し、独立して高品質のメールを生成すると同時にデザインチームへの依存を軽減できるようになりました。 [詳細情報](../email/apply-email-themes.md)

  >[!AVAILABILITY]
  >
  >この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。

  ![](assets/do-not-localize/themes.gif)

* **決定 – 新しい AI 式ビルダー** – 公開日：2025 年 5 月 14 日（PT）

  新しく改善されたインターフェイスから条件を定義および組み合わせることで、特定の決定ランキング式を作成できるようになりました。静的なオファーの優先度のみに依存するのではなく、ガイド付きインターフェイスを介して AI モデルスコア、オファーの優先度、プロファイル属性、オファー属性、コンテキストシグナルを組み合わせるカスタムランキング式を定義できます。 [詳細情報](../experience-decisioning/exd-ranking-formulas.md)

  ![](assets/do-not-localize/formula-builder.gif)

* **ランディングページのフォルダー** - 公開日：2025年5月9日（PT）

  ランディングページを簡単に管理するために、フォルダーを使用して、より効果的に整理し、より効率的な階層にすることができるようになりました。  [詳細情報](../landing-pages/manage-lp.md)

* **パーソナライゼーションのための錠剤のアクティベーション** – 公開日：2025 年 5 月 5 日（PT）

  パーソナライゼーションエディターに新しい「錠剤」ボタンが追加されました。 有効にすると、プロファイルとコンテキストの属性が錠剤として表示され、コードの読みやすさが向上します。 [詳細情報](../personalization/personalization-build-expressions.md#options)

  >[!AVAILABILITY]
  >
  >この機能は、今後 30 日間にわたってすべての環境に徐々に展開される予定です。

* **サンドボックスコピーの新規オブジェクトのサポート**

   * **キャンペーン** – 公開日：2025 年 5 月 15 日（PT）

     パッケージのエクスポートおよびインポート機能を使用して、複数のサンドボックス間でキャンペーンをコピーする場合、チャネル設定、実験のバリアントと設定、決定ポリシーと項目の依存関係もコピーされるようになりました。 [詳細情報](../configuration/copy-objects-to-sandbox.md)

   * **決定** – 公開日：2025 年 5 月 16 日（PT）

     サンドボックス間で決定オブジェクトをコピーできるようになり、テストおよびデプロイメントワークフローを合理化します。 [詳細情報](../configuration/copy-objects-to-sandbox.md#decisioning)

* **ダイレクトメール：SFTP 接続用の SSH キーのサポート** – 公開日：2025 年 5 月 5 日（PT）

  ダイレクトメールファイルのルーティング設定で、SFTP サーバー接続で SSH キー認証がサポートされるようになりました。


## 2025年4月リリースノート {#25-4-rn}

**リリース日**：2025年4月29～30日（PT）

### 新機能 {#25-04-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>パーソナライゼーションエディター - 実践で学ぶ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライゼーション式を実験できるパーソナライゼーションプレイグラウンドが使用可能になりました。これを使用すると、サンプルテンプレートとペイロードを探索して、開始し、独自のパーソナライゼーション式を試すことができます。</p>
<p>詳しくは、<a href="../personalization/personalize.md#playground">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年4月24日（PT）</p>
<img src="assets/do-not-localize/templating-playground.gif"/>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Adobe Experience Manager as a Cloud Service integration</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The integration between Adobe Journey Optimizer and Adobe Experience Manager as a Cloud Service is now released in General Availability (GA). This integration enables seamless content sourcing and management for personalized customer journeys.</p>
<p>For more information, refer to the <a href="../integrations/aem-templates.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

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
<th><strong>LINE チャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer では、クロスチャネル機能を拡張し、LINE チャネルのサポートを含めました。この機能強化により、LINE エクスペリエンスを作成、編集、プレビューできます。これにより、よりパーソナライズされた魅力的なインタラクションが可能になります。LINE を使用すると、より多くのお客様とつながり、関連性の高いコンテンツを送信し、エンゲージメントを向上させることができます。</p>
<p>リクエストに応じて、Adobe Journey Optimizerのお客様は LINE チャネルを有効にすることができます。 組織でこの機能を有効にするには、アドビカスタマーケアまたはアドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../line/get-started-line.md">詳細なドキュメント</a>を参照してください。</p></td>
</tr>
</tbody>
</table>


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
</br>
<img src="assets/do-not-localize/success-metric.gif"/>
<p>詳しくは、<a href="../building-journeys/success-metrics.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025年4月9日（PT）</p>
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
<th><strong>Adobe Express の統合（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer は、Adobe Express と統合され、クリエイティブアセットを Journey Orchestration とシームレスに接続できるようになりました。この統合により、キャンペーン全体でパーソナライズされたコンテンツを設計およびデプロイするプロセスが簡素化されます。 </p>
<p>この統合は、現在、Healthcare Shield またはプライバシーとセキュリティシールドでは使用できません。</p>
<img src="assets/do-not-localize/express_resize.gif">
<p>詳しくは、<a href="../integrations/express.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>バッチセグメント化の完了後の毎日のジャーニー実行のトリガー（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>毎日スケジュールしたジャーニーでは、新しいオプションを使用すると、バッチセグメント化ジョブからのオーディエンスデータを待機する最大 6 時間の時間枠を定義できるので、ジャーニーが最新のデータで実行されるか、準備が整っていない場合はスキップされます。「バッチオーディエンス評価後にトリガー」オプションは、一連の組織に対してのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../building-journeys/read-audience.md#schedule">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/trigger-journeys.gif">
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Themes in the Email Designer (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now quickly apply pre-approved styling themes to your email content to ensure brand consistency across all emails, speed up your campaign creation process and independently produce hight-quality emails while reducing dependency on design teams.</p>
<p>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../content-management/brands-score.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/themes.gif">
<p>Availability date: May 5, 2025</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>ブランド一致スコア（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ブランド整合性スコア機能は、E メールデザイナーで直接、明確なフィードバックを提供し、コンテンツがブランドのトーン、スタイル、ガイドラインと合っているかどうかを確認するのに役立ちます。この機能はベータ版で使用できます。</p>
<p>詳しくは、 <a href="../content-management/brands-score.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/brand-score.gif">
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Decisioning - New AI formula builder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create specific Decisioning ranking formulas by defining and combining criteria from a new improved interface. Ranking formulas allow you to define rules that will determine which decision items should be presented first, rather than taking into account the priority scores.</p>
<p>For more information, refer to the <a href="../content-management/brands-score.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/formula-builder.gif">
<p>Availability date: May 5, 2025</p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化 {#25-04-improv}

**キャンペーンのプレビュー API**

キャンペーンのプレビュー用の新しい API が、既存のプルーフ送信機能に加えて追加されました。 [詳細情報](https://developer.adobe.com/journey-optimizer-apis/references/simulations/#operation/createCampaignPreview){target="_blank"}。

**サンドボックスツール**

* **カスタムアクション用のサンドボックスツール**

  サンドボックスツール機能を使用してコピーできる Adobe Journey Optimizer オブジェクトのリストにカスタムアクションが含まれるようになり、テストとデプロイメントが効率化されます。[詳細情報](../configuration/copy-objects-to-sandbox.md)

* **キャンペーン用のサンドボックスツール** - 公開日：2025年4月3日（PT）

  パッケージのエクスポート機能とインポート機能を使用して、複数のサンドボックス間でキャンペーンをコピーできるようになりました。キャンペーンは、プロファイル、オーディエンス、スキーマ、インラインメッセージおよび依存オブジェクトに関連するすべての項目と共にコピーされます。決定項目、データ使用ラベル、言語設定など、一部の項目はコピーされません。[詳細情報](../configuration/copy-objects-to-sandbox.md#custom-actions)

**パーソナライゼーション**

* **新しいコンテキスト属性**

  新しいコンテキスト属性の&#x200B;**メッセージプロファイル ID** が、パーソナライゼーションエディターから選択できるようになりました。これは、配信内の各ターゲットプロファイルに送信された各メッセージを一意に識別するメッセージ指向の属性です。この一意の ID は、例えば、受信者が開いたりクリックした各リンクを区別するための URL トラッキングパラメーターとして使用できます。

* **属性パネルに入力した属性** - 公開日：2025年4月2日（PT）

  パーソナライゼーションエディターの属性パネルには、デフォルトで入力した属性のみが表示されるようになりました。すべての属性を表示するには、設定ボタンを使用して「**[!UICONTROL 入力した属性のみを表示]**」オプションをオフに切り替えます。[詳細情報](../personalization/personalization-build-expressions.md)

**メールチャネル**

* **パーソナライズされた URL のトラッキング** – 公開日：2025 年 4 月 30 日（PT）

  メール設定の柔軟性と制御を高めるために、コンテンツ内のリンクごとに電子メールデザイナーで実行する代わりに、電子メールチャネルの設定レベルで、すべての URL トラッキングパラメーターを一度にパーソナライズできるようになりました。 [詳細情報](../email/surface-personalization.md#personalize-url-tracking)

* **E メールデザイナー** - 公開日：2025年4月1日（PT）

  Journey Optimizer のアクセシビリティを強化するために、E メールデザイナーで 2 つの新しいフィールドが使用できるようになりました。これらは、メールコンテンツの `<html>` 要素の `<title>` 要素と `lang` 属性に対応しています。これらの設定は、メールの「**[!UICONTROL 本文]**」セクションの「**[!UICONTROL プリヘッダー]**」フィールドに加えて定義できます。[詳細情報](../email/email-metadata.md)

**ユースケースプレイブック**

* **プレイブックのオーサリングと共有（プライベートベータ版）** – 独自のユースケースプレイブックを作成、管理、共有できるようになりました。 この機能は、現在、一連の組織に対してのみプライベートベータ版として使用できます。 アクセス権を取得するには、Adobe担当者にお問い合わせください。 [詳細情報](../start/playbooks.md)

**ナビゲーション**

* **コンテンツ管理** - 公開日：2025年4月2日（PT）

  コンテンツテンプレートとフラグメントを簡単に管理することを目的に、フォルダーを使用して、より効果的に構造化された階層に整理できるようになりました。詳しくは、[コンテンツテンプレート](../content-management/access-content-templates.md#folders)および[フラグメント](../content-management/manage-fragments.md#folders)の節を参照してください。

  >[!AVAILABILITY]
  >
  >この機能強化は、一連の組織のみが使用できます（限定提供）。

<!--- **Folders for content templates and fragments** - Availability date: May 5, 2025

  Previously available for a set of organizations (LA), folders are now available to all users (GA) to manage their content templates and fragments. Folders let you organize your content templates and fragments more easily and effectively into a structured hierarchy.



<!--- **Right rail in campaigns list**  

  A right rail has been added to the campaigns list, providing detailed information when a campaign is selected.-->

<!--**Playbooks**

- **Create your own playbooks (Beta)**
  
  You can now create your own playbooks in Adobe Journey Optimizer, enabling greater customization and flexibility in journey planning.-->




