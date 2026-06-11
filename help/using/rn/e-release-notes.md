---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
TQID: https://experienceleague.adobe.com/951PJzmmITN1nSUapVomlYnPws9pS0TosI1Gl3R9yL4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: a7b2bfc5-be71-4740-b371-76fa6be8df02
subfeature_v2:
  - id: eac3bd2c-b027-4dfa-80d2-0bd752ae4794
  - id: e437f8db-d1f7-44c0-bdc0-b0a361adc4c0
  - id: c4e1378f-bb85-43a2-8b7c-1623ad3b14b5
source-git-commit: a144c1518f1835495eaf27fa055b89a3bf8d5559
workflow-type: tm+mt
source-wordcount: 1706
ht-degree: 7%

---


# プレリリースノート {#e-release-notes}

Adobe Journey Optimizerでは、新機能、既存の機能の強化、バグ修正を継続的に提供します。 [リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

## 26年6月のプレリリースノート {#june-26-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。 変更が本番環境で公開されると、リンク、スクリーン、更新されたドキュメントが公開されます。 ほとんどの変更はリリース日に配信されますが、一部の変更は後でロールアウトされる場合があります。詳細については、各エントリに記載されている利用可能日を参照してください。

詳しくは、[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**: 2026年6月16日～17日

### ジャーニー {#june-26-journeys}

このリリースでは、次の機能と機能強化がジャーニーに提供されます。

* **ライブジャーニーの制限と新しいガードレールの増加** – 最大&#x200B;**200個のアクティブなジャーニー**&#x200B;を追加でき、以前の制限の100から増やすことができるようになりました。

* **ジャーニーヘッダーの開始日と終了日** - ライブジャーニーで開始日と終了日を設定すると、ライブステータスバッジの横にある&#x200B;**ジャーニーヘッダー**&#x200B;に表示されるようになりました。 表示されるラベルは、各日付が予定されているか、すでに経過しているかに基づいて適応します。

* **一時停止したジャーニーを直接停止または閉じる** - **一時停止**&#x200B;状態から直接&#x200B;**ジャーニーを停止するか、新しいエントリ**&#x200B;に閉じることができるようになりました。 以前は、一時停止したジャーニーを停止または閉じる前に、「ライブ」に再開する必要がありました。

<!--
* **Supplemental identifier support for external audiences** - Supplemental identifiers in journeys are now supported for external audiences, including audiences imported from a CSV file and audiences created with Federated Audience Composition. You can designate any non-identity attribute or non-person identity attribute from the audience as the supplemental ID, no schema labeling is required.
-->

### オーケストレーションキャンペーン {#june-26-oc}

このリリースのオーケストレーション済みキャンペーンには、次の機能と機能強化が導入されています。

<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンでのファイルアクティビティの読み込み</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションされたキャンペーンでは、最初にAdobe Experience Platformにファイルを取り込むことなく、<strong>CSVまたはTXT ファイル </strong>をターゲットオーディエンスとしてキャンペーンキャンバスに直接読み込むことがサポートされるようになりました。 ファイルデータは実行時に消費され、Adobe Experience Platform データセットとして保持されません。 ファイルの設定時に、列のマッピング、データタイプ、NULL処理、列ごとのエラーポリシーを定義できます。 これは、完全な取り込みパイプラインの構築が実用的ではないアドホック送信やパートナーリストキャンペーンをサポートしています。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>

* オーケストレーションされたキャンペーンのリレーショナルデータに対する&#x200B;**ループベースのパーソナライゼーション** - パーソナライゼーションエディターで、注文、アカウント、予約などのリレーショナルコレクションを繰り返し処理し、レコードごとに1つのコンテンツブロックを1つの電子メールまたはSMS内にレンダリングする&#x200B;**ループブロック**&#x200B;がサポートされるようになりました。 コレクションは、パーソナライゼーショントークンを使用してデータピッカーを通じて設定され、式の書き込みは必要ありません。

* **受信者とキャンペーンごとにメール送信者の詳細をパーソナライズ** – 統合されたキャンペーンでは、プロファイル属性またはリレーショナルデータを使用して、送信者名、送信者アドレス、返信先を含む&#x200B;**メールヘッダーフィールド**&#x200B;のパーソナライゼーションがサポートされるようになりました。 これにより、送信者の詳細では、単一の企業アドレスを介してすべての送信をルーティングするのではなく、各受信者に関連するアドバイザー、場所、またはブランチを反映できます。 ヘッダー値はチャネルレベルで設定でき、コンテキストデータを使用してキャンペーンごとに上書きすることで、より正確な制御が可能になります。

<!--
* **Target dimension simplification in Orchestrated campaigns** - The active **targeting dimension** is now shown on the workflow canvas, so you can see which dimension is used by a channel activity. The multi-entity segmentation flow is simpler as you no longer need a separate "Change dimension" activity. Moreover, you can now choose explicitly whether messages are sent at the profile level or at a secondary dimension level.
-->

### 決定 {#june-26-decisioning}

このリリースでは、次の機能がDecisioningに導入されます。

<table>
<thead>
<tr>
<th><strong>DecisioningでのAdobe Experience Manager コンテンツフラグメントの活用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Decisioningで<strong>Adobe Experience Manager コンテンツフラグメント </strong>を<strong>決定項目</strong>にマッピングし、決定ポリシー内でそれらを活用して、適切なフラグメントを適切な顧客にタイミングよく配信できるようになりました。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
</td>
</tr>
</tbody>
</table>

### チャネル {#june-26-channels}

このリリースでは、次の機能が導入されています。

<table>
<thead>
<tr>
<th><strong>カスタムアウトバウンドチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、<strong> カスタムチャネル </strong>を導入しました。これは、管理者がWeChat、Kakao Talk、Messenger、独自のプロバイダーなど、任意のアウトバウンド HTTP ベースのメッセージングチャネルを、ノーコードチャネルビルダーを介してJourney Optimizerに直接取り込めるようにするための新機能です。</p>
<p>一度設定されたカスタムチャネルは、キャンペーン、ジャーニー、オーケストレーションされたキャンペーンをまたいで利用でき、ネイティブチャネルと同じフルセットの機能を使用します。式エディターを使用したパーソナライゼーション、コンテンツの実験、プレビューとプルーフ、すぐに使えるレポート、同意とガバナンスの適用などです。 これにより、ジャーニーに限定されたカスタムアクションや、専用のコンテンツオーサリングに欠けていたカスタムアクションで以前に対処したギャップが埋まります。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
</td>
</tr>
</tbody>
</table>

### メール {#june-26-email}

このリリースでは、次の機能と機能強化がメールチャネルに導入されます。

<!--
<table>
<thead>
<tr>
<th><strong>Advanced Components</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>The Email Designer now includes a library of ready-to-use layout components — such as Headers, Product Cards (1, 2, or 3 columns), Information blocks, and Footers — that you can drag and drop directly into your email canvas. Each component comes pre-configured with editable properties (image, title, text, button, links) and can be fully customized through the WYSIWYG interface, speeding up email creation without requiring you to build structures from scratch.</p>
</td>
</tr>
</tbody>
</table>
-->

<table>
<thead>
<tr>
<th><strong>電子メールDesignerのコンテンツチェック</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、ユーザーがEmail Designer インターフェイス内で直接<strong> メールコンテンツ品質</strong>を検証できるようになりました（読みやすさ、有効性、コンテンツの一貫性など）。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>電子メールサイズの縮小を有効にする</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>この新しいオプションを使用すると、電子メールの外観を変えることなく、不要な空白、コメント、冗長なコードを削除して、電子メール内のHTML</strong>のサイズを<strong>縮小できます。 これにより、到達性の向上（一部のメールプロバイダーがサイズの大きすぎるメールを拒否またはフラグ付けする）と、受信者の読み込み時間の短縮に役立ちます。</p>
<p>ご利用いただけます：2026年6月10日（PT）</p>
</td>
</tr>
</tbody>
</table>

* **フラグメントの編集可能なフィールド内のリッチテキスト** - メールコンテンツで使用されるカスタマイズ可能なフラグメントにリッチテキストを追加できるようになりました。 例えば、電子メールDesignerでテキストコンポーネントを編集可能フィールドとして使用する場合、コンテンツの書式（太字や斜体など）を直接設定し、ハイパーリンクを挿入できます。

<!--
* **Text mode support in fragments** - To support text-based email workflows, you can now create and manage text versions of your visual fragments for optimal use in the plain text version of emails that include that fragment. When using a fragment that was created before the current release, the fragment text version may be incorrectly rendered — both in the Email Designer and in the final email delivered to your recipients. For best results with older fragments, edit, save and republish each fragment.
-->

### モバイルメッセージ（SMS、MMS、RCS、LINE） {#june-26-mobile}

このリリースでは、モバイルメッセージに次の改善が加えられています。

* **SMS レポートのユニーククリック数** - SMS レポートに新しい&#x200B;**ユニーククリック数** モジュールが導入され、現在メールレポートで使用できるSMSと同じレベルの詳細なパフォーマンストラッキングが実現されました。

* **LINE チャネル – オーサリングの変更** - LINE チャネル UIが高度なメッセージ オーサリング機能でアップグレードされました。 このリリースでは、テキスト、画像、Imagemap、カルーセル、Flex（JSON エディター）など、**複数のメッセージ形式**&#x200B;のサポートが導入され、リアルタイムのデバイスプレビューと共に提供されます。 ユーザーは、最大5つの順序付きメッセージ（追加、削除、並べ替えコントロールを使用）のグループ化されたメッセージを管理し、統合されたパーソナライゼーションエディターを使用して、検証済みの動的メッセージを作成できるようになりました。

* **SMS – 使用状況の指標を表示** - Adobe Journey Optimizerを通じて直接SMSを購入するお客様に対して、新しい&#x200B;**SMS使用状況ダッシュボード**&#x200B;が導入されました。 Mobile Originated （MO）およびMobile Terminated （MT）メッセージで分類された、過去90日間のメッセージ送信指標を表示および追跡できるようになりました。 このデータはCSVでダウンロードすることもでき、SMS費用の可視性と制御を強化します。

### コンテンツと統合 {#june-26-content}

このリリースでは、コンテンツ管理と統合に次の機能と機能強化が導入されています。

<table>
<thead>
<tr>
<th><strong>Journey OptimizerでのAdobe Experience Manager コンテンツフラグメントの機能強化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>このリリースでは、Journey Optimizer オーサリングワークフロー内で<strong>Adobe Experience Manager コンテンツフラグメント </strong>をより使いやすく、より制御しやすく、より実稼動対応にするための機能強化がいくつか追加されました。</p>
<ul>
<li>Journey Optimizerでは、オーサー、パブリッシュ、認証済みパブリッシュ層など、複数のAdobe Experience Manager設定からコンテンツフラグメントを取得できるようになりました。</li>
<li>フラグメントを選択すると、そのコンテキストはメッセージ全体を通じて保持されるので、作成者は再選択することなく、コンテンツブロック間でフラグメントフィールドを再利用できます。</li>
<li>新しい専用のコンテンツフラグメントリストページがJourney Optimizerに導入され、ライフサイクル管理が向上しました。同期されていないフラグメントを特定し、手動で同期をトリガーして最新の状態を維持できます。</li>
<li>ロケールとバリエーションのサポートにより、マーケターは同じコンテンツフラグメントの代替バージョンをより慎重に操作できるようになりました。</li>
<li>Adobe Journey OptimizerからAdobe Experience Manager コンテンツへのアクセス方法を柔軟に設定できるようになりました。 このリリースでは、ジャーニーとキャンペーンで使用するコンテンツフラグメントのソースリポジトリ </strong>を<strong>切り替える機能が導入されました。</li>
<li><b>Managed Services</b>との互換性を持つようになり、Adobe Experience Manager コンテンツフラグメントをJourney Optimizerで直接表示、アクセス、使用してパーソナライズできるようになりました。 Adobe Experience Manager Managed Servicesのリポジトリ URLを、1回限りの設定として設定に追加するだけです。</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ADOBE EXPERIENCE MANAGER Asset EssentialsのAI アシスタントとの統合</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントが、メール、Web ページ、プッシュ通知を生成する際に、Adobe Experience Manager Assetsから<b> ブランド承認済み画像</b>を直接自動的に取得するようになりました。 これにより、Assetsを手動で検索したり、汎用的なAI フォールバックを利用したりする必要がなくなり、あらゆるビジュアルが完全に正確で、ブランドに準拠したものになります。</p>
</td>
</tr>
</tbody>
</table>

### キャンペーン {#june-26-campaigns}

このリリースでは、キャンペーンに次の改善が加えられています。

* **キャンペーンのデフォルトの実行フィールドを上書き** – 以前はジャーニーレベルで使用されていましたが、キャンペーンのパラメーターで、メール、SMS、WhatsApp配信にグローバルに設定されたデフォルトの&#x200B;**実行フィールド**&#x200B;を上書きできるようになりました。

### レポート {#june-26-reporting}

このリリースでは、レポートに次の改善が加えられています。

* 電子メールとSMS レポートの推定クリック数&#x200B;**指標** - **推定クリック数**&#x200B;が、ジャーニー、キャンペーン、チャネル レポートで利用できるようになりました。 この指標は、特定されたボットと人間以外（NHI）のトラフィックを除外した後の合計クリック数を反映しており、真の顧客エンゲージメントをより明確に把握することができます。

+++ 近日リリース予定 – **以下の情報は変更される可能性があります。**

* **電子メールとSMS レポートの新しいクリック数値見積もり指標** – 実際の顧客エンゲージメントをより正確に把握するために、ジャーニー、キャンペーン、チャネル レポートで新しい見積もり指標を使用できるようになりました。 次の指標は、レポート情報から人間ではないインタラクション（NHI）やボットクリックを除外するのに役立ちます。

   * 推定CTR：合計配信数に対するクリック数の推定値。
   * メールの推定CTORのみ：推定開封数に対する推定クリック数。

  利用可能日：2026年6月下旬

+++

### 設定 {#june-26-configuration}

このリリースでは、設定と管理に次の機能強化が加えられています。

* **データセットがストリーミングモードからバッチモードに移行しています** - AJO Message Feedback Event データセットは、ストリーミングモードから&#x200B;**バッチ取り込みモード**&#x200B;に移行しています。 この変更により、データ取り込みがストリーミング取り込み制限を超えないことが保証されます。 このデータセットをCustomer Journey Analytics レポートで使用する場合や、このデータセットに対してクエリを実行する場合は、最大2時間のデータ遅延が発生すると予想されます。

+++ 近日リリース予定 – **以下の情報は変更される可能性があります。**

* **Web Application Firewall （WAF） IP ホワイトリストへの登録** - Adobe Journey Optimizerでは、ランディングページのWeb Application Firewall （WAF） IP ホワイトリストへの登録がサポートされるようになりました。これにより、組織は、すべての着信リクエストが設定されたWAF インフラストラクチャを通じてのみルーティングされるようにすることができます。 この機能強化により、お客様はJourney Optimizerを設定して、WAF レイヤーをバイパスするダイレクトリクエストを拒否し、Impervaなどのツールで定義されたセキュリティポリシーが一貫して適用されるようにすることができます。 この機能により、厳格なネットワークアクセス要件を持つ企業のセキュリティ体制が強化され、AJOでホストされているランディングページへのトラフィックフローを完全に制御できるようになります。

  利用可能日：2026年6月下旬

+++

### ユーザビリティの向上 {#june-26-usability}

このリリースでは、次の操作性の改善が行われています。

* **ジャーニーとキャンペーン用のフォルダー** - ジャーニーとキャンペーンを&#x200B;**フォルダー**&#x200B;に整理して、インターフェイスのナビゲーションと管理を改善できるようになりました。
