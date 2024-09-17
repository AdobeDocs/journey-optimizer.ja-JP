---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: d7d77bcbd401f7af68f644ded25d61f0921c03be
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 80%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。

## 9月のアップデート {#9-2024}

>[!IMPORTANT]
>
>現在のレポートエクスペリエンスは、10 月リリースの時点で廃止されます。この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。
> [Journey Optimizerの新しいレポートインターフェイスの概要 ](../reports/report-gs-cja.md)

<table>
<thead>
<tr>
<th><strong>AI アシスタント コンテンツ アクセラレータ </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メッセージを作成してパーソナライズしたら、Journey Optimizerのコンテンツアクセラレーション用 AI アシスタントを使用してコンテンツを次のレベルに引き上げます。 AI アシスタントを使用して、様々なメインタイトルや画像を試すことで、メッセージの影響を最適化できるようになりました。 各バリアントは独自の処理として管理され、より効果的にクリックを生成するタイトルを測定および比較します。</p>
<p>機能を直接探索し、その機能を完全に理解できるように設計された <a href="https://experienceleague.adobe.com/en/apps/journey-optimizer/ai-assistant-content-accelerator"> ライブ機能プレビュー </a> を使用して、実践的な体験に没頭してください。</a></p>
<p>詳しくは、<a href="../content-management/gs-generative.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/ai-content.gif"/>
<p>公開日：9 月 12 日（Pt）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ガイド付きチャネル設定</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ガイド付きチャネル設定を使用すると、統合エクスペリエンスでチャネル設定を自動化および検証し、Journey Optimizer の使用を開始するプロセスを高速化できます。この新しいガイド付き設定により、迅速なチャネル設定が効率化され、必要なすべてのリソースがすぐにインストールされ、Experience Platform、Journey Optimizer およびデータ収集内で機能するようになります。これにより、マーケティング、製品、データエンジニアリングの各チームは、キャンペーンとジャーニーの作成をすぐに開始できます。</p>
<p>詳しくは、<a href="../configuration/set-mobile-config.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/guided-setup.gif"/>
<p>公開日：9 月 3 日（PT）</p>
</br>
</td>
</tr>
</tbody>
</table>

**オーディエンス**

（公開日：9 月 17 日（PT）） **ライセンス使用状況** - ライセンス使用状況ダッシュボードに、エンゲージメント可能なオーディエンスではなく、エンゲージメント可能なプロファイルが表示されるようになりました。 [詳細情報](../audience/license-usage.md)

**ジャーニー**

