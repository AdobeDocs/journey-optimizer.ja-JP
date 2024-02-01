---
solution: Journey Optimizer
product: journey optimizer
title: ジャーニーのグローバルレポート
description: ジャーニーのグローバルレポートのデータの利用方法を学ぶ
feature: Reporting, Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: e851646e-4cef-45e8-97c2-a8f4c9d2cc08
source-git-commit: fa704bd6c82a3068f163bb74542107b34f1815d1
workflow-type: tm+mt
source-wordcount: '3523'
ht-degree: 41%

---

# ジャーニーのグローバルレポート {#journey-global-report}

>[!CONTEXTUALHELP]
>id="ajo_journey_global_report"
>title="ジャーニーのグローバルレポート"
>abstract="ジャーニーのグローバルレポートを使用すると、選択した期間におけるジャーニーの効果を測定できます。レポートは、ジャーニーの成功とエラーの詳細を示す様々なウィジェットに分かれています。各レポートダッシュボードは、ウィジェットのサイズ変更や削除を行うことで変更できます。"

「全期間」タブからアクセスできるグローバルレポートには、少なくとも 2 時間前に発生したイベントと、選択した期間のイベントが表示されます。これに対し、ライブレポートには、過去 24 時間以内に発生したイベントが焦点となり、イベント発生から最小 2 分の時間間隔で表示されます。

「**[!UICONTROL グローバルレポート]**」ボタンで、ジャーニーのグローバルレポートにジャーニーから直接アクセスします。

![](assets/report_journey.png)

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;ページが表示され、次のタブが表示されます。

