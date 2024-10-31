---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: ab6289ff4b1a9302adb94d9cdf150210eece3a27
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 42%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。 [!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2024 年 10 月リリース {#24-10-rn}

**リリース日**:2024 年 10 月 29～30 日

### 新機能 {#24-10-features}

このリリースでは、以下に説明する新機能が提供されています。

<table>
<thead>
<tr>
<th><strong>メールコンテンツのロック</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、テンプレート全体をロックするか、特定の構造とコンポーネントをロックして、メールテンプレート内のコンテンツをロックできるようになりました。これにより、意図しない編集や削除を防ぎ、テンプレートのカスタマイズをより細かく制御して、メールキャンペーンの効率と信頼性を向上させることができます。</p>
<p>詳しくは、<a href="../content-management/content-locking.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/gif-content-locking.gif">
<p>2024 年 10 月 24 日（PT）以降に使用可能</p>
</td>
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
<p>2024 年 10 月 1 日（PT）から使用可能</p>
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
<p>2024 年 10 月 1 日（PT）から使用可能</p>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>競合と優先度管理（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、過剰な数のインタラクションで顧客が圧倒されるのを避けるために、キャンペーンとジャーニーの量とタイミングを管理することが不可欠です。Journey Optimizerには、競合の管理と優先順位付けのためのいくつかのツールが用意されるようになりました。 <p>詳しくは、<a href="../conflict-prioritization/gs-conflict-prioritization.md">詳細なドキュメント</a>を参照してください。</p></p><p><ul><li><b>ジャーニーのフリークエンシーキャップ </b>：ジャーニーに適用するルールセットを作成できるようになりました。1 日、1 週間または 1 か月あたりのプロファイルのジャーニー数を制限し、同時に実行される同時ジャーニーの数を制御できます。</li>
<li><b> 優先度スコア </b>：キャンペーンまたはジャーニーに 0 ～ 100 の範囲で優先度スコアを割り当てることができるようになりました。 数値が大きいほど、優先度が高くなります。2 つのキャンペーンまたはジャーニーアクションが同じチャネル設定を使用する場合、Journey Optimizerは優先度スコアが最も高いキャンペーンまたはジャーニーアクションを選択します。 キャンペーンのスコアが同じ場合は、最近変更が最も少なかったキャンペーンが選択されます。</li>
<li><b> 潜在的な競合の表示 </b>：ジャーニーとキャンペーンの新しい「潜在的な競合の表示」ボタンで、開始日、ターゲットオーディエンス、選択したチャネル設定など、他のジャーニーやキャンペーンとの重複を特定できるようになりました。</li>
<li><b>ジャーニーの判別 </b>：この新機能を使用すると、顧客にとって最も重要なジャーニーに優先順位を付けることができます。 顧客が今後予定されている優先度の高いジャーニーの対象になったときに、優先度の低いジャーニーへのエントリを抑制するルールを作成できます。</li>
<li><b> 通信タイプ別のフリークエンシーキャップ：</b> ルールセットでは、類似したメッセージを持つ顧客に過負荷がかかるのを防ぐために、通信タイプ（販売、プロモーションなど）別に詳細なルールを設定できるようになりました。 複数のチャネルにわたる頻度を制御し、過剰に配信を受けているプロファイルを自動的に除外して、カスタマーエクスペリエンス（顧客体験）を向上させることができます。</li></ul>

<img src="assets/do-not-localize/gif-conflict.gif">

<p>競合管理機能と優先管理機能は、一部のお客様のグループが限定提供で利用できます。 これらの機能は、今後、より多くのユーザーに徐々に展開される予定です。 これらの機能のキャンセル待ちに追加することに関心がある場合は、アカウントチームにお問い合わせください。</p>

</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>可動インクとAdobe Journey Optimizerの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Movable Ink Da Vinci とAdobe Journey Optimizerを統合できるようになりました。 この新しい統合により、以下が可能になります。 </p>
<p><ul><li>Movable Ink の Da Vinci 製品の強力な機能を活用して、バッチキャンペーン用のメールバリエーションを組み立て、パーソナライズします</li>
<li>オーサリングに Da Vinci を、最適化と配信にAdobe Journey Optimizerを使用することで、Journey Optimizerのお客様向けの実践者ワークフローを高速化します</li>
<li>Adobeデータを使用してダヴィンチモデルを最適化します。</li></ul></p>
<p>詳しくは、<a href="https://movableink.com/adobe-and-movable-ink">Movable Ink Da Vinci のドキュメント </a> を参照してください。</p>
</tr>
</tbody>
</table>

以前は一連の組織（LA）で使用できましたが、現在は、すべてのユーザー（GA）が次の機能を使用できます。

<table>
<thead>
<tr>
<th><strong>メール設定のパーソナライゼーション（一般提供） </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール設定の柔軟性と制御を高めるために、メールチャネル設定を作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義できます。
</p>
<p>詳しくは、<a href="../email/surface-personalization.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/surface-perso.gif"/>
<p>2024 年 10 月 23 日（PT）以降に使用可能</p>
</tr>
</tbody>
</table>


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
<p>2024 年 10 月 22 日（PT）以降に使用可能</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ジャーニーでのコンテンツ実験（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer は、キャンペーンで既に使用可能で、ジャーニーでの実験をサポートするようになりました。実験はランダム化試験です。オンラインテストのコンテキストでは、ランダムに選択された一部のユーザーにはメッセージの特定のバリエーションを表示し、別のランダムに選択された一連のユーザーには別のバリエーションや処理を行うことを意味します。公開後、メールの開封数、購読数、購入数など、興味のある結果指標を測定できます。</p>
<p>詳しくは、<a href="../content-management/content-experiment.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<!--<table>
<thead>
<tr>
<th><strong>Decisioning (General Availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Decisioning, previously available for a set of organizations (LA) and known as Experience Decisioning, is now available to all users (GA), including organizations that have purchased the Adobe Healthcare Shield or Privacy and Security Shield add-on offerings.</p><p>Decisioning simplifies personalization by offering a centralized catalog of marketing offers known as 'decision items' and a sophisticated decision engine. This engine leverages rules and ranking criteria to select and present the most relevant decision items to each individual. These decision items are seamlessly integrated into a wide range of inbound surfaces through the code-based experience channel.</p>
<p>For more information, refer to the <a href="../experience-decisioning/gs-experience-decisioning.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table>-->

<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンでの多言語メッセージ（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>1 つのキャンペーンまたはジャーニー内で複数の言語のコンテンツを簡単に作成できるようになりました。この機能を使用すると、キャンペーンやジャーニーを編集する際に言語を切り替え、編集プロセス全体を効率化し、多言語コンテンツを効率的に管理する機能を向上させることができます。</p>
<p>詳しくは、<a href="../content-management/multilingual-gs.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/multilingual.gif">
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
<p>重要：現在のレポートエクスペリエンスは、2025 年 1 月をもって廃止されます。 この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。<a href="../reports/report-gs-cja.md">Journey Optimizer の新しいレポートインターフェイスの使用を開始する方法を学ぶ</a></p>
<p>2024 年 10 月 16 日（PT）以降に使用可能</p>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サンプル入力データを使用したコンテンツのテスト（Beta）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーオプティマイザーを使用すると、ファイルからアップロードされた、または手動で追加されたサンプル入力データを使用して、コンテンツの様々なバリアントをプレビューし、配達確認を送信することで、テストできるようになりました。 パーソナリゼーションのコンテンツで使用されるすべてのプロファイル属性は、システムによって自動的に検出され、テストで複数のバリアントを作成するのに使用できます。</p>
<p>この機能は、現在、すべてのお客様がメール、SMS およびプッシュ通知チャネルのパブリックベータ版として利用できます。</p>
<p>詳しくは、 <a href="../test-approve/simulate-sample-input.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--The following capabilities are available to all customers in public beta:

<!--<table>
<thead>
<tr>
<th><strong>Use Adobe Experience Platform data for personalization (Beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Leverage data from Adobe Experience Platform in the personalization editor to personalize your content. To do this, datasets needed for lookup personalization must first be enabled through an API call. Once done, you can use their data to personalize your content into [!DNL Journey Optimizer].</p>
<p>This capability is currently available to all customers as a public beta.</p>
<p>For more information, refer to the <a href="../personalization/lookup-aep-data.md"</a>.</p>
</td>
</tr>
</tbody>
</table>-->

### 機能強化 {#24-10-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**SMS チャネル**

* SMS API チャネル設定を編集または削除できるようになりました。

* Infobip および Sinch を使用して SMS メッセージ機能を改善するための次の機能強化が導入されました。

   * SMS キャンペーンおよびジャーニーに固有のキーワードを定義および管理して、よりパーソナライズされた効率的な通信を可能にできます。

   * キーワードが認識されない場合は、デフォルトの SMS メッセージを作成して配信できます。

  これらの改善点について詳しくは、[Infobip](../sms/sms-configuration-infobip.md) および [Sinch](../sms/sms-configuration-sinch.md) の SMS 設定ドキュメントを参照してください。


<!--**Journeys**-->

<!--* **Path experiment in journeys** - With the journey path experiment, you can now define and track key metrics for your journey paths, allowing you to measure the impact of your activities and to provide clearer insights into your performance. -->

&lt;! —* **ライブジャーニーの最大数** - Journey Optimizerには、100 個ではなく 500 個のライブジャーニーというガードレールが実稼動用サンドボックスに追加されました。 ライブジャーニーの数は、ジャーニーキャンバスに表示されます。<!-- DOCAC-10977-->

**Web チャネル**

* **Web デザイナーの非視覚編集モード** - Journey Optimizer Web デザイナーの代わりに、非視覚編集を使用して web サイトに変更を加えられるようになりました。 これにより、ビジュアルエディターでページを開かずに、手動で変更を入力できます。 この非視覚編集モードは、web デザイナーでページを読み込むために必要なAdobe Experience Cloud Visual Helper などのブラウザー拡張機能をインストールできない場合に役立ちます。 [詳細情報](../web/web-non-visual-editor.md)


**データセット**

* **送信イベントとオープンイベント** - 2024 年 11 月 1 日（PT）以降、ストリーミングセグメント化では、Journey Optimizerのトラッキングデータセットおよびフィードバックデータセットからの送信イベントとオープンイベントの使用をサポートしなくなります。 この変更は、すべての顧客サンドボックスおよび組織に適用されます。 [詳細情報](../data/datasets-ttl.md#segmentation-update)

* **データセットの有効期間（TTL）** - 2025 年 2 月以降、有効期間（TTL）ガードレールが、新しいサンドボックスと新しい組織のJourney Optimizer システム生成データセットに次のようにロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、後続フェーズで既存の顧客サンドボックスにロールアウトされます。 [詳細情報](../data/datasets-ttl.md#ttl)

* **カスタムアクションのパラメーター** – 公開日：2024 年 10 月 3 日（PT） – カスタムアクションで NULL およびオプションパラメーターがサポートされるようになりました。 [詳細情報](../action/about-custom-action-configuration.md#define-the-message-parameters)

**レポート**

* **Experience Decisioning レポート** が使用できるようになりました。訪問者がエクスペリエンスとやり取りする方法に関する基本的なインサイトが提供されます。 [詳細情報](../reports/campaign-global-report-cja-code.md#decisioning-kpis)

**データガバナンスおよび同意ポリシー** - 公開日：2024年10月7日（PT）

* **データガバナンスポリシー**&#x200B;が、Journey Optimizer のすべてのチャネルで運用されるようになりました。Adobe Experience Platformでポリシーを作成したお客様の場合、これらはチャネル設定のセットアップの一環としてマーケティングアクションに適用されます。 設定を使用してコンテンツを作成すると、すべてのパーソナライゼーションフィールドでデータガバナンス違反がないかを確認します。違反が見つかった場合、ジャーニーまたはキャンペーンを公開することはできません。[詳細情報](../action/action-privacy.md)

* **カスタム同意ポリシー**&#x200B;がすべての Journey Optimizer チャネルに適用されるようになりました。メッセージの送信やインバウンドエクスペリエンスの配信の前に適用されると、ユーザーが受信するコンテンツでパーソナライゼーションフィールドを使用することに同意しているかどうかが確認されます。同意が得られない場合、エクスペリエンスは表示されません。[詳細情報](../action/consent.md)

  >[!NOTE]
  >
  >同意ポリシーは、現在、Adobe **Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

**オーディエンス** - 公開日：2024年10月8日（PT）

* CSV ファイルオーディエンスをターゲティングする場合、パーソナライゼーションエディターや、ジャーニーおよびキャンペーンのルールビルダーで、ファイルの属性を使用できるようになりました。[詳細情報](../audience/about-audiences.md)

* カスタムアップロード（CSV ファイル）からのオーディエンスおよび属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。

**設定** – 公開日：2024 年 10 月 23 日（PT）

* キャンペーンやジャーニーでパーソナライズされた設定を使用する際に、メールコンテンツをプレビューして、定義した動的設定で潜在的なエラーを確認できるようになりました。 [詳細情報](../email/surface-personalization.md#check-configuration)

**コードベースチャネル**

* コンテンツテンプレートが使用できるようになりました。 開発者が作成したコンテンツテンプレートから始まる、コードベースのエクスペリエンスのオーサリングを高速化できます。 コンテンツテンプレートを使用すると、マーケターは、HTML全体や JSON コンテンツペイロードを構成するのではなく、一部の値やフィールドを修正するだけで済みます。 [詳細情報](../content-management/content-templates.md)

**判定**

<!--* [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) users can now choose custom models to optimize on when setting up an AI model in Decisioning (formerly known as Experience Decisioning). This allows you, for example, to optimize on a custom "purchases" table rather than defined constraints such as clickthrough rate."-->

* Experience Decisioning を使用してコードベースのキャンペーンに決定ポリシーを追加する際に、選択戦略に加えて、単一の決定項目を手動で選択できるようになりました。 さらに、複数のフォールバックオファーを選択できるようになりました。 これにより、返される決定項目の数が一定に保たれます。 [詳細情報](../experience-decisioning/create-decision.md)
