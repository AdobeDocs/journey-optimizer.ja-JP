---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンのグローバルレポート
description: キャンペーンのグローバルレポートからデータを使用する方法を説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: fa64f5b8-75f2-40e6-8566-5766fafe6cd6
source-git-commit: d26dbebaf36241d0e91c36c95f83ce6cf712ecee
workflow-type: tm+mt
source-wordcount: '4648'
ht-degree: 55%

---

# キャンペーンのグローバルレポート {#campaign-global-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_report"
>title="キャンペーンのグローバルレポート"
>abstract="キャンペーンのグローバルレポートを使用すると、選択した期間におけるキャンペーンの効果を測定できます。 レポートは、キャンペーンの成功とエラーの詳細を示す様々なウィジェットに分かれています。各レポートダッシュボードは、ウィジェットのサイズ変更や削除を行うことで変更できます。"

「**全期間**」タブからアクセスできるグローバルレポートには、少なくとも 2 時間前に発生したイベントと、選択した期間のイベントが表示されます。これに対し、ライブレポートには、過去 24 時間以内に発生したイベントが焦点となり、イベント発生から最小 2 分の時間間隔で表示されます。

キャンペーンのグローバルレポートへは、「**[!UICONTROL レポートを表示]**」ボタンを使用して、キャンペーンから直接アクセスできます。

![](assets/campaign_report_global_5.png)

キャンペーンの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;ページは次のタブで表示されます。

