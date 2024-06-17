---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 354c05746b6aa45356969fab9af6ffdcee6b9e66
workflow-type: tm+mt
source-wordcount: '1152'
ht-degree: 74%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。


## 2024 年 6 月先行リリースノート {#24-6-2024}

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**.

**リリース日**:2024 年 6 月 18～19 日

### 新機能 {#june-24-features}

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
<th><strong>Adobe Journey Optimizerの AI アシスタント</strong><br/></th>
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
<p>Multilingual content is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
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
<p>Experimentation in journeys is currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
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

### 機能強化 {#june24-improvements}

このリリースでは、以下に示す機能強化が含まれています。


**意思決定管理**

* **意思決定管理でのマルチルールのサポート**  – 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

<!--**Content fragments**

* Fragments can now be edited, and changes can be propagated across all live journeys and campaigns where they are used.
* New statuses for content fragments have been introduced: **Draft**, **Live**, **Publishing**, and **Archived**. 
* To use a fragment in a journey or campaign, it must now be in the **Live** status. A new step has been added to the fragment creation process, allowing the fragment to be published and made available for use in journeys and campaigns. Note that fragment publishing requires a new permission.
   
   **CAUTION** - Since **Draft** and **Live** statuses have been introduced with Journey Optimizer June release, all fragments created before this release have the **Draft** status, even if they are used in a journey or campaign. Learn how to update your existing fragments in this section.-->

**ジャーニー**

* ジャーニーのグローバルタイムアウトが 30 日から 90 日に増えました。
* Adobe Journey Optimizerは、プライバシーの削除/アクセスリクエストと、データライフサイクル管理リクエストをサポートするようになりました。
* ジャーニーインベントリの列のサイズを変更できるようになりました。
* **イベント設定の高度な式エディター** 一般提供を開始 – イベントの設定時に高度な式エディターを活用して、より複雑な式を定義したり、イベント ID 条件で関数を使用したりできるようになりました。 この機能は、一部のお客様を対象に限定提供でリリースされています。 <!--[Read more](../event/about-creating.md)-->
* **結合ポリシー** 一般提供を開始 – ジャーニーで使用される結合ポリシーが、ジャーニー全体を通して表示され一貫性を持つようになりました。 この機能は、一部のお客様を対象に限定提供でリリースされています。 <!--[Read more](../building-journeys/journey-gs.md#merge-policies)-->



**キャンペーン**

* Adobe Journey Optimizerでキャンペーンを作成する際、新しいモーダルでキャンペーンのタイプ（スケジュール済みまたはトリガー済み）を選択できるようになりました。

<!--**Email channel**

* **List-unsubscribe** - Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)-->


**SMS チャネル**

* 単一の API 設定で、各サンドボックスに一意のショートコードを追加できるようになり、プロセスの効率と合理化が向上しました。
  <!--* You can now modify existing SMS configurations.-->

**アプリ内チャネル**

* **式フラグメント**  – 式フラグメントを **アプリ内チャネル**. <!--[Read more](../personalization/use-expression-fragments.md)-->


* これで、エッジ配信プラグインを使用して、インバウンド実装を理解し、トラブルシューティングするために必要な情報を取得できます。

<!--
**Direct mail channel**

* Direct mail channel is now available for organizations that have purchased the Adobe **Healthcare Shield** and **Privacy and Security Shield** add-on offerings.
-->

## 2024年5月リリースノート {#may-2024}

**リリース日**：2024年5月21～22日（PT）

### 新機能 {#e-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>エクスペリエンス決定 – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>エクスペリエンス決定は、「決定項目」と呼ばれるマーケティングオファーの一元化されたカタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。</p>
<p>これらの決定項目は、Journey Optimizer キャンペーン内でアクセス可能になった新しいコードベースのエクスペリエンスチャネルを通じて、幅広いインバウンドサーフェスにシームレスに統合されます。エクスペリエンス決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。</p>
<p>エクスペリエンス決定は、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<img src="assets/do-not-localize/gif-exd.gif"/>
<p>詳しくは、<a href="../experience-decisioning/gs-experience-decisioning.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールサーフェスのパーソナライゼーション - 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール設定の柔軟性と制御を高めるために、メールチャネルサーフェスを作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義できるようになりました。</p>
<p>メールサーフェスのパーソナライゼーションは、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../email/surface-personalization.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>IP Warmup Workflow</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>If you are sending email on a brand new IP address, you can now easily perform IP warmup workflows directly from the user interface. Adobe Journey Optimizer offers a standardized and efficient way to warm up your IP adresses that follows the best practices for optimal deliverability.</p>
<p>For more information, refer to the <a href="../configuration/ip-warmup-gs.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<!--table>
<thead>
<tr>
<th><strong>Business rules - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now create granular frequency capping rules, and apply them to different types of marketing communications through rule sets. This new capability lets you control how often your audiences receive a message by setting cross-channel rules, that automatically exclude over-solicited profiles from messages and actions.</p>
<p>Business rules capability is currently available as a beta. To join the beta program, contact your Adobe representative.</p>
<p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p>
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

