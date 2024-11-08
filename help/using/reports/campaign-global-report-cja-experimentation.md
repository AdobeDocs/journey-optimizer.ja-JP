---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンレポート
description: キャンペーンレポートから実験データを使用する方法について説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
source-git-commit: 47482adb84e05fe41eb1c50479a8b50e00469ec4
workflow-type: ht
source-wordcount: '279'
ht-degree: 100%

---

# 実験キャンペーンレポート {#campaign-global-report-cja-experimentation}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="成功指標"
>abstract="実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。"

## 実験 {#experimentation}

「**[!UICONTROL 実験]**」タブには、各バリアントのパフォーマンスに関する主要なインサイトが表示され、最も成功したものを特定します。

最もパフォーマンスの高い処理の判定には時間がかかる場合があります。実験が成功しなかった場合は、**決定的でない**&#x200B;に設定されます。

![](assets/cja-experimentation-1.png)

### 実験 KPI {#experimentation-kpis}

![](assets/cja-experimentation-kpis.png)

**[!UICONTROL 実験]**&#x200B;の主要業績評価指標（KPI）は包括的なダッシュボードとして機能し、実験に関連する重要な指標の分析を提供します。

+++ 実験 KPI 指標の詳細情報

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../content-management/experiment-calculations.md#understand-confidence)

+++

### インバウンドクリック数によるバリアント {#variant-inbound}

![](assets/cja-experimentation-variants.png)

**[!UICONTROL インバウンドクリック数によるバリアント]**ウィジェットは、各バリアントのパフォーマンスの詳細を説明します。
これらの結果の詳細と解釈について詳しくは、[このページ](../content-management/get-started-experiment.md#interpret-results)を参照してください。

+++ インバウンドクリック数指標によるバリアントの詳細情報

* **[!UICONTROL ユーザー]**：メッセージのターゲットプロファイルに適格な、ユーザープロファイルの数。

* **[!UICONTROL インバウンドクリック数]**：アウトバウンドチャネルでのクリック総数。

* **[!UICONTROL コンバージョン率]**：実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。

* **[!UICONTROL 上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../content-management/experiment-calculations.md#understand-confidence)

<!--
* **[!UICONTROL Confidence Upper bound]**:

* **[!UICONTROL Confidence Lower bound]**:
-->
+++

### インバウンドクリック数のコンバージョン率 {#conversion-rate}

![](assets/cja-experimentation-conversion.png)

**[!UICONTROL 信頼区間]**&#x200B;グラフは、改善に関する不確実性を測定します。ベースラインと最もパフォーマンスの高い処理との間のパフォーマンス差の割合を詳細に示します。[詳細情報](../content-management/experiment-calculations.md#confidence-intervals)
