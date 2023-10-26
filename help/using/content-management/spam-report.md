---
title: スパムレポートを使用
description: スパムレポートの使用方法を説明します。
feature: Preview
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: b6872806b3961bb2afbfc03999d984384492cc6d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 2%

---

# スパムレポートを使用 {#spam-report}

>[!AVAILABILITY]
>
>スパムレポート機能は、現在、一部のユーザーのみを対象としたベータ版として利用できます。 ベータ版プログラムに参加するには、アドビカスタマーケアにお問い合わせください。

[!DNL Journey Optimizer] では、コンテンツがスパムフィルタリングに対してどのように実行されるかを確認し、メッセージがスパムではなく、顧客の受信ボックスに入っていることを確認できます。

>[!CAUTION]
>
>* この機能は、現在、E メールチャネルでのみ使用できます。
>
>* 現時点では、スパムレポート分析は英語のコンテンツに対してのみ実行できます。

コンテンツを編集またはプレビューする際に、 **[!UICONTROL スパムレポート]** 「 」オプションでは、リストされる個々の項目のスコアを改善するためのスコア付けとアドバイスを提供します。

これにより、受信時に使用されるスパム対策ツールによってメッセージがスパムと見なされるリスクがあるかどうかを判断し、そうでない場合は対策を講じることができます。

>[!CAUTION]
>
>スパムレポートは、示唆と警告のみを提供します。 スパムレポートでコンテンツがスパムと見なされた場合にメッセージの送信が妨げられないことに注意してください。 スコアに基づいて行動する選択肢と推奨される改善点です。

次の手順で **[!UICONTROL スパムレポート]** 機能を使用するには、次の手順に従います。

<!--For example spam scoring tool can tell that there are too many Images compared to the text. Retailers tend to do this even though the spam score gets worse because the content is more engaging.-->

<!--Michael, who is a marketer with NIKE works along with Tara from testing team to ensure that the emails being sent as part of the campaign/journey don't get categorised as SPAM.

They need an integration within AJO's marketing system to show how the curated content is doing against different SPAM compliance pillars like for SPAM trigger words, HTML Body content and layout, subject line etc.

They should be able to get scores for each individual items as shown by market standard SPAM filtering tools like Spam Assassin, Symantec etc.

They should also get suggestions on how to improve the score better to be confident that the messages don't get categorised as spam.-->

1. 次から： **[!UICONTROL シミュレート]** 画面で、 **[!UICONTROL スパムレポート]** 」ボタンをクリックします。

   ![](assets/spam-report-button.png)

<!--
    You can also open the [Email Designer](../email/content-from-scratch.md), click the **[!UICONTROL More]** button and select **[!UICONTROL Check spam score]** from the menu.

    ![](assets/spam-report-check-score.png)
-->

1. スパム対策チェックが自動的に実行され、 **[!UICONTROL スパムレポート]** ウィンドウに結果が表示されます。 本文のレイアウト、構造、画像サイズ、スパムのトリガー語（存在する場合）などの観点から、コンテンツがどのように行われているかを示します。

   ![](assets/spam-report-high-score.png)

1. 各項目のスコアと説明を確認します。

   スコアが 5 を超える場合は、警告が表示されます。 これは、一部のメッセージが受信時にスパム対策ツールによってブロックされたり、スパムとしてマークされたりする可能性があることを示しています。

1. このスコアリングに基づいて、一部の要素を改善できると考えられる場合は、 [E メールデザイナー](../email/content-from-scratch.md) 必要に応じて更新を行います。

1. 変更が完了したら、 **[!UICONTROL スパムレポート]** 画面を表示して、スコアを確実に向上させます。

   ![](assets/spam-report-low-score.png)

<!--You can also check the message's alerts for warnings on potential risk of spam detection. Follow the steps below.

1. Click the **[!UICONTROL Alerts]** button on top right of the screen. [Learn more on email alerts](../email/create-email.md#check-email-alerts)

1. If **[!UICONTROL Spam checker alert]** is displayed, you should check your content for a potential risk of spam using the **[!UICONTROL Spam report]** feature as detailed above.

    ![](assets/spam-report-alert.png)
-->



