---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート 2024
description: Journey Optimizer 2024 リリースノート
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: bae533c5-1bfc-48bf-9f8d-1145383c040c
source-git-commit: 40bef9a05fef1433773a73d546752e84f81b7366
workflow-type: ht
source-wordcount: '6785'
ht-degree: 100%

---

# リリースノート 2024 {#release-notes-2024}

このページでは、2024年にリリースされた [!DNL Journey Optimizer] の機能と改善点をすべて一覧表示しています。

## 2024年10月リリース {#24-10-rn}

**リリース日**：2024年10月29～30日（PT）

### 新機能 {#24-10-features}

このリリースでは、以下に示す新機能が導入されています。

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
<p>公開日：2024年10月24日（PT）以降</p>
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
<p>公開日：2024年10月1日（PT）以降</p>
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
<p>公開日：2024年10月1日（PT）以降</p>
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
<p>Journey Optimizer では、過剰な数のインタラクションで顧客が圧倒されるのを避けるために、キャンペーンとジャーニーの量とタイミングを管理することが不可欠です。Journey Optimizer では、競合の管理と優先順位付けのためのツールがいくつか提供されるようになりました。 <p>詳しくは、<a href="../conflict-prioritization/gs-conflict-prioritization.md">詳細なドキュメント</a>を参照してください。</p></p><p><ul><li><b>ジャーニーのフリークエンシーキャップ</b>：ジャーニーに適用するルールセットを作成できるようになりました。これにより、プロファイルのジャーニーの数を 1 日、1 週間、または 1 か月ごとに制限することや、同時に実行される同時ジャーニーの数を制御することができます。</li>
<li><b>優先度スコア</b>：キャンペーンまたはジャーニーに 0～100 の範囲の優先度スコアを割り当てることができるようになりました。数値が大きいほど、優先度が高くなります。2 つのキャンペーンまたはジャーニーアクションが同じチャネル設定を使用する場合、Journey Optimizer は優先度スコアが最も高いものを選択します。キャンペーンのスコアが同じ場合は、最近変更したキャンペーンが選択されます。</li>
<li><b>潜在的な競合を表示</b>：ジャーニーとキャンペーンの新しい「潜在的な競合を表示」ボタンを使用すると、開始日、ターゲットオーディエンス、選択したチャネル設定など、他のジャーニーやキャンペーンとの重複を特定できるようになりました。</li>
<li><b>ジャーニーの判別</b>：この新機能を使用すると、お客様にとって最も重要なジャーニーに優先順位を付けることができます。お客様が今後の優先度の高いジャーニーの対象になった際に、優先度の低いジャーニーへのエントリを抑制するルールを作成できます。</li>
<li><b>通信タイプ別のフリークエンシーキャップ</b>：ルールセットを使用すると、通信タイプ（販売、プロモーションなど）別に詳細なルールを設定して、類似したメッセージでお客様に過負荷がかかるのを防ぐことができます。複数のチャネルにわたって頻度を制御し、過度に配信を受けているプロファイルを自動的に除外して、より良い顧客体験を確保できます。</li></ul>

<img src="assets/do-not-localize/gif-conflict.gif">

<p>競合と優先度管理機能は、一部のお客様のグループに対して限定提供で使用できます。これらの機能は、今後、より多くのユーザーに段階的にロールアウトされる予定です。これらの機能の待機リストに追加されることに興味がある場合は、アカウントチームにお問い合わせください。</p>

</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Movable Ink と Adobe Journey Optimizer の統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Movable Ink Da Vinci と Adobe Journey Optimizer を統合できるようになりました。この新しい統合により、次のことができます。 </p>
<p><ul><li>Movable Ink の Da Vinci 製品の強力な機能を活用して、バッチキャンペーン用のメールバリエーションを組み立て、パーソナライズします</li>
<li>Da Vinci によるオーサリングと Adobe Journey Optimizer による最適化と配信を使用して、Journey Optimizer のお客様の実践者ワークフローを高速化します。</li>
<li>アドビのデータを使用して Da Vinci モデルを最適化します。</li></ul></p>
<p>詳しくは、<a href="https://movableink.com/adobe-and-movable-ink">Movable Ink Da Vinci のドキュメント</a>を参照してください。</p>
</tr>
</tbody>
</table>

以前は一連の組織（LA）に対して提供されていましたが、次の機能はすべてのユーザー（GA）に対して提供されるようになりました。

<table>
<thead>
<tr>
<th><strong>メール設定のパーソナライゼーション（一般公開） </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール設定の柔軟性と制御を高めるために、メールチャネル設定を作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義できます。
</p>
<p>詳しくは、<a href="../email/surface-personalization.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/surface-perso.gif"/>
<p>公開日：2024年10月23日（PT）以降</p>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンでの承認（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>承認ポリシーでは、Journey Optimizer 内で承認プロセスを設定できるようになりました。これにより、マーケティングチームは、キャンペーンとジャーニーが運用開始前に適切な関係者によってレビュー、およびサインオフされていると確かめられます。</p>
<p>詳しくは、<a href="../test-approve/gs-approval.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/approval.gif"/>
<p>公開日：2024年10月22日（PT）以降</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ジャーニーでのコンテンツ実験（一般公開）</strong><br/></th>
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


