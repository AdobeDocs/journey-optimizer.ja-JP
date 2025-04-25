---
title: 決定に関するレポート
description: 決定に関するレポート方法について説明します。
feature: Decisioning
topic: Integrations
role: User
level: Experienced
exl-id: 7c45cd8a-8e86-4646-ba0a-db393e92d9da
source-git-commit: 4c0605d6ccff5cd62ef7aeb04e0610342d7cc3d5
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 82%

---


# 決定に関するレポート {#decisioning-report}

## コードベースのキャンペーンレポート {#campaigns}

コードベースのエクスペリエンスが公開されると、専用レポートにアクセスし、包括的なダッシュボードとして機能する主要業績評価指標（KPI）を監視して、キャンペーンに関連する重要な指標の分析を確認できます。

これには、決定項目のパフォーマンスと、ユーザーが決定項目をどのように操作したかに関する詳細が含まれます。[詳しくは、コードベースのエクスペリエンスレポートの操作方法を参照してください](../reports/campaign-global-report-cja-code.md)

![](../reports/assets/cja-decisioning-item-performance.png)

## Customer Journey Analytics でのレポート {#cja}

Customer Journey Analytics を操作している場合は、決定を活用して、コードベースのキャンペーン用のカスタムレポートダッシュボードを作成できます。

主な手順は以下のとおりです。Customer Journey Analyticsの操作方法について詳しくは、[Customer Journey Analytics ドキュメント ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-landing){target="_blank"} を参照してください。

1. Customer Journey Analytics で&#x200B;**接続**&#x200B;を作成して設定します。これにより、レポートが必要なデータセットに接続できます。[ 接続の作成方法についてはこちらを参照してください ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}

1. **データビュー**&#x200B;を作成し、前に作成した接続に関連付けます。「**[!UICONTROL コンポーネント]**」タブで、レポートに表示する関連スキーマフィールドを選択します。決定の場合は、「**propositioninteract**」フィールドと「**propositiondisplay**」フィールドを必ず含めてください。[ データビューの作成および設定方法を学ぶ ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}

1. **ワークスペースプロジェクト**&#x200B;でデータコンポーネント、テーブル、ビジュアライゼーションを組み合わせて、コードベースのキャンペーンのレポートを作成して共有します。[ ワークスペースプロジェクトの作成方法を学ぶ ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects){target="_blank"}
