---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーレポート
description: ジャーニーレポートのデータの使用方法について説明します
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
badge: label="限定提供" type="Informative"
source-git-commit: 30a7ebde95f2cb1ddecf3dc48420076914db4b12
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---

# カスタムアクションの監視 {#reporting}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_custom_actions_monitor"
>title="カスタムアクションの監視"
>abstract="**[!UICONTROL カスタムアクション]**&#x200B;レポートページでは、ジャーニーでサードパーティシステムに対して実行される API 呼び出しのパフォーマンスと信頼性を追跡できます。"

>[!AVAILABILITY]
>
>カスタムアクションレポートは現在、一連の組織でのみ使用できます（限定提供）。

**[!UICONTROL カスタムアクション]**&#x200B;レポートページでは、サードパーティシステムに対してジャーニーから実行される API 呼び出しの信頼性とパフォーマンスを監視できます。これらのレポートは、配信に影響を与える場合がある統合の問題、待ち時間のボトルネック、スロットル／キャップ制限をすばやく特定するのに役立ちます。

カスタムアクションレポートページは、Journey Optimizer の他の全期間のレポートと同様に機能します。ダッシュボードの機能について詳しくは、[このドキュメント](../reports/report-cja-manage.md)を参照してください。

**[!UICONTROL カスタムアクション]**&#x200B;レポートページにアクセスするには、**[!UICONTROL アクション]**&#x200B;ホームページから「![](assets/do-not-localize/Smock_Monitoring_18_N.svg)」をクリックします。

![](assets/monitor-1.png)

➡️ [カスタムアクションの設定方法の詳細情報](../action/about-custom-action-configuration.md)

**[!UICONTROL カスタムアクション]**&#x200B;レポートページに加えて、**[!DNL Adobe Experience Platform Query Service]** を使用して、カスタムアクションのパフォーマンス指標に関するレポートに対してクエリを作成できます。クエリの例について詳しくは、[この節](../reports/query-examples.md)を参照してください。

## KPI {#kpis}

![](assets/monitor-2.png)

**[!UICONTROL カスタムアクション]**&#x200B;の主要業績評価指標（KPI）は一元化されたダッシュボードとして機能し、カスタムアクション呼び出しの運用の健全性と信頼性の統合ビューを提供します。これらの指標を使用すると、パフォーマンスを評価し、ボトルネックを特定し、外部システムとの安定した統合を確保できます。

+++ カスタムアクション KPI の詳細情報

* **[!UICONTROL 成功した呼び出し]**：エラーなしで有効な応答を返した HTTP 呼び出しの合計数。

* **[!UICONTROL 4xx／5xxエラー]**：クライアントサイド（4xx）またはサーバーサイド（5xx）のエラーにより失敗した呼び出しの数。設定の問題またはエンドポイントのエラーがハイライト表示されます。

* **[!UICONTROL タイムアウト]**： 最大応答時間を超えたので失敗した呼び出しの数。これは、外部エンドポイントの待ち時間やパフォーマンスの問題を明らかにするのに役立ちます。

* **[!UICONTROL キャッピングされた呼び出し]**：キャップ制限によりブロックされた呼び出しの数。ダウンストリームシステムが過負荷にならないようにします。

* **[!UICONTROL 平均 RPS]**：選択した時間範囲でカスタムアクションにより処理された 1 秒あたりのリクエスト数。

+++

## 時間外呼び出し {#calls}

![](assets/monitor-3.png)

**[!UICONTROL 時間外呼び出し]**&#x200B;グラフには、レポートに対して選択した期間の HTTP 呼び出し KPI のトレンドが表示されます。時系列の精度は、選択した時間範囲に応じて異なります。例：

* 7 日間のレポートの場合、各データポイントには 1 日の KPI が表示されます。
* 1 日間の時間範囲を選択した場合、グラフには 1 時間あたりの KPI が表示されます。
* 1 時間の時間範囲を選択した場合、グラフには 1 分あたりの KPI が表示されます。

➡️[HTTP 呼び出し指標について詳しくは、KPI の節を参照してください](#kpis)

## 呼び出し分類 {#breakdown}

![](assets/monitor-4.png)

**[!UICONTROL 呼び出し分類]**&#x200B;テーブルには、上位レベルのエンドポイントごとの全体的な指標から、各エンドポイントを使用するカスタムアクションごとの指標、下位レベルで依存するジャーニーまで、HTTP 呼び出し指標の階層的な分類が示されます。

➡️[HTTP 呼び出し指標について詳しくは、KPI の節を参照してください](#kpis)


