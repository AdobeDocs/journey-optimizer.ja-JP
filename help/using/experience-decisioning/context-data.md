---
title: 決定でのコンテキストデータの活用
description: Decisioning でコンテキストデータを活用する方法を説明します
feature: Decisioning
topic: Integrations
role: User
level: Intermediate
exl-id: ddc4b681-020b-4433-b4b3-3791c41907c9
source-git-commit: 616e1dd9fbfd029f7209356d5c19cfff9d4b4f06
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 59%

---

# 決定でのコンテキストデータの活用 {#context}

Decisioning を使用すると、Adobe Experience Platformで提供されている任意の情報を活用して、[ 決定ルール ](rules.md) または [ ランキング式 ](ranking.md) の作成などの様々なアクションを実行できます。 例えば、決定リクエストが行われた時点で現在の天気が 80 度以上であることを要求する決定ルールを設計できます。

>[!NOTE]
>
>コンテキストデータは、Adobe Experience Platform で定義され、決定リクエスト時に送信されます。履歴データは含まれません。

コンテキストデータを使用するには、まず Decisioning で使用可能にするデータを定義する必要があります。 完了すると、このデータは、決定ルールの作成時に使用できる「**[!UICONTROL コンテキストデータ]**」タブの決定にシームレスに統合されます。 また、ランキング式を編集する際に、データを活用することもできます。

![](assets/decision-rules-context.png)

Decisioning にAdobe Experience Platform データをフィードする手順は次のとおりです。

1. Adobe Experience Platform で&#x200B;**エクスペリエンスイベントスキーマ**&#x200B;およびそれに関連する&#x200B;**データセット**&#x200B;を作成します。[スキーマの作成方法については、こちらを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. 新しい Adobe Experience Platform データストリームを次の手順で作成します。

   1. **[!UICONTROL データストリーム]**&#x200B;メニューに移動し、「**[!UICONTROL 新規データストリーム]**」を選択します。

   1. **[!UICONTROL イベントスキーマ]**&#x200B;ドロップダウンリストで、先ほど作成したエクスペリエンスイベントスキーマを選択し、「**[!UICONTROL 保存]**」をクリックします。

      ![](assets/decision-rule-context-datastream.png)

   1. 「**[!UICONTROL サービスを追加]**」をクリックし、サービスとして「Adobe Experience Platform」を選択します。**[!UICONTROL イベントデータセット]**&#x200B;ドロップダウンリストで、先ほど作成したイベントデータセットを選択し、「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。

      ![](assets/decision-rules-context-datastream-service.png)

データストリームが保存されると、選択されたデータセットの情報が自動的に取得され、Decisioning に統合されます。通常、約 24 時間以内に使用可能になります。

Adobe Experience Platform の操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

* [エクスペリエンスデータモデル（XDM）スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [データセット](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview){target="_blank"}
