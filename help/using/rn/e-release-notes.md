---
solution: Journey Optimizer
product: journey optimizer
title: Journey Optimizer のプレリリースノート
description: Adobe Journey Optimizer プレリリースノート
feature: Release Notes
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 180b517c311f1d9a19f8c185f4ce5acd824aa3d9
workflow-type: tm+mt
source-wordcount: '1472'
ht-degree: 26%

---

# プレリリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

## 2025 年 9 月プレリリースノート {#25-9-rn}

**以下のプレリリースノートの内容は、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新済みのドキュメントは、リリース日にリリースノートに公開されます。

[Adobe Experience Platform プレリリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/pre-release-notes){target="_blank"}も参照してください。

**リリース日**:2025 年 9 月 23～24 日

### 新機能 {#sept-25-9-features}

<table>
<thead>
<tr>
<th><strong>ジャーニーを取得するパブリック API</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ジャーニーと、キャンペーンやサーフェスなどの関連オブジェクトを取得する新しいJourney Optimizer API が使用できるようになりました。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>New Web Push notifications channel</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer now supports Web Push notifications, expanding the push channel beyond mobile. You can seamlessly deliver notifications to both mobile and desktop browsers, enabling you to reach customers directly on their devices without requiring an app.</p>
<p>This enhancement allows you to engage users with timely, personalized messages in real time, leveraging the same authoring workflows and targeting capabilities already available for mobile push.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>ロイヤルティアプリ用の新しいソースコネクタ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platformで、Talon.One、Capilary、Kobie の各ロイヤルティアプリで新しいソースコネクタが使用できるようになりました。 これらのコネクタを使用すると、ロイヤルティデータをAdobe Experience Platformにシームレスにストリーミングし、これらのデータをJourney Optimizerで活用できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Agent</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Agentを使用すると、Journey Optimizerのユーザーは、自然言語インターフェイスを使用してジャーニーを作成、分析および最適化できます。 Journey Agentを使用すると、実務担当者は、スケジュールやオーディエンスの競合をすばやく検出して解決し、パフォーマンスとドロップオフポイントを分析し、今後のキャンペーンでレプリケートするパフォーマンスの高いジャーニーを特定できます。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Journey Optimizer Experimentation Accelerator</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer Experimentation Acceleratorは、実験を次のレベルに引き上げるために設計された AI ファーストの製品です。 Adobe Journey OptimizerおよびAdobe Target ユーザー向けに構築されたこのサービスは、実験管理を統合し、AI を活用したインサイトとオポチュニティを提供し、新しい実験エージェントを導入します。</p>
<p>次の点にご期待ください。</p>
<ul>
<li><strong> 統合された実験インベントリ：</strong>Adobe Journey OptimizerとAdobe Targetのすべての実験を 1 つの中央ワークスペースですばやく表示、フィルタリング、管理します。 新しいチームスイッチャーを使用すると、ユーザーはチームや役割別にビューを調整し、適切な人物に最も関連性の高い実験を確実に表示できます。</li>
<li><strong>AI 実験のインサイトと機会：</strong>GenAI によるインサイトと推奨事項を使用して、統計的な読み上げを超えます。 各実験では、根拠を裏付ける完全な、実用的な機会が得られるため、チームは次に何をテストすべきかをより自信を持って決定できます。</li>
<li><strong> マルチアームバンディット（MAB）のサポート：</strong> マルチアームバンディット実験で無駄になるトラフィックを減らしながら、影響を最大化します。 MAB では、オーディエンスを均等に分割するのではなく、パフォーマンスの最も高いバリエーションにリアルタイムでより多くの訪問者を自動的に割り当てるため、機能を学びながら、より多くの顧客により良いエクスペリエンスを提供できます。</li>
</ul>
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
<p><img src="assets/do-not-localize/dark-mode.gif"/></p>
<p>詳しくは、<a href="../email/dark-mode.md">詳細なドキュメント</a>を参照してください。</p>
 <p>公開日：2025 年 9 月 16 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>ジャーニーパスの最適化</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新しい最適化ノードを使用して特定のオーディエンスにターゲットを設定するか、A/B テストを実行して、ビジネス目標に焦点を合わせた KPI を達成する最適なパスを決定します。</p>