* [キャンペーン](#campaign-global)
* [メール](#email-global)
* [アプリ内](#inapp-global)
* [プッシュ](#push-global)
* [SMS](#sms-global)
* [Web](#web-tab)
* [ダイレクトメール](#direct-mail-global)

キャンペーンの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;は、キャンペーンの成功とエラーの詳細を示す様々なウィジェットに分かれています。必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。詳しくは、この[節](../reports/global-report.md#modify-dashboard)を参照してください。

Adobe Journey Optimizerで使用可能なすべての指標の詳細なリストについては、[このページ](global-report.md#list-of-components-global.md)を参照してください。

## 「キャンペーン」タブ {#campaign-global}

### 配信 {#delivery-global}

>[!CONTEXTUALHELP]
>id="ajo_campaign_delivery_global"
>title="キャンペーンの統計"
>abstract="キャンペーンの統計ウィジェットには、入力したプロファイルや配信したアクションなど、キャンペーンに関連する主な情報の詳細が表示されます。"

![](assets/campaign_report_global_1.png)

The **[!UICONTROL キャンペーンの統計]** KPI は包括的なダッシュボードとして機能し、キャンペーンに関連する主要指標の詳細な分類を提供します。 これには、配信されたプロファイル数やアクション数など、キャンペーンのパフォーマンスとエンゲージメントを完全に把握できる重要な情報が含まれます。

+++ Campaign の統計指標の詳細を説明します

* **[!UICONTROL 対象ユーザ]**：ターゲットプロファイルの数。

* **[!UICONTROL 配信されたアクション]**：アクションが配信されたユニーク回数の合計。

* **[!UICONTROL アクションが%で失敗しました]**：アクションが配信されたユニーク回数の合計に対する、アクションが失敗したユニーク回数の割合。

+++

<!--
### Objectives report {#objectives-global}

![](assets/performance_report.gif)

The **[!UICONTROL Objectives]** tab allows you to better fine-tune your deliveries' reports by targeting one specific metric.

The **[!UICONTROL Objectives]** listed are linked to **[!UICONTROL Datasets]** that define a connection to a system in order to retrieve additional information. A list of built-in **[!UICONTROL Objectives]** is available but you can add your own by adding new **[!UICONTROL Dataset]**. For the detailed procedure, refer to this [section](../campaigns/reporting-configuration.md).

After selecting the Objectives you want to target on, the two **[!UICONTROL Performance overview]** and **[!UICONTROL Campaign objective]** widgets will provide a detailed summary of your delivery performance. 

With the **[!UICONTROL Campaign objective]** widget, you can also choose to compare your main objective with another metric.
-->

### 実験レポート {#experimentation-global}

>[!CONTEXTUALHELP]
>id="ajo_campaigns_content_experiment_click"
>title="成功指標"
>abstract="実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。"

![](assets/experimentation_report_3.png)

「**[!UICONTROL 実験]**」タブには、各バリアントのパフォーマンスに関する主要なインサイトが表示され、最も成功したものを特定します。

最もパフォーマンスの高い処理の判定には時間がかかる場合があり、このアイコン ![](assets/experimentation_report_1.png) が表示されます。

+++実験レポートで使用できる様々な指標およびウィジェットの詳細を説明します。

**[!UICONTROL 実験結果]**&#x200B;ウィジェットは、各バリアントのパフォーマンスの詳細を説明します。ベースラインを変更するには、**[!UICONTROL ベースライン]**&#x200B;ドロップダウンから処理の 1 つを選択します。最も優れた処理には、星のアイコンが表示されます。

これらの結果の詳細と解釈について詳しくは、[このページ](../campaigns/get-started-experiment.md#interpret-results)を参照してください。

このテーブルは、次の指標を表しています。

* **[!UICONTROL ベースライン上の上昇率]**：ベースラインに対する特定の処理のコンバージョン率の向上率を測定します。

* **[!UICONTROL 信頼性]**：ある処理がベースライン処理と同じであることを示す証拠。[詳細情報](../campaigns/experiment-calculations.md#understand-confidence)

* **[!UICONTROL ユニークアウトバウンドクリック数]**：アウトバウンドチャネルでのクリック総数。

* **[!UICONTROL プロファイル]**：この処理の対象となるプロファイルの数。

* **[!UICONTROL ユニークアウトバウンドクリック数／プロファイル数]**：実験の作成時に以前に選択した成功指標の合計値を、プロファイル数で割った値です。

**[!UICONTROL 信頼区間]**&#x200B;グラフは、改善に関する不確実性を測定します。ベースラインと最もパフォーマンスの高い処理との間のパフォーマンス差の割合を詳細に示します。[詳細情報](../campaigns/experiment-calculations.md#confidence-intervals)

![](assets/experimentation_report_4.png)

最後のウィジェットは、以前に処理用に選択した&#x200B;**[!UICONTROL 成功指標]**&#x200B;に関連するデータを提供します。**[!UICONTROL 指標]**&#x200B;ドロップダウンメニューから別のターゲット指標を選択して、代替データを追跡することもできます。

>[!CAUTION]
>
>実験でフィルタリングされた指標を使用する場合は、実験の比較ページのドロップダウンから指標の選択を変更すると、フィルター値が保持されないことに注意してください。例えば、「クリック数」から「ユニーククリック数」に切り替えると、適用されたフィルターが失われ、比較が不正確または無効になります。

+++

## 「メール」タブ {#email-global}

### 電子メール — 送信統計 {#sending-statistics-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_sending_statistics"
>title="メール - 送信統計"
>abstract="メール - 送信統計テーブルは、ターゲットや配信など、メールに関する重要なデータを要約します。"

![](assets/campaign_email_sending.png)

The **[!UICONTROL E メール送信統計]** 表は、E メールキャンペーンに関する重要なデータの包括的な概要を示しています。 ターゲットオーディエンスのサイズや正常に配信された電子メールの数など、主要な指標の詳細を説明し、電子メールの効果とリーチに関する有益なインサイトを提供します。

+++ 電子メール送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：送信プロセス中に処理された電子メールの合計数。

* **[!UICONTROL 送信済み]**：メール用の送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの総数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL バウンス率]**：送信メールに対するバウンスメールの割合。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたメールに対して、送信プロセス中にエラーが発生して送信できなかったメールの割合。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

### メール - トラッキング統計 {#tracking-statistics-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_tracking_statistics"
>title="メール - トラッキング統計"
>abstract="メール - トラッキング統計テーブルには、メールのプロファイルアクティビティに関するデータが表示されます。"

![](assets/campaign_email_tracking.png)

The **[!UICONTROL E メール — トラッキング統計]** テーブルには、E メールキャンペーンに関連するプロファイルアクティビティの詳細なアカウントが表示されます。 これには、開封数、クリック数、その他の関連するエンゲージメント指標など、プロファイルが E メールコンテンツとどのようにやり取りするかを包括的に示す指標が含まれます。

+++ E メール — トラッキング統計指標の詳細を説明します

* **[!UICONTROL 開封数]**：メールが開封された回数。

* **[!UICONTROL ユニーク開封数]**：開封されたメールのパーセンテージ。

* **[!UICONTROL 開封率]**：配信されたメール数に対して、開封されたメールの合計数。

* **[!UICONTROL クリック数]**:E メールでコンテンツがクリックされた回数。

* **[!UICONTROL ユニーククリック数]**:E メールのコンテンツをクリックしたプロファイルの数。

* **[!UICONTROL ユニーククリック率]**：電子メールでインタラクションをおこなったユーザーの割合。

* **[!UICONTROL 購読解除]** : 購読解除リンクのクリック数。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

+++

### 電子メール — 送信パフォーマンス {#sending-performance-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_sending_performance"
>title="メール - 送信パフォーマンス"
>abstract="E メール — 送信パフォーマンスグラフは、送信済み E メールに関する包括的なデータを表示し、配信済みとバウンスなどの主要指標に関するインサイトを提供し、E メール配信プロセスを詳細に分析できます。"

![](assets/campaign_email_sending_performance.png)

The **[!UICONTROL 電子メール — 送信パフォーマンス]** グラフは、送信された電子メールに関連するデータの包括的なビューを提供し、配信済み指標やバウンス指標などの主要指標に関するインサイトを提供します。 これにより、E メール送信プロセスの詳細な分析が可能になり、E メールキャンペーンの効率性とパフォーマンスに関する貴重な情報が提供されます。

+++ 電子メール — 送信パフォーマンス指標の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL バウンス]**：送信済み E メールの合計数に関して、送信プロセスと自動返信処理の間に累積したエラーの合計。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### 電子メール — バウンスの理由とカテゴリ {#bounces-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounce_categories"
>title="メール - バウンスカテゴリ"
>abstract="メール - バウンスカテゴリのグラフとテーブルには、一時的なエラーと永続的なエラーの両方に関するデータが表示されます。"

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_bounce_reasons"
>title="メール - バウンス理由"
>abstract="メール - バウンス理由のグラフとテーブルには、バウンスされたメッセージに関連して使用可能なデータが含まれます。"

![](assets/campaign_email_bounces.png)

The **[!UICONTROL 電子メール — バウンスの理由]** および **[!UICONTROL 電子メール — バウンスのカテゴリ]** ウィジェットは、バウンスメッセージに関連する使用可能なデータをコンパイルし、電子メールバウンスの背後にある特定の理由とカテゴリに関する詳細なインサイトを提供します。

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

+++ メール — バウンスカテゴリ指標の詳細を説明します

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

+++


### メール - エラー理由 {#errors-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_error_reasons"
>title="メール - エラー理由"
>abstract="メール - エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/campaign_email_error_reasons.png)

The **[!UICONTROL エラーの理由]** グラフと表には、送信プロセス中に発生した特定のエラーを表示し、エラーの特性と発生に関する貴重な情報を提供します。

表、棒グラフ、ドーナツグラフから切り替えることができます。

### メール - 除外された理由 {#excluded-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_excluded_reasons"
>title="メール - 除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/campaign_email_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表は、ターゲットオーディエンスからユーザープロファイルを除外した結果、メッセージが受信されなかった様々な要因の包括的なビューを示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### ドメイン別に送信および配信 {#sent-domains}

![](assets/campaign_email_sent_domains.png)

The  **[!UICONTROL ドメイン別に送信および配信]** 表とグラフは、ドメインレベルでの電子メールの詳細な分類を提供し、電子メールのパフォーマンスに関する包括的なインサイトを提供します。

+++ ドメイン指標別の送信および配信の詳細を説明します

* **[!UICONTROL 送信済み]**：メール用の送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

+++

### ドメイン別のバウンス数とエラー数 {#bounces-domains}

![](assets/campaign_email_bounce_domains.png)

The  **[!UICONTROL ドメイン別バウンス数とエラー数]** グラフと表には、送信プロセス中に発生した特定のエラーのドメインレベルでの分類が表示され、発生した問題の詳細な分析が可能です。

+++ ドメイン別バウンス数およびエラー数指標の詳細を説明します

* **[!UICONTROL バウンス]**：送信済み E メールの合計数に関して、送信プロセスと自動返信処理の間に累積したエラーの合計。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、E メールをプロファイルに送信できなかったエラーの合計数。

+++

### ドメイン別の開封数およびクリック数 {#opens-domains}

![](assets/campaign_email_open_domains.png)

The  **[!UICONTROL ドメイン別の開封数およびクリック数]** グラフと表では、プロファイルの E メールに対するエンゲージメントのドメインレベルの分類を確認し、様々なドメインがコンテンツとどのようにやり取りするかに関する有益なインサイトを提供します。

+++ ドメイン別の開封数およびクリック数指標の詳細を説明します

* **[!UICONTROL 開封数]**：メールが開封された回数。

* **[!UICONTROL クリック数]**:E メール内でコンテンツがクリックされた回数。

+++

### ドメイン別のバウンス理由 {#bounce-reasons-domains}

![](assets/campaign_email_bounce_reasons_domains.png)

The  **[!UICONTROL ドメイン別のバウンス理由]** グラフとテーブルでは、一時的なエラーと永続的なエラーの両方に関するデータをドメインレベルで分類し、バウンスメッセージの原因に関する詳細なインサイトを提供します。

+++ ドメイン指標別のバウンス理由の詳細を説明します

* **[!UICONTROL 開封数]**：メールが開封された回数。

* **[!UICONTROL クリック数]**:E メール内でコンテンツがクリックされた回数。

+++

### メール - 上位の URL {#top-url-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_top_url"
>title="メール - 上位の URL"
>abstract="メール - 上位 URL のグラフとテーブルには、訪問者のトラフィックが最も多いメール内の URL の包括的な概要が表示され、一番人気のあるリンクを特定できます。"

![](assets/campaign_email_topurl.png)

The **[!UICONTROL 電子メール — 上位の URL]** 最も高い訪問者トラフィックを引き付ける e メール内の URL の包括的な概要を示すグラフと表。 これにより、最頻訪問リンクを識別し優先順位を付け、E メール内の特定のコンテンツに対するプロファイルのエンゲージメントに対する理解を深めることができます。

### メール - 最適な受信者ドメイン {#top-recipient-email}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_email_best_recipient"
>title="メール - 最適な受信者ドメイン"
>abstract="メール - 最適な受信者ドメインのグラフとテーブルには、受信者がメールを開くために最も頻繁に使用するドメインの詳細な分類が表示され、受信者の行動に関する貴重なインサイトが得られます。"

![](assets/campaign_email_best_recipient.png)

>[!CAUTION]
>
> The **[!UICONTROL E メール — 最適な受信者ドメイン]** ウィジェットの精度は 99.95%です。

The **[!UICONTROL E メール — 最適な受信者ドメイン]** グラフと表には、プロファイルが E メールを開く際に最も頻繁に使用するドメインの詳細な分類が表示されます。 これにより、プロファイルの動作に関する貴重なインサイトが得られ、優先プラットフォームの理解に役立ちます。

+++ E メール — 最高の受信者ドメイン指標の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス数+エラー率]**：送信された E メールに対する、バウンスした E メールの割合。

+++

### 電子メール — 最適化 {#optimized-email}

![](assets/campaign_email_optimized.png)

>[!NOTE]
>
>**[!UICONTROL 最適化済みと最適化されていない]**&#x200B;ウィジェットと&#x200B;**[!UICONTROL 送信時間の最適化]**&#x200B;ウィジェットは、メールの「送信時間の最適化」オプションがアクティブ化されている場合にのみ使用できます。送信時間の最適化について詳しくは、[このページ](../building-journeys/journeys-message.md#send-time-optimization)を参照してください。

The **[!UICONTROL 最適化済みと最適化されていない]** および **[!UICONTROL 送信時間の最適化]** ウィジェットは、メッセージが最適化されているかどうかに関する主な情報の詳細を示します。

+++ 送信時間の最適化指標の詳細を説明します

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL クリック数]**：メールのコンテンツがクリックされた回数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

+++

### 電子メール — オファー {#email-offers}

![](assets/campaign_email_offers.png)

The **[!UICONTROL オファー統計]**, **[!UICONTROL オファーの統計の推移]** および **[!UICONTROL 詳細な統計を提供します]** ウィジェットは、オファーの成功と、ターゲットオーディエンスに与える影響を測定します。

+++ 電子メール — オファー指標の詳細を説明します

* **[!UICONTROL 送信されたオファー]**：オファーの送信の総数。

* **[!UICONTROL オファーインプレッション]**：オファーが電子メールで開かれた回数。

* **[!UICONTROL オファークリック数]**：オファーが E メールでクリックされた回数。

* **[!UICONTROL プレースメント名]**：オファーを表示するために使用するプレースメントの名前。プレースメントについて詳しくは、この[ページ](../offers/offer-library/creating-placements.md)を参照してください。

* **[!UICONTROL オファー名]**：配信に追加されたオファーの名前。プレースメントについて詳しくは、この[ページ](../offers/offer-library/creating-personalized-offers.md)を参照してください。

* **[!UICONTROL 送信されたオファー]**：オファーの送信の総数。

* **[!UICONTROL オファーのインプレッション率]**：送信されたオファーの数に対する、開封されたオファーの割合。

+++

## 「アプリ内」タブ {#inapp-global}

キャンペーンから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL アプリ内]** 「 」タブには、キャンペーンで送信されるアプリ内メッセージに関する主な情報の詳細が表示されます。

### アプリ内パフォーマンス {#in-app-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_performance"
>title="アプリ内パフォーマンス"
>abstract="アプリ内パフォーマンス KPI は、アプリ内メッセージに対する訪問者のエンゲージメントに関する重要なインサイトを提供します。"

![](assets/campaign_inapp_performance.png)

The **[!UICONTROL アプリ内パフォーマンス]** KPI は、訪問者のアプリ内メッセージに対する関与に関する基本的なインサイトを提供し、アプリ内キャンペーンの有効性と影響を評価するための重要な指標を提供します。

+++ アプリ内パフォーマンス指標の詳細を説明します

* **[!UICONTROL ユニークインプレッション数]**：アプリ内メッセージが配信されたユニークユーザーの数。

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション]**：アプリ内メッセージに対するエンゲージメントの合計数。 これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### タイプ別インタラクション数 {#interactions-type}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_interactions"
>title="タイプ別インタラクション数"
>abstract="タイプ別インタラクション数グラフと表は、クリック、破棄、インタラクションを追跡して、ユーザーがアプリ内メッセージに対してどのような操作をしたかを示します。"

![](assets/campaign_inapp_interactions.png)

The **[!UICONTROL タイプ別のインタラクション数]** のグラフと表に、プロファイルがアプリ内メッセージ、クリック数、破棄数などのトラッキングアクション、その他のエンゲージメントの形態とどのようにやり取りしたかに関する詳細な説明が表示されます。

### アプリ内の概要 {#in-app-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_inapp_summary"
>title="アプリ内の概要"
>abstract="アプリの内概要グラフは、指定した期間におけるアプリ内のインプレッション数とインタラクション数の進行状況を示します。"

![](assets/campaign_inapp_summary.png)

The **[!UICONTROL アプリ内概要]** グラフは、指定した期間におけるアプリ内インプレッション数とインタラクション数の進行状況を示し、アプリ内メッセージのパフォーマンスの包括的な概要を示します。

+++ アプリ内概要指標の詳細を説明します

* **[!UICONTROL ユニークインプレッション数]**：アプリ内メッセージが配信されたユニークユーザーの数。

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション]**：アプリ内メッセージに対するエンゲージメントの合計数。 これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

## 「プッシュ通知」タブ {#push-global}

キャンペーンから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL プッシュ通知]** 「 」タブには、キャンペーンで送信されるプッシュ通知に関する主な情報の詳細が表示されます。

### プッシュ通知 - 送信統計 {#push-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_sending_statistics"
>title="プッシュ通知 - 送信統計"
>abstract="プッシュ通知 - 送信統計テーブルは、ターゲットメッセージや配信メッセージなどのプッシュ通知に関する重要なデータを要約します。"

![](assets/campaign_push_sending.png)

The **[!UICONTROL プッシュ通知 — 送信統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージ数など、主要指標を含む、プッシュ通知に関する重要なデータの簡潔な概要を示しています。

+++ プッシュ通知 — 統計指標の送信の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しプッシュ通知の各実行の開始時間。1 つまたは複数の繰り返しプッシュ通知のみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：分析中に処理されたプッシュ通知の合計数。

* **[!UICONTROL 送信済み]**：プッシュ通知用の送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 配信率]**：正常に送信されたプッシュ通知の割合。

* **[!UICONTROL バウンス]**：プッシュ通知の合計数に関する、送信プロセスおよび自動返信処理の間に累積したエラーの合計。

* **[!UICONTROL バウンス率]**：送信済みのプッシュ通知に対する、バウンスしたプッシュ通知の割合。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知に対する、送信を妨げている間に発生したエラーの割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

### プッシュ通知 - トラッキング統計 {#push-tracking-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_tracking_statistics"
>title="プッシュ通知 - トラッキング統計"
>abstract="プッシュ通知 - トラッキング統計では、プッシュ通知のプロファイルアクティビティに関するデータを提供します。"

![](assets/campaign_push_tracking.png)

The **[!UICONTROL プッシュ通知 — トラッキング統計]** ウィジェットは、プッシュ通知に関連するプロファイルアクティビティの詳細なスナップショットを提供し、エンゲージメントとプッシュ通知の効果に関する重要なインサイトを提供します。

+++ プッシュ通知 — トラッキング統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しプッシュ通知の各実行の開始時間。1 つまたは複数の繰り返しプッシュ通知のみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

+++

### プッシュ通知 - 送信の概要 {#push-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_sending_summary"
>title="プッシュ通知 - 送信の概要"
>abstract="プッシュ通知 - 送信の概要グラフには、送信されたプッシュ通知に使用可能なデータが表示されます。"

![](assets/campaign_push_sending_summary.png)

The **[!UICONTROL プッシュ通知 — 送信の概要]** グラフは、プッシュ通知アクティビティの分析を表示する動的な表現を提供します。 このグラフでは、送信されたプッシュ通知の包括的な分類を示します。

+++ プッシュ通知 — 概要指標の送信の詳細を説明します

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス]**：送信されたプッシュ通知の合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

+++

### プッシュ通知 — 最適化 {#push-optimized}

>[!NOTE]
>
>**[!UICONTROL 最適化済みと最適化されていない]**&#x200B;ウィジェットと&#x200B;**[!UICONTROL 送信時間の最適化]**&#x200B;ウィジェットは、プッシュ通知の「送信時間の最適化」オプションがアクティブ化されている場合にのみ使用できます。送信時間の最適化について詳しくは、[このページ](../building-journeys/journeys-message.md#send-time-optimization)を参照してください。

The **[!UICONTROL 最適化済みと最適化されていない]** および **[!UICONTROL 送信時間の最適化]** ウィジェットは、メッセージが最適化されているかどうかに関する主な情報の詳細を示します。

+++ プッシュ通知 — 送信時間最適化指標の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス]**：送信されたプッシュ通知の合計数に関する、送信プロセス中のエラーと自動返信処理の合計。

+++

### プッシュ通知 - エラー理由 {#error-reasons-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_error_reasons"
>title="プッシュ通知 - エラー理由"
>abstract="エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/campaign_push_error_reasons.png)

The **[!UICONTROL エラーの理由]** 表とグラフは、プッシュ通知の送信プロセス中に発生した特定のエラーを識別し、進行中に発生した問題に関する詳細なインサイトを提供する機能を提供します。

### プッシュ通知 - 除外された理由 {#excluded-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_excluded_reasons"
>title="プッシュ通知 - 除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/campaign_push_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表には、ターゲットプロファイルから除外されたユーザープロファイルがプッシュ通知を受信できなかった様々な理由が表示されます。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### プッシュ通知 - プラットフォームごとの分類 {#breakdown-platform-push}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_push_breakdown_platform"
>title="プッシュ通知 - プラットフォームごとの分類"
>abstract="プラットフォームごとの分類のグラフとテーブルには、プロファイルのオペレーティングシステムに基づいたプッシュ通知の成功の分類が表示されます。"

![](assets/campaign_push_breakdown.png)

The **[!UICONTROL プッシュ通知 — プラットフォーム別の分類]** グラフと表は、プッシュ通知の成功の詳細な分析を提供し、プロファイルのオペレーティングシステムに基づいたインサイトを提供します。 この分類により、様々なプラットフォームでのプッシュ通知のパフォーマンスを把握できます。

+++ プッシュ通知の詳細を説明します — プラットフォーム指標による分類

* **[!UICONTROL ターゲット]**：分析中に処理されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス]**：送信されたプッシュ通知の合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

