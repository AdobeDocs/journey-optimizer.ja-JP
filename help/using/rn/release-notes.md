---
title: リリースノート
description: Journey Optimizer リリースノート
exl-id: 06fa956a-b500-416e-9d42-b683c328e837
source-git-commit: b31eb2bcf52bb57aec8e145ad8e94790a1fb44bf
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 28%

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
<p>Journey Optimizerでは、メッセージをオーサリングするための新しいフローがジャーニーで提供されます。 インラインメッセージにより、Journey Optimizerで E メール、プッシュ通知または SMS を作成および配信する際のユーザーの時間を大幅に節約し、ワークフロープロセスを合理化します。 メッセージを別の手順として削除し、ジャーニーキャンバス上での操作の一環としてインラインで編集可能にすることで、ユーザーはボタンを少なくし、画面を移動してコンテンツをデザインおよび編集する必要があります。</p>
<img src="assets/do-not-localize/inline.gif"/>
<p>詳しくは、<a href="../messages/get-started-content.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr>
<th><strong>属性ベースのアクセス制御（限られた可用性）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>組織またはデータの使用範囲を定義するラベルを持つスキーマフィールドを識別できるようになりました。 管理者は、権限インターフェイスを使用して、XDM スキーマフィールドをカバーするアクセスポリシーを定義し、ユーザーまたはユーザーのグループ（内部、外部、またはサードパーティのユーザー）に与えるアクセスをより管理し、特定の種類のデータ（機密の個人データ/SPD）にアクセスできます。</p>
<p>属性ベースのアクセス制御の使用は、現在、選択したユーザーに制限されており、将来のリリースですべての環境にデプロイされます。</p>
<p>詳しくは、<a href="../administration/attribute-based-access.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>バッチ判定ジョブ</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>ユーザーインターフェイスからバッチ判定ジョブを実行できるようになり、開発者がバッチ api ジョブを実行する必要がなくなり、マーケティングに必要な時間を短縮できます。 この新しいインターフェイスでは、ジョブを作成し、現在/過去のジョブを管理できます。</p>
<img src="assets/do-not-localize/batch.gif"/>
<p>詳しくは、<a href="../offers/batch-delivery.md">詳細なドキュメントを参照してください。</p>
</td>
</tr>
</tbody>
</table>

<!--
<table>
<thead>
<tr>
<th><strong>Automatically use the best performing offer in your decisions (limited availability)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>You can now use personalized optimization model systems in Decision Management. This new type of model allows you to optimize and personalize offers based on segments and offer performance.</p>
<p>The use of personalized optimization AI models is currently restricted to selected users, and will be deployed to all environments in a future release.</p>
<img src="assets/do-not-localize/ai-ranking.gif"/>
<p>For more information, refer to the detailed documentation.</p>
</td>
</tr>
</tbody>
</table>
-->

### 機能強化

<!--
**Journeys**

* **Ending a journey** - In the journey canvas, the **End** activity has been removed from the palette. End tags are now added by default at the end of each path and cannot be removed. This improvement allows better reporting of where a customer dropped out of the journey, without any action from the user.
-->

**メッセージ**

* メッセージプリセットが **チャンネルサーフェス**. [詳細情報](../configuration/channel-surfaces.md)

**管理**

* **PTR レコードのエディション** - PTR レコードを更新する場合、処理時間は最大 3 時間に制限されました。 [詳細情報](../configuration/ptr-records.md#processing)

* **許可リストUI** - Journey Optimizerユーザーインターフェイスを使用して、新しい電子メールアドレスまたはドメインを許可リストに追加できるようになりました。 [詳細情報](../configuration/allow-list.md)

* **許可リストロジックの更新** -許可リストロジックは、機能が有効になるとすぐに、リストが空でも適用されるようになりました。 [詳細情報](../configuration/allow-list.md#logic)

* **URL トラッキングパラメーター** ：式エディターを使用して、E メールの表面に URL トラッキングパラメーター（メッセージプリセット）を設定できるようになりました。 [詳細情報](../configuration/email-settings.md#url-tracking)

**Offer Decisioning**

* **オーディエンスサイズ**  — 決定ルールを作成する際、オファーの実施要件を設定するセグメントやルールを選択する際、または決定範囲にセグメントやルールを追加する際に、新しいオーディエンスサイズ予測コンポーネントがユーザーインターフェイスに表示されるようになりました。