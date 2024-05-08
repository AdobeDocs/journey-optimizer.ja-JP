---
title: Experience Decisioning でのコンテキストデータの活用
description: Experience Decisioning でコンテキストデータを活用する方法を説明します
feature: Experience Decisioning
topic: Integrations
role: User
level: Intermediate
badge: label="限定提供（LA）"
source-git-commit: 5ce388e5d86950e5cc6b173aab48225825f1c648
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 50%

---

# Experience Decisioning でのコンテキストデータの活用 {#context}

Experience Decisioning を使用すると、Adobe Experience Platformで提供されている任意の情報を活用して、次のような様々なアクションを実行できます [決定ルール](rules.md) または [ランキング式](ranking.md). 例えば、決定リクエストを行う際に現在の天気を≥80 度にすることを要求する決定ルールをデザインできます。

>[!NOTE]
>
>コンテキストデータはAdobe Experience Platformで定義され、決定リクエストの際に送信されます。 履歴データは含まれません。

コンテキストデータを使用するには、まず Experience Decisioning で使用可能にするデータを定義する必要があります。 完了すると、このデータはで Experience Decisioning にシームレスに統合されます **[!UICONTROL コンテキストデータ]** 決定ルールの作成時に使用可能なタブ。 ランキング式を編集する際に、データを活用することもできます。

![](assets/decision-rules-context.png)

エクスペリエンス決定に Adobe Experience Platform データをフィードする手順は、次のとおりです。

1. Adobe Experience Platform で&#x200B;**エクスペリエンスイベントスキーマ**&#x200B;およびそれに関連する&#x200B;**データセット**&#x200B;を作成します。[スキーマの作成方法については、こちらを参照してください](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/ui/resources/schemas){target="_blank"}

1. 新しい Adobe Experience Platform データストリームを次の手順で作成します。

   1. **[!UICONTROL データストリーム]**&#x200B;メニューに移動し、「**[!UICONTROL 新規データストリーム]**」を選択します。

   1. **[!UICONTROL イベントスキーマ]**&#x200B;ドロップダウンリストで、先ほど作成したエクスペリエンスイベントスキーマを選択し、「**[!UICONTROL 保存]**」をクリックします。

      ![](assets/decision-rule-context-datastream.png)

   1. 「**[!UICONTROL サービスを追加]**」をクリックし、サービスとして「Adobe Experience Platform」を選択します。**[!UICONTROL イベントデータセット]**&#x200B;ドロップダウンリストで、先ほど作成したイベントデータセットを選択し、「**[!UICONTROL Adobe Journey Optimizer]**」オプションを有効にします。

      ![](assets/decision-rules-context-datastream-service.png)

データストリームを保存すると、選択したデータセットの情報が自動的に取得されてエクスペリエンス決定に統合され、通常は約 24 時間以内に使用可能になります。

Adobe Experience Platform の操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

* [エクスペリエンスデータモデル（XDM）スキーマ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition){target="_blank"}
* [データセット](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview){target="_blank"}
* [データストリーム](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/overview){target="_blank"}