## 「SMS」タブ {#sms-global}

キャンペーンから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL SMS]** 「 」タブには、キャンペーンで送信される SMS メッセージに関する主な情報の詳細が表示されます。

### SMS - 送信統計 {#sms-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_sending_statistics"
>title="SMS - 送信統計"
>abstract="SMS - 送信統計テーブルは、ターゲットメッセージや配信メッセージなど、SMS メッセージに関する重要なデータを要約します。"

![](assets/campaign_sms_sending.png)

The **[!UICONTROL SMS — 送信統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージの数などの主要指標を含む、SMS メッセージに関する重要なデータの簡潔な概要を示しています。

+++ SMS — 送信統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返し SMS メッセージの各実行の開始時間。1 つまたは複数の繰り返し SMS メッセージのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：ターゲットプロファイルとして適合するユーザープロファイルの数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：SMS メッセージ用の送信の合計数。

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する、送信プロセス中と自動返信処理中に累積したエラーの合計。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

+++

### SMS — トラッキング統計 {#sms-tracking-statistics}

![](assets/campaign_sms_tracking.png)

The **[!UICONTROL SMS — トラッキング統計]** ウィジェットは、訪問者の URL とのエンゲージメントに関する主要情報の詳細な概要を提供し、SMS メッセージの効果に関するインサイトを提供します。

+++ SMS — トラッキング統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返し送信される SMS の実行のたびの開始時間。 1 つまたは複数の繰り返し送信 SMS のみをターゲットにするには、 **[!UICONTROL 実行時間]** 」ドロップダウンリストから選択できます。

* **[!UICONTROL クリック数]**:SMS メッセージでコンテンツがクリックされた回数。

+++

### SMS - 日別パフォーマンス {#sms-perfomance-date}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_performance"
>title="SMS - 日別パフォーマンス"
>abstract="SMS - 日別パフォーマンスウィジェットには、メッセージに関する主な情報がグラフィックで表示されます。"

![](assets/campaign_sms_performance.png)

The **[!UICONTROL 日付別の SMS パフォーマンス]** ウィジェットは、メッセージに関する主要情報の詳細な概要をグラフで示し、特定の期間におけるパフォーマンスの傾向に関するインサイトを提供します。

+++ SMS — 日付指標別のパフォーマンスの詳細を説明します

* **[!UICONTROL 送信済み]**：SMS メッセージ用の送信の合計数。

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する、送信プロセス中と自動返信処理中に累積したエラーの合計。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

+++

### SMS - エラー理由 {#sms-error}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_error_reasons"
>title="SMS - エラー理由"
>abstract="SMS - エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/campaign_sms_error_reasons.png)

The **[!UICONTROL エラーの理由]** グラフと表を使用すると、SMS メッセージの送信プロセス中に発生した特定のエラーを特定し、発生した問題を完全に分析できます。

### SMS - 除外された理由 {#sms-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_excluded_reasons"
>title="SMS - 除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/campaign_sms_excluded.png)

The **[!UICONTROL 理由を除外]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、SMS メッセージを受信できなくなった様々な要因を視覚的に示しています。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### SMS - バウンス理由 {#sms-bounces-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_bounces_reasons"
>title="SMS - バウンス理由"
>abstract="バウンス理由のグラフとテーブルには、バウンスされたメッセージに関連して使用可能なデータが含まれます。"

The **[!UICONTROL バウンス理由]** グラフと表は、バウンスした SMS メッセージに関するデータの包括的な概要を示し、SMS メッセージのバウンスインスタンスの背後にある特定の理由に関する貴重なインサイトを提供します。

### SMS - リンク別のクリック数 {#sms-clicks-links}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_sms_clicks_links"
>title="SMS - リンク別のクリック数"
>abstract="SMS - リンク別のクリック数ウィジェットは、メッセージ内の URL に対する訪問者のエンゲージメントに関する重要なインサイトを提供します。"

![](assets/campaign_sms_clicks.png)

The **[!UICONTROL SMS — リンク別のクリック数]** ウィジェットは、訪問者のメッセージに含まれる URL とのエンゲージメントに関する基本的なインサイトを提供し、最もインタラクションを引き付けるリンクに関する貴重な情報を提供します。

## 「Web」タブ {#web-tab}

キャンペーンの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL Web]**」タブには、web ページに関連する主な情報の詳細が表示されます。

