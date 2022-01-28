---
title: シミュレーションの作成
description: シミュレーションの作成方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: da9e898b-8e5d-43da-9226-5c9ccb78e174
source-git-commit: 39b52f39ec19c185d2cd95634a60e37f62a66f83
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 94%

---

# シミュレーションの作成

## シミュレーションについて

決定ロジックを検証するために、特定のプレースメントの場合にテストプロファイルに配信されるオファーをシミュレートできます。

<!--Simulation allows you to view the results of offer decisions as a selected profile.-->

これにより、ターゲットの受信者に影響を与えずに、オファーの様々なバージョンをテストして改良できます。

>[!NOTE]
>
>この機能は、[!DNL Decisions] API への単一のリクエストをシミュレートします。詳しくは、[決定 API を使用したオファーの配信](../api-reference/decisions-api/deliver-offers.md)を参照してください。

この機能にアクセスするには、**[!UICONTROL 意思決定管理]**／**[!UICONTROL オファー]**&#x200B;メニューから「**[!UICONTROL シミュレーション]**」タブを選択します。

![](../../assets/offers_simulation-tab.png)

<!--
➡️ [Discover this feature in video](#video)
-->

## テストプロファイルの選択

まず、シミュレーションに使用するテストプロファイルを選択する必要があります。

1. 「**[!UICONTROL プロファイルを管理]**」をクリックします。

   ![](../../assets/offers_simulation-manage-profile.png)

1. テストプロファイルの識別に使用する ID 名前空間を選択します。以下の例では、**Email** 名前空間を使用します。

   >[!NOTE]
   >
   >ID 名前空間は、メールアドレスや CRM ID などの識別情報のコンテキストを定義します。 Adobe Experience Platform の ID 名前空間について詳しくは、[この節](../../get-started-identity.md){target=&quot;_blank&quot;}を参照してください。

1. ID 値を入力し、「**[!UICONTROL 表示]**」をクリックして、使用可能なプロファイルを一覧表示します。

   ![](../../assets/offers_simulation-add-profile.png)

1. 別のプロファイルデータをテストする場合は、他のプロファイルを追加し、選択を保存します。

   ![](../../assets/offers_simulation-save-profiles.png)

1. 追加すると、すべてのプロファイルが「**[!UICONTROL テストプロファイル]**」ドロップダウンリストに一覧表示されます。保存したテストプロファイルを切り替えて、選択したプロファイルごとに結果を表示できます。

   ![](../../assets/offers_simulation-saved-profiles.png)

1. 「**[!UICONTROL プロファイルの詳細]**」リンクをクリックすると、選択したプロファイルデータが表示されます。

<!--Learn more on [selecting test profiles](preview.md#select-test-profiles)-->

## 決定範囲の追加

テストプロファイルでシミュレートするオファー決定を選択します。

1. 「**[!UICONTROL 決定範囲を追加]**」を選択します。

   ![](../../assets/offers_simulation-add-decision.png)

1. リストからプレースメントを選択します。

   ![](../../assets/offers_simulation-add-decision-scope.png)

1. 使用可能な決定が表示されます。

   * 検索フィールドを使用して、選択を絞り込むことができます。
   * 「**[!UICONTROL オファー決定を開く]**」リンクをクリックして、作成したすべての決定のリストを開きます。詳しくは、[決定の作成](create-offer-activities.md)を参照してください。

   任意の決定を選択し、「**[!UICONTROL 追加]**」をクリックします。

   ![](../../assets/offers_simulation-add-decision-scope-add.png)

1. 定義した決定範囲は、メインワークスペースに表示されます。

   リクエストするオファーの数を調整できます。 例えば、2 を選択した場合、この決定範囲では最適な 2 つのオファーが表示されます。

   ![](../../assets/offers_simulation-request-offer.png)

   >[!NOTE]
   >
   >最大 30 個のオファーをリクエストできます。

1. 上記の手順を繰り返して、決定を必要な数だけ追加します。

   ![](../../assets/offers_simulation-add-more-decisions.png)

   >[!NOTE]
   >
   >複数の決定範囲を定義した場合でも、シミュレートされるのは 1 つの API リクエストのみです。
   >
   >デフォルトでは、すべての重複排除フラグがシミュレーションに対して有効になっています。つまり、決定エンジンは重複を許可し、複数の決定/配置間で同じ提案をおこなうことができます。 [!DNL Decisions] API リクエストのプロパティについて詳しくは、[この節](../api-reference/decisions-api/deliver-offers.md)を参照してください。<!--Deduplication note TO REMOVE WHEN SIMULATIONS V2 is on PROD-->

<!--SIMULATIONS V2

## Define simulation settings {#define-simulation-settings}

To edit the default settings for your simulations, follow the steps below.

1. Click **[!UICONTROL Settings]**.

    ![](../../assets/offers_simulation-settings.png)

1. In the **[!UICONTROL Deduplication]** section, you can choose to allow duplicate offers accross decisions and/or placements. It means that multiple decisions/placements may get assigned the same offer.

    ![](../../assets/offers_simulation-settings-deduplication.png)

    >[!NOTE]
    >
    >By default, all Deduplication flags are enabled for simulation, which means that the decision engine allows duplicates and thus can make the same proposition accross multiple decisions/placements. Learn more on the [!DNL Decisions] API request properties in [this section](../api-reference/decisions-api/deliver-offers.md).

1. In the **[!UICONTROL Response format]** section, you can choose to include metadata in the code view. Check the corresponding option, and select the metadata of your choice. They will be displayed in the request and response payloads when selecting **[!UICONTROL View code]**. Learn more in the [View simulation results](#simulation-results) section.

    ![](../../assets/offers_simulation-settings-response-format.png)

    >[!NOTE]
    >
    >When turning on the option, all items are selected by default.

1. Click **[!UICONTROL Save]**.-->

<!--NOT FOR SIMULATIONS V2

In the **[!UICONTROL API for simulation]** section, select the API you want to use: **[!UICONTROL Hub]** or **[!UICONTROL Edge]**.
Hub and Edge are two different end points for simulation data.

In the **[!UICONTROL Context data]** section, you can add as many elements as needed.

    >[!NOTE]
    >
    >This section is hidden if you select Edge API in the section above. Hub allows the use of Context Data, Edge does not.

Context data allows the user to add contextual data that could affect the simulation score.
For instance, let's say the customer has an offer for a discount on ice cream. In the rules for that offer, it can have logic that would rank it higher when the temperature is above 80 degrees. In simulation, the user could add context data: temperature=65 and that offer would rank lower, of they could add temperature=95 and that would rank higher.
-->

## シミュレーション結果の表示 {#simulation-results}

決定範囲を追加し、テストプロファイルを選択したら、結果を表示できます。

1. 「**[!UICONTROL 結果を表示]**」をクリックします。

   ![](../../assets/offers_simulation-view-results.png)

1. 決定ごとに、選択したプロファイルに応じて、利用可能な最適なオファーが表示されます。

   詳細を表示するオファーを選択します。

   ![](../../assets/offers_simulation-offer-details.png)

   <!--
    SIMULATIONS V2
    1. Click **[!UICONTROL View code]** to display the request and response payloads. [Learn more](#view-code)-->

1. リストから別のプロファイルを選択して、別のテストプロファイルに対するオファー決定の結果を表示します。

1. 決定範囲は、必要な回数だけ追加、削除または更新できます。

>[!NOTE]
>
>プロファイルを変更したり決定範囲を更新したりするたびに、「**[!UICONTROL 結果を表示]**」ボタンを使用して結果を更新する必要があります。

<!--
SIMULATIONS V2

## View code {#view-code}

To use the request payload outside of [!DNL Journey Optimizer] - for troubleshooting purpose for example, you can copy it by clicking the corresponding button on top of the code view.
    
>[!NOTE]
>
>You cannot copy the response payload.

Below is an example of code view:

    ```
    curl -X POST \
    'https://platform.adobe.io/data/core/ode/{CONTAINER_ID}/decisions' \
    -H 'Accept: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-response;version=1.0"' \
    -H 'Content-Type: application/vnd.adobe.xdm+json; schema="https://ns.adobe.com/experience/offer-management/decision-request;version=1.0"' \
    -H 'Authorization: Bearer eyJhbGciOiJSUzI1NiIsIng1dSI6Imltc19uYTEtc3RnMS1rZXktMS5jZXIifQ.eyJpZCI6IjE2NDMxMzg3NDMxODlfOTIzY2ZjZjgtOWVkYy00MjE1LWJjODgtYmEyYTY2ZGIyYmMyX3VlMSIsInR5cGUiOiJhY2Nlc3NfdG9rZW4iLCJjbGllbnRfaWQiOiJhY3BfdWlfcGxhdGZvcm0iLCJ1c2VyX2lkIjoiNDhENTc0N0E2MDc3NkRERTBBNDk0MDFEQEFkb2JlSUQiLCJzdGF0ZSI6IntcInNlc3Npb25cIjpcImh0dHBzOi8vaW1zLW5hMS1zdGcxLmFkb2JlbG9naW4uY29tL2ltcy9zZXNzaW9uL3YxL1l6azNNakE0TXpNdFpXVTVaUzAwTVdOaExUZ3pNamd0TmpFM1pqZ3lOak5qTmpSakxTMDBPRVExTnpRM1FUWXdOemMyUkVSRk1FRTBPVFF3TVVSQVFXUnZZbVZKUkFcIn0iLCJhcyI6Imltcy1uYTEtc3RnMSIsImFhX2lkIjoiNDhENTc0N0E2MDc3NkRERTBBNDk0MDFEQEFkb2JlSUQiLCJjdHAiOjAsImZnIjoiV0VQQTNUSUY0UjRaQTZEWlBDUk1BMklBQ1U9PT09PT0iLCJzaWQiOiIxNjQzMDYwMDg0NzI2XzYzNGJkNDEzLWMwYTktNDA0NS1iNTM3LWRmMzgzYzU5ZGIxY191ZTEiLCJydGlkIjoiMTY0MzEzODc0MzE4OV9lYWMxOWY5Yi00ZjhhLTQ1NWMtOWVmMi1mNjYwNmQ0ODY4N2ZfdWUxIiwibW9pIjoiYmVjOTQzYzIiLCJwYmEiOiIiLCJvYyI6InJlbmdhKm5hMXItc3RnMSoxN2U5MmIzNzYzNCo2MEJEVjBGUlhOMFlRMkdHSkRON0E5Tk1HOCIsInJ0ZWEiOiIxNjQ0MzQ4MzQzMTg5IiwiZXhwaXJlc19pbiI6Ijg2NDAwMDAwIiwic2NvcGUiOiJvcGVuaWQsc2Vzc2lvbixyZWFkX29yZ2FuaXphdGlvbnMsYWRkaXRpb25hbF9pbmZvLnByb2plY3RlZFByb2R1Y3RDb250ZXh0LGFkZGl0aW9uYWxfaW5mby5yb2xlcyxhdWRpZW5jZW1hbmFnZXJfYXBpLEFkb2JlSUQiLCJjcmVhdGVkX2F0IjoiMTY0MzEzODc0MzE4OSJ9.TgZ998KHA4Zeoyq7b_NbPv8aPHb2cs9GgP3uJKrTbzosylKKRYqLpj_8HkloI-bFVQFCBCOWbCwtJtkcRIvFlQFruTr5bpMatPV8izEUVutO6smkYBFoGFYyEGuN5Xe97uOJZEHzFSWguGZtgttSrNhXr-j0hFloofjXDJXPB_911dzXALp5s15sd3HLH9XWTwwlqF_a5SMNDXaSj1800RxsB9bJ8_YL0x4pqQwjYJxRGMhiy7Y9IOpwogSBEiqCQitlKYgaO7yaJzFwhfyisnqM7_MWX2ETn-kGFEOoBHxXDTx9P2OPojzb8ChWQgmGf7Expyvtc1ke3nJkppzrxg' \
    -H 'x-api-key: {API_KEY}' \
    -H 'x-gw-ims-org-id: 5D1328435BF324E90A49402A@AdobeOrg' \
    -H 'x-sandbox-name: prod' \
    -D '{
      "xdm:propositionRequests": [
            {
                  "xdm:placementId": "xcore:offer-placement:1416f4109d9d292c",
                  "xdm:activityId": "xcore:offer-activity:1416f4aad9fd99d7",
                  "xdm:itemCount": 2
            }
      ],
      "xdm:profiles": [
            {
                  "xdm:identityMap": {
                        "email": [
                              {
                                    "xdm:id": "poyfair@adobe.com"
                              }
                        ]
                  }
            }
      ],
      "xdm:allowDuplicatePropositions": {
            "xdm:acrossActivities": true,
            "xdm:acrossPlacements": true
      },
      "xdm:responseFormat": {
            "xdm:includeMetadata": {
                  "xdm:activity": [],
                  "xdm:option": [],
                  "xdm:placement": []
            }
      }
    }'
    ```

>[!NOTE]
>
>When copying the request payload into your own code, make sure you replace CONTAINER_ID and API_KEY with your own values.-->

