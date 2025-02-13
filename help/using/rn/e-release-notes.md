---
solution: Journey Optimizer
product: journey optimizer
title: 早期リリースノート
description: Journey Optimizer 早期リリースノート
feature: Release Notes
topic: Content Management
hide: true
hidefromtoc: true
exl-id: 6e7d1300-8efd-4fdc-90e3-3ccdc3babd2f
source-git-commit: 6d072ed9b0312ee06efa9fdfaafd0fff913e6276
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 26%

---

# 早期リリースノート {#e-release-notes}

[!DNL Adobe Journey Optimizer] は、新機能、既存機能の強化、およびバグ修正を継続的に提供します。[リリースノート](release-notes.md)では、各月の終わりにすべての変更がまとめられます。

**以下の早期リリースノートは、リリースの公開日まで予告なく変更される場合があります**。リンク、画面、更新されたドキュメントは、リリース日に[リリースノート](release-notes.md)で公開されます。

## 2025 年 2 月先行リリース {#25-02-rn}

### 新機能 {#25-02-features}

このリリースに含まれる新機能について、以下で詳しく説明します。

<table>
<thead>
<tr>
<th><strong>ビジネスルール</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ルール・セットを使用してビジネス・ルールを作成できるようになりました。 ルールセットは、チャネルをまたいでキャンペーンやジャーニーアクション内の送信済みメッセージを制限し、ジャーニーへのプロファイルエントリを制御するのに役立つルールのグループです。<p>
<p><ul><li>チャネルルールセットを作成して、1 つまたは複数のチャネルにわたって送信されるメッセージの数を制限します。 ルールをキャンペーンやジャーニーアクションに適用して、ルールセットで定義されているルールを適用します。 チャネルルールセットを使用すると、通信タイプに基づいてキャッピングルールを適用できます。 例えば、「プロモーションメッセージ」を制限するルールセットと「ニュースレター」用に別のルールセットを設定します。 送信する通信のタイプに応じて、キャンペーンまたはジャーニーアクションに適切なルールセットを適用します。</li>
<li> ジャーニーのルールセットを作成して、ジャーニーへのプロファイルエントリを制御します。 プロファイルが特定の期間内にジャーニーにエントリできる頻度や、プロファイルが同時に登録できるジャーニーの数を制限します。 これらをジャーニーレベルで適用して、エントリを適切に管理します。</li></p>
<p>以前は一連の組織（LA）で使用できましたが、現在はすべてのユーザー（GA）がビジネス・ルールを使用できます。</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>SMS の複数地域サポート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>配信、フィードバック、受信、コールバックの URL を上書きすることで、複数の地域のエンドポイントからの SMS メッセージ配信を管理できるようになりました。 これをサポートするために、新しい「フィールドオーバーライド URL」が API 資格情報設定に追加されました。 この変更は、Sinch プロバイダーでのみ使用できます。</p>
<!--p>For more information, refer to the <a href="../configuration/business-rules.md">detailed documentation</a>.</p-->
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>Customer Journey Analytics テンプレート</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Customer Journey Analytics テンプレートを活用して Journey Optimizer レポートを強化するオプションが追加されました。この新しい機能を使用すると、分析のニーズに合わせて事前に設計されたテンプレートを使用して、レポートプロセスを効率化できます。
</p>
<img src="assets/do-not-localize/cja-templates.gif">
<p>詳しくは、<a href="../reports/report-cja-manage.md#cja-template">詳細なドキュメント</a>を参照してください。</p>
<p>公開日：2025 年 1 月 15 日（PT）より</p>
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
<p>詳しくは、<a href="../audience/about-audiences.md#flexible">詳細なドキュメント</a>を参照してください。</p>
<p> 柔軟なオーディエンス評価は、一連の組織（使用制限あり）でのみ使用できます。 アクセスするには、アドビ担当者にお問い合わせください。</p>
<p>公開日：2025 年 1 月 28 日（PT）</p>
</tr>
</tbody>
</table>


### 機能強化 {#25-02-improvements}

以下の改善点は、2 月のアップデートに伴うものです。

* **データセットの有効期間（TTL）** – 今月から、新しいサンドボックスと新しい組織のJourney Optimizer システム生成データセットに、有効期間（TTL）ガードレールが次のようにロールアウトされます。

   * プロファイルストアのデータの場合は 90 日
   * データレイクのデータの場合は 13 か月

  この変更は、後続フェーズで既存の顧客サンドボックスにロールアウトされます。

* **プレイブック** - Journey Optimizerで独自のユースケースプレイブックを作成して公開できるようになりました。

* **ダイレクトメール** - DLZ （DAta ランディングゾーン）が、ダイレクトメール設定でのファイルルーティング用のサーバータイプとしてサポートされるようになりました。

**メール設定** – 公開日：2025 年 2 月 12 日（PT）

* Adobe以外で同意を管理している場合は、メールチャネルの設定の一部として、カスタム購読解除メールアドレスとカスタムワンクリック購読解除 URL を設定できるようになりました。 [ 詳細を表示 ](../email/list-unsubscribe.md#custom-managed)

  ![](../email/assets/surface-list-unsubscribe-custom.png){width="80%"}

  >[!AVAILABILITY]
  >
  >この機能は、少数の顧客向けに限定提供（LA）でリリースされています。

**決定** – 公開日：2025 年 1 月 28 日（PT）

* 決定では、項目カタログのスキーマを編集する際に、オブジェクトデータタイプをサポートするようになりました。 [詳細情報](../experience-decisioning/catalogs.md)

**Personalization** – 公開日：2025 年 1 月 29 日（PT）

* 新しい日付/時間ヘルパー関数を、パーソナライゼーションエディターで使用できるようになりました。 [詳細情報](../personalization/functions/dates.md)