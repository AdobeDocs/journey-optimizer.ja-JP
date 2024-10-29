---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 42b9bfcc9079570a047462c23001d102abda58c9
workflow-type: tm+mt
source-wordcount: '2000'
ht-degree: 40%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2024年10月先行リリースノート {#e-2024}

**リリース日**:2024 年 10 月 29～30 日

### 新機能 {#e-features}

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
<!--p>For more information, refer to the <a href="../content-management/gs-generative.md">detailed documentation</a>.</p>
<img src="assets/do-not-localize/ai-content.gif"/-->
</td>
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
<p>一般公開により、すべてのチャネルで多言語コンテンツにアクセスできるようになりました。 </p>
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

### 機能強化 {#e-improvements}

このリリースでは、以下に示す機能強化が含まれています。

**SMS チャネル**

>[!AVAILABILITY]
>
>次の機能強化は、Sinch プロバイダーと Infobip プロバイダーでのみ使用できます。

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

**コードベースチャネル**

* コンテンツテンプレートが使用できるようになりました。 開発者が作成したコンテンツテンプレートから始まる、コードベースのエクスペリエンスのオーサリングを高速化できます。 コンテンツテンプレートを使用すると、マーケターは、HTML全体や JSON コンテンツペイロードを構成するのではなく、一部の値やフィールドを修正するだけで済みます。

**判定**

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) Decisioning （旧称：Experience Decisioning）で AI モデルを設定する際に、最適化するカスタムモデルを選択できるようになりました。 これにより、例えば、クリックスルー率などの定義済みの制約ではなく、カスタムの「購入」テーブルを最適化できます。