### Web パフォーマンス {#web-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_performance"
>title="Web パフォーマンス"
>abstract="Web パフォーマンス KPI では、web エクスペリエンスに対する訪問者のエンゲージメントに関する包括的な情報を提供します。"

![](assets/campaign_web_performance.png)

The **[!UICONTROL Web パフォーマンス]** KPI は、インプレッション数やインタラクション数などの主要指標を含む、訪問者の Web ページとのエンゲージメントに関する包括的なインサイトを提供します。

+++ Web パフォーマンス指標の詳細を説明します

* **[!UICONTROL ユニークインプレッション数]**：web エクスペリエンスが配信されたユニークユーザーの数。

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション数]**：web ページにおけるエンゲージメントの割合。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### Web の概要 {#web-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_summary"
>title="Web の概要"
>abstract="Web の概要グラフは、指定した期間におけるインプレッション数、ユニークインプレッション数、インタラクション数などの web エクスペリエンスの進行状況を示します。"

![](assets/campaign_web_summary.png)

**[!UICONTROL Web の概要]**&#x200B;グラフでは、該当する期間の web エクスペリエンス（インプレッション数、ユニークインプレッション数、インタラクション数）の変化を確認できます。

+++ Web サマリ指標の詳細を説明します

* **[!UICONTROL ユニークインプレッション数]**：web エクスペリエンスが配信されたユニークユーザーの数。

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション]**:Web ページに対するアクションの合計数。 これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### 要素別インタラクション数 {#web-interactions}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_web_interactions"
>title="要素別インタラクション数"
>abstract="要素別インタラクション数テーブルには、web ページ上の様々な要素に対する訪問者のエンゲージメントに関する主な情報が表示されます。"

