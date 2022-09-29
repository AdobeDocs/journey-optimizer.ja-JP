---
title: アラート
description: アラートの管理方法の詳細
feature: Alerts
topic: Administration
role: Admin
level: Intermediate
source-git-commit: 3d0d1b7d092ffae48ded337d5a1b14a5f5c4653b
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 20%

---

# アラートの概要 {#alerts}

Journey OptimizerはAdobe Experience Platformのアラート機能を活用します。 これにより、ユーザーインターフェイスからシステムアラートにアクセスできます。 使用可能なアラートを表示し、購読することができます。 操作の特定の条件セットに達すると（システムがしきい値に達した場合に問題が発生する可能性があるなど）、アラートメッセージは、組織内でその条件を購読しているユーザーに配信されます。 これらのメッセージは、アラートが解決されるまで、事前に定義された時間間隔で繰り返すことができます。

Adobe Experience Platformのアラートの詳細 [ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=ja).
アラートを購読して設定する方法については、次を参照してください。 [ページ](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html).

左側のメニューで、 **管理**&#x200B;をクリックし、 **アラート**. Journey Optimizerの事前設定済みのアラートを使用できます。 このアラートは、セグメント読み取りノードが定義された期間内にプロファイルを処理しなかった場合に警告を表示します。

![](assets/alerts1.png)

このような予期しない動作が発生した場合は、インターフェイスの右上隅にある電子メールおよびアプリ内通知を通じて、アラートの購読者にアラート通知が送信されます。

![](assets/alerts2.png)

[Platform UI でアラートルールを表示](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html)すると、各ルールを個別に登録できます。ただし、[I/O イベント通知](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html)を通じてアラートを登録する場合、アラートルールは異なる登録パッケージに整理されます。「セグメントを読み取り」アラートに対応する I/O イベントの購読名は次のとおりです。「ジャーニー読み取りセグメントの遅延、失敗、エラー」

>[!WARNING]
>
>これらのアラートは、ライブジャーニーにのみ適用されます。 テストモードのジャーニーに対しては、アラートはトリガーされません。