（公開日：9 月 10 日（PT）） **再試行機能** - エクスポートジョブを取得する際、オーディエンストリガーのジャーニー（**オーディエンスを読み取り** または **ビジネスイベント** で始まる）で、再試行がデフォルトで適用されるようになりました。 エクスポートジョブの作成中にエラーが発生した場合は、10 mn ごとに最大 1 時間の再試行が行われます。 その後は失敗と考えます。 したがって、これらのタイプのジャーニーは、スケジュールされた時間から最大 1 時間後に実行できます。 [詳細情報](../building-journeys/read-audience.md#retries)



## 2024年8月リリースノート {#8-2024}

**リリース日**：2024年8月20日～21日（PT）

<!--
>[!CAUTION]
>
>**Early release notes below are subject to change without prior notice until the release date**. Links, screens and updated documentation are published at the release date.
>
-->

### 新機能 {#8-features}

このリリースでは、以下に示す新機能が導入されています。

<!--
<table>
<thead>
<tr>
<th><strong>Content Cards (Limited Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Content cards are a new digital messaging feature in Adobe Journey Optimizer that delivers personalized and engaging content directly within mobile apps and websites. Unlike traditional push notifications, Content Cards integrate seamlessly into the user interface, offering persistent, non-intrusive updates that enhance user interaction and experience.</p>
<p>This feature enables marketers to present relevant, rich media content to users, driving higher engagement and ensuring important messages are seen without disrupting the user journey.</p>
</br>
<p>Content card are currently only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>チャネル設定の改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>現在のチャネルサーフェス機能が強化され、すべてのチャネルで一貫したアプローチが可能になりました。これで、Web、アプリ内メッセージ、コードベースのエクスペリエンスなど、任意のチャネルに対してこれらの設定を定義、管理、再利用できます。</p>
<p><ul>
<li>チャネルサーフェスの名前が「<strong>チャネル設定</strong>」に変更されました</li>
<li>1 つまたは複数のマーケティングアクションを添付して、同意ポリシーとデータガバナンスポリシーを適用できます。</li>
<li>オブジェクトレベルのアクセス制御（OLAC）がチャネル設定ごとに使用できるようになり、特定の設定を作成または使用できるユーザーを決定できるようになりました</li>
<li>一部のチャネルでは、複数のプラットフォームを対象とするチャネル設定を作成できます。例えば、web ページ、iOS アプリ、Android アプリを対象にできるアプリ内メッセージチャネル設定などがあります。</li>
</ul></p>
<p>詳しくは、<a href="../configuration/channel-surfaces.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Marketo Engage カスタムアクション</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer を Adobe Marketo Engage と統合して、B2B ユースケースを作成できるようになりました。新しいカスタムアクションを使用すると、ジャーニーから Marketo にデータを取り込むことができます。</p>
<p>詳しくは、<a href="../action/marketo-engage.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>コンテンツフラグメントの変数</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>フラグメントグローバル変数は、既存のフラグメント機能を強化し、コンテンツの再利用性とスクリプトのユースケースの効率を向上させます。フラグメントは、入力変数を使用し、キャンペーンとジャーニーコンテンツで使用できる出力変数を作成できるようになりました。フラグメントは、<a href="../personalization/use-expression-fragments.md">式フラグメント</a>と<a href="../email/use-visual-fragments.md">ビジュアルフラグメント</a>の両方で入力変数を使用できます。これらの変数を使用すると、キャンペーンとジャーニーで、メッセージのコンテンツとパラメーターをパーソナライズできます。</p>
<p>詳しくは、<a href="../personalization/use-expression-fragments.md">詳細なドキュメント</a>を参照してください。</p>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>IP ウォームアップワークフロー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>公開日：8月13日（PT）</p>
<p>新しい IP アドレスでメールを送信する際に、ユーザーインターフェイスから直接 IP ウォームアップワークフローを簡単に実行できるようになりました。Adobe Journey Optimizer は、標準化された効率的な方法で、最適な配信品質を実現するためのベストプラクティスに従って IP アドレスをウォームアップします。</p>
<p>詳しくは、<a href="../configuration/ip-warmup-gs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#8-improvements}

このリリースでは、以下に示す機能強化が導入されています。

**ジャーニー**

* 「**条件**」アクティビティでは、デフォルトで、**[!UICONTROL 時間条件]**&#x200B;が 00:00 から 12:00 までの時間単位で設定されるようになりました。[詳細情報](../building-journeys/condition-activity.md#time_condition)
* ジャーニーを作成する際に、「**アラート**」ボタンからアラートが表示されるようになり、他のアラートに合わせて一貫したユーザー エクスペリエンスを実現します。[詳細情報](../building-journeys/troubleshooting.md#checking-for-errors-before-testing)
* ジャーニーツールバーのズームオプションが改善されました。ズームの割合が表示され、ズーム値をより簡単にリセットできるようになりました。

<!--**Audiences and Profiles**-->

<!--* The use of audiences from custom upload (CSV file) is now available for use with Privacy and Security Shield add-on.-->
<!--* When targeting a custom upload (CSV file) audience, you can now use attributes from the file in your campaigns and journeys. These attributes are available in the personalization editor, to personalize your messages, and the journey advanced expression editor.-->
<!--* The License usage dashboard now shows the count of Engageable Profiles. [Read more](../audience/license-usage.md)-->

**プッシュチャネル**

* Adobe Journey Optimizer チャネル設定内でモバイルアプリケーションプッシュ資格情報を追加できるようになりました。Adobe Experience Platform データ収集でのアプリサーフェスの作成は不要になりました。

### その他の変更 {#changes}

**レポート**

* 新しいレポートエクスペリエンスに次の新しいユースケースが追加されました。

   * レポート内でカスタム計算指標を直接作成。
   * レポートデータからオーディエンスを作成。
   * 探索的分析ツールを使用すると、選択した&#x200B;**[!UICONTROL ディメンション]**&#x200B;と&#x200B;**[!UICONTROL 指標]**&#x200B;からテーブルとビジュアライゼーションを簡単に作成できます。

  詳しくは、[詳細なドキュメント](../reports/report-cja-manage.md)を参照してください。
