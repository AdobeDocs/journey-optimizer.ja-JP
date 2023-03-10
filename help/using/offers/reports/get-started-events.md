---
title: 意思決定管理イベントの概要
description: Adobe Experience Platform で意思決定管理レポートを作成する方法を説明します。
feature: Offers
topic: Integrations
role: User
level: Beginner
exl-id: 51830c63-fa88-47e7-8605-192297fcf6b8
source-git-commit: b06b545d377fcd1ffe6ed218badeb94c1bb85ef2
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 78%

---

# 意思決定管理イベントの概要 {#monitor-offer-events}

決定管理が特定のプロファイルに対して決定をおこなうたびに、これらのイベントに関する情報がAdobe Experience Platformに自動的に送信されます。

これにより、これらのデータをエクスポートして、その分析結果を独自のレポートシステムに送信できます。また、分析やレポートの強化を目的として、Adobe Experience Platform の[クエリサービス](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ja)を他のツールと組み合わせて利用することもできます。

決定管理イベントを含むデータセットは、Adobe Experience Platformからアクセスできます **[!UICONTROL データセット]** メニュー 各インスタンスのプロビジョニング時、データセットが自動的に 1 つ作成されます。

![](../assets/events-datasets-list.png)

これらのデータセットは、**[!UICONTROL ODE DecisionEvents]** スキーマに基づいています。このスキーマには、意思決定管理サービスから Adobe Experience Platform に情報を送信するために必要なすべての XDM フィールドが含まれています。


>[!NOTE]
>
>なお、ODE DecisionEvents データセットは&#x200B;**プロファイル以外のデータセット**&#x200B;です。つまり、Experience Platform に取り込んでリアルタイム顧客プロファイルで使用することはできません。

**関連トピック：**

* [意思決定管理イベントの主な情報](../reports/key-information.md)
* [イベントの XDM フィールドへのアクセス](../reports/xdm-fields.md)
