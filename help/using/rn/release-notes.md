---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 77a3980b2c18f14d6b7cf0461541d0b9721dab84
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 22%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 2 月リリースノート {#25-02-rn}

<!--
**Early release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.-->

**リリース日**:2025 年 2 月 18～19 日


### 新機能 {#25-02-features}

このリリースに含まれる新機能について、以下で詳しく説明します。

<table>
<thead>
<tr>
<th><strong>ビジネス・ルールの作成と管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ルール・セットを使用してビジネス・ルールを作成できるようになりました。 ルールセットは、チャネルをまたいでキャンペーンやジャーニーアクション内の送信済みメッセージを制限し、ジャーニーへのプロファイルエントリを制御するのに役立つルールのグループです。<p>
<p><ul><li>チャネルルールセットを作成して、1 つまたは複数のチャネルにわたって送信されるメッセージの数を制限します。 ルールをキャンペーンやジャーニーアクションに適用して、ルールセットで定義されているルールを適用します。 チャネルルールセットを使用すると、通信タイプに基づいてキャッピングルールを適用できます。 例えば、「プロモーションメッセージ」を制限するルールセットと「ニュースレター」用に別のルールセットを設定します。 送信する通信のタイプに応じて、キャンペーンまたはジャーニーアクションに適切なルールセットを適用します。</li>
<li> ジャーニーのルールセットを作成して、ジャーニーへのプロファイルエントリを制御します。 プロファイルが特定の期間内にジャーニーにエントリできる頻度や、プロファイルが同時に登録できるジャーニーの数を制限します。 これらをジャーニーレベルで適用して、エントリを適切に管理します。</li></p>
<p>以前は一連の組織（LA）で使用できましたが、現在はすべてのユーザー（GA）がビジネス・ルールを使用できます。</p>
<p>詳しくは、<a href="../configuration/rule-sets.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>AI アシスタントでランディングページを生成</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>AI アシスタントを使用して、完全なページデザイン、パーソナライズされたテキスト、カスタマイズされたビジュアルなど、ランディングページに魅力的なコンテンツを作成できるようになりました。</p>
<img src="assets/do-not-localize/ai-lp.gif">
<p>詳しくは、<a href="../content-management/generative-lp.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>AI アシスタントを使用したブランドガイドライン（Beta）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>独自のブランドガイドラインを設定して、ブランドの視覚的および言語的 ID を定義できるようになりました。 </p>
<p>この機能は、一部のお客様にプライベートベータ版としてリリースされています。 今後のリリースで、すべてのお客様が段階的に利用できるようになります。</p>
<p>詳しくは、<a href="../content-management/brands.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>カスタムアクションのトラブルシューティング（限定提供）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizerから直接、実際の API 呼び出しを行うことで、カスタムアクション設定を検証できるようになりました。 </p>
<p>詳しくは、<a href="../action/troubleshoot-custom-action.md">詳細なドキュメント</a>を参照してください。</p>
<p> この機能は、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
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
<p>柔軟なオーディエンス評価を使用すると、選択したオーディエンスに対してオンデマンドでセグメント化ジョブを実行し、Journey Optimizerのジャーニーやキャンペーンにターゲティングする前にオーディエンスデータを常に最新の状態に保つことができます。</p>
<img src="assets/do-not-localize/flexible-audience.gif">
<p>詳しくは、<a href="../audience/creating-a-segment-definition.md#flexible">詳細なドキュメント</a>を参照してください。</p>
<p>この機能は、一連の組織でのみ使用できます（使用制限あり）。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>公開日：2025 年 1 月 28 日（PT）</p>
</tr>
</tbody>
</table>
</table>


### 機能強化 {#25-02-improvements}

以下の改善点は、2 月のアップデートに伴うものです。

* **ジャーニー** – 管理セクションから API 呼び出しを送信することで、カスタムアクションをテストできるようになりました。 この新しい機能は、ジャーニーで使用する前または後にカスタムアクションをトラブルシューティングするのに役立ちます。

* **データセットの有効期間（TTL）** – 今月から、新しいサンドボックスと新しい組織のJourney Optimizer システム生成データセットに、有効期間（TTL）ガードレールが次のようにロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、後続フェーズで既存の顧客サンドボックスにロールアウトされます。

  この更新について詳しくは、[ 専用 FAQ](../data/datasets-ttl.md#frequently-asked-questions) を参照してください。

<!--* **Playbooks** - You can now create and publish your own Use Case Playbooks in Journey Optimizer.-->

* **ダイレクトメール** – 新しいサーバータイプであるデータランディングゾーンが、ダイレクトメールチャネル設定でのファイルルーティングでサポートされるようになりました。

* **SMS** – 配信、フィードバック、受信、コールバックの URL を上書きすることで、複数の地域のエンドポイントからの SMS メッセージ配信を管理できるようになりました。 これをサポートするために、新しい「フィールドオーバーライド URL」が API 資格情報設定に追加されました。 この変更は、Sinch プロバイダーでのみ使用できます。 [詳細情報](../sms/sms-configuration-sinch.md)

* **Personalization** （公開日：2025 年 1 月 29 日（PT）） – 新しい日付/時間ヘルパー関数を、パーソナライゼーションエディターで使用できます。 [詳細情報](../personalization/functions/dates.md)


<!--
* The personalization editor has been enhanced with new capabilities such as Auto-complete, Search, and filtering options. You can also show or hide deprecated attributes.-->


* **メール設定** - Adobe外で同意を管理している場合は、メールチャネルの設定の一部として、カスタム購読解除メールアドレスとカスタムワンクリック購読解除 URL を設定できるようになりました。 [ 詳細を表示 ](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

* **決定** （公開日：2025 年 1 月 28 日（PT）） – 決定で、項目カタログのスキーマを編集する際に、オブジェクトデータタイプがサポートされるようになりました。 [詳細情報](../experience-decisioning/catalogs.md)

