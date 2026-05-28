---
solution: Journey Optimizer
product: journey optimizer
title: データセットの有効期間（TTL）ガードレールについて
description: ' [!DNL Adobe Journey Optimizer] のデータセットの有効期間ガードレール'
feature: Data Model, Datasets, Data Management
role: Developer, Admin
level: Experienced
keywords: プラットフォーム, データレイク, 作成, レイク, データセット, プロファイル
exl-id: 08633a79-5601-4e36-b8cf-080234956d99
TQID: https://experienceleague.adobe.com/DvcQ6AcWhNIZXnTtmPozvSTp1Ait-oo-8wlo8hQ6xlI
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
subfeature_v2:
  - id: a1cdc218-59b7-4eef-b5cf-2a7ad74b3371
  - id: d6e5c7fd-c1d6-4137-98cd-138ccde6752f
  - id: cf3fbcd7-c075-4ae4-8de5-96e736ab2ea3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 1126
ht-degree: 93%

---

# データセットの有効期間（TTL）ガードレール {#ttl-guardrail}

2025年2月現在、**新しいサンドボックスと新しい組織**&#x200B;の Journey Optimizer システム生成データセットに、次のように有効期間（TTL）ガードレールがロールアウトされます。

* プロファイルストアのデータの場合は 90 日
* データレイクのデータの場合は 13 か月

この変更は、後続のフェーズで&#x200B;**既存顧客のサンドボックス**&#x200B;にロールアウトされます。

## 影響を受けるデータセット {#datasets}

次の表は、影響を受けるすべてのデータセットと、データレイクおよび[&#x200B; プロファイルストア &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja#profile-data-store){target="_blank"}内のそれぞれのTime-To-Liveを示しています。

| データセット | データレイク TTL | プロファイルストア TTL |
|------|-----|-----|
| AJO メッセージフィードバックイベントデータセット | 13 か月 | 90 日 |
| AJO メールトラッキングエクスペリエンスイベントデータセット | 13 か月 | 90 日 |
| AJO プッシュトラッキングエクスペリエンスイベントデータセット | 13 か月 | 90 日 |
| AJO サーフェスデータセット | 13 か月 | 該当なし |
| AJO 受信アクティビティイベントデータセット | 13 か月 | 90 日 |
| セカンダリ受信者フィードバックイベントデータセット | 13 か月 | 該当なし |
| エンティティイベントデータセット | 13 か月 | 該当なし |
| ジャーニーステップイベント | 13 か月 | 該当なし |
| ODE DecisionEvents - 製品決定 | 13 か月 | 該当なし |

## よくある質問 {#faq}

データセットの有効期間（TTL）に関するよくある質問を以下に示します。

さらに詳細が必要ですか？ このページの下部にあるフィードバックオプションを使用して、質問を入力するか、[Adobe Journey Optimizer コミュニティ](https://experienceleaguecommunities.adobe.com/t5/adobe-journey-optimizer/ct-p/journey-optimizer?profile.language=ja){target="_blank"}にアクセスしてください。

+++TTLの対象となるデータセットの種類？

TTLは時系列データセットにのみ適用されます。 レコードタイプのデータセット（エンティティデータセット、分類データセット、決定オブジェクトリポジトリなど）はTTLの対象ではないため、上記の「影響を受けるデータセット」テーブルには表示されません。

+++

+++この変更は、本番サンドボックスにのみ適用されますか？それとも開発サンドボックスにも適用されますか？

この変更は、すべてのサンドボックスタイプに適用されます。

+++

+++プロファイルストアの 90 日の TTL で、プロファイル自体は影響を受けますか？

プロファイル自体ではなく、プロファイル内のシステム生成データセットのデータが 90 日後に削除されます。

+++

+++システム生成データセットのデータが [!DNL Customer Journey Analytics]（CJA）にプッシュされると、CJA のデータも TTL の影響を受けますか？

[!DNL Customer Journey Analytics] のデータは、Experience Platform と同期されます。 したがって、システム生成データセットのデータの TTL によるデータの削除は、[!DNL Customer Journey Analytics] のデータにも影響します。

+++

+++ お客様は、プロファイルストアの [!DNL Journey Optimizer] システムデータセットデータの TTL を増やすことができますか？ 

TTL 拡張機能は、現在サポートされていません。 ただし、2025 年後半から、これらの拡張リクエストに対応できるように TTL プロセスを最適化する作業が予定されています。

>[!NOTE]
>
>プロファイルに保存されたデータには、合計データボリュームの使用権限が適用されます。 したがって、TTL 拡張機能の結果として増加したプロファイルのデータストレージは、合計データボリュームの使用権限に対してカウントされます。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/landing/license/total-data-volume.html?lang=ja){target=_blank}

+++

+++お客様は、データレイクの [!DNL Journey Optimizer] システムデータセットデータの TTL を増やすことができますか？ 

TTL 拡張機能は、現在サポートされていません。 お客様は、宛先を通じてデータをエクスポートし、データを長期間保持できます。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja){target=_blank}。 さらに、**[!DNL Data Distiller]** 使用権限を持つお客様は、派生データセットを作成して、TTL なしでデータレイクにデータを保存できます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/query/data-distiller/derived-datasets/overview){target=_blank}

