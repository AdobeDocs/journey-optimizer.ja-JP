---
solution: Journey Optimizer
product: journey optimizer
title: リリースノート
feature: Release Notes
topic: Content Management
description: Adobe Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 78c1464ccddec75e4827cbb1877d8fab5ac08b90
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 87%

---

# リリースノート {#release-notes}

>[!CONTEXTUALHELP]
>id="ajo_homepage_card1"
>title="新着情報"
>abstract="**Adobe Journey Optimizer** は、新機能、既存機能の強化およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。"

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。これらのリリースノートでは、すべての変更が各月の最終週にまとめられます。[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target="_blank"}を参照してください。

## 2025 年 3 月の更新 {#25-03-rn}

**Personalization エディターの機能強化**

Journey Optimizer パーソナライゼーションエディターが更新され、次の新機能が追加されました。
* **更新されたコードエディターデザイン** – よりクリーンで最新のインターフェイスにより、操作性と集中力が向上しました。
* **検索と置換** - エディター内のコンテンツをすばやく検索および置換する機能が追加されました。
* **取り消しとやり直しのサポート** – 変更を簡単に元に戻したり、再適用したりできます。
* **カスタマイズ可能なフォントサイズ** - エディターのフォントサイズを調整して、読みやすくします。
* **インライン JSON 検証** - JSON コンテンツのリアルタイムのクライアントサイド検証を提供し、エラー検出を高速化します。
* **プロファイル属性とコンテキスト属性のオートコンプリート** - コンテンツ作成を効率化するためのスマートな提案を提供します。
* **構文のハイライト表示機能の強化** - コード構造をより視覚的に区別することで、読みやすさを向上しました。

詳しくは、[詳細なドキュメント](../personalization/personalization-build-expressions.md)を参照してください。

## 2025年2月リリースノート {#25-02-rn}

<!--
**Early release notes below are subject to change without prior notice until the release availability date**. Links, screens and updated documentation are published at the release date.-->

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
<li> ジャーニールールセットを作成して、ジャーニーへのプロファイルエントリを制御します。プロファイルが特定の期間内にジャーニーにエントリできる頻度や、プロファイルが同時に登録できるジャーニーの数を制限します。これらをジャーニーレベルで適用して、適切なエントリ管理を確保します。</li></p>
<p>以前は一連の組織（LA）に対して提供されていましたが、ビジネスルールはすべてのユーザー（GA）に対して提供されるようになりました。</p>
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
<p>Adobe Journey Optimizer から直接実際の API 呼び出しを行って、カスタムアクション設定を検証できるようになりました。 </p>
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

* **ジャーニー** - 管理セクションから API 呼び出しを送信して、カスタムアクションをテストできるようになりました。この新しい機能は、ジャーニーでカスタムアクションを使用する前または使用した後に、カスタムアクションのトラブルシューティングを行うのに役立ちます。[詳細情報](../action/troubleshoot-custom-action.md)

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

