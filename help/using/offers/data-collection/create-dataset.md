---
product: experience platform
solution: Experience Platform
title: イベントを収集するデータセットの作成
description: イベントを収集するデータセットの作成方法を説明します
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 99963ef4-0b19-475e-96f4-2eac3f680c6f
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 71%

---

# イベントを収集するデータセットの作成 {#create-dataset}

エクスペリエンスイベントを収集するには、まずこれらのイベントを送信するデータセットを作成する必要があります。

まず、データセットで使用するスキーマを作成します。

1. 次の **[!UICONTROL データ管理]** メニュー、選択 **[!UICONTROL スキーマ]** そして、 **[!UICONTROL 参照]** タブをクリックします。

1. クリック **[!UICONTROL スキーマを作成]** を選択します。 **[!UICONTROL XDM ExperienceEvent]**.

   ![](../assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >XDM スキーマとフィールドグループについて詳しくは、[XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target="_blank"}を参照してください。

1. 左側の「**[!UICONTROL フィールドグループ]**」セクションで、「**[!UICONTROL 追加]**」を選択します。

   ![](../assets/ai-ranking-fields-groups.png)

1. 内 **[!UICONTROL 検索]** フィールドに、「提案インタラクション」と入力します。

1. を選択します。 **[!UICONTROL エクスペリエンスイベント — 提案インタラクション]** フィールドグループとクリック **[!UICONTROL フィールドグループを追加]**.

   ![](../assets/ai-ranking-add-field-group.png)

   >[!CAUTION]
   >
   >データセットで使用されるスキーマには、「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループが関連付けられている必要があります。そうしないと、ランキング戦略で使用できなくなります。

1. 名前を入力し、スキーマを保存します。

>[!NOTE]
>
>スキーマの構築について詳しくは、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja#understanding-schemas)で説明します{target="_blank"}。

これで、このスキーマを使用してデータセットを作成する準備が整いました。これを行うには、以下の手順に従います。

1. 次の **[!UICONTROL データ管理]** メニュー、選択 **[!UICONTROL データセット]** そして、 **[!UICONTROL 参照]** タブをクリックします。

1. クリック **[!UICONTROL データセットを作成]** を選択し、 **[!UICONTROL スキーマからデータセットを作成]**.

   ![](../assets/ai-ranking-create-dataset-from-schema.png)

1. 作成したスキーマをリストから選択し、「 」をクリックします。 **[!UICONTROL 次へ]**.

1. 「**[!UICONTROL 名前]**」フィールドにデータセットの一意の名前を入力し、「**[!UICONTROL 完了]**」をクリックします。

   ![](../assets/ai-ranking-dataset-name.png)

>[!NOTE]
>
>これで、[ランキング戦略の作成](#create-ranking-strategy)時に、イベントデータを収集するデータセットを選択できる状態になりました。