+++

+++TTL は次の機能に影響を与えますか？ 

* **ストアを参照**：いいえ
* **ジャーニーのキャップ**：いいえ
* **オファーのキャップ**：いいえ
* **送信時間の最適化（STO）**：いいえ
* **メッセージのフリークエンシーキャップ**（ビジネスルールなど）：いいえ
* **レポート**：いいえ

  >[!NOTE]
  >
  >[!DNL Customer Journey Analytics]（CJA）接続には既に TTL が実装されているので、影響を受けるデータセットデータの有効な最大ルックバック期間は 13 か月に短縮されます。

* **Experience Platform データソース**：該当なし - データソース経由でのエクスペリエンスイベントの取得はサポートされていません。
* **計算属性**：はい - 最初のバックフィル計算は、過去 90 日間のデータに制限されます。計算属性は、以降の更新の増分イベントに基づいて更新されます。 以降の更新がルックバック期間（最大 6 か月）に達するとすぐに、TTL は基本的に、計算属性に影響を与えなくなります。 詳細情報。
* **セグメント化とリターゲティング**：はい - セグメント化はプロファイルストア内のデータに依存します。したがって、影響を受けるデータセットデータのルックバックは 90 日に制限されます。
* **トラッキング**：はい - 影響を受けるデータセットデータの有効な最大ルックバック期間は 90 日に短縮されます。 影響を受けるデータセットのデータは、データレイクに 13 か月間保存されます。

+++

+++TTL の適用（バックフィルのユースケースなど）に使用されるタイムスタンプは何ですか？ 

イベントのタイムスタンプが使用されます（つまり、取り込み日ではありません）。

+++

+++新しい TTL は、より長いデータ保持を必要とするユースケース（例：過去 120 日間にメールを受信したプロファイルを除外する、1 年を超えるメールの数を制限するなど）にどのような影響を与えますか？

新しい TTL ポリシーでは、プロファイルストア内のシステム生成データセットデータのルックバック期間が 90 日間、データレイク内のルックバック期間が 13 か月に制限されます。 これらの期間を超えてデータにアクセスする必要があるユースケースは影響を受けます。 例えば、プロファイルストアで 90 日以上経過したイベントに基づくオーディエンスのセグメント化やフリークエンシーキャップは、システムデータセットを使用して行うことはできなくなります。

+++

+++TTL よりも長くデータを保持するための代替手段は何ですか？

より長い保持期間が必要なお客様は、TTL の有効期限が切れる前に、AJO データセットから関連データを外部ストレージにエクスポートすることを考慮する必要があります。 Adobe Journey Optimizer は、様々なクラウドストレージの宛先（Amazon S3、Azure Blob、Google Cloud Storage など）へのデータセットのエクスポートをサポートしています。 [詳細情報](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja){target=_blank}

+++

+++TTL の変更に備えて、お客様は何を行う必要がありますか？

* ユースケースを確認し、新しい TTL を超えてデータ保持が必要なユースケースを特定します。
* データを削除する前に、重要なデータを派生データセットにコピーする自動クエリを設定します。
* その他のニーズや潜在的な TTL 拡張（今後のリリースで予定）について詳しくは、アドビ担当者にお問い合わせください。

+++

+++既存のサンドボックスに TTL を適用する前に顧客に通知されますか？

はい、影響を受けるお客様には事前に通知し、製品チームがお客様と連携してスムーズな移行を実現します。

+++

+++Journey Optimizer システムで生成されたデータセットを削除できますか？

Journey Optimizer システムで生成されたデータセットは保護されており、標準の Adobe Experience Platform UI を通じて削除できません。 これらのデータセットは、Journey Optimizer の機能に不可欠で、システムによって管理されます。

Journey Optimizer システムデータセットを完全に削除する必要がある場合は（例：QA 環境、サンドボックスのクリーンアップ、または特定のデータハイジーン要件に対する）、アドビエンジニアリングまたはアドビカスタマーケアにお問い合わせください。 これらのデータセットを完全で安全に削除するには、特殊なバックエンド手順が必要です。

>[!NOTE]
>
>これらのシステムデータセット内の日常的なデータクリーンアップでは、Privacy Service を通じて利用できる&#x200B;**[!UICONTROL データライフサイクル]**&#x200B;操作を使用して、特定のレコードまたは ID を削除します。 [詳細情報](../privacy/data-hygiene.md)


+++
