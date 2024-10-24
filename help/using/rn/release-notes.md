---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 87cba1d13af7a80cfe3b37a7b79e5fdd95ee5521
workflow-type: tm+mt
source-wordcount: '3162'
ht-degree: 56%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。 [!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2024 年 10 月先行リリースノート {#24-10-rn}

>[!CAUTION]
>
>**以下の早期リリースノートは、リリース日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に公開されます。

**リリース日**:2024 年 10 月 29～30 日

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
<!--p>For more information, refer to the <a href="../content-management/gs-generative.md">detailed documentation</a>.</p>-->
<img src="assets/do-not-localize/ai-content.gif">
</td>
</tr>
</tbody>
</table>


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
<p>以前は複数の組織（LA）で使用できましたが、現在は、すべてのユーザー（GA）がメール設定を使用できます。</p>
<p>詳しくは、<a href="../email/surface-personalization.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/surface-perso.gif"/>
<p>公開日：2024 年 10 月 23 日（PT）</p>
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
<p>以前は一連の組織（LA）で使用できましたが、すべてのユーザーが承認ポリシーを使用できるようになりました（GA）。</p>
<p>詳しくは、<a href="../test-approve/gs-approval.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/approval.gif"/>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>メール設定のパーソナライゼーション（一般提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール設定の柔軟性と制御を高めるために、メールチャネル設定を作成する際に、動的なサブドメインとパーソナライズされたヘッダーパラメーターを定義できるようになりました。</p><p>キャンペーンやジャーニーでパーソナライズされた設定を使用すると、メールコンテンツをプレビューし、定義した動的設定で潜在的なエラーを確認できます。</p>
<p>以前は複数の組織（LA）で使用できましたが、現在は、すべてのユーザー（GA）がメール設定を使用できます。</p>
<p>詳しくは、<a href="../email/surface-personalization.md">詳細なドキュメント</a>を参照してください。</p>
</td>
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
<p>ジャーニーオプティマイザーで、CSV ファイルからアップロードされた、または手動で追加されたサンプル入力データを使用して、プレビューと配達確認の送信を行うことで、メールコンテンツの様々なバリアントをテストできるようになりました。 パーソナリゼーションのコンテンツで使用されるすべてのプロファイル属性は、システムによって自動的に検出され、テストで複数のバリアントを作成するのに使用できます。</p>
<p>この機能は、現在、ベータ版として利用できます。</p>
<!--<p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p>-->
</td>
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
<p>Journey Optimizer では、過剰な数のインタラクションで顧客が圧倒されるのを避けるために、キャンペーンとジャーニーの量とタイミングを管理することが不可欠です。Journey Optimizerには、競合の管理と優先順位付けのためのいくつかのツールが用意されるようになりました。</p><p><ul><li><b>ジャーニーのフリークエンシーキャップ </b>：ジャーニーに適用するルールセットを作成できるようになりました。1 日、1 週間または 1 か月あたりのプロファイルのジャーニー数を制限し、同時に実行される同時ジャーニーの数を制御できます。</li>
<li><b> 優先度スコア </b>：キャンペーンまたはジャーニーに 0 ～ 100 の範囲で優先度スコアを割り当てることができるようになりました。 数値が大きいほど、優先度が高くなります。2 つのキャンペーンまたはジャーニーアクションが同じチャネル設定を使用する場合、Journey Optimizerは優先度スコアが最も高いキャンペーンまたはジャーニーアクションを選択します。 キャンペーンのスコアが同じ場合は、最近変更が最も少なかったキャンペーンが選択されます。</li>
<li><b> 潜在的な競合の表示 </b>：ジャーニーとキャンペーンの新しい「潜在的な競合の表示」ボタンで、開始日、ターゲットオーディエンス、選択したチャネル設定など、他のジャーニーやキャンペーンとの重複を特定できるようになりました。</li>
<li><b>ジャーニーの判別 </b>：この新機能を使用すると、顧客にとって最も重要なジャーニーに優先順位を付けることができます。 顧客が今後予定されている優先度の高いジャーニーの対象になったときに、優先度の低いジャーニーへのエントリを抑制するルールを作成できます。</li></ul></p>
<!--<p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p>-->
<p>競合管理機能と優先管理機能は、一部のお客様のグループが限定提供で利用できます。 これらの機能は、今後、より多くのユーザーに徐々に展開される予定です。 これらの機能のキャンセル待ちに追加することに関心がある場合は、アカウントチームにお問い合わせください。</p>

</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Web デザイナーの非ビジュアル編集モード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerの web デザイナーの代わりに、非ビジュアルエディターを使用して web サイトに変更を追加できるようになりました。 これにより、ビジュアルエディターでページを開かずに、手動で変更を入力できます。
この非視覚編集モードは、web デザイナーでページを読み込むために必要なAdobe Experience Cloud Visual Helper などのブラウザー拡張機能をインストールできない場合に役立ちます。</p>
<!--p>For more information, refer to the <a href="../email/surface-personalization.md">detailed documentation</a>.</p-->
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
<p>以前は一連の組織（LA）で使用できましたが、ジャーニー内の実験をすべてのユーザーが使用できるようになりました（GA）。</p>
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
<p>以前は一連の組織（LA）で使用でき、Experience Decisioning と呼ばれていた決定は、すべてのユーザー（GA）が使用できるようになりました。 「決定項目」と呼ばれるマーケティングオファーの一元化されたカタログと高度な決定エンジンを提供することで、パーソナライゼーションを簡素化します。 このエンジンでは、ルールとランキング条件を活用して、最も関連性の高い決定項目を選択して各個人に表示します。 これらの決定項目は、コードベースのエクスペリエンスチャネルを通じて、様々なインバウンドサーフェスにシームレスに統合されます。</p>

<p>現時点では、Adobeの Healthcare Shield およびプライバシーとセキュリティシールド アドオン製品を購入したお客様は Decisioning を利用できません。</p>

<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>ルールセット （使用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>詳細なフリークエンシーキャッピングルールを作成し、ルールセットを通じてメッセージやジャーニーに適用できるようになりました。 この新しい機能を使用すると、過剰に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルルールを設定することで、オーディエンスがメッセージを受け取る頻度を制御できます。</p><p>また、1 日、1 週間、1 か月あたりのジャーニーの数を制限したり、同時に実行する同時ジャーニーの数を制御したりすることもできます。</p>
<p>ルールセットは、一部のお客様のグループに対して限定提供で利用できます。 これらの機能は、今後、より多くのユーザーに徐々に展開される予定です。 この機能のキャンセル待ちに追加することに関心がある場合は、アカウントチームにお問い合わせください。</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


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
<p>以前は複数の組織（LA）で使用できましたが、多言語メッセージをすべてのユーザーが使用できるようになりました（GA）。</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
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
<li>オーサリングに Da Vinci を、最適化と配信にAJOを使用することで、Journey Optimizerのお客様向けの実践者ワークフローを高速化します</li>
<li>Adobeデータを使用してダヴィンチモデルを最適化します。</li></ul></p>
<!--p>For more information, refer to the <a href="../code-based/get-started-code-based.md">detailed documentation</a>.</p-->
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
<p>2024 年 10 月 16 日（PT）以降に使用可能</p>
<p>Journey Optimizer レポートが一般提供（GA）され、Customer Journey Analytics機能との相互運用性が向上したことで、両方のプラットフォーム間でレポートが標準化され、データの一貫性と信頼性が向上しました。 Journey Optimizer と Customer Journey Analytics のシームレスな統合により、パフォーマンス指標をより明確に把握でき、より十分な情報に基づいた意思決定が可能になります。</p>
<p>一般提供になると、4 つの新機能が導入されます。シンプルな指標を作成する機能、オーディエンスを作成および公開する機能、Insight Builder を使用してアドホックな質問をする機能、主要な受信者に自動的にメールが送信されるレポートをスケジュールする機能です。</p>
<p>詳しくは、<a href="../reports/report-cja-manage.md">詳細なドキュメント</a>を参照してください。</p>
<img src="assets/do-not-localize/ajo-cja.gif">
<p>重要：現在のレポートエクスペリエンスは、2025 年 1 月をもって廃止されます。 この日以降、新しいレポートエクスペリエンスが標準となります。スムーズに移行できるように、新機能を理解しておくことをお勧めします。<a href="../reports/report-gs-cja.md">Journey Optimizer の新しいレポートインターフェイスの使用を開始する方法を学ぶ</a></p>
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
<p>2024 年 10 月 1 日（PT）から使用可能</p>
<p>コードベースのエクスペリエンスチャネルでは、Adobe Journey Optimizer を使用して、あらゆるインバウンドプロパティに対して高度なパーソナライゼーションとテストを行うことができ、web アプリ、モバイルアプリ、デスクトップアプリ、ビデオコンソール、TV 接続デバイス、スマート TV、キオスク、ATM、IoT デバイスなど、多様なタッチポイントに合わせたエクスペリエンスをシームレスに配信できます。コードベースのエクスペリエンスチャネルがジャーニーキャンバスで使用できるようになりました。</p>
<p>詳しくは、<a href="../code-based/create-code-based.md">詳細なドキュメント</a>を参照してください。</p>
<img src="../assets/do-not-localize/code-based-journey.gif"/>
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
<p>2024 年 10 月 1 日（PT）から使用可能</p>
<p>Web チャネルを使用すると、Adobe Journey Optimizer では、インバウンド web ジャーニーを通じて顧客に提供する web エクスペリエンスをパーソナライズできます。Web チャネルをジャーニーキャンバスで使用できるようになりました。</p>
<p>詳しくは、<a href="../web/create-web.md">詳細なドキュメント</a>を参照してください。</p>
<img src="../assets/do-not-localize/web-journey.gif"/>
</tr>
</tbody>
</table>

### 機能強化 {#24-10-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**SMS チャネル**

メッセージング機能を向上させるために、SMS の機能強化が導入されました。

* SMS キャンペーンおよびジャーニーに固有のキーワードを定義および管理して、よりパーソナライズされた効率的な通信を可能にできます。

* キーワードが認識されない場合は、デフォルトの SMS メッセージを作成して配信できます。

* SMS API チャネル設定を編集または削除できるようになりました。

<!--**Journeys**-->

<!--* **Path experiment in journeys** - With the journey path experiment, you can now define and track key metrics for your journey paths, allowing you to measure the impact of your activities and to provide clearer insights into your performance. -->

&lt;! —* **ライブジャーニーの最大数** - Journey Optimizerには、100 個ではなく 500 個のライブジャーニーというガードレールが実稼動用サンドボックスに追加されました。 ライブジャーニーの数は、ジャーニーキャンバスに表示されます。<!-- DOCAC-10977-->

**データセット**

* **有効期間ガードレール** - 2024 年 11 月 1 日（PT）より、有効期間（TTL）ガードレールが、新しいサンドボックスと新しい組織のJourney Optimizer システム生成データセットに次のようにロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、次の第 2 フェーズで既存の顧客サンドボックスにロールアウトされます。

  さらに 11 月 1 日（PT）以降、ストリーミングセグメント化では、トラッキングデータセットとフィードバックデータセットからの送信イベントと開始イベントの使用をサポートしなくなります。 この変更は、そのときのすべての顧客サンドボックスおよび組織に適用されます。 [詳細情報](../data/datasets-ttl.md)

* **カスタムアクションのパラメーター** （公開日：2024 年 10 月 3 日（PT）） – カスタムアクションで NULL およびオプションのパラメーターがサポートされるようになりました。 [詳細情報](../action/about-custom-action-configuration.md#define-the-message-parameters)

**レポート**

* **Experience Decisioning レポート** が使用できるようになりました。訪問者がエクスペリエンスとやり取りする方法に関する基本的なインサイトが提供されます。

**データガバナンスおよび同意ポリシー** - 公開日：2024年10月7日（PT）

* **データガバナンスポリシー**&#x200B;が、Journey Optimizer のすべてのチャネルで運用されるようになりました。Adobe Experience Platform でポリシーを作成したお客様の場合、これらはチャネル設定のセットアップの一環としてマーケティングアクションに適用されます。設定を使用してコンテンツを作成すると、すべてのパーソナライゼーションフィールドでデータガバナンス違反がないかを確認します。違反が見つかった場合、ジャーニーまたはキャンペーンを公開することはできません。[詳細情報](../action/action-privacy.md)

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

* コンテンツテンプレートが使用できるようになりました。 開発者が作成したコンテンツテンプレートから始まる、コードベースのエクスペリエンスのオーサリングを高速化できます。 コンテンツテンプレートを使用すると、マーケターは、HTML全体や JSON コンテンツペイロードを構成するのではなく、一部の値やフィールドを修正するだけで済みます。

**判定**

* [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) Decisioning （旧称：Experience Decisioning）で AI モデルを設定する際に、最適化するカスタムモデルを選択できるようになりました。 これにより、例えば、クリックスルー率などの定義済みの制約ではなく、カスタムの「購入」テーブルを最適化できます。

* Decisioning （旧称 Experience Decisioning）を使用したコードベースのキャンペーンに決定ポリシーを追加する際に、選択戦略に加えて、単一の決定項目を手動で選択できるようになりました。 さらに、複数のフォールバックオファーを選択できるようになりました。 これにより、返される決定項目の数が一定に保たれます。 [詳細情報](../experience-decisioning/create-decision.md)

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