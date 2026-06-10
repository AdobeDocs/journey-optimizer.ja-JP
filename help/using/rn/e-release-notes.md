---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
TQID: https://experienceleague.adobe.com/951PJzmmITN1nSUapVomlYnPws9pS0TosI1Gl3R9yL4
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a7b2bfc5-be71-4740-b371-76fa6be8df02
subfeature_v2: id: eac3bd2c-b027-4dfa-80d2-0bd752ae4794id: e437f8db-d1f7-44c0-bdc0-b0a361adc4c0id: c4e1378f-bb85-43a2-8b7c-1623ad3b14b5
source-git-commit: d7d879286ccb9c2e4567bb70a8f78d34bd663c54
workflow-type: tm+mt
source-wordcount: 2035
ht-degree: 10%

---


# プレリリースノート {#e-release-notes}

Adobe Journey Optimizerでは、新機能、既存の機能の強化、バグ修正を継続的に提供します。 [リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

## 26年6月のプレリリースノート {#june-26-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。 変更が本番環境で公開されると、リンク、スクリーン、更新されたドキュメントが公開されます。 ほとんどの変更はリリース日に配信されますが、一部の変更は後でロールアウトされる場合があります。詳細については、各エントリに記載されている利用可能日を参照してください。

詳しくは、[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**: 2026年6月16日～17日


### ジャーニー {#june-26-journeys}

このリリースでは、次の機能と機能強化がジャーニーに提供されます。

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化 – ターゲティング</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>最適化アクティビティ </strong>は、<strong> ターゲティングルール </strong>をサポートするようになりました。 ターゲティングルールを使用すると、オーディエンスセグメントやプロファイル属性に基づいて、顧客が特定のジャーニーパスに対して選定するために満たす必要がある特定の基準を定義できます。</p>
<p>顧客がランダムにパスに割り当てられる実験とは異なり、ターゲティングでは決定論的ロジックを使用して、適切なオーディエンスまたは顧客プロファイルが目的のパスにルーティングされるようにします。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14720">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニー仲裁 – 数式</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>式</strong>を使用して、顧客プロファイル属性と文脈要因に基づいてジャーニーを自動的に<strong>優先順位付けおよび調停</strong>し、顧客が最も関連性の高いジャーニーに確実に参加できるようにできるようになりました。</p>
<p>この機能は、以前は限定提供でリリースされていましたが、現在はすべての環境で使用できるようになりました（一般提供）。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14719">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

* **ライブジャーニーの制限と新しいガードレールの増加** – 最大&#x200B;**200個のアクティブなジャーニー**を追加でき、以前の制限の100から増やすことができるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14826">DOCAC JIRA タスクへのリンク </a>

* **ジャーニーヘッダーの開始日と終了日** - ライブジャーニーで開始日と終了日を設定すると、ライブステータスバッジの横にある&#x200B;**ジャーニーヘッダー**に表示されるようになりました。表示されるラベルは、各日付が予定されているか、すでに経過しているかに基づいて適応します。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14702">DOCAC JIRA タスクへのリンク </a>

* **一時停止したジャーニーを直接停止または閉じる** - **一時停止**&#x200B;状態から直接&#x200B;**ジャーニーを停止するか、新しいエントリ**に閉じることができるようになりました。以前は、一時停止したジャーニーを停止または閉じる前に、「ライブ」に再開する必要がありました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14229">DOCAC JIRA タスクへのリンク </a>

* **外部オーディエンスの補足識別子のサポート** - ジャーニーの補足識別子が、CSV ファイルから読み込まれたオーディエンスやFederated Audience Compositionで作成されたオーディエンスなど、外部オーディエンスでサポートされるようになりました。オーディエンスからID以外の属性または個人ではないID属性を補足IDとして指定できます。スキーマのラベル付けは必要ありません。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14541">DOCAC JIRA タスクへのリンク </a>

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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14704">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>オーケストレーションされたキャンペーンのサイレントアワーのサポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>オーケストレーションされたキャンペーンに<strong> サイレントアワー</strong>を適用できるようになりました。 サイレントアワーを使用すると、<strong>時間ベースの除外</strong>を定義して、特定の期間にメッセージが送信されないようにすることができます。これにより、キャンペーンのオーケストレーションのユースケース全体で顧客の好みとコンプライアンス要件を尊重することができます。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14054">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

* オーケストレーションされたキャンペーンのリレーショナルデータに対する&#x200B;**ループベースのパーソナライゼーション** - パーソナライゼーションエディターで、注文、アカウント、予約などのリレーショナルコレクションを繰り返し処理し、レコードごとに1つのコンテンツブロックを1つの電子メールまたはSMS内にレンダリングする&#x200B;**ループブロック**がサポートされるようになりました。コレクションは、パーソナライゼーショントークンを使用してデータピッカーを通じて設定され、式の書き込みは必要ありません。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14703">DOCAC JIRA タスクへのリンク </a>

* **受信者とキャンペーンごとにメール送信者の詳細をパーソナライズ** – 統合されたキャンペーンでは、プロファイル属性またはリレーショナルデータを使用して、送信者名、送信者アドレス、返信先を含む&#x200B;**メールヘッダーフィールド**のパーソナライゼーションがサポートされるようになりました。これにより、送信者の詳細では、単一の企業アドレスを介してすべての送信をルーティングするのではなく、各受信者に関連するアドバイザー、場所、またはブランチを反映できます。ヘッダー値はチャネルレベルで設定でき、コンテキストデータを使用してキャンペーンごとに上書きすることで、より正確な制御が可能になります。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13761">DOCAC JIRA タスクへのリンク </a>

* オーケストレーションされたキャンペーンの&#x200B;**ターゲットディメンションの簡素化** - アクティブな&#x200B;**ターゲットディメンション**がワークフローキャンバスに表示されるようになりました。これにより、どのディメンションがチャネルアクティビティで使用されているかを確認できます。複数エンティティのセグメント化フローは、個別の「ディメンションの変更」アクティビティが不要になったため、よりシンプルになります。さらに、メッセージをプロファイルレベルとセカンダリディメンションレベルのどちらで送信するかを明示的に選択できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-13554">DOCAC JIRA タスクへのリンク </a>

* **キャンペーンのデフォルトの実行フィールドを上書き** – 以前はジャーニーレベルで使用されていましたが、キャンペーンのパラメーターで、メール、SMS、WhatsApp配信にグローバルに設定されたデフォルトの&#x200B;**実行フィールド**を上書きできるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14718">DOCAC JIRA タスクへのリンク </a>

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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14885">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

### メールチャネル {#june-26-email}

このリリースでは、次の機能と機能強化がメールチャネルに導入されます。

<table>
<thead>
<tr>
<th><strong>詳細コンポーネント – レイアウト（スーパーコンポーネント）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>メール Designerには、ヘッダー、商品カード（1、2、3列）、情報ブロック、フッターなど、すぐに使用できるレイアウトコンポーネント <strong> ライブラリが含まれるようになりました。これらのコンポーネントをメールキャンバスに直接ドラッグ&amp;ドロップできます。 </strong>各コンポーネントには編集可能なプロパティ（画像、タイトル、テキスト、ボタン、リンク）が事前に設定されており、WYSIWYGインターフェイスで完全にカスタマイズできるため、構造をゼロから構築する必要はなく、メール作成を高速化できます。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14877">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14870">DOCAC JIRA タスクへのリンク</a></p>
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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14777">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

* **フラグメントでのテキストモードのサポート** - テキストベースのメールワークフローをサポートするために、ビジュアルフラグメントの&#x200B;**テキストバージョン**を作成および管理して、そのフラグメントを含むメールのプレーンテキストバージョンで最適に使用できるようになりました。現在のリリースより前に作成されたフラグメントを使用すると、フラグメントテキストのバージョンが、電子メールのDesignerと受信者に配信された最終的な電子メールの両方で誤ってレンダリングされる可能性があります。古いフラグメントで最適な結果を得るには、各フラグメントを編集、保存、再公開します。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14204">DOCAC JIRA タスクへのリンク </a>

* **顧客向けシナリオを使用したバッチ送信スループットベンチマークを更新** - Adobe Journey Optimizerの&#x200B;**バッチ送信スループットベンチマーク**が更新され、基本的な送信から条件付きロジックを使用した複雑な動的コンテンツに至るまで、複数のパーソナライゼーションシナリオをまたいで実稼動用レベルのパフォーマンスを反映するようになりました。更新された指標は、顧客が正確にメッセージング量を計画するのに役立つ製品ドキュメントで利用できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14816">DOCAC JIRA タスクへのリンク </a>

* カスタムサブドメインの&#x200B;**フィードバックループ OTP プロセス** - Yahoo送信者ハブ **One-Time Password （OTP）**を製品UI内で直接表示することで、フィードバックループ （FBL） カスタムサブドメイン設定プロセスが改善されました。ユーザーは、Yahoo送信者ハブドメイン所有権の検証中に生成されたOTPを自動的に取得して表示できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14815">DOCAC JIRA タスクへのリンク </a>

### モバイルメッセージ（SMS、MMS、RCS、LINE） {#june-26-mobile}

このリリースでは、モバイルメッセージに次の改善が加えられています。

* **SMS レポートのユニーククリック数** - SMS レポートに新しい&#x200B;**ユニーククリック数** モジュールが導入され、現在メールレポートで使用できるSMSと同じレベルの詳細なパフォーマンストラッキングが実現されました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14895">DOCAC JIRA タスクへのリンク </a>

* **LINE チャネル – オーサリングの変更** - LINE チャネル UIが高度なメッセージ オーサリング機能でアップグレードされました。このリリースでは、テキスト、画像、Imagemap、カルーセル、Flex（JSON エディター）など、**複数のメッセージ形式**のサポートが導入され、リアルタイムのデバイスプレビューと共に提供されます。ユーザーは、最大5つの順序付きメッセージ（追加、削除、並べ替えコントロールを使用）のグループ化されたメッセージを管理し、統合されたパーソナライゼーションエディターを使用して、検証済みの動的メッセージを作成できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14869">DOCAC JIRA タスクへのリンク </a>

* **SMS – 使用状況の指標を表示** - Adobe Journey Optimizerを通じて直接SMSを購入するお客様に対して、新しい&#x200B;**SMS使用状況ダッシュボード**が導入されました。Mobile Originated （MO）およびMobile Terminated （MT）メッセージで分類された、過去90日間のメッセージ送信指標を表示および追跡できるようになりました。このデータはCSVでダウンロードすることもでき、SMS費用の可視性と制御を強化します。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14345">DOCAC JIRA タスクへのリンク </a>

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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14686">DOCAC JIRA タスクへのリンク</a></p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14821">DOCAC JIRA タスクへのリンク</a></p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14684">DOCAC JIRA タスクへのリンク</a></p>
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
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-14761">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

### カスタムチャネル {#june-26-channels}

このリリースでは、次の機能がチャネルに導入されます。

<table>
<thead>
<tr>
<th><strong>カスタムアウトバウンドチャネル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizerでは、<strong> カスタムチャネル </strong>が導入されました。これは、管理者が<strong> ノーコードチャネルビルダー</strong>を使用して、WeChat、Kakao Talk、Messenger、独自のプロバイダーなど、任意のアウトバウンド HTTP ベースのメッセージングチャネルをAJOに直接取り込めるようにするための新機能です。 一度設定されたカスタムチャネルは、キャンペーン、ジャーニー、オーケストレーションキャンペーンをまたいで利用でき、ネイティブチャネルと同じ機能をフルセットで利用できます。式エディターを使用したパーソナライゼーション、コンテンツの実験、プレビューとプルーフ、すぐに使えるレポート、同意とガバナンスの適用などです。 これにより、ジャーニーに限定され、専用のコンテンツオーサリングが不足していたカスタムアクションで以前に対処したギャップが埋まります。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。 アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><a href="https://jira.corp.adobe.com/browse/DOCAC-11381">DOCAC JIRA タスクへのリンク</a></p>
</td>
</tr>
</tbody>
</table>

### レポート {#june-26-reporting}

このリリースでは、レポートに次の改善が加えられています。

* **電子メールおよびSMS レポートの新しいクリック見積もり指標** – 実際の顧客エンゲージメントをより正確に把握するために、ジャーニー、キャンペーン、チャネル レポートで新しい見積もり指標を使用できるようになりました。 次の指標は、レポート情報から人間ではないインタラクション（NHI）やボットクリックを除外するのに役立ちます。
   * 推定クリック数：識別されたボットと人間ではないトラフィックを削除した後にカウントされた合計クリック数。
   * 推定CTR：合計配信数に対するクリック数の推定値。
   * メールの推定CTORのみ：推定開封数に対する推定クリック数。

  <a href="https://jira.corp.adobe.com/browse/DOCAC-14354">DOCAC JIRA タスクへのリンク </a>

### 設定 {#june-26-configuration}

このリリースでは、設定と管理に次の機能強化が加えられています。

* AJO ランディングページの&#x200B;**Web Application Firewall （WAF） IP ホワイトリスト作成** - Adobe Journey Optimizerは、ランディングページの&#x200B;**Web Application Firewall （WAF） IP ホワイトリスト作成**をサポートするようになりました。これにより、組織は、すべての着信リクエストが設定されたWAF インフラストラクチャを通じてのみルーティングされるようにすることができます。この機能強化により、お客様はAJOを設定して、WAF レイヤーをバイパスするダイレクトリクエストを拒否し、Impervaなどのツールで定義されたセキュリティポリシーが一貫して適用されるようにすることができます。この機能により、厳格なネットワークアクセス要件を持つ企業のセキュリティ体制が強化され、AJOでホストされているランディングページへのトラフィックフローを完全に制御できるようになります。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14814">DOCAC JIRA タスクへのリンク </a>

* **データセットがストリーミングモードからバッチモードに移行しています** - AJO Message Feedback Event データセットは、ストリーミングモードから&#x200B;**バッチ取り込みモード**に移行しています。この変更により、データ取り込みがストリーミング取り込み制限を超えないことが保証されます。このデータセットをCustomer Journey Analytics レポートで使用する場合や、このデータセットに対してクエリを実行する場合は、最大2時間のデータ遅延が発生すると予想されます。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14771">DOCAC JIRA タスクへのリンク </a>

### ユーザビリティの向上 {#june-26-usability}

このリリースでは、次の操作性の改善が行われています。

* **ジャーニーとキャンペーン用のフォルダー** - ジャーニーとキャンペーンを&#x200B;**フォルダー**に整理して、インターフェイスのナビゲーションと管理を改善できるようになりました。
  <a href="https://jira.corp.adobe.com/browse/DOCAC-14038">DOCAC JIRA タスクへのリンク </a>

