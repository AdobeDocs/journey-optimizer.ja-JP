---
solution: Journey Optimizer
product: journey optimizer
title: 待機アクティビティ
description: 待機アクティビティについて説明します
feature: Journeys, Activities
topic: Content Management
role: User
level: Intermediate
keywords: 待機, アクティビティ, ジャーニー, 次, キャンバス
exl-id: 7268489a-38c1-44da-b043-f57aaa12d7d5
source-git-commit: 4e7c4e7e6fcf488f572ccf3e9037e597dde06510
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 100%

---

# 待機アクティビティ{#wait-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_wait"
>title="待機アクティビティ"
>abstract="パス内の次のアクティビティを実行するまで待機する場合は、「待機」アクティビティを使用できます。後に続くアクティビティを実行するタイミングを定義できます。期間とカスタムの 2 つのオプションを使用できます。"

パス内の次のアクティビティを実行するまで待機する場合は、「**[!UICONTROL 待機]**」アクティビティを使用できます。後に続くアクティビティを実行するタイミングを定義できます。次のオプションがあります。

* [期間](#duration)
* [カスタム](#custom)

<!--
* [Email send time optimization](#email_send_time_optimization)
* [Fixed date](#fixed_date) 
-->

## 待機アクティビティについて{#about_wait}

待機期間は最長 29 日です。テストモードでは、「**[!UICONTROL テストの待機時間]**」パラメーターを使用すると、各待機アクティビティの持続時間を定義できます。デフォルト時間は 10 秒です。これにより、テスト結果を迅速に取得できます。[このページ](../building-journeys/testing-the-journey.md)を参照してください。

グローバルジャーニーのタイムアウトが 30 日なので（つまり、プロファイルはジャーニーにエントリしてから最大 30 日後に常にジャーニーからドロップアウトするので）、1 つのジャーニーで複数の待機アクティビティを使用する場合は注意が必要です。詳しくは、[このページ](../building-journeys/journey-gs.md#global_timeout)を参照してください。

個人が待機アクティビティにエントリできるのは、30 日のジャーニータイムアウトより前に待機期間を完了するのに十分な時間がジャーニーに残っている場合のみです。例えば、それぞれ 20 日に設定された 2 つの待機アクティビティを追加すると、2 番目の待機が 30 日のタイムアウト後に終了することをシステムが検出します。したがって、2 番目の待機は無視され、その待機を開始する前に個人はジャーニーを離脱します。この例では、顧客はジャーニーに合計 20 日間滞在します。

ベストプラクティスとして、待機を使用して再エントリをブロックすることは避けます。代わりに、ジャーニープロパティレベルで「**再エントリを許可**」オプションを使用します。詳しくは、[このページ](../building-journeys/journey-gs.md#entrance)を参照してください。

## 期間待機{#duration}

次のアクティビティを実行するまでの待機期間を選択します。最大期間は 29 日です。

![](assets/journey55.png)

<!--
## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![](assets/journey56.png)

-->

## カスタム待機{#custom}

このオプションでは、イベントやデータソースのフィールドに基づく高度な式を使用して、カスタムの日付（例：2023 年 7 月 12 日午後 5 時）を定義できます。カスタムの期間（例えば 7 日など）を定義することはできません。式エディターでは、式を dateTimeOnly 形式にする必要があります。この[ページ](expression/expressionadvanced.md)を参照してください。dateTimeOnly 形式の詳細については、[このページ](expression/data-types.md)を参照してください。

>[!NOTE]
>
>dateTimeOnly 式を利用するか、関数を使用して dateTimeOnly に変換することができます。例えば、toDateTimeOnly(@event{Event.offerOpened.activity.endTime}) では、イベント内のフィールドが 2023-08-12T09:46:06Z の形式になります。
>
>ジャーニーのプロパティには&#x200B;**タイムゾーン**&#x200B;が必要です。そのため、今のところ、時刻とタイムゾーンのオフセットを組み合わせた、完全な ISO-8601 タイムスタンプ（2023-08-12T09:46:06.982-05 など）をインターフェイスから直接指定することはできません。[このページ](../building-journeys/timezone-management.md)を参照してください。

![](assets/journey57.png)

待機アクティビティが期待どおりに動作することを検証するには、ステップイベントを使用できます。[このページ](../reports/query-examples.md#common-queries)を参照してください。

<!--## Email send time optimization{#email_send_time_optimization}

This type of wait uses a score calculated in Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](assets/journey57bis.png)-->
