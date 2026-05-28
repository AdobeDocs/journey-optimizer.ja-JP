---
title: Web エクスペリエンスの監視
description: Journey Optimizer での web エクスペリエンスの監視方法を学ぶ
feature: Web Channel, Reporting, Monitoring
topic: Content Management
role: User
level: Beginner, Intermediate
exl-id: d89795bb-c51d-4d1f-b7ed-2b2c5d278922
TQID: https://experienceleague.adobe.com/CEjKwnKx1ixUKA-mO7FfWGXaW9FyO-I-ZYyYm0scs88
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2: id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
subfeature_v2: id: c618a0dc-1818-4c6d-9916-0d92e6796f24id: d056adbe-402d-4f42-9746-f3d424e598b1
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e9001ce2-5245-4a8e-8601-dd958009072f
source-git-commit: 0ee10a0689d38c22b1180b197796b08a10c286cf
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 100%

---

# Web エクスペリエンスの監視 {#monitor-web-experiences}

## Web レポートの確認 {#check-web-reports}

Web エクスペリエンスがライブになったら、[ジャーニーリポート](../reports/journey-global-report-cja-web.md)と[キャンペーンレポート](../reports/campaign-global-report-cja-web.md)の「**[!UICONTROL Web]**」タブを確認して、インプレッション数、クリック率、web ページでのエンゲージメント数などの要素を比較できます。

<!--You can check the **[!UICONTROL Web]** tab of the campaign reports. Learn more about the campaign web [live report](../reports/campaign-live-report.md#web-tab) and [global report](../reports/campaign-global-report-cja.md#web).-->

Web エクスペリエンスの監視をさらに強化するには、web サイトの特定の要素に対するクリック数を追跡することもできます。 これにより、web レポートにその要素のクリック数を表示できます。 [方法についてはこちらを参照](#use-click-tracing)

## クリックの追跡を使用 {#use-click-tracking}

Web designer を使用すると、web サイトの任意の要素を選択し、その要素に対するクリック数をトラックできます。

この情報は、web サイトのユーザーエクスペリエンスを向上させるのに役立ちます。 例えば、実際にはクリックできない要素を多くのユーザーがクリックしたことが [web レポート](../reports/campaign-global-report-cja-web.md)でわかる場合は、その要素にリンクを追加したほうが良い可能性があります。

1. ページの要素を選択し、コンテキストメニューの「**[!UICONTROL クリック追跡の要素]**」を選択します。

   ![](assets/web-designer-click-track.png)

   >[!NOTE]
   >
   >任意の項目（クリック可能またはクリック不可）を選択できます。

1. 対応する追跡対象のアクションが、左側の&#x200B;**[!UICONTROL クリック追跡]**&#x200B;パネルに表示されます。

   ![](assets/web-designer-click-track-pane.png)

1. 追跡されたすべての要素を管理し、レポートで簡単に見つけるためのわかりやすいラベルを追加します。 **[!UICONTROL CSS セレクター]**&#x200B;フィールドに、選択した要素を見つけるための情報が表示されます。

1. 上記の手順を繰り返し、クリックの追跡に必要な数の他の要素を選択します。 対応するすべてのアクションが左側のウィンドウに表示されます。

   ![](assets/web-designer-click-tracking-actions.png)

1. 要素でのクリックの追跡を削除するには、対応する削除アイコンを選択します。

キャンペーンがライブになったら、キャンペーン web [ライブレポート](../reports/campaign-live-report.md#web-tab)および [Customer Journey Analytics レポート](../reports/campaign-global-report-cja-web.md)で各要素のクリック数を確認できます。
