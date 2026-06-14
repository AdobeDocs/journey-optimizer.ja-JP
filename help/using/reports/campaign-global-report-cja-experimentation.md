---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンレポート
description: キャンペーンレポートから実験データを使用する方法について説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 69742163-7378-49ab-929e-86213d6e65e3
TQID: https://experienceleague.adobe.com/m11Vxa3bSvaOHe1kFs5tU9oQS08lzcL0DSPyrABbXBI
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: a9f73820-6899-47c2-a597-3fec28ab756aid: b49ca41f-eb7a-4f4b-abeb-a97c06fd0c04
subfeature_v2: id: d145add9-d5b9-481b-aa8a-e15e6bb7f813id: a7289281-9ae4-47b1-b8cf-4028b98af776id: b5afe8bf-bda6-41b5-ba06-922638872d63
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 7f28f19b11ead867b0851943fdd997dcc3af170b
workflow-type: tm+mt
source-wordcount: 356
ht-degree: 84%

---

# 実験キャンペーンレポート {#campaign-global-report-cja-experimentation}

>[!BEGINSHADEBOX]

**このページでは、** Adobe Journey Optimizerの実験キャンペーンレポートを読んで、選択した成功指標の上昇率、信頼度、コンバージョン率などの指標を使用してバリエーションのパフォーマンスを比較する方法について説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="成功指標"
>abstract="実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。"

## 実験 {#experimentation}

「**[!UICONTROL 実験]**」タブには、各バリアントのパフォーマンスに関する主要なインサイトが表示され、最も成功したものを特定します。

最もパフォーマンスの高い処理の判定には時間がかかる場合があります。 実験が成功しなかった場合は、**決定的でない**&#x200B;に設定されます。

![](assets/cja-experimentation-1.png)

### 実験 KPI {#experimentation-kpis}

![](assets/cja-experimentation-kpis.png)

**[!UICONTROL 実験]**&#x200B;の主要業績評価指標（KPI）は包括的なダッシュボードとして機能し、実験に関連する重要な指標の分析を提供します。

+++ 詳しくは、実験 KPI 指標を参照してください

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。 [詳細情報](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)

+++

### 成功指標別のバリアント {#variant-inbound}

![](assets/cja-experimentation-variants.png)

成功指標ごとの&#x200B;**バリアント** テーブルは、実験の設定時に選択した成功指標に基づいて、各バリアントがどのように機能するかを示します。
これらの結果の詳細と解釈方法については、[このページ ](../content-management/get-started-experiment.md#interpret-results)を参照してください。

+++ 成功指標別のバリアントの詳細情報

* **[!UICONTROL ユーザー]**：メッセージのターゲットプロファイルに適格な、ユーザープロファイルの数。

* **[!UICONTROL インバウンドクリック数]**：実験の作成時に以前に選択した成功指標の合計値。

* **[!UICONTROL コンバージョン率]**：実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼下限]**：選択した信頼区間内での、処理とベースライン間のコンバージョン率の差の最小推定値。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。 [詳細情報](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)

* **[!UICONTROL 信頼上限]**：選択した信頼区間内での、処理とベースライン間のコンバージョン率の差の最高推定値。

+++

### 成功指標のコンバージョン率 {#conversion-rate}

![](assets/cja-experimentation-conversion.png)


**[!UICONTROL 信頼区間]**&#x200B;グラフには、選択した成功指標に対してベースラインと最もパフォーマンスの高い処理を比較し、改善の可能性のある範囲が表示されます。 [学習を増やす](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)。