<p>このツールを使用すると、コミュニケーション、シーケンス、タイミングをテスト、調整、カスタマイズし、顧客に最も効果的にリーチできます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p><img src="assets/do-not-localize/optimize.gif"/></p>
<p>詳しくは、<a href="../building-journeys/optimize.md">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025 年 9 月 4 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>サブドメインのカスタムデリゲーションメソッド</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>完全なデリゲーションと CNAME メソッドに加えて、新しいサブドメイン設定メソッドとして、カスタムデリゲーションメソッドが使用できるようになりました。これにより、メッセージの配信、レンダリング、トラッキングに必要な DNS のあらゆる側面を完全に制御および管理できます。</p>
<p>この機能は、限定提供です。アクセス権を取得するには、アドビ担当者にお問い合わせください。</p>
<p>詳しくは、<a href="../configuration/delegate-custom-subdomain.md">詳細なドキュメント</a>を参照してください</p>
<p>公開日：2025 年 9 月 4 日（PT）</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>パーソナライゼーションと意思決定へのAdobe Experience Platform データの使用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>以前パブリックベータ版でリリースされていましたが、この機能は、すべての環境で限定提供（LA）で利用できるようになりました。 このリリースでは、次の機能強化が導入されました。</p>
<ul><li>インバウンドチャネルでのデータセットルックアップパーソナライゼーションのサポート。</li>
<li>「datasetLookup」ヘルパー関数を式フラグメント内で使用できるようになりました。 現時点では、この機能は一部のお客様のみが利用できます。 アクセスするには、アドビ担当者にお問い合わせください。</li>
<li>データセット管理インターフェイスのオプションを使用すると、API 呼び出しを実行しなくても、ルックアップパーソナライゼーション用のレコードベースのデータセットを有効にできるようになりました。</li>
<li>データ取り込みステータスを追跡し、データセットの検索準備が整ったタイミングを把握するための監視機能を強化しました。</li>
<li>最適なパフォーマンスと信頼性を確保するために、使用ガイドラインとガードレールを更新しました。</li>
<li>Adobe Experience Platform データセットを決定キャッピングルールで活用できるようになりました。</li></ul></p>
<p>詳しくは、<a href="../data/lookup-aep-data.md">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 9 月 1 日（PT）</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

- **承認ポリシーの権限**
承認ポリシーを作成または設定する際に、ジャーニー/キャンペーン作成者が独自のオブジェクトを承認できないようにするオプションを追加しました。

- **新しいジャーニーアラート**\
  ジャーニーには、事前設定済みの新しいアラートを使用できます。
   - プロファイル破棄率の超過：過去 5 分に入力されたプロファイルに対するプロファイル破棄の割合が、しきい値を超えました。
   - カスタムアクションエラー率を超えました：過去 5 分の、成功した HTTP 呼び出しに対するカスタムアクションエラーの割合が、しきい値を超えました。
   - プロファイルエラー率の超過：過去 5 分に入力されたプロファイルに対する、エラーのプロファイルの割合が、しきい値を超えました。

- **カスタム認証でネストされた JSON ボディパラメーターがサポートされるようになりました**\
  カスタムアクションにカスタム認証を設定する場合、ネストされた JSON オブジェクト（`bodyParams` 内のサブオブジェクトなど）がサポートされるようになりました。

- **決定項目へのフラグメントの添付**\
  Journey Optimizerで、意思決定ポリシーを通じてコードベースのエクスペリエンスキャンペーンで利用できるフラグメントを意思決定項目に添付する機能が提供されるようになりました。

- **ワンクリック登録解除 URL でのカスタム属性のサポート**\
  Journey Optimizerを使用すると、Adobe外で同意を管理している場合に、メール設定で独自のワンクリック購読解除リンクを定義することで、外部カスタムエンドポイントを設定できます。 受信者が登録解除リンクをクリックすると、Journey Optimizer では、同意更新イベントにいくつかのデフォルトのプロファイル固有のパラメーターが追加されます。

  購読解除メールアドレスをさらにパーソナライズするために、同意イベントに追加するカスタム属性を定義できるようになりました。 この機能は、8 月 25 日リリース以降、カスタムのワンクリック購読解除リンクで既に使用されています。

