---
solution: Journey Optimizer
product: Journey Optimizer
title: イベントを収集するデータセットの作成
description: イベントを収集するデータセットの作成方法を説明します
feature: Ranking, Datasets, Decisioning
role: Developer
level: Experienced
hide: true
exl-id: 96c1326f-be40-4738-8997-a67dc14872bb
version: Journey Orchestration
TQID: https://experienceleague.adobe.com/U-4AWTYWPOzBhtT3gxE6ORtMI8jNKOZGns-0P3t7-lE
product_v2: id: cb954087-f4fc-4456-afb9-e939cabcdc79
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
feature_v2: id: a4cb03e1-327e-499d-9de8-e0c0db8a63a2
subfeature_v2: id: a7a194a0-75e2-4913-8a83-14714fbf68e6id: eb547372-2a95-4d13-b0fd-f720c9895880
source-git-commit: ee6e1c0a2d86736e51257315fa41c4796286579f
workflow-type: tm+mt
source-wordcount: 270
ht-degree: 100%

---

# イベントを収集するデータセットの作成 {#create-dataset}

エクスペリエンスイベントを収集するには、まずこれらのイベントを送信するデータセットを作成する必要があります。

まず、データセットで使用するスキーマを作成します。

1. **[!UICONTROL データ管理]**&#x200B;メニューで「**[!UICONTROL スキーマ]**」を選択します。

1. 右上の「**[!UICONTROL スキーマを作成]**」をクリックして、「**[!UICONTROL エクスペリエンスイベント]**」を選択し、「**次へ**」をクリックします。

   ![](../../offers/assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >XDM スキーマとフィールドグループについて詳しくは、[XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

1. スキーマの名前と説明を入力して、「**終了**」をクリックします。
   ![](../../offers/assets/ai-ranking-xdm-event-2.png)

1. 左側の「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL 追加]**」を選択します。

   ![](../../offers/assets/ai-ranking-fields-groups.png)

1. 「**[!UICONTROL 検索]**」フィールドに「提案インタラクション」と入力します。

1. 「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループを選択し、「**[!UICONTROL フィールドグループの追加]**」をクリックします。

   ![](../../offers/assets/ai-ranking-add-field-group.png)

   >[!CAUTION]
   >
   >データセットで使用されるスキーマには、「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループが関連付けられている必要があります。 そうしないと、AI モデルで使用できなくなります。

1. スキーマを保存します。

>[!NOTE]
>
>スキーマの作成について詳しくは、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja#understanding-schemas){target="_blank"}を参照してください。

これで、このスキーマを使用してデータセットを作成する準備が整いました。 これを行うには、以下の手順に従います。

1. **[!UICONTROL データ管理]**&#x200B;メニューで「**[!UICONTROL データセット]**」を選択し、「**[!UICONTROL 参照]**」タブに移動します。

1. 「**[!UICONTROL データセットを作成]**」をクリックし、「**[!UICONTROL スキーマからデータセットを作成]**」を選択します。

   ![](../../offers/assets/ai-ranking-create-dataset-from-schema.png)

1. 作成したスキーマをリストから選択し、「**[!UICONTROL 次へ]**」をクリックします。

1. 「**[!UICONTROL 名前]**」フィールドにデータセットの一意の名前を入力し、「**[!UICONTROL 終了]**」をクリックします。

   ![](../../offers/assets/ai-ranking-dataset-name.png)

>[!NOTE]
>
>このデータセットは、[AI モデル](../ranking/create-ai-models.md)の作成時にイベントデータを収集するのに選択できるようになりました。
