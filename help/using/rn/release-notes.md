---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 06eb2ebec284f807de7ddca5d26e13fc08194642
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 84%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022年5月リリース {#may-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>メッセージ頻度ルール</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>過度に配信を受けているプロファイルをメッセージやアクションから自動的に除外するクロスチャネルのビジネスルールを設定できるようになりました。</p>
<img src="assets/frequency-rn.gif"/>
<p>詳しくは、<a href="../configuration/frequency-rules.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<!--table>
<thead>
<tr>
<th><strong>Email BCC</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Availability date: <strong>May, 31</strong></p>
<p>You can now use the Email BCC (blind carbon copy) capability to store emails sent by Adobe Journey Optimizer. Enable this option in your email presets so that every email sent is blind-copied to your BCC address.</p>
<img src="assets/bcc-rn.gif"/>
<p>For more information, refer to the <a href="../configuration/email-settings.md#bcc-email">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->


<table>
<thead>
<tr>
<th><strong>決定管理 — AI ランキング自動最適化モデル</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>判定管理で、トレーニング済みモデルシステムを使用できるようになりました。 この新しい機能は、特定のプロファイルに対して表示するオファーをランク付けします。</p>
<img src="assets/optimization.gif"/>
<p>詳しくは、<a href="../offers/offer-activities/configure-offer-selection.md#use-ranking-strategy">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--table>
<thead>
<tr>
<th><strong>Attribute-based Access Control (ABAC)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Permission management in Journey Optimizer has been extended to data access. You can now manage data access for specific teams or groups of users (i.e. internal, external, 3rd parties) ​and manage access to specific types of data (i.e. Sensitive Personal Data/SPD).</p>
<p>This capability is available for a limited set of customers.</p>
<p>For more information, refer to the <a href="../landing-pages/create-lp.md">detailed documentation</a>.</p>
</td>
</tr>
</tbody>
</table-->

<table>
<thead>
<tr>
<th><strong>Journey Optimizer 監査ログ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Journey Optimizer リソースでユーザーが実行したアクションを監視できるようになりました。</p>
<img src="assets/audit-rn.gif"/>
<p>詳しくは、 <a href="../reports/audit-logs.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**パーソナライゼーション**

* **文字を非表示にする新しいヘルパー関数** - `mask` ヘルパー関数を使用すると、文字列の一部を「X」文字に置き換えることができます。[詳細情報](../personalization/functions/string.md#mask)

**ランディングページ**

* **フォームのないランディングページ** - フォームを含まず、訪問者のアクションを必要としないランディングページを作成および公開できるようになりました。
* **ランディングページテンプレート** - ランディングページをテンプレートとして保存し、他のランディングページを作成する際に再利用できるようになりました。[詳細情報](../landing-pages/lp-templates.md)
* **プライマリページに戻る** - 同じランディングページ内の任意のサブページからプライマリページへのリンクを追加できるようになりました。
* **カスタム JavaScript のサポート** - ランディングページコンテンツにカスタム JavaScript を追加して、高度なスタイル設定を実行したり、ランディングページにカスタム動作を追加したりできるようになりました。[詳細情報](../landing-pages/lp-custom-js.md)

**ジャーニー**

* **セグメントを読み取り** - 一回限りのセグメントを読み取りジャーニーは、ジャーニーの実行から 30 日後に、完了ステータスに移動するようになりました。スケジュールされた読み取りセグメントの場合、最後の実行から 30 日後になります。[詳細情報](../building-journeys/read-segment.md)
* **式エディター** - [limit](../building-journeys/functions/functionlimit.md) 関数が追加され、リストの項目数を制限できるようになりました。[sort](../building-journeys/functions/functionsort.md) 関数を使用して、リストオブジェクトを並べ替えることができるようになりました。また、listObject のサポートが [discint](../building-journeys/functions/functiondistinct.md) および [distinctWithNull](../building-journeys/functions/functiondistinctwithnull.md) 関数に追加されました。

**管理**

* **ライセンス使用状況ダッシュボードの更新**  — で利用できるライセンス使用状況ダッシュボード [!DNL Adobe Journey Optimizer] ユーザーインターフェイスに **ライセンス済み** 平均的なプロファイル充実度。 この指標表現にドロップが表示されます。つまり、ライセンス制限が正しくレポートされました。 [詳細情報](../segment/licence-usage.md)