<table>
<thead>
<tr>
<th><strong>決定（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前は一連の組織（LA）に対して提供され、エクスペリエンス決定と呼ばれていた決定が、Adobe Healthcare Shield またはプライバシーとセキュリティシールドアドオン機能を購入した組織を含むすべてのユーザー（GA）に対して提供されるようになりました。</p><p>決定は、「決定項目」と呼ばれるマーケティングオファーの一元カタログと、高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。このエンジンは、ルールとランキング条件を活用して、各個人に最も関連性の高い決定項目を選択し、提示します。これらの決定項目は、コードベースのエクスペリエンスチャネルを通じて、幅広いインバウンドサーフェスにシームレスに統合されます。</p>
<p>詳しくは、<a href="../experience-decisioning/gs-experience-decisioning.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンでの多言語メッセージ（一般公開）</strong><br/></th>
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
<th><strong>更新済みレポートエクスペリエンス（一般公開）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer レポートは現在一般公開（GA）され、Customer Journey Analytics 機能との相互運用性が改善され、両方のプラットフォーム間でレポートが標準化され、データの一貫性と信頼性が向上します。Journey Optimizer と Customer Journey Analytics のシームレスな統合により、パフォーマンス指標がより明確に表示され、ユーザーはより多くの情報に基づいて意思決定を行うことができます。</p>
<p>一般公開では、シンプルな指標を作成する機能、オーディエンスを作成して公開する機能、インサイトビルダーを使用してアドホックな質問をする機能、主要な受信者にレポートを自動的にメールで送信するようにスケジュールする機能など、4 つの新機能が導入されています。</p>
<p>詳しくは、<a href="../reports/report-cja-manage.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/ajo-cja.gif">
<p>重要：現在のレポートエクスペリエンスは、2025年1月に廃止されます。この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。<a href="../reports/report-gs-cja.md">Journey Optimizer の新しいレポートインターフェイスの使用を開始する方法を学ぶ</a></p>
<p>公開日：2024年10月16日（PT）以降</p>
</tr>
</tbody>
</table>

<!--The following capabilities are available to all customers in public beta:-->

<table>
<thead>
<tr>
<th><strong>サンプル入力データを使用したコンテンツのテスト（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer を使用すると、ファイルからアップロードされた、または手動で追加されたサンプル入力データを使用して、プレビューしメールの配達確認を送信することで、コンテンツの様々なバリアントをテストできるようになりました。パーソナライズ機能のコンテンツで使用されるすべてのプロファイル属性は、システムによって自動的に検出され、テストで複数のバリアントを作成するのに使用できます。</p>
<p>この機能は、現在、パブリックベータ版としてすべてのお客様がメール、SMS、プッシュ通知チャネルで使用できます。</p>
<p>詳しくは、<a href="../test-approve/simulate-sample-input.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/gif-simulate.gif">
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform データをパーソナライズ機能に活用（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライゼーションエディターで Adobe Experience Platform のデータを利用して、コンテンツをパーソナライズします。これを行うには、まず、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、そのデータを使用して、コンテンツを [!DNL Journey Optimizer] にパーソナライズできます。</p>
<p>この機能は現在、パブリックベータ版としてすべてのお客様に対して使用可能です。</p>
<p>詳しくは、 <a href="../personalization/lookup-aep-data.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#24-10-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**SMS チャネル**

* SMS API チャネル設定を編集または削除できるようになりました。[詳細情報](../sms/sms-configuration.md)

* Infobip や Sinch を使用して SMS メッセージ機能を改善する次の機能強化が導入されました。

   * SMS キャンペーンとジャーニーに一意のキーワードを定義および管理して、よりパーソナライズされた効率的な通信を可能にできます。

   * キーワードが認識されない場合は、デフォルトの SMS メッセージを作成して配信できます。

  これらの改善点について詳しくは、[Infobip](../sms/sms-configuration-infobip.md) と [Sinch](../sms/sms-configuration-sinch.md) の SMS 設定ドキュメントを参照してください。


<!--**Journeys**-->

<!--* **Path experiment in journeys** - With the journey path experiment, you can now define and track key metrics for your journey paths, allowing you to measure the impact of your activities and to provide clearer insights into your performance. -->

<!--* **Max number of Live journeys** - Journey Optimizer now has a guardrail of 500 live journeys on production sandboxes, instead of 100. The number of live journeys is visible in the journey canvas. (DOCAC-10977) -->

**Web チャネル**

* **Web デザイナー向けの非ビジュアル編集モード** - Journey Optimizer の web デザイナーの代わりに、非ビジュアルエディターを使用して web サイトに変更を追加できるようになりました。これにより、ビジュアルエディターでページを開かなくても、手動で変更を入力できます。この非ビジュアル編集モードは、web デザイナーでページを読み込むのに必要な Adobe Experience Cloud Visual Helper などのブラウザー拡張機能をインストールできない場合に役立ちます。[詳細情報](../web/web-non-visual-editor.md)


**データセット**