**エクスペリエンス決定**（限定提供）

ベータ版からこのリリースまでの、追加された機能強化を以下に示します。

* **エクスペリエンス決定 + コードベースエクスペリエンス**：エクスペリエンス決定機能を活用して、コードベースのキャンペーンで決定項目を使用できるようになりました。メモ：Adobe Healthcare Shield および Privacy and Security Shield アドオン製品を購入した組織では、コードベースのエクスペリエンスチャネルと エクスペリエンス決定を使用できません。[詳細情報](../code-based/get-started-code-based.md)
* **コンテキストデータ** - Adobe Experience Platform からのコンテキストデータを決定ルールやランキング式で活用できるようになりました。[詳細情報](../experience-decisioning/context-data.md)
* **新しい権限** - 意思決定管理リソースで、新しい「エクスペリエンス決定を管理」権限を利用できるようになりました。エクスペリエンス決定に関連する権限を管理できます。[詳細情報](../experience-decisioning/gs-experience-decisioning.md)
* **キャッピングルール** - エクスペリエンス決定で特定の決定項目に対して、複数のキャッピングルールを追加できるようになりました。これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../experience-decisioning/items.md#capping)
* **レポート** - [!DNL Customer Journey Analytics] を使用して、エクスペリエンス決定キャンペーンのカスタムレポートダッシュボードを作成できるようになりました。[詳細情報](../experience-decisioning/cja-reporting.md)


<!--**Decision Management**

* **Multi-rule support** - You can now add up to 10 capping rules for a given offer in Decision Management. This allows you to increase the level of control over the way offers are sent.
* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->


**メールチャネル**

<!--
* **List-unsubscribe** - Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. Refer to the following pages: [Email opt-out management](../email/email-opt-out.md#unsubscribe-header) and [Configure email settings](../email/email-settings.md#list-unsubscribe)
-->

* **スパムのスコアリング**（ベータ版）- 専用のスパムレポートでコンテンツのスパムのスコアを確認できるようになりました。Adobe Journey Optimizer では、SpamAssassin を使用してメールコンテンツをテストし、ISP またはメールボックスプロバイダーがスパムと見なすかどうかを示すスコアを付与できるようになりました。[詳細情報](../content-management/spam-report.md)

  >[!AVAILABILITY]
  >
  >この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。

<!--
**Audiences**

* The use of audiences and attributes from audience composition and custom upload (CSV file) is now available for use with Healthcare Shield or Privacy and Security Shield.-->

<!--**Personalization**

* **Expression fragment** - Expression fragments are now available for the **In-app channel**. [Read more](../personalization/use-expression-fragments.md)-->

**ジャーニー**

<!--* **Merge policies** (Limited Availability)- Merge policies used by a journey are now visible and consistent throughout the journey.-->
* **mTLS サポート** - カスタムアクションで mTLS 認証がサポートされるようになりました。mTLS をアクティブ化するために、カスタムアクションまたはジャーニーで追加の設定は必要ありません。mTLS 対応エンドポイントが検出されると、自動的に実行されます。[詳細情報](../action/about-custom-action-configuration.md#mtls-protocol-support)
* **イベントのルックアップテーブル** - オブジェクトの配列内の属性を使用して関係が定義されている場合に、ルックアップデータセットのデータを活用できるようになりました。ルックアップ値は、ジャーニー（条件、カスタムアクションなど）とメッセージのパーソナライゼーションで使用できます。[詳細情報](../event/experience-event-schema.md#relationships_limitations)
* **イベント設定の高度な式エディター**（LA）- イベントを設定する際に高度な式エディターを活用できるようになり、より複雑な式を定義したり、イベント ID 条件で関数を使用したりできるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。[詳細情報](../event/about-creating.md)
* **結合ポリシー**（LA）- ジャーニーで使用される結合ポリシーがジャーニー全体で表示され、一貫性が保たれるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。[詳細情報](../building-journeys/journey-gs.md#merge-policies)

**グローバライゼーション**

統一されたユーザーエクスペリエンスを提供するための継続的な取り組みの一環として、Adobe Experience Cloud 製品とアプリで使用される用語を統一します。これは、ドイツ語の用語「Titel」（オブジェクトの名前に関連する場合は「ラベル」に変更される）に影響します。変更は、UI とドキュメントで段階的にロールアウトされます。