- **SMS BYOP の mTLS サポート**\
  カスタム SMS プロバイダーを設定する際に、相互 TLS （mTLS）認証を有効にするオプションが追加されました。この場合、安全な接続が確立される前に、クライアントとサーバーの両方が相互の ID を確認する必要があります。

- **モデルベースのスキーマ**\
  より明確で直感的なエクスペリエンスを実現するために、リレーショナルスキーマは現在、オーケストレートキャンペーンではモデルベースのスキーマと呼ばれています。

- **ジャーニーでのデータセットルックアップのサポート**\
  ジャーニーの新しいアクティビティ **データセットルックアップ** を使用すると、実行時にAdobe Experience Platform レコードデータセットからデータを動的に取得できます。 この機能を活用すると、プロファイルまたはイベントペイロードに存在しない可能性のあるデータにアクセスできるので、顧客とのインタラクションが関連性が高く、タイムリーなものとなります。

- **すべてのインバウンドチャネルのコンテンツバリエーションのシミュレーション**\
  以前は、メール、SMS、プッシュ通知のチャネルでのみ使用できましたが、コンテンツのバリエーションのシミュレーションはすべてのインバウンドチャネルにも適用されるようになりました。

- **カスタムアクションの監視とレポート作成**\
  この機能により、ライフサイクルステータスやパフォーマンスアラートなど、ジャーニーの正常性と実行がよりわかりやすく表示されます。 カスタムアクションで異常な状況が発生しているタイミング、場所、理由をすばやく理解できるようになりました。

- **API トリガーキャンペーンの Webhook サポート**\
  API トリガーキャンペーンで Webhook がサポートされるようになりました。 Webhook の URL を設定して、メッセージごとにリアルタイムのステータス更新を受信するようにすると、観測性が向上し、シームレスな監視と自動化が可能になります。

- **ジャーニーカスタムアクションでのリダイレクトのサポート**\
  リダイレクト （302）がジャーニーのカスタムアクションでサポートされるようになりました。

- **API トリガーメールキャンペーンの高スループットモード**\
  API トリガーキャンペーンで新しい高スループットモードが使用できるようになりました。 このモードは、大規模なリアルタイムメッセージ（1 秒あたり最大 5000 トランザクション）向けに設計されており、より高い可用性とより低い待ち時間を提供します。\
  この機能は、Adobeの高スループットトランザクションメッセージのアドオン機能を購入した組織のメールチャネルでのみ使用できます。 詳しくは、Adobe担当者にお問い合わせください。


- **時間単位での頻度キャップのリセット** - チャネルルールセットに対して時間単位でキャップを適用できるようになりました。以前は限定提供（LA）で利用できましたが、現在はすべての環境で利用でき、1 時間（以前は 3 時間）を選択できるようになりました。 [ 詳細情報 ](../conflict-prioritization/channel-capping.md)。 実施可能日：9 月 17 日（PT）

- **動的ドメインのサポート** - Journey Optimizerで、Adobeが受け入れる事前定義済みドメインの完全/ベース URL パーソナライゼーションがサポートされるようになりました。 [ 詳細を表示 ](../personalization/personalization-build-expressions.md#where)<!--Availability date: September 12-->

  >[!NOTE]
  >
  >この機能は、一連のお客様に対して限定提供で利用できます。

- **決定キャッピングルールの式** – 決定項目のキャッピングルールのしきい値を定義する独自の式を作成できるようになりました。 [詳細情報](../experience-decisioning/items.md#capping)

>[!NOTE]
>
>この機能は、現在、すべてのユーザーに対する限定提供として利用できます。

- **チャネル設定の監視アラート** - カスタムサブドメインデリゲーションタイプを使用したメールチャネル設定エラーが発生した場合に、メールまたはJourney Optimizer通知センターでシステムアラートを受け取ることを登録できるようになりました。 [詳細情報](../reports/alerts.md#alert-dns-record-missing)

