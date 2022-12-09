---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーングローバルレポート
description: キャンペーングローバルレポートのデータを使用する方法について学習します。
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: fa64f5b8-75f2-40e6-8566-5766fafe6cd6
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 0%

---

# キャンペーングローバルレポート {#campaign-global-report}

キャンペーングローバルレポートには、 **[!UICONTROL All time]** ボタンを使用してキャンペーンから直接アクセスすることができます。

![](assets/campaign_report_global_5.png)

キャンペーン **[!UICONTROL Global report]** ページには、次のタブが表示されます。

* [キャンペーン](#campaign-global)
* [電子メール](#email-global)
* [プル](#push-global)
* [SMS](#sms-global)

**[!UICONTROL Global report]**&#x200B;キャンペーンは、キャンペーンの成功とエラーについての様々な widget に分割されています。各 widget については、必要に応じてサイズ変更や削除を行うことができます。 詳細については、ここを [ ](../reports/global-report.md#modify-dashboard) 参照してください。

アドビシステムズ社のオプティマイザーで利用可能なすべてのメトリックスのリストについては、このページを [ 参照してください。](global-report.md#list-of-components-global.md)

## 「キャンペーン」タブ {#campaign-global}

### 先住 {#delivery-global}

![](assets/campaign_report_global_1.png)

Widget には、キャンペーンに関する重要な情報が表示され **[!UICONTROL Campaign's Statistics]** ます。

* **[!UICONTROL Entered profiles]**: 旅を開始したプロファイルの数。

* **[!UICONTROL Actions delivered]**: 処理が配信された一意の時間の合計数です。

* **[!UICONTROL Actions failed in %]**: アクションが配信された一意の時間の合計数と比較して、操作が失敗した時間の合計数です。

## 電子メールタブ {#email-global}

![](assets/campaign_report_global_2.png)

キャンペーン **[!UICONTROL Global report]** からは、キャンペーンで送信された電子メール配信を基準とした重要な情報がタブに **[!UICONTROL Email]** 表示されます。

電子メールレポートに使用できる様々なメトリックスと widget について詳しくは、+ + + こちらを参照してください。

このグラフは **[!UICONTROL Email Sending Statistics]** 、配信が成功したことを示します。

* **[!UICONTROL Targeted]**: 配信分析中に処理されたメッセージの合計数。

* **[!UICONTROL Sent]**: 配布に使用された送信の合計数。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Delivery Rate]**: 送信に成功したメッセージの割合 (%) を指定します。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Bounce Rate]**: 送り返された電子メールのうち、送信された電子メールのパーセンテージを示します。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

* **[!UICONTROL Error Rate]**: 配信中に発生したエラーのうち、送信中に発生したメールと比較して送信されたものを防ぐことができます。

* **[!UICONTROL Retries]**: リトライ用のキューの電子メールの数。

* **[!UICONTROL Excluded]**: Adobe の旅オプティマイザーによって除外されたプロフィールの数です。

**[!UICONTROL Email - Tracking statistics]**&#x200B;この widget には、配信に使用できる受信者アクティビティのデータが格納されています。

* **[!UICONTROL Opens]**: 配信が開かれた回数を指定します。

* **[!UICONTROL Unique Opens]**: 開かれた出荷に対する割合です。

* **[!UICONTROL Open Rate]**: 配信された電子メールの数と比較して開かれた電子メールの合計数。

* **[!UICONTROL Clicks]**: 電子メールのコンテンツがクリックされた回数を指定します。

* **[!UICONTROL Unique Clicks]**: 電子メールのコンテンツをクリックした受信者の数です。

* **[!UICONTROL Unique Click Rate]**: 配信にアクセスしたユーザのパーセンテージです。

* **[!UICONTROL Unsubscriptions]**: Unsubscription リンクのクリック回数。

* **[!UICONTROL Spam complaints]**: メッセージがスパムまたは迷惑メールとして宣言された回数。

このグラフに **[!UICONTROL Sending Statistics]** は、送信された電子メールで利用可能なデータが含まれています。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Retries]**: リトライ用のキューの電子メールの数。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

**[!UICONTROL Bounce Reasons]**&#x200B;および **[!UICONTROL Bounce categories]** widget には、バウンスメッセージに関連する次のようなデータが含まれています。

* **[!UICONTROL Hard bounce]**: 電子メールアドレスの間違いなどの永続的なエラーの合計数。 これには、不明なユーザーなど、アドレスが無効であることを示すエラーメッセージが表示されます。

* **[!UICONTROL Soft bounce]**: 完全な受信ボックスなど、一時的なエラーの合計数。

* **[!UICONTROL Ignored]**: 「外出中」などの一時的な合計数、または送信者の種類がポストマスターである場合などの技術的なエラーが挙げられます。

バウンスについて詳しくは、抑制リスト ](../reports/suppression-list.md) ページを [ 参照してください。

**[!UICONTROL Error Reasons]**&#x200B;グラフとテーブルを使用すると、配信中に発生したエラーを確認することができます。

**[!UICONTROL Excluded reasons]**「グラフとテーブル」には、対象のプロファイルから除外されたユーザープロファイルがメッセージの受信から除外されるというさまざまな理由が表示されます。

表示されている情報は、グラフとテーブルに **[!UICONTROL Email - Top Url]** よって異なります。

グラフとテーブルに **[!UICONTROL Email - Top recipient domain]** は、電子メールを開くために受信者が最も頻繁に使用するドメインが詳しく表示されます。

>[!NOTE]
>
>**[!UICONTROL Optimized vs non optimized]** And **[!UICONTROL Send time optimization]** widget を使用できるのは、配信時に「送信時の最適化」オプションが有効になっている場合のみです。送信時最適化について詳しくは、このページ ](../building-journeys/journeys-message.md#send-time-optimization) を [ 参照してください。

グラフは **[!UICONTROL Optimized vs non optimized]** 、最適化されているかどうかに関係なく、メッセージに関する主な情報を示します。

* **[!UICONTROL Sent]**: 配布に使用された送信の合計数。
* **[!UICONTROL Opens]**: 配信が開かれた回数を指定します。
* **[!UICONTROL Clicks]**: 電子メールのコンテンツがクリックされた回数を指定します。

送信方法に応じて、 **[!UICONTROL Send time optimization]** 「最適化」または「標準」を使用して配信を成功させることができます。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。
* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。
+++

## 「プッシュ通知」タブ {#push-global}

キャンペーン **[!UICONTROL Global report]** から、このタブは **[!UICONTROL Push notification]** 、キャンペーンで送信された配信配信を基準とした重要な情報を表示します。

![](assets/campaign_report_global_3.png)

+ + + プッシュレポートに使用できる様々なメトリックスと widget について詳しくは、こちらを参照してください。

この表では、 **[!UICONTROL Push notification - Sending statistics]** グラフと kpi を使用した push 通知に関する主な情報について説明しています。

* **[!UICONTROL Targeted]**: 配信分析中に処理されたメッセージの合計数。

* **[!UICONTROL Sent]**: 配布に使用された送信の合計数。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Delivery Rate]**: 送信に成功したメッセージの割合 (%) を指定します。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Bounce Rate]**: プッシュ通知が送信されたときにバウンスされた push 通知の割合。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

* **[!UICONTROL Error Rate]**: 配信中に発生したエラーのうち、プッシュ通知が送信されたときとの間に発生したエラーの割合を示します。

* **[!UICONTROL Excluded]**: Adobe の旅オプティマイザーによって除外されたプロフィールの数です。

には **[!UICONTROL Push - Tracking statistics]** 、配信に使用できる受信者アクティビティのデータが格納されています。

* **[!UICONTROL Opens]**: メッセージが配信中に開かれた回数を示します。

* **[!UICONTROL Open Rate]**: 開かれたプッシュ通知の割合。

* **[!UICONTROL Actions]**: プッシュ通知で配信されたアクションの合計数 (例えば、ボタンのクリックまたは dismissal)。

* **[!UICONTROL Engagements]**: このプッシュ通知のオープン数とアクション数の合計、つまり、プロファイルからプッシュが開かれたか、ボタンがクリックされたかどうかを示します。

* **[!UICONTROL Engagement Rate]**: このプッシュ通知のオープン数とアクション数、つまり、プロファイルがプッシュを開いたか、ボタンがクリックされたかどうかを示します。

このグラフに **[!UICONTROL Push notification summary]** は、送信されたプッシュ通知の次のようなデータが含まれています。

* **[!UICONTROL Opens]**: メッセージが配信中に開かれた回数を示します。

* **[!UICONTROL Actions]**: プッシュ通知で配信されたアクションの合計数 (例えば、ボタンのクリックまたは dismissal)。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

>[!NOTE]
>
>**[!UICONTROL Optimized vs non optimized]** And **[!UICONTROL Send time optimization]** widget を使用できるのは、配信時に「送信時の最適化」オプションが有効になっている場合のみです。送信時最適化について詳しくは、このページ ](../building-journeys/journeys-message.md#send-time-optimization) を [ 参照してください。

グラフは **[!UICONTROL Optimized vs non optimized]** 、最適化されているかどうかに関係なく、メッセージに関する主な情報を示します。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。
* **[!UICONTROL Opens]**: 配信が開かれた回数を指定します。
* **[!UICONTROL Actions]**: プッシュ通知で配信されたアクションの合計数 (例えば、ボタンのクリックまたは dismissal)。

送信方法に応じて、 **[!UICONTROL Send time optimization]** 「最適化」または「標準」を使用して配信を成功させることができます。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。
* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

**[!UICONTROL Error Reasons]**&#x200B;グラフとテーブルを使用すると、配信中に発生したエラーを確認することができます。

**[!UICONTROL Excluded reasons]**「グラフとテーブル」には、対象のプロファイルから除外されたユーザープロファイルがメッセージの受信から除外されるというさまざまな理由が表示されます。

**[!UICONTROL Tracking by platform]**、 **[!UICONTROL Sending by platform]** 、グラフ、および **[!UICONTROL Breakdown by platform]** テーブルによって、受信者のオペレーティングシステムに応じた push 通知の成否が詳しく説明されています。
+++

## 「SMS」タブ {#sms-global}

キャンペーン **[!UICONTROL Global report]** からは、キャンペーンで送信された SMS 配信に関する重要な情報がタブに **[!UICONTROL SMS]** 表示されます。

![](assets/campaign_report_global_4.png)

、SMS レポートに使用できる様々なメトリックスと widget について詳しく説明します。

以下の表は **[!UICONTROL SMS - Sending statistics]** 、配信が成功したことを示しています。

* **[!UICONTROL Targeted]**&#x200B;この配信には、ターゲットのプロファイルとして認定されるユーザープロファイルの数を指定します。

* **[!UICONTROL Excluded]**: メッセージが配信されなかった対象のプロファイルから除外されたユーザープロファイルの数。

* **[!UICONTROL Sent]**: 配布に使用された送信の合計数。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

Widget を使用すると、 **[!UICONTROL SMS Performance by date]** グラフでメッセージを基準とした主な情報が詳細に表示されます。

* **[!UICONTROL Sent]**: 配布に使用された送信の合計数。

* **[!UICONTROL Delivered]**: 送信されたメッセージの総数に対する、送信が成功したメッセージの数を指定します。

* **[!UICONTROL Bounces]**: 配信中に発生したエラーの合計数が、送信メッセージの総数に対する相対処理で累積されます。

* **[!UICONTROL Errors]**: 配信中に発生したエラーの総数が、プロファイルに送信されるのを防ぐことができます。

**[!UICONTROL Exclude Reasons]**、 **[!UICONTROL Bounces Reasons]** グラフ、および **[!UICONTROL Error Reasons]** テーブルを使用すると、配信中に発生したエラーと除外を確認することができます。
+++

## その他のリソース

* [キャンペーンの開始](../campaigns/get-started-with-campaigns.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [API トリガキャンペーンの作成](../campaigns/api-triggered-campaigns.md)
* [キャンペーンの変更または停止](../campaigns/modify-stop-campaign.md)
* [キャンペーンライブレポート](campaign-live-report.md)
