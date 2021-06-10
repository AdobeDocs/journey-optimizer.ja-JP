---
title: Adobe Analytics データについて
description: Adobe Analytics データの活用方法について説明します
source-git-commit: 55b9e5d8ed259ec6ed7746e835691d7d6261a8a4
workflow-type: ht
source-wordcount: '192'
ht-degree: 100%

---

# Adobe Analytics データの活用{#analytics-data}

![](../assets/do-not-localize/badge.png)

>[!NOTE]
>
>この節は、ルールベースのイベントと、Adobe Analytics データを使用する必要があるお客様にのみ当てはまります。

ジャーニーをトリガーし顧客向けのエクスペリエンスを自動化するために、既にキャプチャして Platform にストリーミングしている Adobe Analytics のあらゆる行動イベントデータを活用できます。

そのためには、利用するレポートスイートを Adobe Experience Platform で有効化する必要があります。

1. Adobe Experience Platform の「Adobe Analytics」セクションで、「**[!UICONTROL ソース]**」を選択してから「**[!UICONTROL データを追加]**」を選択します。使用可能な Adobe Analytics レポートスイートのリストが表示されます。

1. 有効にするレポートスイートを選択し、「**[!UICONTROL 次へ]**」をクリックして、「**[!UICONTROL 終了]**」をクリックします。

1. ソースデータ ID をベータプログラムの連絡窓口と共有します。

これにより、そのレポートスイートの Analytics ソースコネクタが有効になります。データが入ってくるたびに、データはエクスペリエンスイベントに変換され、Adobe Experience Platform に送信されます。

![](../assets/jo-event9.png)

Adobe Analytics ソースコネクタの詳細については、[ドキュメント]https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ja) および[チュートリアル](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja)を参照してください。
