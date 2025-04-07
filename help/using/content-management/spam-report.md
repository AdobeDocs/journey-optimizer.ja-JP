---
title: メールスパムレポートの使用
description: 詳しくは、メールスパムレポートの使用方法を参照してください。
feature: Preview
role: User
level: Beginner
exl-id: 9ab43b14-41cf-49f1-bdcf-6fee58db5000
source-git-commit: b6fd60b23b1a744ceb80a97fb092065b36847a41
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 100%

---

# メールスパムレポート {#spam-report}

>[!CONTEXTUALHELP]
>id="ajo_simulate_spam_report"
>title="メールスパムレポート"
>abstract="スパムレポートを使用すると、メールコンテンツのスパムスコアを確認できます。このスコアは、ISP またはメールボックスプロバイダーがメッセージをスパムと見なすかどうかを示します。スコアが低いほど、より良い結果が得られます。メールコンテンツスコアが 2 を超える場合は、テストが失敗する原因である問題の修正を検討する必要があります。"

専用のスパムレポートで、メールコンテンツのスパムスコアを確認できます。[SpamAssassin](https://spamassassin.apache.org/){target="_blank"} を使用すると、Adobe Journey Optimizer は、メールの内容をテストし、ISP またはメールボックスプロバイダーがそれをスパムと見なすかどうかを示すスコアを提示します。

メールの内容を編集またはプレビューする際に、「**[!UICONTROL スパムレポート]**」オプションでは、リストされる個々の項目のスコアを向上させるために、スコアリングとアドバイスを提供します。

この機能を使用すると、受信時に使用されるスパム対策ツールによってメッセージがスパムと見なされるかどうかを判断し、スパムと判断された場合に対策を講じることができます。多くのメールインボックスプロバイダーは、スパムフィルタリングプロセスの一環としてツールを使用しています。悪いスコアのメールを送信すると、配信品質に重大な影響を与える可能性があります。

**[!UICONTROL スパムレポート]**&#x200B;にアクセスするには、次の手順に従います。

1. **[!UICONTROL シミュレート]**&#x200B;画面で、「**[!UICONTROL スパムレポート]**」ボタンをクリックします。

   ![](assets/spam-report-button.png)

<!--
    You can also open the [Email Designer](../email/content-from-scratch.md), click the **[!UICONTROL More]** button and select **[!UICONTROL Check spam score]** from the menu.

    ![](assets/spam-report-check-score.png)
-->

1. スパム対策チェックが自動的に実行され、**[!UICONTROL スパムレポート]**&#x200B;ウィンドウに結果が表示されます。本文のレイアウト、構造、画像サイズ、スパムのトリガー語（存在する場合）などの観点から、コンテンツに関する情報を示します。

   ![](assets/spam-report-high-score.png)

1. 各項目のスコアと説明を確認します。

   スコアが低いほど、より良い結果が得られます。スコアが 5 以上の場合、警告が表示されます。これは、一部のメッセージが受信時にブロックされるか、スパムとしてマークされる可能性があることを示します。ベストプラクティスは、スコアを 2 未満にすることです。

   >[!NOTE]
   >
   >スパムスコアは [SpamAssassin](https://spamassassin.apache.org/){target="_blank"} によって得られ、ルールは Adobe の所有ではありません。これらのルールについて詳しくは、SpamAssassin ドキュメントを参照してください。
   >

1. このスコアリングに基づいて、一部の要素を改善できると考えられる場合は、[E メールデザイナー](../email/content-from-scratch.md)でコンテンツを編集し、必要な更新を行ってください。

1. 変更が完了したら、**[!UICONTROL スパムレポート]**&#x200B;画面に戻り、スコアが向上していることを確認します。

   ![](assets/spam-report-low-score.png)

<!--You can also check the message's alerts for warnings on potential risk of spam detection. Follow the steps below.

1. Click the **[!UICONTROL Alerts]** button on top right of the screen. [Learn more about email alerts](../email/create-email.md#check-email-alerts)

1. If **[!UICONTROL Spam checker alert]** is displayed, you should check your content for a potential risk of spam using the **[!UICONTROL Spam report]** feature as detailed above.

    ![](assets/spam-report-alert.png)
-->
