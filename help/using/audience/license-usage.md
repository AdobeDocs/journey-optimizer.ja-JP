---
solution: Journey Optimizer
product: journey optimizer
title: ライセンス使用状況ダッシュボード
description: Journey Optimizer ライセンス使用状況ダッシュボードについて説明します
feature: Audiences, Profiles
topic: Content Management
role: User
level: Beginner
exl-id: 7e91face-c8f4-4e70-9123-9e36bae7e67e
TQID: https://experienceleague.adobe.com/KrsJKfvAPAE5yW2Lgrc-MrMUtoxi336rsmQIglfs7Mc
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: bb359667-ec7d-4d4b-8663-5850fc219d32id: d998adac-2f81-400b-a669-d07bb196e4ebid: dc22c819-3f29-4e91-8b7d-5c6719831141id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2: id: fb9a80eb-bebc-492f-a0e9-584595621ebbid: fdac7813-bd56-47ae-9f6d-fa94ad1c5dee
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 868
ht-degree: 23%

---

# ライセンス使用状況ダッシュボード {#license-usage}

[!DNL Adobe Journey Optimizer] [ユーザーインターフェイス](../start/user-interface.md)は、毎日のスナップショットでキャプチャされた、組織のライセンス使用状況に関する重要な情報を表示するダッシュボードを提供します。

このダッシュボードにアクセスするには、**[!UICONTROL 管理]**／**[!UICONTROL ライセンスの使用状況]**&#x200B;に移動します。 これにより、ダッシュボードに表示される「**[!UICONTROL 概要]**」タブが開きます。

![ライセンス使用状況ダッシュボードの概要](assets/license-usage-dashboard.png)

