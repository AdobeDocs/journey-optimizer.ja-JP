---
title: web エクスペリエンスの監視
description: Journey Optimizerでweb エクスペリエンスをモニターする方法について説明します
feature: Web Channel, Reporting, Monitoring
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: d89795bb-c51d-4d1f-b7ed-2b2c5d278922
TQID: https://experienceleague.adobe.com/CEjKwnKx1ixUKA-mO7FfWGXaW9FyO-I-ZYyYm0scs88
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: dc22c819-3f29-4e91-8b7d-5c6719831141
subfeature_v2:
  - id: fb9a80eb-bebc-492f-a0e9-584595621ebb
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 0%

---

# web エクスペリエンスの監視 {#monitor-web-experiences}

## Web レポートを確認する {#check-web-reports}

Web エクスペリエンスが公開されたら、[ジャーニーレポート &#x200B;](../reports/journey-global-report-cja-web.md)および[&#x200B; キャンペーンレポート &#x200B;](../reports/campaign-global-report-cja-web.md)の「**[!UICONTROL Web]**」タブを確認して、インプレッション数、クリック率、web ページのエンゲージメント数などの要素を比較できます。

<!--You can check the **[!UICONTROL Web]** tab of the campaign reports. Learn more about the campaign web [live report](../reports/campaign-live-report.md#web-tab) and [global report](../reports/campaign-global-report-cja.md#web).-->

web エクスペリエンスのモニタリングをさらに改善するには、web サイトの特定の要素のクリックを追跡することもできます。 これにより、web レポート内のその要素のクリック数を表示できます。 [方法を学ぶ](#use-click-tracing)

## クリックトラッキングの使用 {#use-click-tracking}

web デザイナーを利用すれば、web サイトのあらゆる要素を選択して、その要素のクリック数を追跡できます。

この情報は、web サイトのユーザーエクスペリエンスを向上させるのに役立ちます。 例えば、[web レポート &#x200B;](../reports/campaign-global-report-cja-web.md)で、多くのユーザーが実際にはクリックできない要素をクリックしていることが示されている場合は、その要素にリンクを追加することができます。

1. ページ内の要素を選択し、コンテキストメニューから「**[!UICONTROL 要素を追跡]**」を選択します。

   ![](assets/web-designer-click-track.png)

   >[!NOTE]
   >
   >クリック可能かどうかに関係なく、任意の項目を選択できます。

1. 対応するトラッキングされたアクションが、左側の&#x200B;**[!UICONTROL クリックトラック]** ペインに自動的に表示されます。

   ![](assets/web-designer-click-track-pane.png)

1. トラッキング対象の要素をすべて管理し、レポートで簡単に見つけることができるように、意味のあるラベルを追加します。 **[!UICONTROL CSS セレクター]** フィールドには、選択した要素を検索するための情報が表示されます。

1. 上記の手順を繰り返して、クリックのトラッキングに必要な数だけ他の要素を選択します。 対応するアクションはすべて、左側のペインに一覧表示されます。

   ![](assets/web-designer-click-tracking-actions.png)

1. エレメントのクリックトラッキングを削除するには、対応する削除アイコンを選択します。

キャンペーンが開始されると、キャンペーン web [&#x200B; ライブレポート &#x200B;](../reports/campaign-live-report.md#web-tab)および[Customer Journey Analytics レポート &#x200B;](../reports/campaign-global-report-cja-web.md)の各要素のクリック数を確認できます。
