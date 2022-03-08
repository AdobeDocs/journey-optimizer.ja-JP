---
title: メールライブレポート
description: メールライブレポートからのデータの使用方法を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: 1ddfbf1a-3cd5-446a-b0fb-76b81b88c1b4
source-git-commit: 51254efaab08a572def118d475dc18f74c9d29b7
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 100%

---

# メールライブレポート {#email-live-report}

メール&#x200B;**[!UICONTROL ライブレポート]**&#x200B;は、特定のメール配信のみをターゲットにします。

**[!UICONTROL メッセージ]**&#x200B;メニューの「**[!UICONTROL 実行]**」タブで、「**[!UICONTROL ライブ表示]**」を選択し、選択した配信の詳細メニューで「**[!UICONTROL ライブレポート]**」を選択します。

![](../assets/live_report.png)

メール&#x200B;**[!UICONTROL ライブレポート]**&#x200B;は、配信の成功やエラーを示す様々なウィジェットに分かれています。必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。この機能について詳しくは、この[節](live-report.md#modify-dashboard)を参照してください。

![](../assets/live_report_5.png)

**[!UICONTROL メールのパフォーマンス]**&#x200B;および&#x200B;**[!UICONTROL メールの概要]** ウィジェットでは、メッセージに関連する主な情報の詳細がグラフと KPI と共に表示されます。

* **[!UICONTROL ターゲット]** : この配信のターゲットプロファイルと認定されるユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：配信に対する送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL 開封数]**：配信でメッセージが開封された回数。

* **[!UICONTROL クリック数]**：配信でコンテンツがクリックされた回数。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL スパムの苦情]** : スパムとして分類されたメッセージの数。

* **[!UICONTROL 購読解除]** : 購読解除リンクのクリック数。

* **[!UICONTROL 除外]** : ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

**[!UICONTROL 送信統計]**&#x200B;ウィジェットは、配信の成功の詳細を表示します。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

![](../assets/live_report_6.png)

「**[!UICONTROL エラー理由]**」グラフと表を使用すると、配信中に発生したエラーを確認できます。

**[!UICONTROL バウンスの理由]**&#x200B;ウィジェットおよび&#x200B;**[!UICONTROL バウンスのカテゴリ]**&#x200B;ウィジェットには、次のようなバウンスメッセージに関するデータが含まれています。

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

<!--
![](../assets/live_report_8.png)

>[!NOTE]
>
>The Offers widgets and metrics are only available if a decision was inserted in an email. For more information on Decision Management, refer to this [page](../offers/get-started/starting-offer-decisioning.md).

The **[!UICONTROL Offers statistic]** and **[!UICONTROL Offers statistics]** over time widgets measure your offer's success and impact on your targeted audience. It detail the main information relative to your message with KPIs:

* **[!UICONTROL Offer sent]**: Total number of sends for the offer.

* **[!UICONTROL Offer impression]**: Number of times the offer was opened in a delivery.

* **[!UICONTROL Offer clicks]**: Number of times an offer was clicked on in a delivery.
-->
>[!NOTE]
>
>「**[!UICONTROL 抑制]**」または「**[!UICONTROL 許可されていない]**」のステータスを持つプロファイルは、メッセージ送信プロセス中に除外されます。 したがって、**ジャーニーレポート**&#x200B;には、これらのプロファイルがジャーニー（[セグメントを読み取り](../building-journeys/read-segment.md)アクティビティと[メッセージ](../building-journeys/journeys-message.md)アクティビティ）を移動したものとして表示されますが、これらはメール送信前に除外されるので、**メールレポート**&#x200B;では、**[!UICONTROL 送信済み]**&#x200B;指標に含まれません。
>
>詳しくは、[抑制リスト](../messages/suppression-list.md)と[許可リスト](../messages/allow-list.md)を参照してください。すべての除外ケースの理由を確認するには、[Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=ja){target=&quot;_blank&quot;} を使用します。
