---
solution: Journey Optimizer
product: journey optimizer
title: キャンペーンのライブレポート
description: キャンペーンのライブレポートからデータを使用する方法を学ぶ
feature: Reporting, Campaigns
topic: Content Management
role: User
level: Intermediate
exl-id: 925494b6-e08a-4bd3-8a2f-96a5d9cbc387
source-git-commit: d26dbebaf36241d0e91c36c95f83ce6cf712ecee
workflow-type: tm+mt
source-wordcount: '3484'
ht-degree: 62%

---

# キャンペーンのライブレポート {#campaign-live-report}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_report"
>title="キャンペーンのライブレポート"
>abstract="キャンペーンのライブレポートでは、過去 24 時間のみのキャンペーンの効果とパフォーマンスをリアルタイムで測定および視覚化できます。レポートは、キャンペーンの成功とエラーの詳細を示す様々なウィジェットに分かれています。各レポートダッシュボードは、ウィジェットのサイズ変更や削除を行うことで変更できます。"

「過去 24 時間」タブからアクセスできるライブレポートには、過去 24 時間以内に発生したイベントが、イベント発生から最小 2 分の時間間隔で表示されます。これに対し、グローバルレポートでは、少なくとも 2 時間前に発生したイベントに焦点を当て、選択した期間のイベントが表示されます。

キャンペーンのライブレポートは、「**[!UICONTROL ライブ表示]**」ボタンを使用して、キャンペーンから直接アクセスできます。

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;ページには次のタブが表示されます。

