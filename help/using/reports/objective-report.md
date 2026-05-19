---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンのグローバルレポート
description: キャンペーンのグローバルレポートからデータを使用する方法を説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
hide: true
exl-id: ec1af88c-7b0a-4eaf-97e1-0d9676268fed
badge: label="ベータ版" type="Informative"
TQID: https://experienceleague.adobe.com/x-01SLf7JHabLWahy--Kbf8OQIDaUbu7r6YrM-vSs0o
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 481
ht-degree: 100%

---

# キャンペーンのグローバルレポート {#objective-report}

キャンペーンのグローバルレポートへは、「**[!UICONTROL レポートを表示]**」ボタンを使用して、キャンペーンから直接アクセスできます。

キャンペーンの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;は、キャンペーンの成功とエラーの詳細を示す様々なウィジェットに分かれています。 必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。 詳しくは、この <!--[section](../reports/global-report.md#modify-dashboard)--> を参照してください。

Adobe Journey Optimizer で使用できるすべての指標のリストについて詳しくは、<!--[this page](global-report.md#list-of-components-global.md)--> を参照してください。

## 「キャンペーン」タブ {#campaign-global-objectives}

### 配信 {#delivery-global-objectives}

<!--
![](assets/campaign_report_global_1.png)
-->

**[!UICONTROL キャンペーンの統計]**&#x200B;ウィジェットには、キャンペーンに関連する主な情報の詳細が表示されます。

* **[!UICONTROL エントリ済みプロファイル]**：ジャーニーを開始したプロファイルの数。

* **[!UICONTROL 配信されたアクション]**：ジャーニー内のアクションが配信されたユニーク回数の合計。

* **[!UICONTROL アクションが % で失敗しました]**：アクションが配信されたユニーク回数の合計に対する、ジャーニーでアクションが失敗したユニーク回数の合計。

### 目標レポート {#objective-global}

>[!AVAILABILITY]
>
>**目標レポート**&#x200B;機能は現在、一連の組織でのみ使用できます（使用制限あり）。 詳しくは、アドビ担当者にお問い合わせください。

![](assets/performance_report.gif)

「**[!UICONTROL 目標]**」タブを使用すると、1 つの特定の指標をターゲティングすることで、配信のレポートをより細かく調整できます。

一覧表示された&#x200B;**[!UICONTROL 目標]**&#x200B;は、追加情報を取得するためのシステムへの接続を定義する&#x200B;**[!UICONTROL データセット]**&#x200B;にリンクされています。 ビルトインの&#x200B;**[!UICONTROL 目標]**&#x200B;リストが用意されていますが、新しい&#x200B;**[!UICONTROL データセット]**&#x200B;を追加することで独自の目標を追加できます。 詳細な手順については、こちらの[節](../reports/reporting-configuration.md)を参照してください。

ターゲットにする目標を選択した後、2 つの&#x200B;**[!UICONTROL パフォーマンスの概要]**&#x200B;および&#x200B;**[!UICONTROL キャンペーン目標]**&#x200B;ウィジェットには、配信パフォーマンスの詳細な概要が表示されます。

**[!UICONTROL キャンペーン目標]**&#x200B;ウィジェットを使用して、主な目標を別の指標と比較することもできます。

### 実験レポート {#experimentation-global-objectives}

<!--
![](assets/experimentation_report_3.png)
-->

「**[!UICONTROL 実験]**」タブには、各バリアントのパフォーマンスに関する主要なインサイトが表示され、最も成功したものを特定します。

最もパフォーマンスの高い処理の判定には時間がかかる場合があり、このアイコン ![](assets/experimentation_report_1.png) が表示されます。

+++実験レポートで使用できる様々な指標およびウィジェットについて説明します。

**[!UICONTROL 実験結果]**&#x200B;ウィジェットは、各バリアントのパフォーマンスの詳細を説明します。 ベースラインを変更するには、**[!UICONTROL ベースライン]**&#x200B;ドロップダウンから処理の 1 つを選択します。 最も優れた処理には、星のアイコンが表示されます。

このテーブルは、次の指標を表しています。

* **[!UICONTROL ベースライン上の上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。 [詳細情報](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)

* **[!UICONTROL ユニークアウトバウンドクリック数]**：アウトバウンドチャネルでのクリック総数。

* **[!UICONTROL プロファイル]**：この処理の対象となるプロファイルの数。

* **[!UICONTROL ユニークアウトバウンドクリック数／プロファイル数]**：実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。

**[!UICONTROL 信頼区間]**&#x200B;グラフは、改善に関する不確実性を測定します。 ベースラインと最もパフォーマンスの高い処理との間のパフォーマンス差の割合を詳細に示します。 [詳細情報](../content-management/experiment-calculations.md#adobes-statistical-methodology-any-time-valid-confidence-sequences)
+++

これらの結果の詳細と解釈について詳しくは、[このページ](../content-management/get-started-experiment.md#interpret-results)を参照してください。
