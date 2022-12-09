---
solution: Journey Optimizer
product: journey optimizer
title: 待機アクティビティー
description: 待機アクティビティーについて
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: 7268489a-38c1-44da-b043-f57aaa12d7d5
source-git-commit: 021cf48ab4b5ea8975135a20d5cef8846faa5991
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# 待機アクティビティー{#wait-activity}

>[!CONTEXTUALHELP]
>id="ajo_journey_wait"
>title="待機アクティビティー"
>abstract="パス内の次のアクティビティーが実行される前に待機する場合は、待機アクティビティーを使用できます。 これを使用すると、次のアクティビティが実行される瞬間を定義できます。 「期間」と「カスタム」の2つのオプションを選択できます。"

パス内の次のアクティビティーが実行される前に待機する場合は、アクティビティーを使用 **[!UICONTROL Wait]** できます。 これを使用すると、次のアクティビティが実行される瞬間を定義できます。 次の3つのオプションを選択できます。

* [持続](#duration)
* [](#custom)

<!--
* [Email send time optimization](#email_send_time_optimization)
* [Fixed date](#fixed_date) 
-->

## 待機アクティビティーについて{#about_wait}

最大待機時間は30日です。 テストモードでは、 **[!UICONTROL Wait time in test]** このパラメーターを使用して、各待機アクティビティーが終了する時刻を定義することができます。 初期設定では、10秒に設定されています。 これにより、テスト結果がすばやく取得されるようになります。 このページを参照してください [ 。](../building-journeys/testing-the-journey.md)

グローバルな旅タイムアウトは30日なので、一度に複数の待機処理を使用する場合は注意してください。つまり、プロファイルは、それを入力してから30日後に必ずしも外出中に出てきます。

## デュレーション待ち{#duration}

次のアクティビティが実行されるまでの待機時間を選択します。

![](assets/journey55.png)

<!--
## Fixed date wait{#fixed_date}

Select the date for the execution of the next activity.

![](assets/journey56.png)

-->

## カスタム待機{#custom}

このオプションを使用すると、イベントまたはデータソースから取得されたフィールドを基にした高度な式を使用して、5pm に12月 12 2020 月など、カスタム日付を定義することができます。 カスタムデュレーションを定義することはできません。例えば、7日を指定することもできます。 式エディター内の式には、dateTimeOnly 形式を指定する必要があります。 この [ ページ ](expression/expressionadvanced.md) を参照してください。 DateTimeOnly 形式について詳しくは、この [ ページ ](expression/data-types.md) を参照してください。

>[!NOTE]
>
>DateTimeOnly 式を活用したり、関数を使用して dateTimeOnly に変換したりすることができます。 例えば、次のようにします。 toDateTimeOnly (@ {offerOpened)、イベントのフィールドは 2016-08-12T09 :46: 06z になります。
>
>**このタイムゾーン** は、フライトのプロパティに含まれている必要があります。その結果、今日のインターフェイスでは、完全な ISO-8601 タイムスタンプの混合時刻と 2016-08 (12T09 :46: ) のようなタイムゾーンのオフセットを直接ポイントすることはできません。 このページ ](../building-journeys/timezone-management.md) を参照してください [ 。

![](assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

This type of wait uses a score calculated in Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

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
