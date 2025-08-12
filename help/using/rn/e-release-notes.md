---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 6326e1e3056f41f1550ac785bcbf83af175b37cc
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 55%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。


## 2025年8月プレリリースノート {#25-7-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日に公開されます。

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
<li>日付でのナビゲーションのデザインの改善</li>
<li>開始日と終了日を設定した場合に、ドラフトキャンペーンを表示する機能</li>
<li>長期間実行されているカレンダー項目の表示と非表示を切り替える新しい設定</li>
</ul>
<p><!--img src="assets/do-not-localize/calendar.gif"/>--></p>
<p><!--For more information, refer to the <a href="../building-journeys/journey-ui.md#journeys-calendar">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>E メールデザイナーでのダークモード</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer E メールデザイナーに、ダークモード表示に切り替える機能が追加されました。この機能を使用すると、ダークモードでメールを読む受信者にのみ表示される特定のカスタム設定を定義できます。</p>
<p>次のことに注意してください。</p>
<ul>
<li>ダークモードの最終的なレンダリングは、受信者のメールクライアントに応じて異なります。</li>
<li>すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。さらに、一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードのみが適用されます。どちらの場合も、E メールデザイナーで定義したカスタム設定はレンダリングできません。</li>
</ul>
<P>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/dark-mode.gif"/>--></p>
<p><!--For more information, refer to the <a href="../email/dark-mode.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

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
<li>インバウンドチャネルのサポート</li>
<li>式およびビジュアルフラグメント内で「datasetLookup」ヘルパー関数を使用して、Adobe Experience Platform データセットのデータを使用してコンテンツをパーソナライズできるようになりました。</li>
<li>データセット内のオプションを使用すると、API 呼び出しを実行しなくても、データセットで参照パーソナライゼーションを有効にできるようになりました。</li>
</ul>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>メールチャネルでの決定の使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メールジャーニーとキャンペーンに決定ポリシーを追加できるようになりました。決定ポリシーは、配信する最適なコンテンツを各オーディエンスメンバーに応じて動的に返すことを目的に、決定エンジンを活用するオファーのためのコンテナです。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
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
<p>この機能は現在ベータ版で、ベータ版のお客様のみご利用いただけます。ベータ版プログラムに参加するには、アドビ担当者にお問い合わせください。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerに追加されたツールを使用すると、AI および実験フレームワークを活用してジャーニーを最適化しながら、条件と最適化機能のシームレスな操作性と差別化を実現できます。</p>
<p><!--img src="assets/do-not-localize/FILE.gif"/>--></p>
<p><!--For more information, refer to the <a href="../FILE.md">detailed documentation</a>--></p>
</td>
</tr>
</tbody>
</table>


### 機能強化 {#Aug-25-8-improv}

このリリースに含まれる機能強化を以下に示します。


- **キャンペーン**
   - **アウトバウンドキャンペーンのレートコントロール** - アウトバウンドキャンペーン（メール、SMS、プッシュ通知）のスロットルレート制御を有効にして、ランディングページやカスタマーケアプラットフォームなどのダウンストリームシステムでの過負荷を防ぐことができるようになりました。
   - **アクションキャンペーンのスケジュール設定** - キャンペーンの日別、週別および月別のスケジューラーが更新され、精度が向上しました。 例えば、スケジュール間の週数や月数を設定し、実行する日を定義して、特定の回数の発生後または特定の日付に停止することを決定できるようになりました。

- **管理**
   - **Channel Configuration Monitoring アラート** - チャネルコンフィギュレーションエラーが発生した場合や DNS レコードが見つからない場合に、システムアラートをメールまたはJourney Optimizer通知センターで受け取るよう登録できるようになりました。

- **チャネル – プッシュ**
   - **プッシュ通知の有効期限** – 各プッシュ通知に有効期限を指定できるようになりました。これにより、特定の日付を過ぎると時間依存のメッセージ（ブラックフライデーセールなど）が送信されなくなり、顧客に悪いエクスペリエンスを提供するのを防ぐことができます。

- **チャネル – メール**
   - **メールへのPDF添付ファイル** - Journey Optimizerで送信されるメールメッセージに静的PDF ファイルを添付できるようになりました。

- **設定**
   - **動的ドメインのサポート** - Journey Optimizerでは、チャネル設定レベルでリストされる事前定義済みドメインのトラッキング URL でのパーソナライゼーションをサポートするようになりました。
   - **ワンクリック登録解除 URL でのカスタム属性のサポート** - Journey Optimizerを使用すると、Adobe以外で同意を管理している場合、メール設定に独自のワンクリック登録解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が購読解除リンクをクリックすると、Journey Optimizerによって、プロファイル固有のデフォルトのパラメーターが同意更新イベントに追加されます。

     ワンクリック購読解除リンクをさらにパーソナライズするために、同意イベントに追加するカスタム属性を定義できるようになりました。

- **ジャーニー**
   - **ジャーニーのアクションアクティビティ** - Journey Optimizerでは、単一チャネルとマルチチャネルの両方のアウトバウンドアクションを設定でき、ジャーニーキャンバス内でのアクション設定を合理化できる、新しい汎用のアクションアクティビティをサポートしています。 この新しいアクティビティを使用すると、組み込みのチャネルアクションにターゲティングの最適化、実験、多言語言語のバリアントを追加することもできます。
   - **ジャーニーの一括操作** - ジャーニーのリストから、複数の項目を選択できるようになりました。 選択すると、一度に 10 件までのジャーニーを一時停止または再開できます。