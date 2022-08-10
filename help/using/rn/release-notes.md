---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: 8766f64c4ea7985c6c9d6e4ba022ef6b1fc0dbed
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 86%

---

# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。また、その他の変更点については、[最新のドキュメント更新](documentation-updates.md)ページを参照してください。

[!DNL Adobe Journey Optimizer] が [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html?lang=ja){target=&quot;_blank&quot;} を参照してください。

![ニュースレター](../assets/do-not-localize/nl-icon.png) 今すぐ [Adobe Journey Optimizer 季刊ニュースレター](https://www.adobe.com/subscription/Adobe_Journey_Optimizer_NL.html){target=&quot;_blank&quot;}に登録すると、最新の製品アップデート、わくわくするような顧客事例、ユースケース、ヒントなどが、四半期ごとに受信トレイに直接配信されます。

## 2022年7月リリース {#july-2022-release}

### 新機能

<table>
<thead>
<tr>
<th><strong>新しいインラインメッセージフロー</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Optimizer では、メッセージをオーサリングするための新しいフローがジャーニーで提供されるようになりました。 インラインメッセージにより、ユーザーの時間を大幅に節約し、Journey Optimizer でメール、プッシュ通知または SMS を作成して配信するためのワークフロープロセスを合理化します。メッセージを別の手順として削除し、代わりにジャーニーキャンバス上でのアクションの一部としてインラインで編集できるようにすると、ユーザーがコンテンツをデザインおよび編集するためにクリックするボタンや、ナビゲートする画面が少なくて済みます。</p>
<img src="assets/do-not-localize/inline.gif"/>
<p>詳しくは、<a href="../messages/get-started-content.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>属性ベースのアクセス制御（使用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>組織またはデータの使用範囲を定義するラベルが付いたスキーマフィールドを識別できるようになりました。 管理者は、権限インターフェイスを使用して、XDM スキーマフィールドをカバーするアクセスポリシーを定義し、ユーザーまたはユーザーのグループ（内部、外部、またはサードパーティのユーザー）に付与するアクセス権をより適切に管理し、特定の種類のデータ（機密性の高い個人データ／SPD など）へのアクセスを管理できます。</p>
<p>属性ベースのアクセス制御の使用は、現在、選択したユーザーに制限されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、<a href="../administration/attribute-based-access.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Batch Decisioning ジョブ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ユーザーインターフェイスからバッチ決定ジョブを実行できるよりました。これにより、開発者はバッチ API ジョブを実行する必要がなくなり、マーケティングに必要な時間を短縮できます。この新しいインターフェイスでは、ジョブを作成し、現在／過去のジョブを管理できます。</p>
<img src="assets/do-not-localize/batch.gif"/>
<p>詳しくは、<a href="../offers/batch-delivery.md">詳細なドキュメントを参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>最もパフォーマンスの高いオファーを意思決定で自動的に使用（利用制限あり）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>意思決定管理で、パーソナライズされた最適化モデルシステムを使用できるようになりました。この新しいタイプのモデルを使用すると、セグメントとオファーのパフォーマンスに基づいて、オファーを最適化およびパーソナライズできます。</p>
<p>パーソナライズされた最適化 AI モデルの使用は、現在、選択したユーザーに制限されており、将来のリリースですべての環境にデプロイされます。</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>詳しくは、 <a href="../offers/ranking/personalized-optimization-model.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* **ジャーニーの終了**  — ジャーニーキャンバスで、 **終了** アクティビティがパレットから削除されました。 終了タグは、デフォルトで各パスの最後に追加され、削除できなくなりました。 この改善により、ジャーニーの実行者から何のアクションも必要とせずに、お客様がジャーニーから離脱した場所をより適切にレポートできます。 詳しくは、 [ドキュメント](../building-journeys/journey-end.md) および [機能ビデオ](https://video.tv.adobe.com/v/345376){target=&quot;_blank&quot;}。

**メッセージ**

* メッセージプリセットは&#x200B;**チャネルサーフェス**&#x200B;になりました。[詳細情報](../configuration/channel-surfaces.md)

**管理**

* **PTR レコードの編集** - PTR レコードを更新する際の処理時間が、最大でわずか 3 時間になりました。[詳細情報](../configuration/ptr-records.md#processing)

* **許可リスト UI** - Journey Optimizer ユーザーインターフェイスを使用して、新しいメールアドレスまたはドメインを許可リストに追加できるようになりました。[詳細情報](../configuration/allow-list.md)

* **許可リストロジックの更新** - リストが空でも、機能が有効になるとすぐに許可リストロジックが適用されるようになりました。[詳細情報](../configuration/allow-list.md#logic)

* **URL トラッキングパラメーター** ：式エディターを使用して、電子メールの表面（つまりプリセット）で URL トラッキングパラメーターを設定できるようになりました。 [詳細情報](../configuration/email-settings.md#url-tracking)

**Offer Decisioning**

* **オーディエンスサイズ** - 決定ルールを作成するとき、オファーの実施要件を設定するセグメントまたはルールを選択するとき、またはセグメントやルールを決定範囲に追加するとき、新しいオーディエンスサイズ推定コンポーネントがユーザーインターフェイスに表示されるようになりました。