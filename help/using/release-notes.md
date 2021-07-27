---
title: リリースノート
description: Journey Optimizer リリースノート
source-git-commit: 0fb6d8f611a849696d83e0f129e6462431e5fe83
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 43%

---


# リリースノート {#release-notes}

このページでは、Journey Optimizer の新機能と改善点をすべて挙げています。
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
<p>Adobe Experience Platformでは、あるデータセットを別のデータセットのルックアップテーブルとして使用するために、スキーマ間の関係を定義できます。 Journey Optimizerは、リンクされたスキーマからのデータを活用できるようになりました。</p>
<p>これらのフィールドは、単一のイベント設定、ジャーニー条件、メッセージのパーソナライゼーション、カスタムアクションのパーソナライゼーションで使用できます。
<p>詳しくは、 <a href="event/experience-event-schema.md#leverage_schema_relationships">詳細なドキュメント</a>を参照してください。</p>
</td>
</tr>
</tbody>
</table>

### 機能強化

* 同じサンドボックス内で同時に実行されるすべての読み取りセグメントの全体的なスロットリング率は、1秒あたり17,000メッセージに制限されます。 [詳細を読む](building-journeys/read-segment.md#configuring-segment-trigger-activity)
* **Cache duration**&#x200B;フィールドがデータソース設定ペインから削除されました。 [詳細を読む](datasource/about-data-sources.md)
* 外部データソースの場合、1 秒あたり 15 回というキャッピングルールが自動的に定義されるようになりました。 [詳細を読む](configuration/external-systems.md#capping)
* ライブジャーニーの場合、ジャーニーのプロパティ画面に、ジャーニーの公開日と公開したユーザー名が表示されるようになりました。 [詳細を読む](building-journeys/journey-gs.md#change-properties)
* ジャーニーリスト画面に、ジャーニータイプフィルターが追加されました。 [詳細を読む](user-interface.md#section_lgm_hpz_pgb)
* 「セグメントの読み取り」アクティビティに[!UICONTROL Throttling rate]パラメーターが追加されました。 [詳細を読む](building-journeys/read-segment.md#configuring-segment-trigger-activity)