* [ジャーニー](#journey-global)
* [メール](#email-global)
* [プッシュ](#push-global)
* [SMS](#sms-global)
* [アプリ内](#in-app-global)

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;は、ジャーニーの成功とエラーについて説明する様々なウィジェットに分かれています。必要に応じて、各ウィジェットのサイズを変更したり削除したりできます。詳しくは、この[節](global-report.md#modify-dashboard)を参照してください。

Adobe Journey Optimizer で使用可能なすべての指標の詳細なリストについては、[このページ](global-report.md#list-of-components-global)を参照してください。

## 「ジャーニー」タブ {#journey-global}

ジャーニーの&#x200B;**[!UICONTROL グローバルレポート]**&#x200B;の「**[!UICONTROL ジャーニー]**」タブには、ジャーニーに関する重要なトラッキングデータが明確に表示されます。

### ジャーニー効果 {#journey-perfomance}

>[!CONTEXTUALHELP]
>id="ajo_journey_performance"
>title="ジャーニー効果"
>abstract="XX"

![](assets/journey_performance.png)

The **[!UICONTROL ジャーニー効果]** ウィジェットを使用すると、ジャーニー内を移動する際に、ターゲットプロファイルの軌道を視覚的に追跡できます。

### ジャーニー統計 {#journey-statistics}

>[!CONTEXTUALHELP]
>id="ajo_journey_statistics"
>title="ジャーニー統計"
>abstract="XX"

![](assets/journey_statistics.png)

The **[!UICONTROL ジャーニー統計]** 主要業績評価指標 (KPI) は包括的なダッシュボードとして機能し、ジャーニーに関連する重要な指標の分析を提供します。 これには、入力されたプロファイルの数や失敗した個々のジャーニーのインスタンスなどの詳細が含まれ、ジャーニーの効果とエンゲージメントレベルを包括的に把握できます。

+++ ジャーニー統計指標の詳細

* **[!UICONTROL エントリしたプロファイル]**：ジャーニーのエントリイベントに到達した個人の合計数。

* **[!UICONTROL 退出したプロファイル]**：ジャーニーから退出した個人の合計数。

* **[!UICONTROL 失敗した個人のジャーニー]**：正常に実行されなかった個人のジャーニーの合計数。

+++

### アクションの効果 {#action-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_action_performance"
>title="アクションの効果"
>abstract="XX"

![](assets/journey_action_performance.png)

The **[!UICONTROL アクションの効果]** ウィジェットは、 **[!UICONTROL アクション]** がトリガーされました。

### 上位のアクション {#top-actions}

>[!CONTEXTUALHELP]
>id="ajo_journey_top_actions"
>title="上位のアクション"
>abstract="XX"

![](assets/journey_top_actions.png)

The **[!UICONTROL 上位のアクション]** テーブルは、 **[!UICONTROL アクション]**. 各アクションの頻度とパフォーマンスに関する簡潔なインサイトを提供します。

+++ 上位のアクション指標の詳細を説明します

* **[!UICONTROL 正常に実行されたアクション]**：ジャーニーに対して正常に実行された&#x200B;**[!UICONTROL アクション]**&#x200B;の合計数。

* **[!UICONTROL アクションのエラー]**：**[!UICONTROL アクション]**&#x200B;で発生したエラーの合計数。

+++

### アクションのエラー理由 {#action-error}

>[!CONTEXTUALHELP]
>id="ajo_journey_actions_error_reasons"
>title="アクションのエラー理由"
>abstract="XX"

![](assets/journey_action_error.png)

The **[!UICONTROL アクションエラーの理由]**  表とグラフには、 **[!UICONTROL アクション]**.

### 接触チャネル別のイベント {#events-origin}

>[!CONTEXTUALHELP]
>id="ajo_journey_events_origin"
>title="接触チャネル別のイベント"
>abstract="XX"

![](assets/journey_events_origin.png)

The **[!UICONTROL 接触チャネル別のイベント]** 表とグラフは、 **[!UICONTROL イベント]**. これらの視覚表現を通じて、 **[!UICONTROL イベント]** は効果的に受け取られ、ジャーニー内の個々のイベントのパフォーマンスと影響に関する貴重なインサイトを提供します。

### イベントが受信したイベント {#events-received}

>[!CONTEXTUALHELP]
>id="ajo_journey_events_received"
>title="イベントが受信したイベント"
>abstract="XX"

![](assets/journey_event_received.png)

The **[!UICONTROL イベントが受信したイベント]** グラフを使用すると、特定の **[!UICONTROL イベント]** ジャーニー内では効果的に実行され、個々のイベントのパフォーマンスと成功率に関する貴重なインサイトを提供します。

### 上位のイベント {#top-events}

>[!CONTEXTUALHELP]
>id="ajo_journey_top_events"
>title="上位のイベント"
>abstract="XX"

![](assets/journey_top_events.png)

The **[!UICONTROL 上位のイベント]** テーブルは、 **[!UICONTROL イベント]**. 各の頻度とパフォーマンスに関する簡潔なインサイトを提供します **[!UICONTROL イベント]**.

### 同意ポリシー {#consent-policies}

>[!CONTEXTUALHELP]
>id="ajo_journey_consent_policies"
>title="同意ポリシー"
>abstract="XX"

![](assets/journey_consent.png)

The **[!UICONTROL 同意ポリシー]** 表およびグラフは、カスタムアクション内の各ポリシーから除外されたプロファイル数を表示します。 これにより、各同意ポリシーがプロファイルの除外に与える影響を明確に把握できます。

カスタムアクションについて詳しくは、[詳細ドキュメント](../action/about-custom-action-configuration.md)を参照してください。

これらのウィジェットをジャーニーレポートに表示するには、ダッシュボードをリセットする必要があります。これを行うには、**[!UICONTROL 変更]**&#x200B;をクリックし、その後レポートの上部にある&#x200B;**[!UICONTROL リセット]**&#x200B;をクリックします。

## 「メール」タブ {#email-global}

ジャーニーから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL 電子メール]** 「 」タブには、ジャーニーで送信される e メールに関する主な情報の詳細が表示されます。

### 電子メール — 送信統計 {#email-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_sending_statistics"
>title="電子メール — 送信統計"
>abstract="XX"

![](assets/journey_email_statistics.png)

The **[!UICONTROL E メール送信統計]** 表は、ジャーニー内の E メールに関する重要なデータの包括的な概要を示しています。 ターゲットオーディエンスのサイズや正常に配信された電子メールの数など、主要な指標の詳細を説明し、電子メールやジャーニーの効果とリーチに関する有益なインサイトを提供します。

+++ 電子メール送信統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しジャーニーの場合の各ジャーニー実行の開始時間。1 つまたは複数の繰り返しのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：任意のアクション（メールや SMS の送信など）でターゲットとするプロファイルの数。

* **[!UICONTROL 送信済み]**：ジャーニーで送信された電子メールの合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス]**：送信済み E メールの合計数に関して、送信プロセスと自動返信処理の間に累積したエラーの合計。

* **[!UICONTROL バウンス率]**：送信メールに対するバウンスメールの割合。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたメールに対して、送信プロセス中にエラーが発生して送信できなかったメールの割合。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

### メール - トラッキング統計 {#email-tracking}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_tracking_statistics"
>title="メール - トラッキング統計"
>abstract="XX"

![](assets/journey_email_tracking.png)

The **[!UICONTROL E メール — トラッキング統計]** テーブルには、ジャーニーに含まれる E メールに関連するプロファイルアクティビティの詳細なアカウントが表示されます。 これには、開封数、クリック数、その他の関連するエンゲージメント指標など、プロファイルが E メールコンテンツとどのようにやり取りするかを包括的に示す指標が含まれます。

+++ 電子メール — トラッキング統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：ジャーニーでの繰り返しメールの各実行の開始時間。1 つまたは複数の繰り返しメールのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL 開封数]**：ジャーニーで E メールが開封された回数。

* **[!UICONTROL ユニーク開封数]**：開封されたメールのパーセンテージ。

* **[!UICONTROL ユニーク開封率]**：配信されたメール数に対して、開封されたメールの合計数。

* **[!UICONTROL クリック数]**:E メールでコンテンツがクリックされた回数。

* **[!UICONTROL ユニーククリック数]**:E メールのコンテンツをクリックした受信者の数。

* **[!UICONTROL クリックスルー率]**：ジャーニーに対して何らかのアクションを起こしたユーザーの割合。

* **[!UICONTROL 購読解除]** : 購読解除リンクのクリック数。

* **[!UICONTROL スパムの苦情]**：メールがスパムまたは迷惑メールとして宣言された回数。

+++

### メール - 送信パフォーマンス {#email-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_sending_performance"
>title="メール - 送信パフォーマンス"
>abstract="XX"

![](assets/journey_email_performance.png)

The **[!UICONTROL 電子メール — 送信パフォーマンス]** グラフでは、ジャーニーの送信済みメールに関するデータの包括的なビューを提供し、配信済みメールとバウンス数などの主要指標に関するインサイトを提供します。 これにより、E メール送信プロセスの詳細な分析を可能にし、ジャーニーの効率性とパフォーマンスに関する貴重な情報を提供します。

+++ 電子メール — パフォーマンス指標の送信の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL 再試行]**：再試行のキュー内のメール数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルに送信できなかったエラーの合計数。

+++

### 電子メール — バウンスのカテゴリと理由 {#email-bounce-categories}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_bounces"
>title="電子メール — バウンスのカテゴリと理由"
>abstract="XX"

![](assets/journey_email_bounce_categories.png)

The **[!UICONTROL バウンスの理由]** および **[!UICONTROL バウンスのカテゴリ]** ウィジェットは、バウンスメッセージに関連する使用可能なデータをコンパイルし、電子メールバウンスの背後にある特定の理由とカテゴリに関する詳細なインサイトを提供します。

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

+++ メール — バウンスカテゴリ指標の詳細を説明します

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

+++

### メール - エラー理由 {#email-errors}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_error_reasons"
>title="メール - エラー理由"
>abstract="XX"

![](assets/journey_email_error.png)

The **[!UICONTROL エラーの理由]** グラフと表には、送信プロセス中に発生した特定のエラーを表示し、エラーの特性と発生に関する貴重な情報を提供します。

### メール - 除外された理由 {#email-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_excluded_reasons"
>title="メール - 除外された理由"
>abstract="XX"

![](assets/journey_email_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表は、ターゲットオーディエンスからユーザープロファイルを除外した結果、メッセージが受信されなかった様々な要因の包括的なビューを示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### ドメイン別に送信および配信 {#sent-domains}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_sent_delivered_domains"
>title="ドメイン別に送信および配信"
>abstract="XX"

![](assets/journey_email_sent_domains.png)

The  **[!UICONTROL ドメイン別に送信および配信]** 表とグラフは、ドメインレベルでの電子メールの詳細な分類を提供し、電子メールのパフォーマンスに関する包括的なインサイトを提供します。

+++ ドメイン指標別の送信および配信の詳細を説明します

* **[!UICONTROL 送信済み]**:E メールの送信総数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

+++

### ドメイン別の開封数およびクリック数 {#open-domains}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_open_clicks_domains"
>title="ドメイン別の開封数およびクリック数"
>abstract="XX"

![](assets/journey_email_open_domains.png)

The  **[!UICONTROL ドメイン別の開封数およびクリック数]** グラフと表では、プロファイルの E メールに対するエンゲージメントのドメインレベルの分類を確認し、様々なドメインがコンテンツとどのようにやり取りするかに関する有益なインサイトを提供します。

+++ ドメイン別の開封数およびクリック数指標の詳細を説明します

* **[!UICONTROL 開封数]**：メールが開封された回数。

* **[!UICONTROL クリック数]**：メールのコンテンツがクリックされた回数。

+++

### ドメイン別のバウンス数とエラー数 {#bounces-domains}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_bounces_errors_domains"
>title="ドメイン別のバウンス数とエラー数"
>abstract="XX"

![](assets/journey_email_bounce_domains.png)

The  **[!UICONTROL ドメイン別バウンス数とエラー数]** グラフと表には、送信プロセス中に発生した特定のエラーのドメインレベルでの分類が表示され、発生した問題の詳細な分析が可能です。

+++ ドメイン別バウンス数およびエラー数指標の詳細を説明します

* **[!UICONTROL バウンス]**：送信済み E メールの合計数に関して、送信プロセスと自動返信処理の間に累積したエラーの合計。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### ドメイン別のバウンス理由 {#bounce-reasons-domains}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_bounces_reasons_domains"
>title="ドメイン別バウンス理由"
>abstract="XX"

![](assets/journey_email_bounce_reasons_domain.png)

The  **[!UICONTROL ドメイン別のバウンス理由]** グラフとテーブルでは、一時的なエラーと永続的なエラーの両方に関するデータをドメインレベルで分類し、バウンスメッセージの原因に関する詳細なインサイトを提供します。

### メール - 上位の URL {#email-top}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_top_url"
>title="メール - 上位の URL"
>abstract="XX"

![](assets/journey_email_top.png)

The **[!UICONTROL 電子メール — 上位の URL]** 最も高い訪問者トラフィックを引き付ける e メール内の URL の包括的な概要を示すグラフと表。 これにより、最頻訪問リンクを識別し優先順位を付け、E メール内の特定のコンテンツに対するプロファイルのエンゲージメントに対する理解を深めることができます。

### 電子メール — 最適化 {#email-sto}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_optimization"
>title="電子メール — 最適化"
>abstract="XX"

![](assets/journey_email_sto.png)

>[!NOTE]
>
>The **[!UICONTROL 送信時間の最適化]** および **[!UICONTROL 最適化済みと最適化されていない]** ウィジェットは、配信で「送信時間の最適化」オプションが有効になっている場合にのみ使用できます。 送信時間の最適化について詳しくは、[このページ](../building-journeys/journeys-message.md#send-time-optimization)を参照してください。

The **[!UICONTROL 送信時間の最適化]** および **[!UICONTROL 最適化済みと最適化されていない]** ウィジェットでは、送信方法（最適化、通常）に応じて、e メールの成功の詳細を説明します。

+++ 送信時間の最適化と最適化された指標と最適化されていない指標の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。
* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL 送信済み]**：ジャーニーで送信された電子メールの合計数。

* **[!UICONTROL 開封数]**：ジャーニーで E メールが開封された回数。

* **[!UICONTROL クリック数]**:E メールでコンテンツがクリックされた回数。

+++

### 電子メール — オファー {#email-offers}

>[!CONTEXTUALHELP]
>id="ajo_journey_email_offers"
>title="電子メール — オファー"
>abstract="XX"

>[!NOTE]
>
>オファーのウィジェットと指標は、決定がメールに挿入された場合にのみ使用できます。 意思決定管理について詳しくは、[このページ](../offers/get-started/starting-offer-decisioning.md)を参照してください。

The **[!UICONTROL オファー統計]** および **[!UICONTROL 詳細な統計を提供します]** 時間の経過と共に、ウィジェットは、オファーの成功と、ターゲットオーディエンスに与える影響を測定します。 KPI を使用して、メッセージに関する主な情報の詳細を示します。

+++ 電子メール — オファー指標の詳細を説明します

* **[!UICONTROL 送信されたオファー]**：オファーの送信の総数。

* **[!UICONTROL オファーインプレッション]**：オファーが電子メールで開かれた回数。

* **[!UICONTROL オファークリック数]**：オファーが E メールでクリックされた回数。

* **[!UICONTROL プレースメント名]**：オファーを表示するために使用するプレースメントの名前。プレースメントについて詳しくは、この[ページ](../offers/offer-library/creating-placements.md)を参照してください。

* **[!UICONTROL オファー名]**:E メールに追加されたオファーの名前。 プレースメントについて詳しくは、この[ページ](../offers/offer-library/creating-personalized-offers.md)を参照してください。

* **[!UICONTROL 送信されたオファー]**：オファーの送信の総数。

* **[!UICONTROL オファーのインプレッション率]**：送信されたオファーの数に対する、開封されたオファーの割合。

* **[!UICONTROL オファーのクリック率]**：オファーに対してアクションを起こしたユーザーの割合。

+++

## 「プッシュ通知」タブ {#push-global}

ジャーニーから **[!UICONTROL グローバルレポート]**、 **[!UICONTROL プッシュ通知]** 「 」タブには、ジャーニーで送信されるプッシュ通知に関する主な情報の詳細が表示されます。

### プッシュ通知 - 送信統計 {#push-sending-stat}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_sending_statistics"
>title="プッシュ通知 - 送信統計"
>abstract="XX"

![](assets/journey_push_sending.png)

The **[!UICONTROL プッシュ通知 — 送信統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージ数など、主要指標を含む、プッシュ通知に関する重要なデータの簡潔な概要を示しています。

+++ プッシュ通知 — 統計指標の送信の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しジャーニーの場合の各ジャーニー実行の開始時間。1 つまたは複数の繰り返しのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**：任意のアクション（メールや SMS の送信など）でターゲットとするプロファイルの数。

* **[!UICONTROL 送信済み]**：送信されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 配信率]**：正常に送信されたプッシュ通知の割合。

* **[!UICONTROL バウンス]**：送信されたプッシュ通知の合計数に関する、送信プロセス中のエラーと自動返信処理の合計。

* **[!UICONTROL バウンス率]**：送信済みのプッシュ通知に対する、バウンスしたプッシュ通知の割合。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

* **[!UICONTROL エラー率]**：送信プロセス中に発生し、送信されたプッシュ通知と比較して、送信を妨げたエラーの割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

+++

### プッシュ通知 - トラッキング統計 {#push-tracking-stat}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_tracking_statistics"
>title="プッシュ通知 - トラッキング統計"
>abstract="XX"

The **[!UICONTROL プッシュ — トラッキング統計]** ウィジェットは、プッシュ通知に関連するプロファイルアクティビティの詳細なスナップショットを提供し、エンゲージメントとプッシュ通知の効果に関する重要なインサイトを提供します。

+++ プッシュ通知 — トラッキング統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しジャーニーの場合の各ジャーニー実行の開始時間。1 つまたは複数の繰り返しのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL 開封数]**：ジャーニーでプッシュ通知が開かれた回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

+++

### プッシュ通知 - 送信の概要 {#push-summary}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_sending_summary"
>title="プッシュ通知 - 送信の概要"
>abstract="XX"

![](assets/journey_push_summary.png)

The **[!UICONTROL プッシュ通知 — 送信の概要]** グラフは、プッシュ通知アクティビティの分析を表示する動的な表現を提供します。 このグラフでは、送信されたプッシュ通知の包括的な分類を示します。

+++ プッシュ通知 — 概要指標の送信の詳細を説明します

* **[!UICONTROL 開封数]**：ジャーニーでプッシュ通知が開かれた回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL バウンス]**：送信されたプッシュ通知の合計数に関する、送信プロセス中のエラーと自動返信処理の合計。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### プッシュ通知 - エラー理由 {#push-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_error_reasons"
>title="プッシュ通知 - エラー理由"
>abstract="XX"

![](assets/journey_push_error.png)

The **[!UICONTROL エラーの理由]** 表とグラフは、プッシュ通知の送信プロセス中に発生した特定のエラーを識別し、進行中に発生した問題に関する詳細なインサイトを提供する機能を提供します。

### プッシュ通知 - 除外された理由 {#push-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_excluded_reasons"
>title="プッシュ通知 - 除外された理由"
>abstract="XX"

![](assets/journey_push_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表には、ターゲットプロファイルから除外されたユーザープロファイルがプッシュ通知を受信できなかった様々な理由が表示されます。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### プッシュ通知 - プラットフォームごとの分類 {#push-breakdown}

>[!CONTEXTUALHELP]
>id="ajo_journey_push_breakdown_platform"
>title="プッシュ通知 — プラットフォーム別の分類"
>abstract="XX"

![](assets/journey_push_breakdown.png)

The **[!UICONTROL プラットフォーム別の分類]** グラフと表は、プッシュ通知の成功の詳細な分析を提供し、プロファイルのオペレーティングシステムに基づいたインサイトを提供します。 この分類により、様々なプラットフォームでのプッシュ通知のパフォーマンスを把握できます。

### プッシュ通知 — 最適化 {#push-sto}

>[!NOTE]
>
>この&#x200B;**[!UICONTROL 最適化済みと最適化されていない]**&#x200B;および&#x200B;**[!UICONTROL 送信時間の最適化]**&#x200B;ウィジェットは、配信で「送信時間の最適化」オプションが有効になっている場合にのみ使用できます。送信時間の最適化について詳しくは、[このページ](../building-journeys/journeys-message.md#send-time-optimization)を参照してください。

The **[!UICONTROL 最適化済みと最適化されていない]** および **[!UICONTROL 送信時間の最適化]**  ウィジェットは、メッセージが最適化されているかどうかに関係なく、メイン情報の詳細を表示します。

+++ プッシュ通知 — 最適化指標の詳細を説明します

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL 開封数]**：ジャーニーでプッシュ通知が開かれた回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

+++

## 「SMS」タブ {#sms-global}

### SMS - 送信統計 {#sms-sending-stat}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_sending_statistics"
>title="SMS - 送信統計"
>abstract="XX"

![](assets/journey_sms_sending.png)

The **[!UICONTROL SMS — 送信統計]** この表は、ターゲットメッセージ数や正常に配信されたメッセージの数などの主要指標を含む、SMS メッセージに関する重要なデータの簡潔な概要を示しています。

+++ SMS — 送信統計指標の詳細を説明します

* **[!UICONTROL 実行時間]**：繰り返しジャーニーの場合の各ジャーニー実行の開始時間。1 つまたは複数の繰り返しのみをターゲットにするには、**[!UICONTROL 実行時間]**&#x200B;ドロップダウンから選択します。

* **[!UICONTROL ターゲット]**:SMS メッセージのターゲットプロファイルとして認定されるユーザープロファイルの数。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外され、SMS メッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：ジャーニーで送信された SMS メッセージの合計数。

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する、送信プロセス中と自動返信処理中に累積したエラーの合計。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### SMS — トラッキング統計 {#sms-tracking-stat}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_tracking_statistics"
>title="SMS — トラッキング統計"
>abstract="XX"

![](assets/journey_sms_tracking.png)

The **[!UICONTROL SMS — トラッキング統計]** ウィジェットは、訪問者の URL とのエンゲージメントに関する主要情報の詳細な概要を提供し、SMS メッセージの効果に関するインサイトを提供します。

* **[!UICONTROL 実行時間]**：繰り返し送信される SMS の実行のたびの開始時間。 1 つまたは複数の繰り返し送信 SMS のみをターゲットにするには、 **[!UICONTROL 実行時間]** 」ドロップダウンリストから選択できます。

* **[!UICONTROL クリック数]**:SMS メッセージでコンテンツがクリックされた回数。

### SMS - 日別パフォーマンス {#sms-performance-date}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_perfomance_date"
>title="SMS - 日別パフォーマンス"
>abstract="XX"

![](assets/journey_sms_performance.png)

The **[!UICONTROL SMS — 日別パフォーマンス]** ウィジェットは、メッセージに関する主要情報の詳細な概要をグラフで示し、特定の期間におけるパフォーマンスの傾向に関するインサイトを提供します。

+++ SMS — 日付指標別のパフォーマンスの詳細を説明します

* **[!UICONTROL 送信済み]**：ジャーニーで送信された SMS メッセージの合計数

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する、送信プロセス中と自動返信処理中に累積したエラーの合計。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### SMS - バウンス理由 {#sms-bounce}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_bounces_reasons"
>title="SMS - バウンス理由"
>abstract="XX"

![](assets/journey_sms_bounce_reasons.png)

The **[!UICONTROL バウンス理由]** グラフと表は、バウンスした SMS メッセージに関するデータの包括的な概要を示し、SMS メッセージのバウンスインスタンスの背後にある特定の理由に関する貴重なインサイトを提供します。

### SMS - エラー理由 {#sms-error}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_error_reasons"
>title="SMS - エラー理由"
>abstract="XX"

![](assets/journey_sms_error.png)

The **[!UICONTROL エラーの理由]** グラフと表を使用すると、SMS メッセージの送信プロセス中に発生した特定のエラーを特定し、発生した問題を完全に分析できます。

### SMS - 除外された理由 {#sms-excluded}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_excluded_reasons"
>title="SMS - 除外された理由"
>abstract="XX"

![](assets/journey_sms_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、SMS メッセージを受信できなくなった様々な要因を視覚的に示しています。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### SMS - リンク別のクリック数 {#sms-clicks}

>[!CONTEXTUALHELP]
>id="ajo_journey_sms_clicks"
>title="SMS - リンク別のクリック数"
>abstract="XX"

![](assets/journey_sms_clicks.png)

The **[!UICONTROL SMS — リンク別のクリック数]** ウィジェットは、訪問者のメッセージに含まれる URL とのエンゲージメントに関する基本的なインサイトを提供し、最もインタラクションを引き付けるリンクに関する貴重な情報を提供します。

## 「アプリ内」タブ {#in-app-global}

ジャーニー **[!UICONTROL グローバルレポート]**、 **[!UICONTROL アプリ内]** 「 」タブには、ジャーニーで送信されるアプリ内メッセージに関する主な情報の詳細が表示されます。

### アプリ内パフォーマンス {#inapp-performance}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_performance"
>title="アプリ内パフォーマンス"
>abstract="XX"

![](assets/journey_inapp_performance.png)

The **[!UICONTROL アプリ内パフォーマンス]**  KPI は、プロファイルのアプリ内メッセージとの関わりに関する基本的なインサイトを提供し、ジャーニーに含まれるアプリ内メッセージの有効性と影響を評価するための重要な指標を提供します。

+++ アプリ内 — 日付指標別のパフォーマンスの詳細を説明します

* **[!UICONTROL ユニークインプレッション数]**：アプリ内メッセージが表示されたユニークユーザーの数。

* **[!UICONTROL インプレッション数]**：すべてのユーザーに表示されたアプリ内メッセージの合計数。

  >[!NOTE]
  >
  >インプレッションが確実にカウントされるようにするには、ユーザーが次の 2 つの条件を満たす必要があります。
  >* アプリ内エクスペリエンス内の認定。ジャーニー内の特定のアプリ内アクティビティに到達することで達成されます。
  >* トリガールールで指定された条件を満たす。
  > 
  >2 つ目の条件により、ターゲットプロファイルの数と個別インプレッション数には顕著な違いが生じる場合があります。

* **[!UICONTROL インタラクション数]**：アプリ内メッセージに対するエンゲージメント数。これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。
+++

### アプリ内の概要 {#inapp-summary}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_summary"
>title="アプリ内の概要"
>abstract="XX"

![](assets/journey_inapp_summary.png)

The **[!UICONTROL アプリ内概要]** グラフは、指定した期間におけるアプリ内インプレッション数とインタラクション数の進行状況を示し、アプリ内メッセージのパフォーマンスの包括的な概要を示します。

### タイプ別インタラクション数 {#interactions-type}

>[!CONTEXTUALHELP]
>id="ajo_journey_inapp_interactions"
>title="タイプ別インタラクション数"
>abstract="XX"

![](assets/journey_inapp_interactions.png)

The **[!UICONTROL タイプ別のインタラクション数]** のグラフと表に、プロファイルがアプリ内メッセージ、クリック数、破棄数などのトラッキングアクション、その他のエンゲージメントの形態とどのようにやり取りしたかに関する詳細な説明が表示されます。
