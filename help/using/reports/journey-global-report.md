---
title: ジャーニーのグローバルレポート
description: ジャーニーのグローバルレポートのデータの利用方法を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: e851646e-4cef-45e8-97c2-a8f4c9d2cc08
source-git-commit: b43e3432ede1d4985e0a6b57b57c5efc3cf60c50
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 100%

---

# ジャーニーグローバルレポート {#journey-global-report}

ジャーニーのグローバルレポートにジャーニーから直接アクセスするには、「**[!UICONTROL グローバルレポート]**」ボタンを押します。

![](../assets/global_report_1.png)

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;ページが表示され、次のタブが表示されます。

* [ジャーニー](#journey-global)
* [メール](#email-global)
* [プッシュ](#push-global)

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;は、ジャーニーの成功とエラーについて説明する様々なウィジェットに分かれています。必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。詳しくは、この[節](global-report.md#modify-dashboard)を参照してください。

## 「ジャーニー」タブ {#journey-global}

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL ジャーニー]**」タブには、ジャーニーに関する重要なトラッキングデータが明確に表示されます。

![](../assets/global_report_2.png)

**[!UICONTROL ジャーニーのパフォーマンス]**&#x200B;ウィジェットを使用すると、ターゲットプロファイルのパスを、ジャーニーを通じて段階的に確認できます。

**[!UICONTROL ジャーニーの統計情報]**&#x200B;ウィジェットには、次の KPI が表示されます。

* **[!UICONTROL エントリしたプロファイル]**：ジャーニーのエントリイベントに到達した個人の合計数。

* **[!UICONTROL 退出したプロファイル]**：ジャーニーから退出した個人の合計数。

* **[!UICONTROL 失敗した個人のジャーニー]**：正常に実行されなかった個人のジャーニーの合計数。

![](../assets/global_report_12.png)

**[!UICONTROL イベントごとに受信したイベント]**、**[!UICONTROL 発信元別のイベント]**&#x200B;および&#x200B;**[!UICONTROL 上位のイベント]**&#x200B;の各ウィジェットを使用すると、どの&#x200B;**[!UICONTROL イベント]**&#x200B;が正常に実行されたかをグラフや表を通して確認できます。

![](../assets/global_report_13.png)

**[!UICONTROL アクションパフォーマンス]**、**[!UICONTROL アクションエラーの理由]**&#x200B;および&#x200B;**[!UICONTROL 上位アクション]**&#x200B;の各ウィジェットは、最も成功したアクションと、**[!UICONTROL アクション]**&#x200B;がトリガーされた際に発生したエラーを表します。

**[!UICONTROL 上位のアクション]**&#x200B;テーブルには、**[!UICONTROL アクション]**&#x200B;に関する次のようなデータが表示されます。

* **[!UICONTROL 正常に実行されたアクション]**：ジャーニーに対して正常に実行された&#x200B;**[!UICONTROL アクション]**&#x200B;の合計数。

* **[!UICONTROL アクションのエラー]**：**[!UICONTROL アクション]**&#x200B;で発生したエラーの合計数。

## 「メール」タブ {#email-global}

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL メール]**」タブには、ジャーニーで送信したメールの配信に関する主な情報が表示されます。

特定のメール配信に関する詳細なレポートについては、[メールのグローバルレポート](#email-global-report)のセクションを参照してください。

![](../assets/global_report_14.png)

**[!UICONTROL メール送信統計]**&#x200B;グラフは、成功した配信の詳細を示します。

* **[!UICONTROL 送信済み]**：配信に対する送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL バウンス率]**：送信メールに対するバウンスメールの割合。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたメールに対して、配信中にエラーが発生して送信できなかったメールの割合。

**[!UICONTROL メール - トラッキング統計情報]**&#x200B;には、配信に対する受信者のアクティビティを確認できるデータが表示されます。

* **[!UICONTROL 開封数]**：配信でメッセージが開かれた回数。

* **[!UICONTROL ユニーク開封数]**：開封された配信の割合。

* **[!UICONTROL 開封率]**：配信されたメール数に対して、開封されたメールの合計数。

* **[!UICONTROL クリック数]**：メールのコンテンツがクリックされた回数。

* **[!UICONTROL ユニーククリック数]**：メールのコンテンツをクリックした受信者の数。

* **[!UICONTROL クリックスルー率]**：ジャーニーに対して何らかのアクションを起こしたユーザーの割合。

* **[!UICONTROL 購読解除]**：購読解除リンクのクリック数。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

**[!UICONTROL 送信統計情報]**&#x200B;グラフを使用すると、次のような送信済みメールに関するデータを確認できます。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

![](../assets/global_report_15.png)

**[!UICONTROL バウンスの理由]**&#x200B;ウィジェットおよび&#x200B;**[!UICONTROL バウンスのカテゴリ]**&#x200B;ウィジェットには、次のようなバウンスメッセージに関するデータが含まれています。

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

バウンスの詳細については、[抑制リスト](../messages/suppression-list.md)のページを参照してください。

![](../assets/global_report_16.png)

「**[!UICONTROL メール - 上位の URL]**」のグラフと表は、配信されたメールの中で最もアクセス頻度の高い URL の詳細を示しています。

「**[!UICONTROL メール - 上位の受信者ドメイン]**」のグラフと表は、受信者が電子メールを開くために最も多く使用しているドメインの詳細を示しています。

<!--
![](../assets/global_report_21.png)

>[!NOTE]
>
>The Offers widgets and metrics are only available if a decision was inserted in an email. For more information on Decision Management, refer to this [page](../offers/get-started/starting-offer-decisioning.md).

The **[!UICONTROL Offers statistic]** and **[!UICONTROL Offers statistics]** over time widgets measure your offer's success and impact on your targeted audience. It detail the main information relative to your message with KPIs:

* **[!UICONTROL Offer sent]**: Total number of sends for the offer.

* **[!UICONTROL Offer impression]**: Number of times the offer was opened in a delivery.

* **[!UICONTROL Offer clicks]**: Number of times an offer was clicked on in a delivery.

The **[!UICONTROL Offers detailed statistic]** table contains the available data for recipient activity with your offer:

* **[!UICONTROL Placement name]**: Name of your placement used to display your offer. For more information on placement, refer to this [page](../offers/offer-library/creating-placements.md).

* **[!UICONTROL Offer name]**: Name of the offer added in the delivery. For more information on placement, refer to this [page](../offers/offer-library/creating-personalized-offers.md).

* **[!UICONTROL Offer sent]**: Total number of sends for the offer.

* **[!UICONTROL Offer impression rate]**: Percentage of opened offers compared to the number of sent offers.

* **[!UICONTROL Offer click rate]**: Percentage of users who interacted with the offer.
-->

## 「プッシュ」タブ {#push-global}

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL プッシュ]**」タブには、ジャーニーで送信されるプッシュ配信に関連する主な情報が詳しく表示されます。

特定のプッシュ配信に関する詳細なレポートについては、[プッシュグローバルレポート](#push-global-report)を参照してください。

![](../assets/global_report_17.png)

「**[!UICONTROL プッシュ通知 - 送信統計]**」テーブルは、プッシュ通知に関連するメイン情報の詳細をグラフと KPI で示します。

* **[!UICONTROL 送信済み]**：配信に対する送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL バウンス率]**：送信されたプッシュ通知と比較した、バウンスしたプッシュ通知の割合。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知と比較した、配信中に発生した送信を妨げるエラーの割合。

「**[!UICONTROL プッシュ - トラッキング統計]**」には、配信の受信者アクティビティに使用できるデータが含まれます。

* **[!UICONTROL 開封数]**：配信でメッセージが開封された回数。

* **[!UICONTROL 開封率]**：開封されたプッシュ通知の割合。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL エンゲージメント]**：このプッシュ通知に対する開封数とアクション数（「プロファイルがプッシュを開封した」、「ボタンがクリックされた」など）の合計。

* **[!UICONTROL エンゲージメント率]**：このプッシュ通知の開封とアクションの割合（プロファイルによるプッシュの開封や、ボタンのクリックなど）。

「**[!UICONTROL プッシュ通知の概要]**」グラフには、次のような送信済みプッシュ通知に使用できるデータが含まれています。

* **[!UICONTROL 開封数]**：配信でメッセージが開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス]**：送信されたメッセージの総数に対して、配信と自動返信の処理中に発生したエラーの累計。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL エラー]**：配信中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

![](../assets/global_report_18.png)

「**[!UICONTROL エラー理由]**」グラフと表を使用すると、配信中に発生したエラーを確認できます。

![](../assets/global_report_19.png)

**[!UICONTROL プラットフォーム別トラッキング]**、**[!UICONTROL プラットフォーム別送信]**、**[!UICONTROL プラットフォーム別分類]**&#x200B;のグラフとテーブルには、プッシュ通知の成功の詳細がオペレーティングシステムに応じて表示されます。
