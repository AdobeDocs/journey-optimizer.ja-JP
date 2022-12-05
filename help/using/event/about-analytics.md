---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Analytics データについて
description: Adobe Analytics データの活用方法について説明します
feature: Events
topic: Administration
role: Admin
level: Intermediate
exl-id: 9d842722-e5eb-4743-849d-b7ba9448062f
source-git-commit: a6735063ec68b40b1441b379a20cba8953b59447
workflow-type: ht
source-wordcount: '203'
ht-degree: 100%

---

# Adobe Analytics データの活用{#analytics-data}

ジャーニーをトリガーし顧客向けのエクスペリエンスを自動化するために、既にキャプチャして Adobe Experience Platform にストリーミングしている Adobe Analytics のあらゆる行動イベントデータを活用できます。

>[!NOTE]
>
>この節では、ルールベースのイベントと、Adobe Analytics データを使用する必要があるお客様が対象です。

そのためには、利用するレポートスイートを Adobe Experience Platform で有効化する必要があります。これを行うには、以下の手順に従います。

1. Adobe Experience Platform に接続し、**[!UICONTROL ソース]**&#x200B;を参照します。
1. 「Adobe Analytics」セクションで、「**[!UICONTROL データを追加]**」を選択します。使用可能な Adobe Analytics レポートスイートのリストが表示されます。

1. 有効にするレポートイートを選択し、「**[!UICONTROL 次へ]**」および「**[!UICONTROL 終了]**」をクリックします。

1. ソースデータ ID をベータプログラムの連絡窓口と共有します。

これにより、そのレポートスイートの Analytics ソースコネクタが有効になります。データが入ってくるたびに、データはエクスペリエンスイベントに変換され、Adobe Experience Platform に送信されます。

![](assets/jo-event9.png)

Adobe Analytics ソースコネクタについて詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja){target=&quot;_blank&quot;}と[チュートリアルl](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja){target=&quot;_blank&quot;}を参照してください。