>[!NOTE]
>
>* ダッシュボードを表示するには、[ライセンス使用状況ダッシュボードを表示](https://experienceleague.adobe.com/docs/experience-platform/dashboards/permissions.html?lang=ja#available-permissions){target="_blank"}権限を付与されている必要があります。
>
>* 開発サンドボックスの場合、割り当て量列に `N/A` と示されるので、特定の指標（例：計算時間、メールなど）は表示されません。 ダッシュボードには、null 以外の値のみが表示されます。指標がゼロまたはゼロに近い場合、これらの値は入力されません。


[!DNL Adobe Journey Optimizer]の場合、ダッシュボードでは&#x200B;**エンゲージ可能なプロファイル**&#x200B;の数を確認できます。

## 魅力的なプロファイルとは？ {#what-is-engageable-profile}

**エンゲージ可能なプロファイル**&#x200B;は、プロファイルサービスに保存され、ジャーニーまたはキャンペーンによってエンゲージされた個人を表す情報の記録です。

エンゲージメント可能なプロファイルの主な特徴：

* **12か月間のローリングウィンドウ**：過去12か月間のエンゲージメントに基づいて、エンゲージ可能なプロファイルがカウントされます。 この指標は、Journey Optimizerのオーサリング、決定、配信、実験、オーケストレーション機能を使用してエンゲージしようとした一意のプロファイルの数を示します。

* **サンドボックスごとのユニーク数**: プロファイルがサンドボックス内で複数のジャーニーまたはキャンペーンにエントリした場合、そのサンドボックスの単一のエンゲージ可能なプロファイルとして1回のみカウントされます。

* **アドレス可能なオーディエンスに基づく**：エンゲージ可能なプロファイルは、アドレス可能なオーディエンスから計算されます。 カウントは、Journey Optimizerの機能を使用して過去12か月間にエンゲージしたオーディエンスを表し、アドレス可能なオーディエンスの合計です。

* **指標の動作**: エンゲージ可能なプロファイル数：
   * ジャーニーや施策を通じて新しいプロファイルがエンゲージする割合が増加する可能性がある
   * 12 カ月以上特定のプロファイルにエンゲージメントがない限り、顧客数は減少しません
   * 仮名プロファイルを既知のプロファイルに合成すると減少する可能性があります

>[!NOTE]
>
>エンゲージメント可能なプロファイル数が急激に増加した場合は、問題の理解と解決に関する詳細なガイダンスについては、以下の[ トラブルシューティングの節](#troubleshooting-engageable-profiles)を参照してください。

## トラブルシューティング：エンゲージメント可能なプロファイル数が大幅に増加 {#troubleshooting-engageable-profiles}

エンゲージメント可能なプロファイル数が急激に増加した場合（例えば、1日以内にプロファイル数が数十万から数百万に増加した場合など）、このセクションでは、問題を理解し、対処するためのガイダンスを提供します。

### 増加について

「エンゲージメント可能なプロファイル」指標には、過去12 ヶ月間にジャーニーまたはキャンペーンによってエンゲージされた一意のプロファイルの数が反映されます。 突然の増加は次の要因から生じる可能性があります。

* 新しいジャーニーや施策のターゲットとなる大規模オーディエンス
* Profile Serviceに対して有効になっているデータセットの変更
* 最近エンゲージしていないオーディエンスのバッチ処理

### 解決ステップ

この問題に対処するには、次の手順に従います。

1. **プロファイル数のロジックについて：**

   * エンゲージメント可能なプロファイルは、過去12 ヶ月間のジャーニーやキャンペーンによってエンゲージされた独自のプロファイルにもとづいて計算されます。
   * プロファイルが複数のジャーニーにエントリした場合、そのサンドボックスの1つのエンゲージ可能なプロファイルとしてカウントされます。
   * 指標を低下させるには、特定のプロファイルに対して12 カ月以上エンゲージメントがない場合や、匿名のプロファイルを既知のプロファイルにつなぎ合わせる必要があります。
   * エンゲージメントプロファイルは、顧客のアドレス可能なオーディエンスを使用して計算されます。
   * 合計アドレス可能なオーディエンスのうち、Journey Optimizerの機能のいずれかを使用して過去12か月間にエンゲージしたオーディエンスは、エンゲージ可能プロファイルの数を決定します。

2. **大規模なオーディエンスを対象としたジャーニー、キャンペーン、決定の調査：**

   * [ エンゲージ可能なプロファイルクエリ ](../reports/query-examples.md#engageable-profiles-queries)または[ クエリサービス ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"}を使用して、多数のプロファイルをターゲットにした最近のジャーニーとキャンペーンを確認します。
   * プロファイル数の急増に貢献した特定のジャーニーバージョンを特定できます。
   * 新しいプロファイルを含むジャーニー、キャンペーン、意思決定は、ジャーニーデータセットのイベント数の増加につながり、エンゲージ可能なプロファイル数の増加につながります。

3. **ジャーニーおよびキャンペーン レベルでオーディエンスをフィルタリング：**

   * ジャーニーやキャンペーンを開始する前にオーディエンスレベルでフィルターを適用し、エンゲージメント可能なプロファイルが不必要に増加するのを防ぎます。
   * エンゲージメント中は、関連オーディエンスのみがターゲットにされるようにします。

4. **アドレス可能なオーディエンスサイズを減らします：**

   * 必要に応じて、仮名プロファイルを削除します。 このアクションは、Journey OptimizerとReal-Time Customer Data Platformの両方に影響することに注意してください。
   * 匿名プロファイルデータの有効期限[について詳しくは、リアルタイム顧客プロファイルガイドを参照してください。](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/pseudonymous-profiles){target="_blank"}
   * **メモ：**&#x200B;匿名プロファイルデータの有効期限は、Platform UIまたはAPIを使用して設定できません。 この機能を有効にするには、サポートにお問い合わせください。

5. **データセットの変更を監視：**

   * プロファイリングが有効になっているデータセットを確認し、過剰なECID （Experience Cloud ID）が含まれていないことを確認します。
   * 必要に応じて、ECID数の多いデータセットを削除し、レコードを減らして再作成します。

6. **長期的な削減戦略の策定：**

   * 特定のプロファイルが12 ヶ月以上エンゲージメントしていない場合、エンゲージメントプロファイルの数は自然に減少します。

**関連トピック：**

* [ エンゲージメント可能なプロファイル クエリの例](../reports/query-examples.md#engageable-profiles-queries) - エンゲージメント可能なプロファイルを監視および分析するためのクエリのサンプル
* [Adobe Experience Platform Query Serviceの概要](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"}

## 関連ドキュメント {#related-documentation}

詳しくは、Adobe Experience Platform ドキュメントを参照してください。

* [ライセンス使用状況ダッシュボードの概要](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja){target="_blank"}
* [ライセンス使用状況ダッシュボードの確認](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja#exploring-the-license-usage-dashboard){target="_blank"}
* [使用可能な指標](https://experienceleague.adobe.com/docs/experience-platform/dashboards/guides/license-usage.html?lang=ja#available-metrics){target="_blank"}
* [偽名プロファイルデータの有効期限](https://experienceleague.adobe.com/docs/experience-platform/profile/pseudonymous-profiles.html?lang=ja){target="_blank"}
