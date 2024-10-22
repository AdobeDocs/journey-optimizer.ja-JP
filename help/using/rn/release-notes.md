---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 8fecd0d4812ba875dba1d47bc32ab08178a13f2c
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 89%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。 [!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2024年10月の更新 {#24-10-rn}

今後の **リリース日**: 2024 年 10 月 28～30 日（PT）

以下に示す [ 機能 ](#24-10-features) および [ 改善点 ](#24-10-improvements) は、今月リリースされました。

### 新機能 {#24-10-features}

<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンの承認（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>承認ポリシーでは、Journey Optimizer 内で承認プロセスを設定できるようになりました。これにより、マーケティングチームは、キャンペーンとジャーニーが運用開始前に適切な関係者によってレビュー、およびサインオフされていると確かめられます。</p>
<p>詳しくは、<a href="../test-approve/gs-approval.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/approval.gif"/>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>レポートエクスペリエンスの更新（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer レポートが一般提供（GA）され、Customer Journey Analytics機能との相互運用性が向上したことで、両方のプラットフォーム間でレポートが標準化され、データの一貫性と信頼性が向上しました。 Journey Optimizer と Customer Journey Analytics のシームレスな統合により、パフォーマンス指標をより明確に把握でき、より十分な情報に基づいた意思決定が可能になります。</p>
<p>一般提供になると、4 つの新機能が導入されます。シンプルな指標を作成する機能、オーディエンスを作成および公開する機能、Insight Builder を使用してアドホックな質問をする機能、主要な受信者に自動的にメールが送信されるレポートをスケジュールする機能です。</p>
<p>詳しくは、<a href="../reports/report-cja-manage.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/ajo-cja.gif">
<p>公開日：2024 年 10 月 16 日（PT）</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーでのコードベースのエクスペリエンス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>コードベースのエクスペリエンスチャネルでは、Adobe Journey Optimizer を使用して、あらゆるインバウンドプロパティに対して高度なパーソナライゼーションとテストを行うことができ、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、IoT デバイスなど、多様なタッチポイントに合わせたエクスペリエンスをシームレスに配信できます。コードベースのエクスペリエンスチャネルがジャーニーキャンバスで使用できるようになりました。</p>
<p>詳しくは、<a href="../code-based/create-code-based.md">詳細なドキュメント</a>を参照してください。</p>
<img src="../assets/do-not-localize/code-based-journey.gif"/>
<p>公開日：2024年10月1日（PT）</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーでの web エクスペリエンス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Web チャネルを使用すると、Adobe Journey Optimizer では、インバウンド web ジャーニーを通じて顧客に提供する web エクスペリエンスをパーソナライズできます。Web チャネルをジャーニーキャンバスで使用できるようになりました。</p>
<p>詳しくは、<a href="../web/create-web.md">詳細なドキュメント</a>を参照してください。</p>
<img src="../assets/do-not-localize/web-journey.gif"/>
<p>公開日：2024年10月1日（PT）</p>
</tr>
</tbody>
</table>

>[!IMPORTANT]
>
>現在のレポートエクスペリエンスは、2025 年 1 月をもって廃止されます。 この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。
>
> [Journey Optimizer の新しいレポートインターフェイスの使用を開始する方法を学ぶ](../reports/report-gs-cja.md)

### 機能強化 {#24-10-improvements}

**ジャーニー** - 公開日：2024年10月3日（PT）

* **カスタムアクションのパラメーター** - カスタムアクションで NULL およびオプションパラメーターがサポートされるようになりました。[詳細情報](../action/about-custom-action-configuration.md#define-the-message-parameters)

**データガバナンスおよび同意ポリシー** - 公開日：2024年10月7日（PT）

* **データガバナンスポリシー**&#x200B;が、Journey Optimizer のすべてのチャネルで運用されるようになりました。Adobe Experience Platform でポリシーを作成したお客様の場合、これらはチャネル設定のセットアップの一環としてマーケティングアクションに適用されます。設定を使用してコンテンツを作成すると、すべてのパーソナライゼーションフィールドでデータガバナンス違反がないかを確認します。違反が見つかった場合、ジャーニーまたはキャンペーンを公開することはできません。[詳細情報](../action/action-privacy.md)

* **カスタム同意ポリシー**&#x200B;がすべての Journey Optimizer チャネルに適用されるようになりました。メッセージの送信やインバウンドエクスペリエンスの配信の前に適用されると、ユーザーが受信するコンテンツでパーソナライゼーションフィールドを使用することに同意しているかどうかが確認されます。同意が得られない場合、エクスペリエンスは表示されません。[詳細情報](../action/consent.md)

  >[!NOTE]
  >
  >同意ポリシーは、現在、Adobe **Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

**オーディエンス** - 公開日：2024年10月8日（PT）

* CSV ファイルオーディエンスをターゲティングする場合、パーソナライゼーションエディターや、ジャーニーおよびキャンペーンのルールビルダーで、ファイルの属性を使用できるようになりました。[詳細情報](../audience/about-audiences.md)

* カスタムアップロード（CSV ファイル）からのオーディエンスおよび属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。

## 2024年9月リリース {#24-9-rn}

<!--
>[!CAUTION]
>
>**Early release notes below are subject to change without prior notice until the release date**. Links, screens and updated documentation are published at the release date.
>
-->

**リリース日**：2024年9月24～26日（PT）

### 新機能 {#24-9-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>モバイルアプリおよび web サイトのコンテンツカード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>コンテンツカードは、Adobe Journey Optimizer の新しいデジタルメッセージ機能で、パーソナライズされた魅力的なコンテンツをモバイルアプリや web サイト内で直接配信します。従来のプッシュ通知とは異なり、コンテンツカードはユーザーインターフェイスにシームレスに統合され、ユーザーのインタラクションとエクスペリエンスを向上させる、永続的で非割り込み型の更新を提供します。</p>
<p>この機能により、マーケターは、関連性の高いリッチメディアコンテンツをユーザーに提示し、エンゲージメントを向上させ、ユーザージャーニーを中断することなく重要なメッセージを確実に確認できるようにします。</p>
<p>詳しくは、<a href="../content-card/get-started-content-card.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/content-card.gif"/>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンでの承認（LA）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>承認ポリシーでは、Journey Optimizer 内で承認プロセスを設定できるようになりました。これにより、マーケティングチームは、キャンペーンとジャーニーが運用開始前に適切な関係者によってレビュー、およびサインオフされていると確かめられます。</p>
<p>承認ポリシーは現在、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../test-approve/gs-approval.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/approval.gif"/>
</td>
</tr>
</tbody>
</table>

<!--<table>
<thead>
<tr>
<th><strong>Email Content Locking</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer now allows you to lock content in email templates, either by locking the entire template or specific structures and component. This allows you to prevent unintentional edits or deletions, giving you greater control over template customization, and improving the efficiency and reliability of your email campaigns.</p>
<p>For more information, refer to the <a href="../content-management/gs-generative.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/gif-content-locking.gif">
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>ジャーニーにおけるグローバル終了条件</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>次に、ジャーニーレベルでの終了条件を定義します。終了条件を追加して、イベント（例：購買）が発生した直後やオーディエンスに適合した直後に、プロファイルによってジャーニーを終了させます。これにより、ユーザーはジャーニーからそれ以降の通信を受信できなくなります。</p>
<p>詳しくは、<a href="../building-journeys/journey-properties.md#exit-criteria">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI アシスタントコンテンツアクセラレータ </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メッセージを作成してパーソナライズしたら、Journey Optimizerの AI アシスタントコンテンツアクセラレーターを使用してコンテンツを次のレベルに引き上げます。 AI アシスタントを使用して、様々なメインタイトルや画像で実験することで、メッセージの影響を最適化できるようになりました。 各バリアントは独自の処理として管理され、より効果的にクリックを生成するタイトルを測定および比較します。</p>
<p><a href="https://experienceleague.adobe.com/ja/apps/journey-optimizer/ai-assistant-content-accelerator">ライブ機能プレビュー</a>で実際のエクスペリエンスに浸ってください。このプレビューは、その機能を直接探索し、その機能を完全に理解できるように設計されています。</a></p>
<p>詳しくは、<a href="../content-management/gs-generative.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/ai-content.gif"/>
<p>公開日：2024年9月12日（PT）</p>
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
<p>リリース日：2024年9月3日（PT）</p>
</br>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#24-9-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス** - 公開日：2024年9月17日（PT）

**ライセンス使用状況** - ライセンス使用状況ダッシュボードに、エンゲージメント可能なオーディエンスではなく、エンゲージメント可能なプロファイルが表示されるようになりました。[詳細情報](../audience/license-usage.md)

**コンテンツ管理**

サンドボックス間でコンテンツテンプレートとフラグメントを書き出せるようになりました。[詳細情報](../configuration/copy-objects-to-sandbox.md)

**ジャーニー**

* **ライブレポートの機能強化** - ライブレポートでは、過去 24 時間のジャーニーのパフォーマンスに関するインサイトを提供します。新しい指標（エントリ済み、終了、破棄されたプロファイルやエラーのあるプロファイル）を追加すること機能を強化し、ジャーニーキャンバスから直接、ユーザーの行動とパフォーマンスをより深く理解できるようになりました。[詳細情報](../building-journeys/report-journey.md)


* （公開日：9月10日（PT））**「オーディエンスを読み取り」の自動再試行** - 書き込みジョブの取得中に、オーディエンスによってトリガーされるジャーニー（「**オーディエンスを読み取り**」または「**ビジネスイベント**」から開始）に再試行がデフォルトで適用されるようになりました。書き出しジョブの作成中にエラーが発生した場合、最大 1 時間、10 分ごとに再試行が行われます。それ以降は失敗と見なされます。したがって、これらのタイプのジャーニーは、スケジュールされた時間から最大 1 時間後に実行できます。[詳細情報](../building-journeys/read-audience.md#retries)

**メールチャネル**

* **送信済みメールのメッセージヘッダーと BCC コピー** - すべてのメールメッセージに新しいヘッダーが追加されました。このヘッダーの値は、送信された各メールと、対応する BCC メールコピーに対して一意です。また、このヘッダーは、メッセージと BCC フィードバックデータセットにも保存され、BCC コピー、および対応する送信済みメール情報を調整できます。[詳細情報](../configuration/archiving-support.md#bcc-header)

* **スパムのスコアリング**（GA）- 専用の&#x200B;**スパムレポート**&#x200B;で、コンテンツのスパムのスコアを確認できるようになりました。Adobe Journey Optimizer では、SpamAssassin を使用してメールコンテンツをテストし、ISP またはメールボックスプロバイダーがスパムと見なすかどうかを示すスコアを付与できるようになりました。[詳細情報](../content-management/spam-report.md)

**SMS チャネル**

* **API 資格情報を編集** - オプトイン／オプトアウトキーワードや返信の更新など、SMS API 資格情報の設定を編集できるようになりました。

**API**

* **Campaign Simulation API** - この API を使用して、キャンペーンの配達確認ジョブをトリガーします。キャンペーンの配達確認の送信は非同期プロセスで、API は配達確認のステータスを確認するために使用できる配達確認ジョブ ID を返します。[詳細情報](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"}

* （公開日：9月10日（PT））[Adobe Journey Optimizer API ドキュメント](https://developer.adobe.com/journey-optimizer-apis/references/simulations/){target="_blank"}がインタラクティブになりました。ドキュメントページから直接 API エンドポイントを調べて、即時のフィードバックを取得し、技術的な実装を高速化します。


  すべての API リファレンスページに&#x200B;**試す**&#x200B;機能が追加され、ドキュメントの web サイトページで直接 API 呼び出しをテストできるようになりました。[必要な認証資格情報を取得し](https://developer.adobe.com/journey-optimizer-apis/references/authentication/){target="_blank"}、API エンドポイントを探索する機能の使用を開始します。

  この新しい機能を使用して、API エンドポイントへのリクエストと API エンドポイントからの応答を調べ、即時のフィードバックを取得し、技術的な実装を高速化します。

  >[!CAUTION]
  >
  >ドキュメントページのインタラクティブ API 機能を使用すると、エンドポイントに対して実際の API 呼び出しを行うことができます。実稼動サンドボックスを使用して実験する際は、この点に留意してください。

**設定**

* **IP ウォームアッププラン** - この機能は、Adobe **Healthcare Shield** または&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織を含む、すべてのお客様が利用できるようになりました。[詳細情報](../configuration/ip-warmup-gs.md)


![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"}に登録すると、最新の製品アップデート、面白い顧客事例、ユースケース、ヒントなどが、四半期ごとに直接配信されます。