* **送信イベントとオープンイベント** - 2024 年11月1日（PT）以降、ストリーミングセグメント化では、Journey Optimizer のトラッキングデータセットとフィードバックデータセットからの送信イベントとオープンイベントの使用をサポートしなくなります。この変更は、すべてのお客様のサンドボックスと組織に適用されます。[詳細情報](../data/datasets-ttl.md#segmentation-update)

* **データセットの有効期間（TTL）** - 2025 年2月以降、新しいサンドボックスと新しい組織の Journey Optimizer システム生成データセットに、次のように有効期間（TTL）ガードレールがロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、後続のフェーズで既存のお客様のサンドボックスにロールアウトされます。[詳細情報](../data/datasets-ttl.md#ttl)

* **カスタムアクションのパラメーター** - 公開日：2024年10月3日（PT） - カスタムアクションで NULL およびオプションパラメーターがサポートされるようになりました。[詳細情報](../action/about-custom-action-configuration.md#define-the-message-parameters)

**レポート**

* **決定レポート**&#x200B;が使用できるようになりました。訪問者がエクスペリエンスとやり取りする方法に関する基本的なインサイトが提供されます。[詳細情報](../reports/campaign-global-report-cja-code.md#decisioning-kpis)

**データガバナンスおよび同意ポリシー** - 公開日：2024年10月7日（PT）

* **データガバナンスポリシー**&#x200B;が、Journey Optimizer のすべてのチャネルで運用されるようになりました。Adobe Experience Platform でポリシーを作成したお客様の場合、これらはチャネル設定のセットアップの一環としてマーケティングアクションに適用されます。設定を使用してコンテンツを作成すると、すべてのパーソナライゼーションフィールドでデータガバナンス違反がないかを確認します。違反が見つかった場合、ジャーニーまたはキャンペーンを公開することはできません。[詳細情報](../action/action-privacy.md)

* **カスタム同意ポリシー**&#x200B;がすべての Journey Optimizer チャネルに適用されるようになりました。メッセージの送信やインバウンドエクスペリエンスの配信の前に適用されると、ユーザーが受信するコンテンツでパーソナライゼーションフィールドを使用することに同意しているかどうかが確認されます。同意が得られない場合、エクスペリエンスは表示されません。[詳細情報](../action/consent.md)

  >[!NOTE]
  >
  >同意ポリシーは、現在、Adobe **Healthcare Shield** および&#x200B;**プライバシーとセキュリティシールド**&#x200B;アドオン機能を購入した組織でのみ利用できます。

**オーディエンス** - 公開日：2024年10月8日（PT）

* CSV ファイルオーディエンスをターゲティングする場合、パーソナライゼーションエディターや、ジャーニーおよびキャンペーンのルールビルダーで、ファイルの属性を使用できるようになりました。[詳細情報](../audience/about-audiences.md)

* カスタムアップロード（CSV ファイル）からのオーディエンスおよび属性を、Healthcare Shield またはプライバシーとセキュリティシールドで使用できるようになりました。

**設定** - 公開日：2024年10月23日（PT）

* キャンペーンやジャーニーでパーソナライズされた設定を使用する際に、メールコンテンツをプレビューし、定義した動的設定で潜在的なエラーを確認できるようになりました。[詳細情報](../email/surface-personalization.md#check-configuration)

**コードベースのチャネル**

* コンテンツテンプレートが使用できるようになりました。開発者が作成したコンテンツ テンプレートから始めることで、コードベースのエクスペリエンスの作成を高速化できます。コンテンツテンプレートを使用すると、マーケターは HTML または JSON コンテンツペイロード全体を作成するのではなく、一部の値やフィールドを変更するだけで済みます。[詳細情報](../content-management/content-templates.md)

**決定**

* [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) ユーザーは、決定（旧称エクスペリエンス決定）で AI モデルを設定する際に、最適化するカスタムモデルを選択できるようになりました。これにより、例えば、クリックスルー率などの定義済みの制約ではなく、カスタムの「購入数」テーブルを最適化できます。[詳細情報](../experience-decisioning/ranking.md)

* 決定を使用してコードベースのキャンペーンに決定ポリシーを追加する際に、選択戦略に加えて、単一の決定項目を手動で選択できるようになりました。さらに、複数のフォールバックオファーを選択できるようになりました。これにより、一定数の決定項目が返されることが保証されます。[詳細情報](../experience-decisioning/create-decision.md)



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
<th><strong>AI アシスタント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メッセージを作成してパーソナライズしたら、Journey Optimizer の AI アシスタントを使用してコンテンツを次のレベルに引き上げます。AI アシスタントを使用して様々なメインタイトルや画像を試すことで、メッセージの影響を最適化できるようになりました。各バリアントは独自の処理として管理され、より効果的にクリックを生成するタイトルを測定および比較します。</p>
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

<!--
![Newsletter](../assets/do-not-localize/nl-icon.png) Sign up for the [Adobe Journey Optimizer quarterly newsletter](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target="_blank"} today, and receive the latest product updates, exciting stories, use cases, tips and more delivered directly to your inbox every quarter.-->



## 2024年8月リリース {#8-2024}

**リリース日**：2024年8月20日～21日（PT）

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

**プッシュチャネル**

* Adobe Journey Optimizer チャネル設定内でモバイルアプリケーションプッシュ資格情報を追加できるようになりました。Adobe Experience Platform データ収集でのアプリサーフェスの作成は不要になりました。

### その他の変更 {#changes}

**レポート**

* 新しいレポートエクスペリエンスに次の新しいユースケースが追加されました。

   * レポート内でカスタム計算指標を直接作成。
   * レポートデータからオーディエンスを作成。
   * 探索的分析ツールを使用すると、選択した&#x200B;**[!UICONTROL ディメンション]**&#x200B;と&#x200B;**[!UICONTROL 指標]**&#x200B;からテーブルとビジュアライゼーションを簡単に作成できます。

  詳しくは、[詳細なドキュメント](../reports/report-cja-manage.md)を参照してください。



## 2024年7月リリース {#24-7-2024}

**リリース日**：2024年7月30～31日（PT）

### 新機能 {#27-4-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>任意のプロバイダーでの SMS チャネル（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>デフォルトのプロバイダーである Sinch、Infobip、Twilio に加えて、Journey Optimizer 内で追加の SMS プロバイダーを設定できるようになりました。</p>
<img src="assets/do-not-localize/byo_sms.gif"/>
<p>詳しくは、<a href="../sms/sms-configuration-custom.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>連合オーディエンス構成（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>連合オーディエンス構成が Adobe Journey Optimizer で使用できるようになりました。これを使用すると、企業は様々なユースケースでの稼動率を高めるデータを作成できます。この新しいアプローチでは、Adobe Real-time Customer Data Platform または Adobe Journey Optimizer のユーザーとして、既存のデータウェアハウスからデータセットを直接統合して、Adobe Experience Platform オーディエンスと属性をすべて 1 つのシステムで作成および強化できます。</p>
<p>詳しくは、 <a href="https://experienceleague.adobe.com/ja/docs/federated-audience-composition/using/home"  target="_blank">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化 {#27-4-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**ジャーニー**

* （提供日：7月8日（PT）**ジャーニーイベント設定の高度な式エディター** - イベントを設定する際に高度な式エディターを活用できるようになりました。これにより、さらに複雑な式を定義したり、イベント ID 条件で関数を使用したりできます。[詳細情報](../event/about-creating.md#adv-exp-editor)



## 2024年6月リリース {#24-6-2024}

**リリース日**：2024年6月18～19日（PT）

### 新機能 {#june-24-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>コンテンツフラグメントのカスタマイズ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>フラグメントをキャンペーンまたはジャーニーに追加する際に編集できる、フラグメント内に特定のフィールドを定義できるようになりました。これにより、使用時にコンテンツ部分を調整でき、コンテキスト固有の詳細でデフォルト値を柔軟に上書きできます。</p>
<img src="../content-management/assets/do-not-localize/gif-fragments.gif"/>
<p>詳しくは、<a href="../content-management/customizable-fragments.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Customer Journey Analytics を使用したレポート（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer レポートでは、Customer Journey Analytics 機能との相互運用性が改善され、両方のプラットフォーム間でレポートが標準化され、データの一貫性と信頼性が向上します。Journey Optimizer と Customer Journey Analytics のシームレスな統合により、パフォーマンス指標がより明確に表示され、ユーザーはより情報に基づいた意思決定を行うことができます。</p>
<img src="assets/do-not-localize/ajo-cja.gif"/>
<p>詳しくは、<a href="../reports/report-gs-cja.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Adobe Journey Optimizer の AI アシスタント</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントは、アドビのコンセプトをナビゲートして理解し、特定の環境の運用上のインサイトを得るために使用できるユーザーインターフェイス機能です。Adobe Journey Optimizer を含む Adobe Experience Cloud 全体の複数の製品で使用できます。</p>
<p>詳しくは、<a href="../start/ai-assistant.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーとキャンペーンでの多言語メッセージ（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>1 つのキャンペーンまたはジャーニー内で複数の言語のコンテンツを簡単に作成できるようになりました。この機能を使用すると、キャンペーンやジャーニーを編集する際に言語を切り替え、編集プロセス全体を効率化し、多言語コンテンツを効率的に管理する機能を向上させることができます。</p>
<p>多言語コンテンツは現在、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ジャーニーでの実験（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer は、キャンペーンで既に使用可能で、ジャーニーでの実験をサポートするようになりました。実験はランダム化試験です。オンラインテストのコンテキストでは、ランダムに選択された一部のユーザーにはメッセージの特定のバリエーションを表示し、別のランダムに選択された一連のユーザーには別のバリエーションや処理を行うことを意味します。公開後、メールの開封数、購読数、購入数など、興味のある結果指標を測定できます。</p>
<p>ジャーニーでの実験は現在、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>

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

#### 意思決定管理

* **意思決定管理でのマルチルールのサポート** - 意思決定管理で、特定のオファーに対して最大 10 個のキャッピングルールを追加できるようになりました。これにより、オファーの送信方法に対する制御レベルを強化できます。[詳細情報](../offers/offer-library/add-constraints.md#capping)

<!--* **Audits** - The **Change log** tab allowing you to see all the changes that have been made to an offer or a decision has been removed. Changes related to offers and decisions can now be seen in the **Audits** menu. -->

#### コンテンツフラグメント

>[!AVAILABILITY]
>
>これらの機能強化は、初回リリース後の数日間にわたって段階的にロールアウトされる予定です。即時にアクセスできるユーザーもいれば、自身の環境で使用できるようになるまでに遅延が生じるユーザーもいます。

* フラグメントを編集し、フラグメントが使用されているすべてのライブジャーニーとキャンペーンに変更を反映できるようになりました。
* コンテンツフラグメントの新しいステータス（**ドラフト**、**ライブ**、**公開**、**アーカイブ済み**）が導入されました。
* ジャーニーまたはキャンペーンでフラグメントを使用するには、フラグメントが&#x200B;**ライブ**&#x200B;ステータスになっている必要があります。フラグメント作成プロセスに新しい手順が追加され、フラグメントを公開して、ジャーニーやキャンペーンで使用できるようになりました。フラグメントの公開には、新しい権限が必要になります。

  **注意** - **ドラフト**&#x200B;および&#x200B;**ライブ** ステータスは Journey Optimizer の 6 月リリースで導入されたので、このリリースより前に作成されたすべてのフラグメントは、ジャーニーやキャンペーンで使用された場合でも、**ドラフト**&#x200B;ステータスになります。これらのフラグメントに変更を加えた場合は、[それらを公開](../content-management/create-fragments.md#publish)して「ライブ」にし、関連するキャンペーンとジャーニーにその変更を生成する必要があります。また、新しいジャーニー／キャンペーンのバージョンを作成し、公開する必要もあります。

詳しくは、[コンテンツフラグメント](../content-management/fragments.md)ドキュメントを参照してください。

#### ジャーニー

* ジャーニーのグローバルタイムアウトが 91 日間に延長されました。[詳細情報](../building-journeys/journey-properties.md#global_timeout)

  新しく作成したジャーニーには、この新しいタイムアウトが反映されます。この [FAQ の節](../building-journeys/journey-properties.md#timeout-faq)を参照してください。これらの変更は 6 月中に段階的にロールアウトされることに注意してください。


* Adobe Journey Optimizer は、プライバシーの削除／アクセスリクエストと、データライフサイクル管理リクエストもサポートするようになりました。[詳細情報](../privacy/requests.md)
* ジャーニーインベントリの列のサイズを変更できるようになりました。
  <!--* **Advanced expression editor in Event configuration** is now GA - You can now leverage the advanced expression editor while configuring an event, allowing you to define more complex expressions or use functions in the event id condition. This capability is released in Limited Availability for selected customers. [Read more](../event/about-creating.md)-->
* **結合ポリシー**（GA）- ジャーニーで使用される結合ポリシーがジャーニー全体で表示され、一貫性が保たれるようになりました。[詳細情報](../building-journeys/journey-properties.md#merge-policies)


#### キャンペーン

* Adobe Journey Optimizer でキャンペーンを作成する際、新しいモーダルでキャンペーンのタイプ（スケジュール済みまたはトリガー済み）を選択できるようになりました。[詳細情報](../campaigns/create-campaign.md)

#### メールチャネル

* **リスト登録解除** - Gmail および Yahoo が最近一括送信者向けに発表した内容に伴い、Journey Optimizer では「投稿／ワンクリック」のリスト登録解除オプションをサポートしています。詳しくは、[メールオプトアウトの管理](../email/email-opt-out.md#unsubscribe-header)および[メール設定](../email/email-settings.md#list-unsubscribe)のページを参照してください。

  **メモ** - 新しいチャネルサーフェスでは、デフォルトでリスト登録解除ヘッダーオプションがアクティブ化されます。既存のサーフェスの場合、デフォルトでは、チャネルサーフェス設定のワンクリック登録解除 URL オプションはオフになっています。以前、メール本文でワンクリックオプトアウト URL を使用していた場合、この設定は引き続き有効です。リスト登録解除チャネルサーフェス設定のワンクリック登録解除 URL がオンになっている場合、Adobe Journey Optimizer では、チャネルサーフェス設定のデフォルトで生成されたワンクリック登録解除 URL を使用します。

#### SMS チャネル

* 1 回の API 設定で各サンドボックスに一意のショートコードを追加できるようになりました。これにより、プロセスが合理化され、効率が上がります。[詳細情報](../sms/sms-configuration.md)

* 作成後、**API 資格情報の詳細**&#x200B;ページの「**API トークン**」フィールドがマスクされます。

<!--* You can now modify existing SMS configurations.-->

#### アプリ内チャネル

<!--* **Expression fragment** - Expression fragments are now available for the **In-app channel**. [Read more](../personalization/use-expression-fragments.md)-->

* これで、Edge Delivery プラグインを使用して、インバウンド実装を理解し、トラブルシューティングに必要な情報を取得できます。[詳しくは、Edge Delivery ビューを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery){target="_blank"}。


#### ダイレクトメールチャネル

* すべてのお客様がダイレクトメールチャネルを利用できるようになりました。[詳細情報](../direct-mail/get-started-direct-mail.md)



## 2024年5月リリース {#may-2024}

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
<p>これらの決定項目は、Journey Optimizer キャンペーン内でアクセス可能になった新しいコードベースのエクスペリエンスチャネルを通じて、幅広いインバウンド設定にシームレスに統合されます。エクスペリエンス決定ポリシーは、コードベースのエクスペリエンスキャンペーンでのみ使用できます。</p>
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
<th><strong>メール設定のパーソナライゼーション - 限定提供</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール設定の柔軟性と制御を高めるために、メールチャネル設定を作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義できるようになりました。</p>
<p>メール設定のパーソナライゼーションは、現在一連の組織でのみ利用可能です（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
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
* **イベントのルックアップテーブル** - オブジェクトの配列内の属性を使用して関係が定義されている場合に、ルックアップデータセットのデータを活用できるようになりました。ルックアップ値はジャーニー（条件、カスタムアクションなど）とメッセージのパーソナライゼーションで利用できるようになります。[詳細情報](../event/experience-event-schema.md#relationships_limitations)
* **イベント設定の高度な式エディター**（LA）- イベントを設定する際に高度な式エディターを活用できるようになり、より複雑な式を定義したり、イベント ID 条件で関数を使用したりできるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。[詳細情報](../event/about-creating.md#adv-exp-editor)
* **結合ポリシー**（LA）- ジャーニーで使用される結合ポリシーがジャーニー全体で表示され、一貫性が保たれるようになりました。この機能は、一部のお客様を対象に限定提供でリリースされています。[詳細情報](../building-journeys/journey-properties.md#merge-policies)

**グローバライゼーション**

統一されたユーザーエクスペリエンスを提供するための継続的な取り組みの一環として、Adobe Experience Cloud 製品とアプリで使用される用語を統一します。これは、ドイツ語の用語「Titel」（オブジェクトの名前に関連する場合は「ラベル」に変更される）に影響します。変更は、UI とドキュメントで段階的にロールアウトされます。


## 2024年4月リリース {#apr-2024}

**リリース日**：2024年5月2日（PT）

### 新機能 {#apr-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>マルチメディアメッセージサービス（MMS）- すべてのプロバイダー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>SMS チャネルを使用すると、マルチメディアメッセージサービス（MMS）メッセージを送信して通信を強化し、画像、GIF またはビデオを顧客と共有できます。当初は Sinch でのみ利用可能でしたが、MMS は Infobip と Twilio でも利用できるようになりました。</p>
<img src="assets/do-not-localize/mms.gif"/>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーデザイナーとライブレポートの改善</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このリリースでは、ジャーニーのキャンバスユーザーインターフェイスが改善され、より直感的で効率的なユーザーエクスペリエンスを実現します。クリック数を減らすことで、ジャーニーキャンバスでアクティビティがより明確になり、より多くの情報が表示されます。</p>
<img src="assets/new-canvas3.gif"/>
<p>ジャーニーキャンバスデザインの改善に加えて、過去 24 時間のレポート指標をジャーニーキャンバスで直接確認できる機能を導入します。 </p>
<img src="assets/new-canvas6bis.png"/>
<p><strong>メモ</strong>：これらの変更は、4 月のリリース以降、すべての環境に徐々に展開されます。</p>
<p>詳しくは、 <a href="new-canvas.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!-- table>
<thead>
<tr>
<th><strong>AI Assistant - Experience Variant Generation - Beta</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Once you have created and personalized your message, take your content to the next level with the AI Assistant. You can now use the AI Assistant to optimize your message's impact by experimenting with different main titles, and images. Each variant is managed as a unique Treatment, to measure and compare which title effectively generates more clicks.</p>
</td>
</tr>
</tbody>
</table-->


<!--table>
<thead>
<tr>
<th><strong>Email Surface Personalization - Private beta </strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now define dynamic subdomains and personalized header parameters when creating email channel configurations, for increased flexibility and control over your email settings.</p>
</td>
</tr>
</tbody>
</table-->

### 機能強化 {#apr-improvements}

このリリースでは、以下に示す機能強化が含まれています。

<!--
* **Expression Fragments supported for Web and In-App**: Expression fragments are now available for the Web and In-app channels. 
-->


<!--
* **DULE for AJO channel configuration**: It is now possible to apply a label on certain profile attributes to restrict their usage inside a channel configuration through marketing actions.
-->


<!--
* **List-Unsubscribe updates**: Following on the recent Gmail and Yahoo announcements for bulk senders, Journey Optimizer supports the "post/1-click" List-Unsubscribe option. 
-->

**設定**

* チャネル設定レベルでマーケティングアクションを選択できるようになりました。設定で使用すると、顧客の環境設定に従うことができるよう、そのマーケティングアクションに関連付けられているすべての同意ポリシーが活用されます。[詳細情報](../action/consent.md#surface-marketing-actions)
* チャネル設定でオブジェクトレベルのアクセス制御を使用できるようになりました。[詳細情報](../configuration/channel-surfaces.md#create-channel-surface)
* チャネル設定でリストの登録解除を有効にする際に、他のすべてのソースからの同意を管理する方法に合わせて同意レベルを定義できるようになりました。[詳細情報](../email/email-settings.md#list-unsubscribe)

**コンテンツ管理**

* すべてのチャネルのコンテンツテンプレートをシミュレートできるようになりました。[詳細情報](../content-management/content-templates.md#test-templates)

**パーソナライゼーション**

* 新しい **toInt** ヘルパー関数が式エディターで使用できます。これらのタイプ（number、double、int、long、float、short、byte、boolean、string）のいずれかを整数に変換できます。[詳細情報](../personalization/functions/math.md#to-int)



## 2024年3月リリース {#mar-2024}

**リリース日**：2024年3月19～20日（PT）

### 新機能 {#mar-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>コードベースのエクスペリエンス</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しいコードベースのエクスペリエンスチャネルでは、Adobe Journey Optimizer を使用して、あらゆるインバウンドプロパティに対して高度なパーソナライゼーションとテストを行うことができ、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、IoT デバイスなど、多様なタッチポイントに合わせたエクスペリエンスをシームレスに配信できます。</p>
<P>主な機能は次のとおりです。</p>
<ul><li> ユニバーサルパーソナライゼーション：すべてのタッチポイントにわたってパーソナライズされたエクスペリエンスを拡張し、一貫性のある調整されたユーザージャーニーを保証します</li>
<li>きめ細かい編集精度：アプリまたは web ページ内の個々の場所で特定のコンテンツを編集します</li>
<li>汎用性の高い実装：サーバーサイド、API ベースまたは SDK ベースの実装方法をサポートし、開発環境とシームレスに統合します。</li></ul></p>
<p>詳しくは、 <a href="../code-based/get-started-code-based.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/code-based.gif"> 
</tr>
</tbody>
</table>

### 機能強化 {#mar-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**コンテンツテンプレート**

* **サムネール** - **グリッド表示**&#x200B;モードがコンテンツテンプレートに対して使用できるようになり、サムネールを表示して視覚的なアクセスが向上しました。現在、メール HTML コンテンツテンプレートのみがサポートされています。[詳細情報](../content-management/content-templates.md#template-thumbnails)

  >[!AVAILABILITY]
  >
  >この機能は、少数の顧客向けに限定提供（LA）でリリースされています。

**ジャーニー**

新しい中間ステータスが次のジャーニーオーサリングライフサイクルに追加されました。

* **ドラフト**&#x200B;ステータスと&#x200B;**ライブ**&#x200B;ステータスの間の&#x200B;**公開**&#x200B;ステータス
* **ライブ**&#x200B;ステータスと&#x200B;**停止**&#x200B;ステータスの間の&#x200B;**停止**&#x200B;ステータス
* **ドラフト**&#x200B;ステータスと&#x200B;**ドラフト（テスト）**&#x200B;ステータスの間の&#x200B;**テストモードのアクティブ化**&#x200B;または&#x200B;**テストモードの非アクティブ化**

ジャーニーが中間の状態にある場合は、読み取り専用です。[詳細情報](../building-journeys/journey-gs.md#filter)

## 2024年2月リリース {#feb-2024}

**リリース日**：2024年2月21～22日（PT）

### 新機能{#feb-features}

このリリースでは、以下に示す新機能が導入されています。


<table>
<thead>
<tr>
<th><strong>Web アプリ内メッセージ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい web アプリ内メッセージ機能を使用して、モーダルオーバーレイメッセージを通じてパーソナライズされたコンテンツを web サイトに直接表示できるようになりました。この機能により、web 訪問者と効果的に関わり、ユーザーインタラクション、定着率およびコンバージョン率を向上させることができます。<br/><br/></p>
<p>詳しくは、<a href="../in-app/create-in-app-web.md">詳細なドキュメント</a>を参照してください。<br></br></p>
<img src="assets/do-not-localize/web_inapp.gif">
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>マルチチャネルコンテンツテンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールに加えて、プッシュ、アプリ内、SMS およびダイレクトメールのチャネルでコンテンツテンプレートが使用できるようになりました。各チャネルには専用のテンプレートタイプがあります。メールの場合、コンテンツタイプを選択できるようになりました。これにより、件名をメールテンプレートの一部として保存できます。 <br/><br/></p>
<p>詳しくは、 <a href="../content-management/content-templates.md">詳細なドキュメント</a>を参照してください。<br></br></p>
<img src="assets/do-not-localize/multi-chan-templates.gif"> 
</tr>
</tbody>
</table>


### 機能強化 {#feb-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**オーディエンス**

* **シードリスト** - **シードリスト**&#x200B;の使用時にバリアントがサポートされるようになりました。シードアドレスは、同じメッセージのすべてのバリアント（コンテンツ実験の異なる処理など）のコピーを受信します。[詳細情報](../configuration/seed-lists.md)

以前はベータ版として提供されていましたが、現在は次の機能強化がすべてのユーザーに提供されています。

* **オーディエンスコンポジションを通じて作成されたオーディエンス**&#x200B;をターゲットにし、ジャーニーのエンリッチメント属性を活用できるようになりました。[詳細情報](../building-journeys/read-audience.md)

* **CSV ファイルからアップロードされたオーディエンス**&#x200B;を、ジャーニーやキャンペーンにターゲットできるようになりました。[詳細情報](../audience/about-audiences.md#segments-in-journey-optimizer)

  >[!AVAILABILITY]
  >
  >* オーディエンス構成とカスタムアップロード（CSV ファイル）からのオーディエンスと属性の使用は、現在、Healthcare Shield または Privacy and Security Shield では使用できません。
  >* **CSV ファイルからのオーディエンスアップロード**&#x200B;の機能強化は、初回リリース後の数日間にわたって段階的にロールアウトされる予定です。即時にアクセスできるユーザーもいれば、自身の環境で使用できるようになるまでに遅延が生じるユーザーもいます。

**ジャーニー**

* **ジャーニーをフィルタリング** - 既存の定義済み日付フィルターに加えて、**カスタム日付を使用してジャーニーインベントリをフィルタリング**&#x200B;できるようになりました。これにより、特定の日付、特定の月内、年間全体、指定した期間内に作成または公開されたジャーニーを表示することで、リストを絞り込むことができます。[詳細情報](../building-journeys/journey-gs.md#filter)
* **カスタムアクション** - **content-type** ヘッダーを更新できるようになりました。この新しい **content-type** は、JSON コンテンツを参照する必要があります。[詳細情報](../action/about-custom-action-configuration.md#url-configuration)
* **設定** - stepEvents のidentityMap 属性が事前に入力されるようになりました。プライマリ ID は「primary = true」として定義されます。[詳細情報](../reports/sharing-field-list.md)
* **ユーザーインターフェイス** - エクスペリエンスを向上させるために、ジャーニー画面の上部バーが再編成されました。様々な更新が行われるなか、ジャーニーのプロパティにアクセスできる「鉛筆」アイコンが、上部バーの左側、ジャーニー名の横に表示されるようになりました。[詳細情報](../building-journeys/journey-properties.md)

**SMS チャネル**

* **オプトイン／オプトアウトのキーワード** - SMS チャネルを設定する際に、環境設定に従って&#x200B;**オプトインおよびオプトアウトキーワード**&#x200B;をカスタマイズできるようになりました。Journey Optimizer は、これらの指定されたキーワードに基づいて応答をトリガーします。[詳細情報](../sms/sms-configuration.md)

**キャンペーン**

* **API トリガーキャンペーン** - API トリガーのキャンペーンをアクティブ化した後に生成される cURL コードが強化されました。メッセージで使用されるすべてのパーソナライゼーション（プロファイルとコンテキスト）変数が含まれるようになりました。[詳細情報](../campaigns/api-triggered-campaigns.md#execute)

**頻度ルール**

* メールとプッシュに加えて、SMS チャネルとダイレクトメールチャネルの頻度ルールを作成できるようになりました。頻度ルールでは、フリークエンシーキャップに達すると、過度に要求されたプロファイルをメッセージとアクションから自動的に除外します。[詳細情報](../configuration/rule-sets.md)

<!--**Decision management**

* **Capping rules** - You can now add **multiple capping rules** for one offer. This allows you to increase the level of control over the way offers are sent.-->


## 2024年1月リリース {#jan-2024}

**リリース日**：2024年1月30～31日（PT）

### 新機能{#jan24-features}

このリリースでは、以下に示す新機能が導入されています。

<table>
<thead>
<tr>
<th><strong>配信品質のアップデート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer は、DMARC 認証テクノロジーをサポートするようになりました。</p>
<p>2024年2月1日（PT）以降、Google と Yahoo! は、メールの送信に使用するドメインの DMARC レコードを要求します。Journey Optimizer でアドビにデリゲートしたすべてのサブドメインや、デリゲート中のすべてのサブドメインに対して、DMARC レコードが設定されていることを確認してください。</p>
<p>詳しくは、<a href="../configuration/dmarc-record-update.md">詳細なドキュメント</a>を参照してください。</p>
<br/><img src="assets/do-not-localize/dmarc.gif"/>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ユースケースプレイブック</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Real-Time CDP と Journey Optimizer における業界固有のユースケースプレイブックのカタログを活用し、Adobe Experience Platform と Adobe Journey Optimizer を使用して実行できる一般的なユースケースに対処します。</p><p>ニーズに最適なプレイブックを選択したら、それを有効にして、ジャーニー、メッセージ、スキーマ、セグメントなどのユースケースをサポートするために必要なアセットを生成し、スキーマに合わせてカスタマイズして価値実現までの時間を短縮できます。</p>
<p>詳しくは、 <a href="../start/playbooks.md">詳細なドキュメント</a>を参照してください。</p>
<br/><img src="assets/do-not-localize/playbooks.gif"/>
</tr>
</tbody>
</table>

### 機能強化 {#jan24-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**レポート**

* **新しいドメインベースの分類ウィジェット** - キャンペーンレポートとジャーニーレポートを強化するための新しいウィジェットが追加されました。**ドメイン別のバウンス理由**、**ドメイン別に送信および配信済み**、**ドメイン別の開封数およびクリック数**&#x200B;および&#x200B;**ドメイン別のバウンス数およびエラー数**&#x200B;ウィジェットは、主なメール配信とトラッキング指標のドメインレベルでの詳細な分類を提供します。[詳細情報](../reports/channel-report-cja.md)

**SMS チャネル**

* **ダブルオプトイン** - SMS のダブルオプトインワークフローでは、デバイスからリクエストが開始された際に、ユーザーがメッセージの受信を明示的にオプトインすることが保証されます。ユーザーは、インバウンド SMS メッセージを送信して同意プロセスを開始します。同意を確認すると、最終検証をリクエストするフォローアップメッセージが送信されます。ユーザープロファイルが存在しない場合は、確認が成功すると作成されます。[詳細情報](../sms/sms-configuration.md)

  この機能は、Sinch および Infobip の SMS プロバイダーで使用できます。

**ジャーニー**

* **反応イベントの期間** - **反応イベント**&#x200B;で定義できる最大期間は、30 日ではなく 29 日になりました。[詳細情報](../building-journeys/reaction-events.md)

<!--* **Date filters** - You can now use custom dates to filter the journeys inventory, in addition to the existing predefined date filters. This allows you to refine the list by displaying journeys published on a specific date, within a particular month, throughout an entire year, or within specified time ranges. [Learn more](../building-journeys/journey-gs.md#filter)-->

* **オーディエンスを読み取り** - 「**オーディエンスを読み取り**」アクティビティは、バッチセグメントのプロファイルスナップショットデータセットに依存するようになりました。このデータセットは、スケジュールされた日次バッチジョブの実行後に 1 日に 1 回のみ生成されます。そのため、データは前回の日次バッチジョブの時点での最新になります。[詳細情報](../building-journeys/read-audience.md)

* **フィールドグループ** - このリリースでは、特定の場合にフィールドグループの保存がブロックされていた問題が修正されています。

* `<listObject>` のサポートは、複数の機能で変更されました。

**頻度ルール**

* **週別のフリークエンシーキャップ** - 顧客プロファイルに送信するメッセージの最大数を、月に加えて、1 週間あたりに指定できるようになりました。フリークエンシーキャップは、選択したカレンダー期間に基づき、対応する時間枠の開始時にリセットされます。[詳細情報](../configuration/rule-sets.md)

  >[!NOTE]
  >
  >また、日別のフリークエンシーキャップは、オンデマンドでも使用可能です。アドビ担当者にお問い合わせください。

**意思決定管理**

* **Edge でのフリークエンシーキャップ** - フリークエンシーキャップカウンターが更新され、3 秒未満で Edge Decisioning API の決定で使用できるようになりました。[詳細情報](../offers/api-reference/offer-delivery-api/start-offer-delivery-apis.md)
