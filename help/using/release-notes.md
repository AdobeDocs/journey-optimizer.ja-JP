---
title: リリースノート
description: Journey Optimizer リリースノート
source-git-commit: a1800c333bfbee178682d773c729aad7e23d86d0
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 37%

---


# リリースノート {#release-notes}

このページでは、[!DNL Journey Optimizer] のすべての新機能と向上した点を一覧にしています。
最新の[ドキュメントの更新](documentation-updates.md)も参照してください。

## 2021年7月リリース {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>スキーマの関係の活用</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Adobe Experience Platform では、あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を定義できます。[!DNL Journey Optimizer]は、リンクされたスキーマからのデータを活用できるようになりました。</p>
<p>これらのフィールドは、単一のイベント設定、ジャーニー条件、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションで使用できます。</p>
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
<p>特定の送信セーフリストをサンドボックスレベルで定義して、テスト目的の安全な環境を構築できるようになりました。 実稼動以外のインスタンスでエラーが発生する可能性がある場合は、許可リストによって、不要なメッセージが顧客に送信されるリスクがなくなります。 この機能は、抑制APIを利用することで有効になります。</p>
<p>詳しくは、 <a href="allow-list.md">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

**ジャーニー**

* 同じサンドボックス内で同時に実行されるすべての読み取りセグメントの全体的なスロットリング率は、1秒あたり17,000メッセージに制限されます。 [詳細を読む](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* **キャッシュ時間**&#x200B;フィールドがデータソース設定ペインから削除されました。[詳細を読む](datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回までの呼び出し回数制限（キャッピング）ルールが自動的に定義されるようになりました。 [詳細を読む](configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーを公開した日付とユーザーの名前がジャーニープロパティ画面に表示されるようになりました。 [詳細を読む](building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面にジャーニータイプフィルターが追加されました。 [詳細を読む](user-interface.md#section_lgm_hpz_pgb)
* 「セグメントの読み取り」アクティビティに&#x200B;**[!UICONTROL Throttling rate]**&#x200B;パラメーターが追加されました。 [詳細を読む](building-journeys/read-segment.md#configuring-segment-trigger-activity)

**メッセージのプレビューとテスト**

* IDと名前空間が&#x200B;**[!UICONTROL プレビュー]**&#x200B;画面に表示されるようになりました。 [詳細を読む](preview.md#preview-your-messages)
* 配達確認のテストEメールの数が10個に制限されるようになりました。
* 配達確認の&#x200B;**件名行のプレフィックス**&#x200B;に使用できる文字が制限されるようになりました。 [詳細を読む](preview.md#send-proofs)

**パーソナライゼーション式エディター**

* ヘルパードロップダウンリストの名前が変更され、順序が変更されました。

### 修正点

* 一括Eメール配信で重複メッセージが配信される問題を修正しました。
* 再試行期間が過ぎるとEメール送信が実行されない場合に、適宜イベントが生成されるようになりました。
* PTRレコード画面にIP情報が表示されない問題を修正しました。
* 式エディター内のオファーレールのローカライゼーションが実装されました。
* 情報ポップアップの間隔の誤りを修正しました。
* `background-image`プロパティを含む内部スタイルシートがサポートされていないHTMLファイルをアップロードする際のEメールデザイナーの問題を修正しました。

