---
title: Customer Journey Analytics でのレポート
description: Customer Journey Analytics でのレポートの実行方法を説明します
feature: Experience Decisioning
topic: Integrations
role: User
level: Experienced
badge: label="限定提供"
exl-id: 7c45cd8a-8e86-4646-ba0a-db393e92d9da
source-git-commit: 2349145fcf698769d16326a19a48a413a3c1dd95
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 100%

---

# Customer Journey Analytics でのレポート {#cja}

Customer Journey Analytics を操作している場合は、エクスペリエンス決定を活用して、コードベースのキャンペーン用のカスタムレポートダッシュボードを作成できます。

主な手順は以下のとおりです。Customer Journey Analytics の操作方法について詳しくは、[Customer Journey Analytics ドキュメント](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-landing){target="_blank"}を参照してください。

1. Customer Journey Analytics で&#x200B;**接続**&#x200B;を作成して設定します。これにより、レポートが必要なデータセットに接続できます。[詳しくは、接続の作成方法を参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}

1. **データビュー**&#x200B;を作成し、前に作成した接続に関連付けます。「**[!UICONTROL コンポーネント]**」タブで、レポートに表示する関連スキーマフィールドを選択します。エクスペリエンス決定の場合は、**propositioninteract** フィールドと **propositiondisplay** フィールドを必ず含めてください。[詳しくは、データビューの作成および設定方法を参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}

1. **ワークスペースプロジェクト**&#x200B;でデータコンポーネント、テーブル、ビジュアライゼーションを組み合わせて、コードベースのキャンペーンのレポートを作成して共有します。[詳しくは、ワークスペースプロジェクトの作成方法を参照してください](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects){target="_blank"}
