---
title: シミュレーションの作成
description: 決定ロジックを検証するために、特定の場所に配信されるオファーをシミュレートする方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: da9e898b-8e5d-43da-9226-5c9ccb78e174
source-git-commit: f50617dc5ea07d01d1f7ec1ab3f9790557dcd957
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 100%

---

# シミュレーションの作成 {#create-simulations}

## シミュレーションについて {#about-simulation}

決定ロジックを検証するために、特定のプレースメントの場合にテストプロファイルに配信されるオファーをシミュレートできます。

<!--Simulation allows you to view the results of offer decisions as a selected profile.-->

これにより、ターゲットの受信者に影響を与えずに、オファーの様々なバージョンをテストして改良できます。

>[!NOTE]
>
>この機能は、[!DNL Decisioning] API への単一のリクエストをシミュレートします。詳しくは、[Decisioning API を使用したオファーの配信](../api-reference/offer-delivery-api/decisioning-api.md)を参照してください。

この機能にアクセスするには、**[!UICONTROL 意思決定管理]**／**[!UICONTROL オファー]**&#x200B;メニューから「**[!UICONTROL シミュレーション]**」タブを選択します。

![](../assets/offers_simulation-tab.png)

>[!NOTE]
>
>シミュレーションでは決定イベントが生成されないので、[キャッピング](../offer-library/creating-personalized-offers.md#capping)カウントに影響はありません。

<!--
➡️ [Discover this feature in video](#video)
-->

## テストプロファイルの選択 {#select-test-profiles}

>[!CONTEXTUALHELP]
>id="ajo_decisioning_simulation_test_profile"
>title="テストプロファイルの追加"
>abstract="ID 名前空間とそれに対応する ID 値を選択することで、テストプロファイルを追加できます。シミュレーションで使用するには、既に使用可能なテストプロファイルが必要です。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/segment/profiles/creating-test-profiles.html?lang=ja" text="テストプロファイルの作成"

まず、シミュレーションに使用するテストプロファイルを選択する必要があります。

>[!CAUTION]
>
>どのオファーが配信されるかをシミュレートするには、使用可能なテストプロファイルがある必要があります。[テストプロファイルを作成](../../segment/creating-test-profiles.md)する方法について説明します。

1. 「**[!UICONTROL プロファイルを管理]**」をクリックします。

   ![](../assets/offers_simulation-manage-profile.png)

1. テストプロファイルの識別に使用する ID 名前空間を選択します。以下の例では、**Email** 名前空間を使用します。

   >[!NOTE]
   >
   >ID 名前空間は、メールアドレスや CRM ID などの識別情報のコンテキストを定義します。Adobe Experience Platform の ID 名前空間について詳しくは、[この節](../../segment/get-started-identity.md){target=&quot;_blank&quot;}を参照してください。

1. ID 値を入力し、「**[!UICONTROL 表示]**」をクリックして、使用可能なプロファイルを一覧表示します。

   ![](../assets/offers_simulation-add-profile.png)

1. 別のプロファイルデータをテストする場合は、他のプロファイルを追加し、選択を保存します。

   ![](../assets/offers_simulation-save-profiles.png)

1. 追加すると、すべてのプロファイルが「**[!UICONTROL テストプロファイル]**」ドロップダウンリストに一覧表示されます。保存したテストプロファイルを切り替えて、選択したプロファイルごとに結果を表示できます。

   ![](../assets/offers_simulation-saved-profiles.png)

   >[!NOTE]
   >
   >選択したプロファイルは、**[!UICONTROL プロファイルの管理]**&#x200B;を使用して削除されるまで、セッションからセッションへの「**[!UICONTROL シミュレーション]**」タブにテストプロファイルとしてリストアップされたままになります。

1. 「**[!UICONTROL プロファイルの詳細]**」リンクをクリックすると、選択したプロファイルデータが表示されます。

<!--Learn more on [selecting test profiles](messages/preview.md#select-test-profiles)-->

## 決定範囲の追加 {#add-decision-scopes}

テストプロファイルでシミュレートするオファー決定を選択します。

1. 「**[!UICONTROL 決定範囲を追加]**」を選択します。

   ![](../assets/offers_simulation-add-decision.png)

1. リストからプレースメントを選択します。

   ![](../assets/offers_simulation-add-decision-scope.png)

1. 使用可能な決定が表示されます。

   * 検索フィールドを使用して、選択を絞り込むことができます。
   * 「**[!UICONTROL オファー決定を開く]**」リンクをクリックして、作成したすべての決定のリストを開きます。詳しくは、[決定の作成](create-offer-activities.md)を参照してください。

   任意の決定を選択し、「**[!UICONTROL 追加]**」をクリックします。

   ![](../assets/offers_simulation-add-decision-scope-add.png)

1. 定義した決定範囲は、メインワークスペースに表示されます。

   リクエストするオファーの数を調整できます。例えば、2 を選択した場合、この決定範囲では最適な 2 つのオファーが表示されます。

   ![](../assets/offers_simulation-request-offer.png)

   >[!NOTE]
   >
   >最大 30 個のオファーをリクエストできます。

1. 上記の手順を繰り返して、決定を必要な数だけ追加します。

   ![](../assets/offers_simulation-add-more-decisions.png)

   >[!NOTE]
   >
   >複数の決定範囲を定義した場合でも、シミュレートされるのは 1 つの API リクエストのみです。

## シミュレーション設定の定義 {#define-simulation-settings}

シミュレーションのデフォルト設定を編集するには、次の手順に従います。

1. 「**[!UICONTROL 設定]**」をクリックします。

   ![](../assets/offers_simulation-settings.png)

1. 「**[!UICONTROL 重複排除]**」セクションで、決定や配置をまたいだ重複オファーを許可するように選択できます。つまり、複数の決定や配置に同じオファーを割り当てることができます。

   ![](../assets/offers_simulation-settings-deduplication.png)

   >[!NOTE]
   >
   >デフォルトでは、重複排除フラグはシミュレーションに対してすべて有効になっています。つまり、決定エンジンで重複が許可されているため、複数の決定や配置にまたがって同じオファーを行うことができます。[!DNL Decisioning] API リクエストのプロパティについて詳しくは、[この節](../api-reference/offer-delivery-api/decisioning-api.md)を参照してください。

1. 「**[!UICONTROL 応答の形式]**」セクションで、コードビューにメタデータを含めるように選択できます。対応するオプションのチェックをオンにし、目的のメタデータを選択します。これらは、「**[!UICONTROL コードを表示]**」を選択すると、リクエストペイロードと応答ペイロードに表示されます。詳しくは、「[シミュレーション結果の表示](#simulation-results) 」セクションを参照してください。

   ![](../assets/offers_simulation-settings-response-format.png)

   >[!NOTE]
   >
   >このオプションをオンにすると、すべての項目がデフォルトで選択されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>現在、シミュレーションデータの場合は、**[!UICONTROL Hub]** API のみを使用できます。

<!--
In the **[!UICONTROL API for simulation]** section, select the API you want to use: **[!UICONTROL Hub]** or **[!UICONTROL Edge]**.
Hub and Edge are two different end points for simulation data.

In the **[!UICONTROL Context data]** section, you can add as many elements as needed.

    >[!NOTE]
    >
    >This section is hidden if you select Edge API in the section above. Hub allows the use of Context data, Edge does not.

Context data allows the user to add contextual data that could affect the simulation score.
For instance, let's say the customer has an offer for a discount on ice cream. In the rules for that offer, it can have logic that would rank it higher when the temperature is above 80 degrees. In simulation, the user could add context data: temperature=65 and that offer would rank lower, of they could add temperature=95 and that would rank higher.
-->

## シミュレーション結果の表示 {#simulation-results}

決定範囲を追加し、テストプロファイルを選択したら、結果を表示できます。

1. 「**[!UICONTROL 結果を表示]**」をクリックします。

   ![](../assets/offers_simulation-view-results.png)

1. 決定ごとに、選択したプロファイルに応じて、利用可能な最適なオファーが表示されます。

   詳細を表示するオファーを選択します。

   ![](../assets/offers_simulation-offer-details.png)

1. 「**[!UICONTROL コードを表示]**」をクリックして、リクエストと応答のペイロードを表示します。[詳細情報](#view-code)

1. リストから別のプロファイルを選択して、別のテストプロファイルに対するオファー決定の結果を表示します。

1. 決定範囲は、必要な回数だけ追加、削除または更新できます。

>[!NOTE]
>
>プロファイルを変更したり決定範囲を更新したりするたびに、「**[!UICONTROL 結果を表示]**」ボタンを使用して結果を更新する必要があります。

## コードを表示 {#view-code}

1. 「**[!UICONTROL コードを表示]**」ボタンを使用して、リクエストと応答のペイロードを表示します。

   ![](../assets/offers_simulation-view-code.png)

   コードビューには、現在のユーザーの開発者情報が表示されます。デフォルトでは、**[!UICONTROL 応答ペイロード]**&#x200B;が表示されます。

   ![](../assets/offers_simulation-request-payload.png)

1. 「**[!UICONTROL 応答ペイロード]**」または「**[!UICONTROL リクエストペイロード]**」をクリックして、2 つのタブ間を移動します。

   ![](../assets/offers_simulation-response-payload.png)

1. [!DNL Journey Optimizer] の外部でリクエストペイロードを使用するには（トラブルシューティングの目的など）、コードビューの上部にある「**[!UICONTROL クリップボードにコピー]**」ボタンを使用してコピーします。

   ![](../assets/offers_simulation-copy-payload.png)

   <!--You cannot copy the response payload. ACTUALLY YES YOU CAN > to confirm with PM/dev? -->

   >[!NOTE]
   >
   >リクエストペイロードまたは応答ペイロードを独自のコードにコピーする場合は、{USER_TOKEN} と {API_KEY} を有効な値に置き換えます。これらの値を取得する方法について詳しくは、[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=ja){target=&quot;_blank&quot;} ドキュメントを参照してください。

