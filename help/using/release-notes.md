---
title: リリースノート
description: Journey Optimizer リリースノート
source-git-commit: a1800c333bfbee178682d773c729aad7e23d86d0
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 94%

---


# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と改善点を一覧にしています。最新の[ドキュメント更新](documentation-updates.md)を参照することもできます。

## 2021 年 7 月リリース {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>スキーマ間の関係の活用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform では、あるデータセットを別のデータセットの参照テーブルとして使用するために、スキーマ間の関係を定義できます。[!DNL Journey Optimizer] では、リンクされたスキーマからのデータを活用できるようになりました。</p>
<p>これらのフィールドは、単一イベントの設定、ジャーニー条件、メッセージのパーソナライゼーションおよびカスタムアクションのパーソナライゼーションで使用できます。</p>
<p>詳しくは、<a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>許可リスト</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>特定の送信セーフリストをサンドボックスレベルで定義して、テスト目的の安全な環境を構築できるようになりました。 ミスが発生する可能性のある非実稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。この機能は、抑制 API を利用することで有効になります。</p>
<p>詳しくは、 <a href="allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックスで同時に実行されるすべての「セグメントを読み取り」アクティビティの全体的なスロットルレートは、1 秒あたり 17,000 メッセージに制限されています。[詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* 「**キャッシュ時間**」フィールドがデータソース設定ペインから削除されました。[詳細情報](datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数制限（キャッピング）ルールが自動的に定義されるようになりました。 [詳細を読む](configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーを公開した日付とユーザーの名前がジャーニープロパティ画面に表示されるようになりました。 [詳細を読む](building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細を読む](user-interface.md#section_lgm_hpz_pgb)
* **[!UICONTROL スロットルレート]**&#x200B;パラメーターが「セグメントを読み取り」アクティビティに追加されました。 [詳細情報](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**メッセージのプレビューとテスト**

* ID と名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。[詳細情報](preview.md#preview-your-messages)
* 配達確認のテストメールの数が 10 個に制限されるようになりました。
* 配達確認の&#x200B;**件名行のプレフィックス**&#x200B;に使用できる文字が制限されるようになりました。 [詳細情報](preview.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前と順序が変更されました。

### 修正点

* 一括メール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が終了した後、メール送信が実行されない場合、それに応じてイベントが生成されるようになりました。
* PTR レコード画面に IP 情報が表示されない問題を修正しました。
* 式エディター内のオファーパネルのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image`プロパティを含む内部スタイルシートがサポートされていないHTMLファイルをアップロードする際のEメールデザイナーの問題を修正しました。