![](assets/campaign_web_interactions.png)

The **[!UICONTROL 要素別インタラクション数]** 次の表は、訪問者の Web ページ上の様々な要素に対する関与に関する包括的な情報を示し、ユーザーのインタラクションと環境設定に関する有益なインサイトを提供します。

+++ 要素指標別インタラクションの詳細を説明します

* **[!UICONTROL インタラクション]**:Web ページに対するアクションの合計数。 これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

* **[!UICONTROL インタラクション数]**：web ページにおけるエンゲージメントの割合。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

## 「ダイレクトメール」タブ {#direct-mail-global}

キャンペーンから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL ダイレクトメール]** 「 」タブには、ダイレクトメールメッセージに関する主な情報の詳細が表示されます。

### ダイレクトメール - 送信統計 {#direct-mail-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_sending_statistics"
>title="ダイレクトメール - 送信統計"
>abstract="ダイレクトメール - 送信統計テーブルは、ターゲットメッセージや配信メッセージなど、ダイレクトメールメッセージに関する重要なデータを要約します。"

![](assets/campaign_direct_sending.png)

The **[!UICONTROL ダイレクトメール — 送信統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージの数などの主要指標を含む、ダイレクトメールメッセージに関する重要なデータの簡潔な概要を示しています。

+++ ダイレクトメール — 送信統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しダイレクトメールの各実行の開始時間。1 つまたは複数の繰り返しダイレクトメールのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：ダイレクトメールメッセージのターゲットプロファイルとして認定されるユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：ダイレクトメールメッセージの送信の合計数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外され、ダイレクトメールメッセージを受信しなかったユーザープロファイルの数。

+++

### ダイレクトメール - エラー理由 {#direct-mail-error}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_error_reasons"
>title="ダイレクトメール - エラー理由"
>abstract="ダイレクトメール - エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/direct-mail-report_1.png)

The **[!UICONTROL ダイレクトメール — エラー理由]** グラフと表は、ダイレクトメールメッセージの送信プロセス中に発生した特定のエラーを識別する手段を提供し、発生した問題を詳細に分析できます。

### ダイレクトメール - 除外された理由 {#direct-mail-excluded}

>[!CONTEXTUALHELP]
>id="ajo_campaign_global_direct_excluded_reasons"
>title="ダイレクトメール - 除外された理由"
>abstract="このダイレクトメール - 除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットプロファイルから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/campaign_direct_excluded.png)

The **[!UICONTROL ダイレクトメール — 除外された理由]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、ダイレクトメールメッセージを受信できなくなった様々な要因を視覚的に示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

## その他のリソース

* [キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [API トリガーキャンペーンの作成](../campaigns/api-triggered-campaigns.md)
* [キャンペーンの変更または停止](../campaigns/modify-stop-campaign.md)
* [キャンペーンのライブレポート](campaign-live-report.md)
