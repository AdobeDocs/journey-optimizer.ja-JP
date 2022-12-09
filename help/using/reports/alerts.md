---
solution: Journey Optimizer
product: journey optimizer
title: よる
description: アラートを管理する方法について説明します。
feature: Alerts
topic: Administration
role: Admin
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: f6db4f7cbb1951c009fa7915f340da96eea74120
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# アラートについての概要 {#alerts}

Adobe エクスペリエンスプラットフォームアラート機能を活用しています。 これにより、ユーザーインターフェイスからシステム警告にアクセスすることができます。 使用可能なアラートを表示して、サブスクライブすることができます。 操作において特定の条件セットに達した場合 (システムがしきい値に達したときに発生する可能性のある問題など)、そのアラートメッセージは組織内のすべてのユーザーに配信されます。 これらのメッセージは、事前に定義された時間間隔で、警告が解決されるまで繰り返されます。

Adobe エクスペリエンスプラットフォーム [ マニュアル ](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html) に記載されているアラートについて詳しく説明しています。アラートのサブスクライブと設定については、この [ ページ ](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html) を参照してください。

左側のメニューで、「管理 **」の下の「** アラート **」をクリックし** ます。旅オプティマイザー用に事前に設定された警告を利用できます。 このアラートは、指定された時間枠内に、「セグメントの読み取り」ノードによってどのプロファイルも処理されていない場合に、警告を表示します。

![](assets/alerts1.png)

このような予想外の動作が発生した場合は、インターフェイスの右上隅に、電子メールで警告通知が通知されます。

![](assets/alerts2.png)

Adobe エクスペリエンスプラットフォームの UI ](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html) で警告ルールを表示しているとき [ に、各ルールを個別に購読することができます。ただし、i/o イベント通知 ](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html) を使用して [ 警告のサブスクライブを行うと、異なる購読パッケージにアラートルールが整理されます。「セグメントの読み取り」アラートに対応する i/o イベントサブスクリプション名は、「旅の読み取りセグメントの遅延、失敗およびエラー」となります。

>[!WARNING]
>
>このようなアラートは、ライブ journeys にのみ適用されます。 Journeys では、警告はテストモードではトリガーされません。
