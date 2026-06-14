---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアップキャンペーンの作成
description: IP ウォームアップキャンペーンの作成方法を学ぶ
feature: Campaigns, IP Warmup Plans
topic: Administration
role: Admin
level: Intermediate
keywords: IP, プール, 配信品質
exl-id: a9995ca1-d7eb-4f8d-a9d9-fe56198ac325
TQID: https://experienceleague.adobe.com/mzP9buvUwW2h0QahDBXWxefokjZv-XziM-uFaPwg3Wg
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: c343082f-e963-4f57-a96b-b64d27f8118e
  - id: e23d48b5-7858-4d45-9c56-9e2b4be8500e
  - id: e30b0a1a-b594-47b8-af94-1e3a2be6df11
  - id: fae48155-b23f-40d2-a252-a25bce350b4d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 0d9c480cc48c4352e82d1f4624c65fc16a60b959
workflow-type: tm+mt
source-wordcount: 486
ht-degree: 94%

---

# IP ウォームアップキャンペーンの作成 {#create-ip-warmup-campaign}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、IP ウォームアップ専用の電子メールキャンペーンを作成およびアクティブ化して、IP ウォームアッププラン内でスケジュールして使用できるようにする方法を説明します。

>[!ENDSHADEBOX]

>[!CONTEXTUALHELP]
>id="ajo_campaign_ip_warmup"
>title="IP ウォームアッププランオプションを有効にする"
>abstract="このオプションを選択すると、キャンペーンを IP ウォームアッププランで使用できます。 その後、キャンペーンスケジュールは、関連付けられている IP ウォームアッププランによって実行されます。"

[!DNL Journey Optimizer] で IP ウォームアッププラン自体を作成する前に、まず IP ウォームアッププランで使用するために特別に設計された 1 つ以上のキャンペーンを作成する必要があります<!--through a dedicated option-->。

IP ウォームアップキャンペーンを作成するには、次の手順に従います。

1. ウォームアッププランで特定したドメインおよび IP のメールチャネル[設定](channel-surfaces.md)を作成します。

   配信品質コンサルタントと協力して、使用するドメインと IP を特定します。 [この節](../email/email-settings.md#ip-pools)では、メール設定でこれらを選択する方法について説明します。

   >[!CAUTION]
   >
   >IP ウォームアッププランの[開始](ip-warmup-execution.md)後は、メールチャネル設定を編集しないでください。

1. スケジュールされたマーケティング[キャンペーン](../campaigns/create-campaign.md)を作成し、[メール](../email/create-email.md#create-email)アクションを選択します。

   <!--Select the Marketing category. The IP warmup plan activation option is only available for  marketing-type campaigns.-->

1. IP ウォームアップ用に作成した設定を選択します。

   ![](assets/ip-warmup-campaign-surface.png)

   <!--You must use the same configuration as the one that will be used for the asociated IP warmup plan. [Learn how to create an IP warmup plan](#create-ip-warmup-plan)-->

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 「**[!UICONTROL スケジュール]**」セクションから、「**[!UICONTROL IP ウォームアッププランのアクティブ化]**」を選択します。

   ![](assets/ip-warmup-campaign-plan-activation.png)

   キャンペーン[スケジュール](../campaigns/campaign-schedule.md)が、関連付けられる IP ウォームアッププランによって実行されます。つまり、スケジュールはキャンペーン自体で定義されなくなります。

1. キャンペーンプロパティ、[オーディエンス](../audience/about-audiences.md)<!--best practices for IP warmup in terms of audience?-->、[コンテンツ](../email/get-started-email-design.md#key-steps)など、メールキャンペーンを作成する手順を完了します。

   >[!IMPORTANT]
   >
   >IP ウォームアップキャンペーンで許可されるオーディエンスは、[セグメントベース](../audience/creating-a-segment-definition.md)であり、[デフォルトの結合ポリシー](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/merge-policies/overview#default-merge-policy){target="_blank"}を使用して作成する必要があります。
   >
   >CSV アップロードオーディエンスは IP ウォームアップキャンペーンではサポートされていないので、キャンペーンのアクティブ化時にエラーが発生します。

   キャンペーンの設定方法について詳しくは、[このページ](../campaigns/get-started-with-campaigns.md)を参照してください。

1. キャンペーンを[アクティブ化](../campaigns/review-activate-campaign.md)します。 ステータスは、「**[!UICONTROL ライブ]**」に変わります。

   >[!NOTE]
   >
   >IP ウォームアッププランでは[ビジネスルール](../conflict-prioritization/rule-sets.md#rule-sets)を使用しないでください。 これらのルールを適用すると、キャンペーンのターゲットプロファイルの希望数に到達できなくなる可能性があります。

   IP ウォームアッププランが有効化されたライブキャンペーンの場合、**[!UICONTROL 削除]**&#x200B;ボタンは、IP ウォームアッププランに関連付けられるまで使用できます。 プランで使用すると、キャンペーンは削除できなくなります。

1. キャンペーンが&#x200B;**[!UICONTROL キャンペーン]**&#x200B;リストに表示されます。 現在のサンドボックスで作成されたすべての IP ウォームアップキャンペーンを簡単に取得するには、**[!UICONTROL IP ウォームアップ]**&#x200B;キャンペーンオプションでフィルタリングできます。

   ![](assets/ip-warmup-campaign-filter.png)

ライブになると、キャンペーンは IP ウォームアッププランで使用できる状態になります。 [詳細情報](ip-warmup-plan.md)

IP ウォームアップキャンペーンは、1 つの IP ウォームアッププランでのみ使用できます。 ただし、同じ IP ウォームアッププランの 1 つ以上のフェーズで同じキャンペーンを使用できます。 [詳細情報](ip-warmup-plan.md#ip-warmup-plan-tab)

>[!NOTE]
>
>ライブキャンペーンが IP ウォームアッププランで使用されている場合、プランが[完了済みとしてマーク](ip-warmup-execution.md#mark-as-completed)されると、そのキャンペーンの[ステータス](../campaigns/manage-campaigns.md#statuses)は「**[!UICONTROL 停止済み]**」に変わります。

