---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 0362cb5af7845333d5657829b073881e1ee3c542
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 88%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 2024 年 6 月更新

* Adobe Journey OptimizerでAdobe Experience Platform AI アシスタントを使用できるようになりました。 [詳細情報](../start/ai-assistant.md)

* **意思決定管理でのマルチルールのサポート**  – 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。 これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

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
<th><strong>メールサーフェスのパーソナライゼーション – 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールチャネルサーフェスを作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義して、メール設定の柔軟性と制御を高めることができるようになりました。</p>
<p>メールサーフェスのパーソナライゼーションは現在、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
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
  >この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、Adobe担当者にお問い合わせください。

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



