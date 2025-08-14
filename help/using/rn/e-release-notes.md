---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 75c3db704853b8d2d8920ddd0086681d1fb02a93
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 32%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。


## 2025 年 8 月のプレリリースノート {#25-8-rn}

**以下のプレリリースノートは、リリースの公開日まで予告なく変更される場合があります**。 リンク、画面、更新されたドキュメントは、リリース日にリリースノートに公開されます。

[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**：2025年8月19日（PT）


### 新機能 {#Aug-25-8-features}

<table>
<thead>
<tr>
<th><strong>ジャーニーの一時停止と再開</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>これで、ジャーニーを一時停止して再開できるようになりました。この機能により、顧客体験を止めずにライブジャーニーを一時中断できるので、ジャーニー実務担当者はより優れた制御と柔軟性を得ることができます。一時停止すると、通信は送信されず、ジャーニーが再開されるまでプロファイルは中断状態のままになります。</p>
<p>1 つのジャーニーのみを一時停止および再開することや、ジャーニーのグループに対して一括で一時停止および再開の操作を実行することができます。</p>
<p>さらに、一時停止したジャーニーにグローバルフィルターを適用して、属性に基づいてプロファイルを除外できます。</p>
<p><!--img src="assets/do-not-localize/PauseResume.gif"/>--></p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-pause.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カレンダー表示</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーとキャンペーンのリストでカレンダー表示を使用できるようになりました。これにより、すべてのジャーニーとキャンペーンのアクティベーションをそれぞれのリストで視覚化できます。</p>
<p>この機能は、以前は限定提供でしたが、現在はすべての環境で使用できるようになりました。この一般提供リリースでは、この機能には次のものが含まれます。</p>
<ul>
<li>日付のナビゲーションのデザインの改善、</li>
<li>開始日と終了日を設定した場合に、ドラフトキャンペーンを表示する機能。</li>
<li>実行されているカレンダー項目の表示/非表示を長時間切り替える新しい設定です。</li>
</ul>
<p><!--img src="assets/do-not-localize/calendar.gif"/>--></p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-ui.md#journeys-calendar">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Dark mode in the Email Designer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Journey Optimizer Email Designer now offers the ability to switch to dark mode view, where you can additionally define specific custom settings that will display only for recipients reading their emails in dark mode.</p>
<p>Note the following:</p>
<ul>
<li>The dark mode final rendering may vary and depends on the recipient's email client.</li>
<li>Not all email clients support custom dark mode. Moreover, some email clients only apply their own default dark mode for all emails that are received. In both cases, the custom settings that you defined in the Email Designer cannot be rendered.</li>
</ul>
<P>This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.</p>
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>For more information, refer to the <a href="../email/dark-mode.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform データをパーソナライゼーションに使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>パーソナライゼーションエディターで Adobe Experience Platform のデータを利用して、コンテンツをパーソナライズします。これを行うには、まず、API 呼び出しを通じて参照パーソナライゼーションに必要なデータセットを有効にする必要があります。完了したら、そのデータを使用して、コンテンツを [!DNL Journey Optimizer] にパーソナライズできます。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できます。この一般提供リリースでは、次の機能強化が導入されました。</p>
<ul>
<li>インバウンドチャネルのサポート、</li>
<li>式およびビジュアルフラグメント内で「datasetLookup」ヘルパー関数を使用して、Adobe Experience Platform データセットのデータを使用してコンテンツをパーソナライズできるようになりました。</li>
<li>データセット内のオプションを使用すると、API 呼び出しを実行しなくても、データセットで参照パーソナライゼーションを有効にできるようになりました。</li>
</ul>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Use Decisioning in email channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now add Decision policies into email journeys and campaigns. Decision policies are containers for your offers that leverage the Decisioning engine to dynamically return the best content to deliver for each audience member.</p>
<p>Previously released in Limited Availability, this capability is now available to all environments (General Availability).</p>
<p><img src="assets/do-not-localize/FILE.gif"/></p>
<p><For more information, refer to the <a href="../FILE.md">detailed documentation</a></p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerに追加されたツールを使用すると、AI および実験フレームワークを活用してジャーニーを最適化しながら、条件と最適化機能のシームレスな操作性と差別化を実現できます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーのアクションアクティビティ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerで新しい汎用アクションアクティビティがサポートされ、単一アクションと複数アクションのインバウンドアクショングループの両方を設定でき、ジャーニーキャンバス内でアクションの設定を合理化できます。 特に、この新機能により、次のことが可能になります。</p>
<ul>
<li>ジャーニーキャンバス内のシンプルなネイティブアクション設定。</li>
<li>複数アクションのインバウンドノードを作成する処理能力。</li>
<li>組み込みのチャネルアクションに最適化を追加する機能。</li>
<li>任意のアクションに実験オプションと多言語オプションの両方を追加する機能。</li>
</ul>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ランディングページのカスタムフォーム</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでカスタムフォームを作成し、ランディングページで活用して、フォームごとに定義されたデータセットにプロファイル属性を取り込むことができるようになりました。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><!--This capability is currently in beta version and only available to beta customers. To join the beta program, contact your Adobe representative.--></p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#Aug-25-8-improv}

このリリースに含まれる機能強化を以下に示します。

* **管理**

   * **Channel Configuration Monitoring アラート** - チャネルコンフィギュレーションエラーが発生した場合や DNS レコードが見つからない場合に、システムアラートをメールまたはJourney Optimizer通知センターで受け取るよう登録できるようになりました。

* **キャンペーン**

   * **アウトバウンドキャンペーンのレートコントロール** - アウトバウンドキャンペーン（メール、SMS、プッシュ通知）のスロットルレート制御を有効にして、ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムでの過負荷を防ぐことができるようになりました。

   * **アクションキャンペーンのスケジュール設定** - キャンペーンの日別、週別および月別のスケジューラーが更新され、精度が向上しました。 例えば、スケジュール間の週数や月数を設定し、実行日を定義して、特定の回数の発生後または特定の日付に停止することを決定できるようになりました。

   * **スケジュールされたトランザクションアクションキャンペーン** - スケジュールされたトランザクションアクションキャンペーンで、メール、SMS、プッシュチャネルを介してバッチ、オーディエンスベースのトランザクション通信を送信できるようになりました。

* **チャネル – プッシュ**

   * **プッシュ通知の有効期限** – 各プッシュ通知に有効期限を指定できるようになりました。これにより、特定の日付を過ぎると時間依存のメッセージ（ブラックフライデーセールなど）が送信されなくなるので、顧客に悪いエクスペリエンスを提供するのを防ぐことができます。

* **チャネル – メール**

   * **メールへのPDF添付ファイル** - Journey Optimizerで送信されるメールメッセージに静的PDF ファイルを添付できるようになりました。

* **チャネル - SMS**

   * **ファジーオプトアウト** – 有効にすると、「**ファジーオプトアウト**」オプションは、定義済みのオプトアウトキーワード（「CANCIL」など）に非常に似た受信メッセージを検出し、ユーザーの購読解除の意図を確認する確認返信を自動的に送信します。 定義済みのプロンプトで確認すると、購読は解除されます。

     **ファジーオプトアウト** は、Sinch および Infobip でのみ使用できます。

   * **SMS 接続の検証** - サンプルメッセージを指定されたデバイスに送信することで、Adobe Journey Optimizer内で SMS API 資格情報を簡単にテストおよび検証できるようになりました。

* **設定**

   * **動的ドメインのサポート** - Journey Optimizerでは、チャネル設定レベルでリストされる事前定義済みドメインのトラッキング URL でのパーソナライゼーションをサポートするようになりました。

   * **ワンクリック登録解除 URL でのカスタム属性のサポート** - Journey Optimizerを使用すると、Adobe以外で同意を管理している場合、メール設定に独自のワンクリック登録解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が購読解除リンクをクリックすると、Journey Optimizerによって、プロファイル固有のデフォルトのパラメーターが同意更新イベントに追加されます。

     ワンクリック購読解除リンクをさらにパーソナライズするために、同意イベントに追加するカスタム属性を定義できるようになりました。

* **決定**

   * **決定項目にフラグメントを添付** - Journey Optimizerでは、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで活用できる決定項目にフラグメントを添付する機能を提供するようになりました。

* **ジャーニー**

   * **ジャーニーの一括操作** - ジャーニーのリストから、複数の項目を選択できるようになりました。 選択すると、一度に 10 件までのジャーニーを一時停止または再開できます。
