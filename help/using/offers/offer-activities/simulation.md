---
title: シミュレーションの作成
description: シミュレーションの作成方法を説明します
feature: Offers
topic: Integrations
role: User
level: Intermediate
exl-id: da9e898b-8e5d-43da-9226-5c9ccb78e174
source-git-commit: 65bae1eae9fe425ce7f7c6ce43c6dd978d23570f
workflow-type: ht
source-wordcount: '501'
ht-degree: 100%

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
   >シミュレーションでは、すべての重複除外フラグがデフォルトで有効になっています。つまり、決定エンジンでは重複が許可され、複数の決定にわたって同じ提案を行うことができます。[!DNL Decisions] API リクエストのプロパティについて詳しくは、[この節](../api-reference/decisions-api/deliver-offers.md)を参照してください。

## シミュレーション結果の表示

決定範囲を追加し、テストプロファイルを選択したら、結果を表示できます。

1. 「**[!UICONTROL 結果を表示]**」をクリックします。

   ![](../../assets/offers_simulation-view-results.png)

1. 決定ごとに、選択したプロファイルに応じて、利用可能な最適なオファーが表示されます。

   詳細を表示するオファーを選択します。

   ![](../../assets/offers_simulation-offer-details.png)

1. リストから別のプロファイルを選択して、別のテストプロファイルに対するオファー決定の結果を表示します。

1. 決定範囲は、必要な回数だけ追加、削除または更新できます。

>[!NOTE]
>
>プロファイルを変更したり決定範囲を更新したりするたびに、「**[!UICONTROL 結果を表示]**」ボタンを使用して結果を更新する必要があります。

<!--Questions

* Is it recommended to first select profiles or first add decision scopes?
* What does Request offer changes?
* Nothing displays when I click View results? Can't see any score...
* What's the typical example? i.e. how many decisions do you select, and how do you compare scores?
* What do you learn from simulation? i.e. if I selected 2 decisions and I compare the scores, which one is better or should I use for my customers?
* Is there a way to create relevant test profiles?
* Error on Profile details link.
* Is there a tutorial planned to be released?
* Why still a big red frame when no profile is found?

## Tutorial video {#video}

>[!NOTE]
>
>This video applies to the Offer Decisioning application service built on Adobe Experience Platform. However, it provides generic guidance to use Offer in the context of Journey Optimizer.

>[!VIDEO](https://video.tv.adobe.com/v/329606?quality=12)
-->