* [キャンペーン](#campaign-live)
* [メール](#email-live)
* [アプリ内](#inapp-live)
* [プッシュ](#push-live)
* [SMS](#sms-live)
* [Web](#web-tab)
* [ダイレクトメール](#direct-mail-tab)

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;は、キャンペーンの成功とエラーの詳細を示す様々なウィジェットに分かれています。必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。詳しくは、この[節](../reports/live-report.md#modify-dashboard)を参照してください。

Adobe Journey Optimizer で使用可能なすべての指標の詳細なリストについては、[こちらのページ](live-report.md#list-of-components-live)を参照してください。

## 「キャンペーン」タブ {#campaign-live}

### 配信 {#delivery-live}

![](assets/campaign_live_statistics.png)

The **[!UICONTROL キャンペーンの統計]** KPI は、包括的なダッシュボードとして機能し、キャンペーンに関連する過去 24 時間の主要指標の詳細な分類を提供します。 これには、配信されたプロファイル数やアクション数など、キャンペーンのパフォーマンスとエンゲージメントを完全に把握できる重要な情報が含まれます。

+++ Campaign の統計指標の詳細を説明します

* **[!UICONTROL 対象ユーザ]**：ターゲットプロファイルの数。

* **[!UICONTROL 配信されたアクション]**：アクションが配信されたユニーク回数の合計。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

<!--
### Experimentation tab (#experimentation-live)

From your Campaign **[!UICONTROL Live report]**, the **[!UICONTROL Experimentation]** tab details the main information relative to how each variant is performing and if there is was winner during the test.
-->

## 「メール」タブ {#email-live}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL メール]**」タブには、キャンペーンで送信されるメール配信に関連する主な情報の詳細が表示されます。

### メール - 送信パフォーマンス {#email-sending-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_sending_statistics"
>title="メール - 送信統計"
>abstract="メール - 送信統計グラフは、過去 24 時間のターゲットや配信など、メールに関する重要なデータを要約します。"

![](assets/campaign_email_live_sending.png)

The **[!UICONTROL 電子メール — 送信パフォーマンス]** では、過去 24 時間以内に送信された e メールに関連するデータの完全な概要を提供します。 配信済みとバウンス数などの重要な指標に関するインサイトを提供し、E メール送信プロセスを詳細に調べることができます。

+++ 電子メール送信パフォーマンス指標の詳細を説明します

* **[!UICONTROL 配信済み]**：正常に送信された電子メールの数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。
+++

### メール - 統計

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_statistics"
>title="メール - 統計"
>abstract="メール - 統計テーブルには、過去 24 時間のメールのプロファイルアクティビティに関するデータが表示されます。"

![](assets/campaign_email_live_statistics.png)

The **[!UICONTROL 電子メール別指標の送信]** 表には、過去 24 時間のデータの包括的な概要が示されています。 ターゲットオーディエンスのサイズや配信に成功した E メールの数など、重要な指標の概要を説明します。 これにより、E メールキャンペーンの効果とリーチに関する貴重なインサイトが得られます。

+++ 電子メール — 統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しメールの各実行の開始時間。1 つまたは複数の繰り返しメールのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：送信プロセス中に処理されたメッセージの合計数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：正常に送信されたメッセージ数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL クリック数]**：コンテンツがクリックされた回数。

* **[!UICONTROL 購読解除]**：購読解除リンクのクリック数。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。
+++

### 電子メール — バウンスのカテゴリと理由 {#bounce-categories}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_bounce_categories"
>title="メール - バウンスカテゴリ"
>abstract="メール - バウンスカテゴリのグラフとテーブルには、過去 24 時間の一時的なエラーと永続的なエラーの両方に関するデータが表示されます。"

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_bounce_reasons"
>title="メール - バウンス理由"
>abstract="メール - バウンス理由のグラフとテーブルには、過去 24 時間のバウンスメッセージに関連して使用可能なデータが含まれています。"

![](assets/campaign_live_email_bounce_categories.png)

The **[!UICONTROL バウンスの理由]** および **[!UICONTROL バウンスのカテゴリ]** ウィジェットは、バウンスメッセージに関連する直近 24 時間の使用可能なデータをコンパイルし、電子メールバウンスの背後にある特定の理由とカテゴリに関する詳細なインサイトを提供します。

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

+++ E メール — バウンスカテゴリと理由指標の詳細を説明します

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

+++

### メール - 日別のパフォーマンス {#email-performance-date}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_performance_bydate"
>title="メール - 日別のパフォーマンス"
>abstract="「 E メール — 日別パフォーマンス」グラフは、送信済み E メールに関する過去 24 時間の包括的なデータを表示し、配信済み E メールやバウンスなどの主要指標に関するインサイトを提供し、E メール送信プロセスを詳細に分析できます。"

![](assets/campaign_email_live_performance.png)

The **[!UICONTROL メール — 日別のパフォーマンス]** ウィジェットは、メッセージに関する主要情報の詳細な概要をグラフで示し、過去 24 時間のパフォーマンスの傾向に関するインサイトを提供します。

+++ 電子メール — 日付および理由指標別のパフォーマンスの詳細を説明します

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：正常に送信されたメッセージ数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL クリック数]**：コンテンツがクリックされた回数。

* **[!UICONTROL 購読解除]** : 購読解除リンクのクリック数。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

+++

### エラーの理由 {#email-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_error_reasons"
>title="メール - エラー理由"
>abstract="メール - エラー理由のグラフとテーブルを使用すると、過去 24 時間の送信プロセス中に発生した特定のエラーを特定できます。"

![](assets/campaign_email_live_error.png)

The **[!UICONTROL エラーの理由]** グラフと表では、過去 24 時間の送信プロセス中に発生した特定のエラーに関するインサイトを得ることができます。 この情報は、エラーの性質と頻度を理解するのに役立ちます。

### 除外された理由 {#email-exclude-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_excluded_reasons"
>title="メール - 除外された理由"
>abstract="「除外された理由」グラフとテーブルには、対象のオーディエンスから除外され、過去 24 時間にメッセージを受信しなかった、ユーザープロファイルにつながった様々な要因が表示されます。"

![](assets/campaign_email_live_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表は、過去 24 時間のターゲットオーディエンスからユーザープロファイルが除外された様々な要因に関する、包括的な視点を提供します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### メール - 最適な受信者ドメイン {#email-best-recipient}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_email_best_recipient"
>title="メール - 最適な受信者ドメイン"
>abstract="メール - 最適な受信者ドメインのグラフとテーブルには、受信者がメールを開くのに最も頻繁に使用するドメインの詳細な分類が表示され、過去 24 時間の受信者の行動に関する有益なインサイトが提供されます。"

![](assets/campaign_email_live_recipient.png)

The **[!UICONTROL E メール — 最適な受信者ドメイン]** グラフと表は、過去 24 時間にプロファイルが e メールを開封する際に最も頻繁に使用したドメインの詳細な分類を提供します。 これにより、プロファイルの動作に関する貴重なインサイトが得られ、優先プラットフォームの理解に役立ちます。

### 電子メール — オファー {#email-offers}

>[!NOTE]
>
>オファーのウィジェットと指標は、決定がメールに挿入された場合にのみ使用できます。 意思決定管理について詳しくは、[このページ](../offers/get-started/starting-offer-decisioning.md)を参照してください。

The **[!UICONTROL オファー統計]** および **[!UICONTROL オファーの統計の推移]** ウィジェットは、オファーの成功と、ターゲットオーディエンスに与える影響を測定します。 KPI を使用して、メッセージに関する主な情報の詳細を示します。

+++ 電子メール — オファー指標の詳細を説明します

* **[!UICONTROL 送信されたオファー]**：オファーの送信の総数。

* **[!UICONTROL オファーインプレッション]**：オファーが電子メールで開かれた回数。

* **[!UICONTROL オファークリック数]**：オファーが E メールでクリックされた回数。

+++

## 「アプリ内」タブ {#inapp-live}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL アプリ内]**」タブには、キャンペーンで送信されたアプリ内配信メッセージに関連する主な情報の詳細が表示されます。

### アプリ内パフォーマンス {#inapp-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_performance"
>title="アプリ内パフォーマンス"
>abstract="アプリ内パフォーマンス KPI は、過去 24 時間の訪問者のアプリ内メッセージに対するエンゲージメントに関する重要なインサイトを提供します。"

The **[!UICONTROL アプリ内パフォーマンス]** KPI は、過去 24 時間のプロファイルのアプリ内メッセージに対する関与に関する重要なインサイトを提供し、アプリ内キャンペーンの有効性と影響を評価するための重要な指標を提供します。

+++ アプリ内パフォーマンス指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに送信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション数]**：アプリ内メッセージに対するエンゲージメントの合計数。これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### アプリ内の概要 {#inapp-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_summary"
>title="アプリ内の概要"
>abstract="アプリ内概要グラフは、過去 24 時間のアプリ内インプレッション数およびインタラクション数の進行状況を示します。"

The **[!UICONTROL アプリ内概要]** グラフは、過去 24 時間のアプリ内インプレッション数とインタラクション数の進行状況を示し、アプリ内メッセージのパフォーマンスの包括的な概要を示します。

+++ アプリ内概要指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション]**：アプリ内メッセージに対するエンゲージメントの合計数。 これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### タイプ別インタラクション数 {#inapp-interactions}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_inapp_interactions"
>title="タイプ別インタラクション数"
>abstract="タイプ別インタラクション数のグラフとテーブルは、過去 24 時間のクリック、破棄、インタラクションを追跡して、ユーザーがアプリ内メッセージに対して行った操作の詳細を示します。"

The **[!UICONTROL タイプ別のインタラクション数]** のグラフと表に、過去 24 時間のアプリ内メッセージとのプロファイルのやり取り、クリック数、破棄数、その他のエンゲージメント形式などの追跡アクションについての詳細な説明が表示されます。

## 「プッシュ通知」タブ {#push-live}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL プッシュ通知]**」タブには、キャンペーンで送信されるプッシュ配信に関連する主な情報の詳細が表示されます。

### プッシュ通知 - 送信パフォーマンス {#push-sending-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_sending_performance"
>title="プッシュ通知 - 送信パフォーマンス"
>abstract="プッシュ通知送信パフォーマンスのグラフは、過去 24 時間のエラーメッセージや配信済みメッセージなど、プッシュ通知に関する重要なデータを要約します。"

![](assets/campain_push_live_sending_performance.png)

The **[!UICONTROL プッシュ通知の送信パフォーマンス]** グラフでは、過去 24 時間以内に送信されたプッシュ通知に関連するデータの詳細な概要を提供します。 配信済みとバウンスなどの重要な指標に関するインサイトを提供し、プッシュ通知の送信プロセスを詳細に調べることができます。

+++ プッシュ通知 — パフォーマンス指標の送信の詳細を説明します

* **[!UICONTROL 配信済み]**：正常に送信されたメッセージ数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

+++

### プッシュ通知 - 統計 {#push-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_statistics"
>title="プッシュ通知 - 統計"
>abstract="プッシュ統計テーブルには、過去 24 時間のプッシュ通知の受信者アクティビティに関するデータが表示されます。"

![](assets/campaign_push_live_statistics.png)

The **[!UICONTROL プッシュ通知 — 統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージ数など、主要指標を含め、過去 24 時間以内のプッシュ通知に関連する重要なデータの簡潔な概要を示しています。

+++ プッシュ通知 — 統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しプッシュ通知の各実行の開始時間。1 つまたは複数の繰り返しプッシュ通知のみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：送信プロセス中に処理されたメッセージの合計数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：正常に送信されたメッセージ数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

+++

### プッシュ通知 - 送信の概要 {#push-sending-summary}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_sending_summary"
>title="プッシュ通知 - 送信の概要"
>abstract="プッシュ通知送信の概要グラフには、過去 24 時間に送信されたプッシュ通知で使用可能なデータが表示されます。"

The **[!UICONTROL プッシュ通知 — 統計]** グラフは、過去 24 時間のプッシュ通知アクティビティの分析を表示する、動的な表現を提供します。 このグラフでは、送信されたプッシュ通知の包括的な分類を示します。

+++ プッシュ通知 — 概要指標の送信の詳細を説明します

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

+++

### プッシュ通知 - 除外された理由 {#push-excluded}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_excluded_reasons"
>title="プッシュ通知 - 除外された理由"
>abstract="「除外された理由」グラフとテーブルには、対象のオーディエンスから除外され、過去 24 時間にメッセージを受信しなかった、ユーザープロファイルにつながった様々な要因が表示されます。"

The **[!UICONTROL 除外された理由]** グラフと表には、過去 24 時間にターゲットプロファイルから除外されたユーザープロファイルがプッシュ通知を受信できなかった様々な理由が表示されます。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### プッシュ通知 - エラー理由 {#push-error}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_error_reasons"
>title="プッシュ通知 - エラー理由"
>abstract="エラー理由のグラフとテーブルを使用して、過去 24 時間の送信プロセス中に発生した特定のエラーを特定できます。"

The **[!UICONTROL エラーの理由]** 表とグラフは、過去 24 時間以内にプッシュ通知の送信プロセス中に発生した特定のエラーを識別し、進行中に発生した問題に関する詳細なインサイトを提供する機能を提供します。

### プッシュ通知 - プラットフォームごとの分類 {#push-breakdown-platform}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_push_breakdown_platform"
>title="プッシュ通知 - プラットフォームごとの分類"
>abstract="プラットフォームごとの分類のグラフとテーブルには、過去 24 時間のプッシュ通知の成功の分類が、受信者のオペレーティングシステムに基づいて表示されます。"

The **[!UICONTROL プッシュ通知 — プラットフォーム別の分類]** グラフと表は、過去 24 時間のプッシュ通知の成功の詳細な分析を示し、プロファイルのオペレーティングシステムに基づいたインサイトを提供します。 この分類により、様々なプラットフォームでのプッシュ通知のパフォーマンスを把握できます。

+++ プッシュ通知の詳細を説明します — プラットフォーム指標による分類

* **[!UICONTROL ターゲット]**：分析中に処理されたメッセージの合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

## 「SMS」タブ {#sms-live}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL SMS]**」タブには、キャンペーンで送信される SMS メッセージに関連する主な情報の詳細が表示されます。

### SMS - 統計 {#sms-statistics}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_statistics"
>title="SMS - 統計"
>abstract="SMS 送信統計のテーブルは、過去 24 時間のターゲットメッセージや配信済みメッセージなど、SMS メッセージに関する重要なデータを要約します。"

![](assets/campaign_live_sms_statistics.png)

The **[!UICONTROL SMS — 統計]** この表は、ターゲットメッセージの数や正常に配信されたメッセージの数などの主要指標を含む、過去 24 時間以内の SMS メッセージに関連する重要なデータの簡潔な概要を示します。

+++ SMS — 統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返し SMS メッセージの各実行の開始時間。1 つまたは複数の繰り返し SMS メッセージのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：ターゲットプロファイルとして適合するユーザープロファイルの数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

* **[!UICONTROL クリック数]**：URL 訪問の合計数。

+++

### SMS - 日別パフォーマンス {#sms-perfomance-date}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_performance"
>title="SMS - 日別パフォーマンス"
>abstract="日付別 SMS パフォーマンスのウィジェットには、過去 24 時間のメッセージに関する重要な情報がグラフで表示されます。"

![](assets/campaign_live_sms_performance_date.png)

The **[!UICONTROL 日付別の SMS パフォーマンス]** ウィジェットは、メッセージに関する主要情報の詳細な概要をグラフで示し、過去 24 時間のパフォーマンスの傾向に関するインサイトを提供します。

+++ SMS — 日付指標別のパフォーマンスの詳細を説明します

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL バウンス数]**：送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

+++

### SMS — エラー理由 {#sms-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_error_reasons"
>title="SMS - エラー理由"
>abstract="SMS - エラー理由のグラフとテーブルを使用すると、過去 24 時間の送信プロセス中に発生した特定のエラーを識別できます。"

The **[!UICONTROL 除外された理由]** グラフと表を使用すると、過去 24 時間以内に SMS メッセージの送信プロセス中に発生した特定のエラーを特定でき、発生した問題を完全に分析できます。

### SMS — 除外された理由 {#sms-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_excluded_reasons"
>title="SMS - 除外された理由"
>abstract="「除外された理由」グラフとテーブルには、対象のオーディエンスから除外され、過去 24 時間にメッセージを受信しなかった、ユーザープロファイルにつながった様々な要因が表示されます。"

![](assets/campaign_live_sms_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、過去 24 時間にユーザーが SMS メッセージを受信できなくなった様々な要因を視覚的に示しています。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### SMS - バウンス理由 {#sms-bounces-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_sms_bounces_reasons"
>title="SMS - バウンス理由"
>abstract="バウンス理由のグラフとテーブルには、バウンスメッセージに関連する過去 24 時間のデータが含まれています。"

The **[!UICONTROL バウンス理由]** グラフと表は、バウンスした SMS メッセージに関するデータの包括的な概要を示し、過去 24 時間に SMS メッセージがバウンスした特定の理由に関する貴重なインサイトを提供します。

## 「Web」タブ {#web-tab}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL Web]**」タブには、web ページに関連する主な情報の詳細が表示されます。

### Web パフォーマンス {#web-performance}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_performance"
>title="Web パフォーマンス"
>abstract="Web パフォーマンス KPI では、過去 24 時間の訪問者の web エクスペリエンスに対するエンゲージメントに関する包括的な情報を提供します。"

![](assets/campaign_live_web_performance.png)

The **[!UICONTROL Web パフォーマンス]** KPI は、インプレッション数やインタラクション数などの主要指標を含む、過去 24 時間の訪問者の Web ページに対するエンゲージメントに関する包括的なインサイトを提供します。

+++ Web パフォーマンス指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション数]**：Web ページに対するエンゲージメントの合計数。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### Web の概要 {#web-summary}

![](assets/campaign_live_web_summary.png)

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_summary"
>title="Web の概要"
>abstract="Web 概要グラフでは、過去 24 時間の web エクスペリエンス（インプレッション数、ユニークインプレッション数、インタラクション数）の変化を確認できます。"

The **[!UICONTROL Web サマリ]** グラフには、過去 24 時間の web エクスペリエンス（インプレッション数、個別インプレッション数およびインタラクション数）の推移が表示されます。

+++ Web サマリ指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション数]**：Web ページに対するエンゲージメントの合計数。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### 要素別インタラクション数 {#web-interactions}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_web_interactions"
>title="要素別インタラクション数"
>abstract="要素別インタラクション数のテーブルには、web ページ上の様々な要素に対する過去 24 時間の訪問者のエンゲージメントに関する重要な情報が表示されます。"

The **[!UICONTROL 要素別インタラクション数]** この表は、過去 24 時間の訪問者の Web ページ上の様々な要素に対する関与に関する包括的な情報を示し、ユーザーのインタラクションと環境設定に関する貴重なインサイトを提供します。

## 「ダイレクトメール」タブ {#direct-mail-tab}

キャンペーンの&#x200B;**[!UICONTROL ライブレポート]**&#x200B;の「**[!UICONTROL ダイレクトメール]**」タブには、ダイレクトメールに関連する主な情報の詳細が表示されます。

### ダイレクトメール - 送信統計 {#direct-mail-sending}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_sending_statistics"
>title="ダイレクトメール - 送信統計"
>abstract="ダイレクトメール送信統計テーブルは、ターゲットメッセージや配信済みメッセージなど、ダイレクトメールメッセージに関する過去 24 時間の重要なデータを要約します。"

![](assets/campaign_live_directmail_statistics.png)

The **[!UICONTROL ダイレクトメール — 送信統計]** この表は、ターゲットメッセージ数や過去 24 時間以内に正常に配信されたメッセージの数など、主要指標を含む、ダイレクトメールメッセージに関する重要なデータの簡潔な概要を示しています。

+++ ダイレクトメール — 送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：ターゲットプロファイルとして認定されるユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL エラー]**：配信中に発生してプロファイルに送信できない原因となったエラーの合計数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外され、ダイレクトメールを受信しなかったユーザープロファイルの数。

+++

### ダイレクトメール - エラー理由 {#direct-mail-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_error_reasons"
>title="ダイレクトメール - エラー理由"
>abstract="ダイレクトメール - エラー理由のグラフとテーブルを使用して、過去 24 時間に発生した特定のエラーを特定できます。"

![](assets/campaign_live_error_reasons.png)

The **[!UICONTROL ダイレクトメール — エラー理由]** グラフと表は、ダイレクトメールメッセージの送信プロセス中に発生した特定のエラーを識別する手段を提供し、過去 24 時間に発生した問題を詳細に分析できます。

### ダイレクトメール - 除外された理由 {#direct-mail-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_campaign_live_direct_excluded_reasons"
>title="ダイレクトメール - 除外された理由"
>abstract="ダイレクトメール除外理由のグラフとテーブルには、対象のオーディエンスから除外され、過去 24 時間にメッセージを受信しなかった、ユーザープロファイルにつながった様々な要因が表示されます。"

![](assets/campaign_live_directmail_excluded.png)

The **[!UICONTROL ダイレクトメール — 除外された理由]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、過去 24 時間にダイレクトメールメッセージが届かなくなった様々な要因を視覚的に示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

## その他のリソース

* [キャンペーンの基本を学ぶ](../campaigns/get-started-with-campaigns.md)
* [キャンペーンの作成](../campaigns/create-campaign.md)
* [API トリガーキャンペーンの作成](../campaigns/api-triggered-campaigns.md)
* [キャンペーンの変更または停止](../campaigns/modify-stop-campaign.md)
* [キャンペーンのグローバルレポート](campaign-global-report.md)
