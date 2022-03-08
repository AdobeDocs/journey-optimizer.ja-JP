---
product: experience platform
solution: Experience Platform
title: ランキング戦略の作成
description: AI モデルを作成してオファーをランク付けする方法を説明します
feature: Ranking Formulas
role: User
level: Intermediate
exl-id: 81d07ec8-e808-4bc6-97b1-b9f7db2aec22
source-git-commit: dcadbbcf8b2cd8422a189b8d02f222f32dd12c54
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 97%

---

# AI モデルの作成 {#ai-rankings}

## ランキング戦略の作成 {#create-ranking-strategy}

ランキング戦略を作成するには、次の手順に従います。

1. **[!UICONTROL コンポーネント]**&#x200B;メニューにアクセスし、「**[!UICONTROL AI ランキング]**」タブを選択します。

   ![](../../assets/ai-ranking-list.png)

   これまでに作成したランキング戦略がすべてリストされます。

1. 「**[!UICONTROL 戦略を作成]**」ボタンをクリックします。

1. 次のフィールドに入力します。

   ![](../../assets/ai-ranking-fields.png)

   * **[!UICONTROL 名前]**：指定する必要がある一意の名前。

   * **[!UICONTROL モデルタイプ]**:現在 [!DNL Journey Optimizer] サポートされているモデルのタイプは次のみです。 **[!UICONTROL 自動最適化]**. [詳細情報](ai-ranking.md#auto-optimization)

   * **[!UICONTROL 最適化指標]**：

      このオプションにより、マーケターは、表示されたオファー、電子メールでクリックされたオファー、web でクリックされたオファーに基づいて、機械学習モデルを構築およびトレーニングする方法を選択できます。

      >[!NOTE]
      >
      >必要に応じて、すべての指標タイプを選択できます。

      最適化指標には次の 2 種類があります。
      * **[!UICONTROL インプレッション]**：現在のインプレッションイベントは、表示されるすべてのオファーに対応しています。
      * **[!UICONTROL コンバージョン]**：コンバージョンイベントは、電子メールまたは web でのクリックにつながるすべてのオファーに対応します。

      選択したすべてのインプレッションイベントやコンバージョンイベントは、提供された web SDK またはモバイル SDK を使用して自動的に取得されます。 詳しくは、[Adobe Experience Platform web SDK の概要](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ja)を参照してください。

   * **[!UICONTROL データセット ID]**：コンバージョンの場合は、ドロップダウンリストからイベントを選択して収集するデータセットを指定する必要があります。そのようなデータセットを作成する方法については、[こちらの節](#create-dataset)を参照してください。 <!--This dataset needs to be associated with a schema that must have the **[!UICONTROL Proposition Interactions]** field group (previously known as mixin) associated with it.-->

   ![](../../assets/ai-ranking-dataset-id.png)

   >[!CAUTION]
   >
   >「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループ（以前の mixin）に関連付けられたスキーマから作成されたデータセットのみがドロップダウンリストに表示されます。

1. ランキング戦略を保存して有効化します。

   ![](../../assets/ai-ranking-save-activate.png)

これで、プレースメントに対して実施要件を満たすオファーをランク付けする決定で使用する準備が整いました。詳しくは、[この節](../offer-activities/configure-offer-selection.md#use-ranking-strategy)を参照してください。<!--TBC?-->

## イベントを収集するデータセットの作成 {#create-dataset}

コンバージョンイベントを収集するデータセットを作成する必要があります。 まず、データセットで使用するスキーマを作成します。

1. **[!UICONTROL データ管理]**&#x200B;メニューから「**[!UICONTROL スキーマ]**」を選択し、「**[!UICONTROL 参照]**」タブに移動して、「**[!UICONTROL スキーマを作成]**」をクリックします。

   ![](../../assets/ai-ranking-create-schema.png)

1. **[!UICONTROL XDM ExperienceEvent]** を選択します。

   ![](../../assets/ai-ranking-xdm-event.png)

   >[!NOTE]
   >
   >    XDM スキーマとフィールドグループについて詳しくは、[XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を参照してください。


1. 「**[!UICONTROL 検索]**」フィールドに「提案インタラクション」と入力し、「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループを選択します。

   ![](../../assets/ai-ranking-proposition-interactions.png)

   >[!CAUTION]
   >
   >    データセットで使用されるスキーマには、「**[!UICONTROL エクスペリエンスイベント - 提案インタラクション]**」フィールドグループが関連付けられている必要があります。そうしないと、ランキング戦略で使用できなくなります。

1. 「**[!UICONTROL フィールドグループを追加]**」をクリックします。

   ![](../../assets/ai-ranking-add-field-group.png)

   >[!NOTE]
   >フィールドグループは、以前は mixin と呼ばれていました。

1. 名前を入力し、スキーマを保存します。<!--How do you edit the fields in this new schema? Examples?-->

>[!NOTE]
>
>    スキーマの構築に関して詳しくは、[スキーマ構成の基本](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ja?lang=ja#understanding-schemas)で説明します。

これで、このスキーマを使用してデータセットを作成する準備が整いました。これを行うには、以下の手順に従います。

1. **[!UICONTROL データ管理]**&#x200B;メニューから「**[!UICONTROL データセット]**」を選択し、「**[!UICONTROL 参照]**」タブに移動して、「**[!UICONTROL データセットを作成]**」をクリックします。

   ![](../../assets/ai-ranking-create-dataset.png)

1. 「**[!UICONTROL スキーマからデータセットを作成]**」をクリックします。

   ![](../../assets/ai-ranking-create-dataset-from-schema.png)

1. 作成したスキーマをリストから選択します。

   ![](../../assets/ai-ranking-dataset-select-schema.png)

1. 「**[!UICONTROL 次へ]**」をクリックします。

1. 「**[!UICONTROL 名前]**」フィールドにデータセットの一意の名前を入力し、「**[!UICONTROL 完了]**」をクリックします。

   ![](../../assets/ai-ranking-dataset-name.png)

これで、[ランキング戦略の作成](#create-ranking-strategy)時に、イベントデータを収集するデータセットを選択できる状態になりました。

## スキーマ要件のオファー {#schema-requirements}

この時点で、次の条件を満たす必要があります。

* ランキング戦略が作成済みであり、
* キャプチャするイベントのタイプ（表示されたオファー（インプレッション）やクリックされたオファー（コンバージョン））、
* およびイベントデータを収集するデータセットが定義済みであること。

これで、オファーが表示およびクリックされるたびに、対応するイベントが、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/web-sdk-faq.html?lang=ja#what-is-adobe-experience-platform-web-sdk%3F){target=&quot;_blank&quot;} または Mobile SDK を使用し、**[!UICONTROL Experience Event - Proposition Interactions]** フィールドグループによって自動的にキャプチャされるようにします。

イベントタイプ（表示されたオファーまたはクリックされたオファー）で送信できるようにするには、Adobe Experience Platform に送信されるエクスペリエンスイベントで、各イベントタイプに正しい値を設定する必要があります。JavaScript コードに実装する必要があるスキーマ要件は、以下のとおりです。

### 表示されるオファーのシナリオ

**イベントタイプ：** `decisioning.propositionDisplay`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取得
+++**サンプルペイロード：**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionDisplay",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4",
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5",
                }
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id - taken from experience event for “nextBestOffer”
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id - taken from experience event for “nextBestOffer”
        }
    ]
}
```

+++

### オファークリック済みシナリオ

**イベントタイプ：** `decisioning.propositionInteract`
**ソース：** Web.sdk/Alloy.js（`sendEvent command -> xdm : {eventType, interactionMixin}`）またはバッチ取得
+++**サンプルペイロード：**

```
{
    "@id": "a7864a96-1eac-4934-ab44-54ad037b4f2b",
    "xdm:timestamp": "2020-09-26T15:52:25+00:00",
    "xdm:eventType": "decisioning.propositionInteract",
    "https://ns.adobe.com/experience/decisioning/propositions":
    [
        {
            "xdm:items":
            [
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee4"
                },
                {
                    "xdm:id": "personalized-offer:f67bab756ed6ee5"
                },
            ],
            "xdm:id": "3cc33a7e-13ca-4b19-b25d-c816eff9a70a", //decision event id
            "xdm:scope": "scope:12cfc3fa94281acb", //decision scope id
        }
    ]
}
```

+++

<!--
## Using a ranking strategy {#using-ranking}

To use the ranking strategy you created above, follow the steps below:

Once a ranking strategy has been created, you can assign it to a placement in a decision. For more on this, see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md).

1. Create a decision.
1. Add a placement.
1. Add a collection.
1. Choose to rank offers by AI ranking (select it from the drop-down list).
1. Click Add ranking.
1. Select the ranking strategy that you created. All the details of the ranking strategy are displayed.
1. Click Next to confirm.
1. Save your decision.

It is now ready to be used in a decision to rank eligible offers for a placement (see [Configure offers selection in decisions](../offer-activities/configure-offer-selection.md)).
-->

