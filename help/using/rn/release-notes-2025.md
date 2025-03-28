---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート 2025
description: Journey Optimizer 2025 リリースノート
feature: Release Notes
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: e80554570d62d1ddb52516366be55711387c5d19
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 89%

---

# リリースノート 2025 {#release-notes-2025}

このページでは、2025年にリリースされた [!DNL Journey Optimizer] の機能と改善点をすべて一覧表示しています。

## 2025年2月リリースノート {#25-02-rn}

**リリース日**：2025年2月18～19日（PT）


### 新機能 {#25-02-features}

このリリースに含まれる新機能を以下に示します。

<table>
<thead>
<tr>
<th><strong>ビジネスルールの作成と管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ルールセットを使用して、ビジネスルールを作成できるようになりました。ルールセットは、チャネルをまたいでキャンペーンやジャーニーアクション内で送信されるメッセージを制限し、ジャーニーへのプロファイルエントリを制御するのに役立つルールのグループです。<p>
<p><ul><li>チャネルルールセットを作成して、1 つまたは複数のチャネルをまたいで送信されるメッセージの数を制限します。これらをキャンペーンまたはジャーニーアクションに適用して、ルールセットで定義されたルールを適用します。チャネルルールセットを使用すると、通信タイプに基づいてキャッピングルールを適用できます。例えば、「プロモーションメッセージ」を制限するルールセットと、「ニュースレター」を制限するルールセットを設定します。送信する通信のタイプに応じて、キャンペーンまたはジャーニーアクションに適切なルールセットを適用します。</li>
<li> ジャーニールールセットを作成して、ジャーニーへのプロファイルエントリを制御します。プロファイルが特定の期間内にジャーニーにエントリできる頻度や、プロファイルが同時に登録できるジャーニーの数を制限します。これらをジャーニーレベルで適用して、適切なエントリ管理を確保します。</li></ul></p>
<p>以前は一連の組織（LA）で使用できましたが、現在はすべてのユーザー（GA）がビジネス・ルールを使用できます。 ジャーニードメインのビジネスルールは、引き続き一部の組織（LA）でのみ使用できます。</p>
<p>詳しくは、<a href="../configuration/rule-sets.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI アシスタントを使用したランディングページの生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントを使用して、完全なページデザイン、パーソナライズされたテキスト、カスタマイズされたビジュアルなど、ランディングページ用の魅力的なコンテンツを作成できるようになりました。</p>
<img src="assets/do-not-localize/ai-lp.gif">
<p>詳しくは、<a href="../content-management/generative-lp.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>AI アシスタントを使用したブランド（ベータ版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>独自のブランドを設定して、ブランドの視覚的および言語的 ID を定義できるようになりました。 </p>
<p>この機能は、一部のお客様に Private Beta としてリリースされています。今後のリリースでは、すべてのお客様が段階的に利用できるようになる予定です。</p>
<p>詳しくは、<a href="../content-management/brands.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタムアクションのトラブルシューティング</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerから直接、実際の API 呼び出しを行うことで、カスタムアクション設定を検証できるようになりました。 この新しい機能は、ジャーニーで使用する前または後にカスタムアクションをトラブルシューティングするのに役立ちます。 </p>
<p>詳しくは、<a href="../action/troubleshoot-custom-action.md">詳細なドキュメント</a>を参照してください。</p>
<!--p> This capability is only available for a set of organizations (Limited Availability). To gain access, contact your Adobe representative.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>柔軟なオーディエンス評価（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>柔軟なオーディエンス評価を使用すると、選択したオーディエンスに対してオンデマンドでセグメント化ジョブを実行できるので、Journey Optimizer のジャーニーやキャンペーンにオーディエンスをターゲティングする前に、常に最新のオーディエンスデータを確保できます。</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>詳しくは、<a href="../audience/creating-a-segment-definition.md#flexible">詳細なドキュメント</a>を参照してください。</p>
<p>この機能は、一連の組織でのみ使用できます（限定提供）。アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>リリース日：2025年1月28日（PT）</p>
</tr>
</tbody>
</table>
</table>


### 機能強化 {#25-02-improvements}

2月の更新では、以下の機能強化が行われます。

* **データセットの有効期間（TTL）** - 今月以降、新しいサンドボックスと新しい組織の Journey Optimizer システム生成データセットに、次のように有効期間（TTL）ガードレールがロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、後続のフェーズで既存のお客様のサンドボックスにロールアウトされます。

  この更新について詳しくは、[専用のよくある質問](../data/datasets-ttl.md#frequently-asked-questions)を参照してください。

<!--* **Playbooks** - You can now create and publish your own Use Case Playbooks in Journey Optimizer.-->

* **ダイレクトメール** - ダイレクトメールチャネル設定でのファイルルーティングに、新しいサーバータイプである Data Landing Zone がサポートされるようになりました。[詳細情報](../direct-mail/direct-mail-configuration.md#file-routing-configuration)

* **SMS** - 配信、フィードバック、インバウンド、コールバックの URL を上書きして、複数の地域のエンドポイントからの SMS メッセージ配信を管理できるようになりました。これをサポートすることを目的に、API 資格情報設定に新しい「上書き URL」フィールドが追加されました。この変更は、Sinch プロバイダーでのみ使用できます。[詳細情報](../sms/sms-configuration-sinch.md)

* **パーソナライゼーション**（公開日：2025年1月29日（PT））- パーソナライゼーションエディターで新しい日付／時刻ヘルパー関数が使用できるようになりました。[詳細情報](../personalization/functions/dates.md)


<!--
* The personalization editor has been enhanced with new capabilities such as Auto-complete, Search, and filtering options. You can also show or hide deprecated attributes.-->


* **メール設定** - アドビの外部で同意を管理している場合は、メールチャネル設定の一部として、カスタムの登録解除メールアドレスとカスタムのワンクリック登録解除 URL を設定できるようになりました。[詳細情報](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

* **決定**（公開日：2025年1月28日（PT））- 決定では、項目カタログのスキーマを編集する際に、オブジェクトデータタイプがサポートされるようになりました。[詳細情報](../experience-decisioning/catalogs.md)

