---
solution: Journey Optimizer
product: journey optimizer
title: チャネルレベルのレポート
description: チャネルレポートのデータの使用方法を学ぶ
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: ead9359b-cdab-43ed-a469-d98b0ca19a17
source-git-commit: 5671f510d8be80b53d57b1ff90a101e500773243
workflow-type: tm+mt
source-wordcount: '3683'
ht-degree: 62%

---

# チャネルレポート {#channel-report}

>[!CONTEXTUALHELP]
>id="ajo_channel_level_report"
>title="チャネルレベルのレポート"
>abstract="チャネルレポートでは、すべてのチャネルにわたるトラフィックとエンゲージメント指標の包括的な概要を提供します。レポートは、キャンペーンとジャーニーの成功とエラーを示す様々なウィジェットに分かれています。各レポートダッシュボードは、ウィジェットのサイズ変更や削除を行うことで変更できます。"

>[!IMPORTANT]
>
> **レポート**&#x200B;メニューにアクセスするには、**[!UICONTROL チャネルレポートを表示]**&#x200B;する権限が必要です。[詳細情報](channel-report-gs.md#before-starting-manage-reports-prereq)

チャネルレポートは、チャネルレベルでのトラフィックとエンゲージメント指標の包括的な概要をユーザーに提供します。指標は集計されて、様々なキャンペーンやジャーニーにわたり、選択したチャネルからのアクションの統合値を示します。

チャネルレポートにアクセスするには、「**ジャーニー管理**」セクション内の&#x200B;**レポート**&#x200B;メニューに移動します。完全にカスタマイズ可能で、レポートの日付やアクションに応じてデータをフィルタリングできます。[詳細情報](channel-report-gs.md)

次のタブを含むレポートページが表示されます。

* [メール](#email)
* [プッシュ通知](#push)
* [SMS](#sms)
* [アプリ内](#inapp)
* [Web](#web)
* [ダイレクトメール](#direct-mail)

➡️ [この機能をビデオで確認](#channel-report-video)

## メール {#email}

チャネルレポートのメールメニューには、キャンペーンおよびジャーニーで送信されたメールに関する主な情報が表示されます。次の指標があります。

### メール - 合計送信統計 {#email-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics"
>title="メール - 合計送信統計"
>abstract="「電子メール — 合計送信統計値」KPI は、ターゲットメッセージや配信済みメッセージなど、電子メールに関する重要なデータを要約します。"

![](assets/channel_email_total_sending.png)

The **[!UICONTROL 電子メールの合計送信統計]** ウィジェットは、電子メールのパフォーマンスに関する包括的な概要を提供し、電子メールに関する重要なデータを要約する主要業績評価指標 (KPI) を表示します。

+++ 電子メールの合計送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：処理されたメールの合計数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの総数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL 配信率]**：正常に送信されたメッセージの割合。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL バウンス率]**：送信メールに対するバウンスメールの割合。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたメールに対する、エラーが発生して送信できなかったメールの割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

* **[!UICONTROL 除外率]**：Adobe Journey Optimizer によって除外されたプロファイルの割合。

+++

### メール - トラッキング統計の合計 {#email-total-tracking}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics"
>title="メール - トラッキング統計の合計"
>abstract="メール - 合計トラッキング統計 KPI は、メールのプロファイルアクティビティに関するデータを提供します。"

![](assets/channel_email_total_tracking.png)

The **[!UICONTROL メール合計トラッキング統計]** ウィジェットは、メールに関連するプロファイルアクティビティの詳細なスナップショットを提供し、エンゲージメントとメールの有効性に関する重要なインサイトを提供します。

+++ メール合計トラッキング統計指標の詳細を説明します

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL 開封率]**：配信されたメール数に対して、開封されたメールの合計数。

* **[!UICONTROL クリック数]**：メッセージでコンテンツがクリックされた回数。

* **[!UICONTROL クリック率]**：メールでインタラクションを行ったユーザーの割合。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

* **[!UICONTROL スパムの苦情率]**：送信されたメールの数に対する、スパムまたは迷惑メールとして判定されたメッセージの割合。

* **[!UICONTROL 登録解除]**：購読リンクのクリック数。

* **[!UICONTROL 登録解除率]**：送信済みメールの数に対する、登録解除の割合。

+++

### メール - 統計を送信（経時的） {#email-sending-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics_overtime"
>title="メール - 統計を送信（経時的）"
>abstract="メール - 経時的な送信統計のグラフには、送信されたメールに関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

![](assets/channel_email_sending_statistics.png)

The **[!UICONTROL 電子メール — 経時的な統計の送信]** グラフは、電子メールアクティビティの分析を表示する動的な表現を提供します。 このグラフでは、送信済み E メールの包括的な分類を使用して、時間単位、日単位、週単位、月単位のスケールでトレンドとパターンを観察できます。

+++ 電子メール — 経時的な指標の送信に関する詳細

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対する、正常に送信されたメッセージの数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

+++

### メール - 経時的なトラッキング統計 {#email-tracking-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics_overtime"
>title="メール - 経時的なトラッキング統計"
>abstract="E メール — 経時的な追跡統計グラフには、メールのプロファイルアクティビティに関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

![](assets/channel_email_tracking_overtime.png)

The **[!UICONTROL E メール — 経時的なトラッキング統計]** グラフは、メールに関連するプロファイルアクティビティの詳細な概要を提供します。 このグラフィカルには、時間単位、日単位、週単位、月単位でデータが分類され、受信者のエンゲージメントが様々な期間でどのように変化しているかに関する貴重なインサイトが提供されます。

+++ E メール — 経時的な指標の追跡統計の詳細を説明します

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL クリック数]**：メッセージでコンテンツがクリックされた回数。

+++

### 電子メール — バウンスのカテゴリと理由 {#bounce-categories}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_categories"
>title="バウンスのカテゴリ"
>abstract="バウンスカテゴリのグラフとテーブルには、一時的なエラーと永続的なエラーの両方に関するデータが表示されます。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons"
>title="バウンスの理由"
>abstract="バウンス理由のグラフとテーブルには、バウンスされたメッセージに関連して使用可能なデータが含まれます。"

![](assets/channel_email_bounce_categories.png)

The **[!UICONTROL バウンスのカテゴリ]** および **[!UICONTROL バウンスの理由]** ウィジェットは、バウンスメッセージに関連付けられたデータをカプセル化し、様々なカテゴリと、メッセージバウンスの背後にある特定の理由の包括的な概要を提供します

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

+++ バウンスカテゴリ指標の詳細を説明します

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

+++

### エラー理由 {#error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_error_reasons"
>title="エラー理由"
>abstract="エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/channel_email_error.png)

The **[!UICONTROL エラーの理由]** グラフと表を使用すると、送信プロセス中に発生した正確なエラーを特定し、発生した問題を明確に把握できます。

### 除外された理由 {#excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_excluded_reasons"
>title="除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/channel_email_excluded.png)

The **[!UICONTROL 除外された理由]** グラフと表は、ターゲットオーディエンスからユーザープロファイルを除外した結果、メッセージが受信されなかった様々な要因の包括的なビューを示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### ドメイン別に送信および配信 {#sent-delivered-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_delivered_domains"
>title="ドメイン別に送信および配信"
>abstract="送信済みおよび配信済み（ドメイン別）のグラフとテーブルは、メール送信の重要なデータすべてのドメインレベルの分類を表します。"

![](assets/channel_email_sent_domains.png)

The **[!UICONTROL ドメイン別に送信および配信]** 表とグラフは、ドメインレベルでの E メール配信の詳細な分類を提供し、E メールのパフォーマンスに関する包括的なインサイトを提供します。

+++ ドメイン指標別の送信および配信の詳細を説明します

* **[!UICONTROL 送信済み]**：メール用の送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に対して、正常に配達できたメッセージの数。

+++

### ドメイン別のバウンス数とエラー数 {#bounces-errors-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounces_errors_domains"
>title="ドメイン別のバウンス数とエラー数"
>abstract="ドメイン別バウンス数とエラー数のグラフとテーブルは、送信プロセス中に発生した特定のエラーのドメインレベルでの分類を表しています。"

![](assets/channel_email_bounces_domain.png)

The **[!UICONTROL ドメイン別バウンス数とエラー数]** グラフと表には、送信プロセス中に発生した特定のエラーのドメインレベルでの分類が表示され、発生した問題の詳細な分析が可能です。

+++ ドメイン別バウンス数およびエラー数指標の詳細を説明します

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対して、送信プロセスおよび自動返信処理の間に累積したエラーの合計数。

* **[!UICONTROL エラー]**：送信プロセス中に発生し、プロファイルへの送信の妨げとなったエラーの合計数。

+++

### ドメイン別の開封数およびクリック数 {#open-clicks-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_open_clicks_domains"
>title="ドメイン別の開封数およびクリック数"
>abstract="ドメイン別の開封数およびクリック数のグラフおよびテーブルは、訪問者のメールに対するエンゲージメントのドメインレベルの分類を表します。"

![](assets/channel_email_open_domains.png)

The **[!UICONTROL ドメイン別の開封数およびクリック数]** グラフと表では、訪問者の E メールに対するエンゲージメントのドメインレベルの分類を確認し、様々なドメインがコンテンツとどのようにやり取りするかに関する有益なインサイトを提供します。

+++ ドメイン別の開封数およびクリック数指標の詳細を説明します

* **[!UICONTROL 開封数]**：メールが開封された回数。

* **[!UICONTROL クリック数]**：メールのコンテンツがクリックされた回数。

+++

### ドメイン別のバウンス理由 {#bounce-reasons-domains}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons_domains"
>title="ドメイン別のバウンス理由"
>abstract="ドメイン別のバウンス理由グラフとテーブルは、一時的なエラーと永続的なエラーの両方でのデータのドメインレベルの分類を表しています。"

![](assets/channel_email_bounce_domain.png)

The **[!UICONTROL ドメイン別のバウンス理由]** グラフとテーブルでは、一時的なエラーと永続的なエラーの両方に関するデータをドメインレベルで分類し、バウンスメッセージの原因に関する詳細なインサイトを提供します。

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

## プッシュ通知 {#push}

チャネルレポートから、 **プッシュ通知** メニューは、キャンペーンおよびジャーニーで送信されるプッシュ通知に関する主な情報の詳細を示します。 以下に指標について説明します。

### プッシュ通知 - 送信統計の合計数 {#push-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics"
>title="プッシュ通知 - 送信統計の合計数"
>abstract="プッシュ通知 - 送信統計の合計数 KPI には、ターゲットや配信など、プッシュ通知に関する重要なデータを要約します。"

![](assets/channel_push_total_sending.png)

The **[!UICONTROL プッシュ通知 — 合計送信統計]** KPI は包括的な概要として機能し、プッシュ通知に関連する重要なデータをカプセル化します。 これらの指標には、ターゲットオーディエンスと実際の配信ステータスに関する詳細なインサイトが含まれ、プッシュ通知の効果とリーチを明確に把握できます。

+++ プッシュ通知 — 合計送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：処理されたプッシュ通知の合計数。

* **[!UICONTROL 送信済み]**：送信されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 配信率]**：正常に送信されたプッシュ通知の割合。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL バウンス率]**：送信済みのプッシュ通知に対する、バウンスしたプッシュ通知の割合。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知に対する、エラーが発生して送信できなかったプッシュ通知の割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

* **[!UICONTROL 除外率]**：Adobe Journey Optimizer によって除外されたプロファイルの割合。

+++

### プッシュ通知 - トラッキング統計の合計数 {#push-total-tracking}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics"
>title="プッシュ通知 - トラッキング統計の合計数"
>abstract="プッシュ通知 - トラッキング統計の合計数では、プッシュ通知のプロファイルアクティビティに関するデータを提供します。"

The **[!UICONTROL プッシュ通知 — トラッキング統計の合計]** ウィジェットは、プッシュ通知に関連するプロファイルアクティビティの詳細なスナップショットを提供し、エンゲージメントとプッシュ通知の効果に関する重要なインサイトを提供します。

+++ プッシュ通知 — 合計トラッキング統計指標の詳細を説明します

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL 開封率]**：開封されたプッシュ通知の割合。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL アクション率]**：送信されたプッシュ通知に対する、配信されたプッシュ通知に対するアクションの割合。

+++

### プッシュ通知 - 送信統計の推移 {#push-sending-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_overtime"
>title="プッシュ通知 - 送信統計の推移"
>abstract="プッシュ通知 - 送信統計の推移グラフには、送信されたプッシュ通知に関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

![](assets/channel_push_sending_statistics.png)

The **[!UICONTROL プッシュ通知 — 時間の経過に伴う統計の送信]** グラフは、プッシュ通知アクティビティの分析を表示する動的な表現を提供します。 このグラフでは、送信済みのプッシュ通知の包括的な分類を使用して、時間単位、日単位、週単位、月単位のスケールでトレンドとパターンを観察できます。

+++ プッシュ通知 — 時間指標の経過に伴う統計の送信に関する詳細

* **[!UICONTROL 送信済み]**：送信されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に対する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL バウンス数]**：送信されたメッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

+++

### プッシュ通知 - トラッキング統計の推移 {#push-tracking-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_overtime"
>title="プッシュ通知 - トラッキング統計の推移"
>abstract="プッシュ通知 - トラッキング統計の推移グラフには、プッシュ通知のプロファイルアクティビティに関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

The **[!UICONTROL プッシュ通知 — 経時的なトラッキング統計]** プッシュ通知に関連するプロファイルアクティビティの詳細な概要を示すグラフ。 このグラフィカルには、時間単位、日単位、週単位、月単位でデータが分類され、受信者のエンゲージメントが様々な期間でどのように変化しているかに関する貴重なインサイトが提供されます。

+++ プッシュ通知 — 時間指標に対するトラッキング統計の詳細を説明します

* **[!UICONTROL 開封数]**：プッシュ通知が開封された回数。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

+++

### プッシュ通知 — 除外された理由 {#push-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_excluded_reasons"
>title="除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/channel_push_excluded.png)

The **[!UICONTROL 除外された理由]** グラフおよびテーブルには、ターゲットプロファイルから除外されたユーザープロファイルがプッシュ通知を受信できなかった様々な理由が表示されます。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### プッシュ通知 — エラー理由 {#push-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_error_reasons"
>title="エラー理由"
>abstract="エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/channel_push_error.png)

The **[!UICONTROL エラーの理由]** グラフと表には、プッシュ通知の送信プロセス中に発生した特定のエラーを特定する機能があり、進行中に発生した問題に関する詳細なインサイトを提供します。

### プッシュ通知 — プラットフォーム別トラッキング {#push-tracking-platform}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_platform"
>title="プラットフォームごとのトラッキング統計"
>abstract="プラットフォームごとのトラッキング統計のグラフとテーブルには、プロファイルのオペレーティングシステムに応じたプッシュ通知のプロファイルアクティビティに関するデータが表示されます。"

The **[!UICONTROL プッシュ通知 — プラットフォーム別トラッキング]** グラフと表は、プロファイルの運用システムに応じて、プッシュ通知の受信者アクティビティの詳細を示します。

### プッシュ通知 — プラットフォームごとの送信 {#push-sending-platform}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_platform"
>title="プラットフォームごとの送信統計"
>abstract="プラットフォームごとの送信統計のグラフとテーブルには、送信されたプッシュ通知に関するデータが表示されます。"

![](assets/channel_push_sending_platform.png)

The **[!UICONTROL プッシュ通知 — プラットフォームごとの送信]** グラフと表は、包括的な分類を提供し、プロファイルの運用システムに関するプッシュ通知の成功の詳細を示します。 この徹底的な分析は、様々なプラットフォームにわたるプッシュ通知の効果に関する有益なインサイトを提供します。

## SMS {#sms}

お使いの **チャネル** レポートの場合は、SMS メニューに、キャンペーンおよびジャーニーで送信される SMS に関する主な情報の詳細が表示されます。 次の指標があります。

### SMS - 送信統計の合計数 {#sms-sending-statistics}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics"
>title="SMS - 送信統計の合計数"
>abstract="SMS - 送信統計の合計数 KPI は、ターゲットまたは配信など、SMS メッセージに関する重要なデータを要約します。"

![](assets/channel_sms_total_sending.png)

The **[!UICONTROL SMS — 送信統計の合計]** KPI は包括的な概要として機能し、SMS に関連する重要なデータをカプセル化します。 これらの指標には、ターゲットオーディエンスと実際の配信ステータスに関する詳細なインサイトが含まれ、SMS メッセージの効果とリーチを明確に把握できます。

+++ プッシュ通知 — 合計送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：SMS チャネルのターゲットプロファイルとして適合するユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信された SMS メッセージの合計数。

* **[!UICONTROL 配信済み]**：送信された SMS メッセージの合計数に対する、正常に送信された SMS メッセージの数。

* **[!UICONTROL 配信率]**：正常に送信された SMS メッセージの割合。

* **[!UICONTROL バウンス数]**：送信された SMS メッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL バウンス率]**：送信された SMS メッセージに対する、バウンスした SMS メッセージの割合。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

* **[!UICONTROL エラー率]**：送信された SMS メッセージに対する、発生したエラーによって送信が妨げられた割合。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの割合。

+++

### SMS - トラッキング統計の合計数 {#sms-tracking-statistics}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics"
>title="SMS - トラッキング統計の合計数"
>abstract="SMS - トラッキング統計の合計数 KPI では、SMS メッセージのプロファイルアクティビティに関するデータを提供します。"

![](assets/channel_sms_tracking.png)

The **[!UICONTROL SMS — トラッキング統計の合計]** ウィジェットは、訪問者の URL とのエンゲージメントに関する主要情報の詳細な概要を提供し、SMS メッセージの効果に関するインサイトを提供します。

* **[!UICONTROL クリック数]**：SMS メッセージでコンテンツがクリックされた回数。

### SMS - 送信統計の推移 {#sms-sending-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics_overtime"
>title="SMS - 送信統計の推移"
>abstract="SMS - 送信統計の推移グラフには、送信された SMS メッセージに関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

![](assets/channel_sms_sending_overtime.png)

The **[!UICONTROL SMS — 経時的に統計を送信]** グラフでは、送信済みの SMS メッセージを包括的に表示し、時間単位、日単位、週単位、月単位でデータを分類できます。 このグラフでは、SMS メッセージアクティビティのトレンドを様々な期間で追跡および分析できます。

+++ SMS の詳細を表示 — 経時的な指標の送信

* **[!UICONTROL 送信済み]**：送信された SMS メッセージの合計数。

* **[!UICONTROL バウンス数]**：送信された SMS メッセージの合計数に対する、累計エラー数および自動返信処理の合計数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げるエラーが発生した合計数。

+++

### SMS - トラッキング統計の推移 {#sms-tracking-statistics-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics_overtime"
>title="SMS - トラッキング統計の推移"
>abstract="SMS - トラッキング統計の推移グラフには、SMS メッセージのプロファイルアクティビティに関するデータが、時間単位、日単位、週単位、または月単位で表示されます。"

![](assets/channel_sms_tracking_overtime.png)

The **[!UICONTROL SMS — 経時的なトラッキング統計]** グラフは、SMS メッセージに関連するプロファイルアクティビティのデータを提供し、時間単位、日単位、週単位、月単位で詳細な分類を提供します。 このグラフでは、様々な期間でのユーザーエンゲージメントのパターンを分析および理解できます。

* **[!UICONTROL クリック数]**：SMS メッセージでコンテンツがクリックされた回数。

### 除外された理由 {#sms-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_excluded_reasons"
>title="除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/channel_sms_excluded.png)

The **[!UICONTROL 理由を除外]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、SMS メッセージを受信できなくなった様々な要因を視覚的に示しています。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### バウンスの理由 {#sms-bounce-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_bounce_reasons"
>title="バウンスの理由"
>abstract="バウンス理由のグラフとテーブルには、バウンスされたメッセージに関連して使用可能なデータが含まれます。"

![](assets/channel_sms_bounce_reasons.png)

The **[!UICONTROL バウンス理由]** グラフと表は、バウンスした SMS メッセージに関するデータの包括的な概要を示し、SMS メッセージのバウンスインスタンスの背後にある特定の理由に関する貴重なインサイトを提供します。

### エラー理由 {#sms-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_error_reasons"
>title="エラー理由"
>abstract="エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

The **[!UICONTROL エラーの理由]** グラフと表を使用すると、SMS メッセージの送信プロセス中に発生した特定のエラーを特定し、発生した問題を完全に分析できます。

## ダイレクトメール {#direct-mail}

お使いの **チャネル** レポート、 **ダイレクトメール** メニューには、 **キャンペーン** および **ジャーニー**. 次に、それらについて説明します。

### ダイレクトメール - 送信統計の合計数 {#direct-mail-total-sending}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_sending_statistics"
>title="ダイレクトメール - 送信統計の合計数"
>abstract="ダイレクトメール - 送信統計の合計数 KPI には、ターゲットまたは配信など、ダイレクトメールメッセージに関する重要なデータがまとめられます。"

![](assets/channel_direct_sending.png)

The **[!UICONTROL ダイレクトメール — 合計送信統計]** widget は、ダイレクトメールメッセージのパフォーマンスに関する包括的な概要を提供し、ダイレクトメールメッセージに関する重要なデータを要約する主要業績評価指標 (KPI) を表示します。

+++ ダイレクトメール — 合計送信統計指標の詳細を説明します

* **[!UICONTROL ターゲット]**：ダイレクトメールメッセージのターゲットプロファイルとして適合するユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL エラー]**：プロファイルへの送信を妨げたエラーの合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知の数と比較して、送信の妨げとなったエラーの割合。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの割合。

+++

### 除外された理由 {#direct-mail-excluded-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_excluded_reasons"
>title="除外された理由"
>abstract="この除外された理由のグラフとテーブルには、ユーザープロファイルがターゲットオーディエンスから除外され、メッセージが受信されない原因となった様々な要因が表示されます。"

![](assets/channel_direct_excluded.png)

The **[!UICONTROL ダイレクトメール — 除外された理由]** グラフと表では、ターゲットオーディエンスからユーザープロファイルが除外され、ダイレクトメールメッセージを受信できなくなった様々な要因を視覚的に示します。

参照： [このページ](exclusion-list.md) 除外の理由の包括的なリストを参照してください。

### エラー理由 {#direct-mail-error-reasons}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_error_reasons"
>title="エラー理由"
>abstract="エラー理由のグラフとテーブルを使用すると、送信プロセス中に発生した特定のエラーを識別できます。"

![](assets/channel_direct_error.png)

The **[!UICONTROL ダイレクトメール — エラー理由]** は、ダイレクトメールメッセージの送信プロセス中に発生した特定のエラーを識別する手段を提供し、発生した問題を詳細に分析できます。

## アプリ内 {#in-app}

チャネルレポートのアプリ内メニューには、キャンペーンおよびジャーニーで送信されたアプリ内メッセージに関する主な情報が詳細に表示されます。次の指標があります。

### アプリ内の合計エンゲージメント数 {#inapp-total-engagement}

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement"
>title="アプリ内 - 総エンゲージメント数"
>abstract="アプリ内 - 総エンゲージメント数 KPI には、インプレッション数やインタラクション数などの指標を含め、訪問者のアプリ内メッセージに対するエンゲージメントに関する包括的な情報が表示されます。"

![](assets/channel_inapp_engagement.png)

The **[!UICONTROL アプリ内の合計エンゲージメント数]** KPI は、次のような主要指標を含む、訪問者のアプリ内メッセージに対するエンゲージメントに関する包括的なインサイトを提供します。 **Impressions** および **インタラクション**.

+++ アプリ内合計エンゲージメント指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション数]**：アプリ内メッセージに対するエンゲージメントの合計数。これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### アプリ内エンゲージメントの時間外 {#inapp-engagement-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement_overtime"
>title="アプリ内 - エンゲージメントの推移"
>abstract="アプリ内 - エンゲージメントの推移グラフには、アプリ内のインプレッション数やインタラクション数を追跡し、時間単位、日単位、週単位および月単位の分類が表示されます。"

![](assets/channel_inapp_engagement_overtime.png)

**[!UICONTROL アプリ内のエンゲージメントの推移]** グラフは、任意のインプレッション数、解除数またはインタラクション数を追跡することにより、該当する期間のアプリ内インプレッション数およびインタラクション数の推移を表示します。

+++ アプリ内エンゲージメントの時間外指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション数]**：アプリ内メッセージに対するエンゲージメントの合計数。これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

## Web {#web}

お使いの **チャネル** レポートの場合、Web メニューには、 **キャンペーン** および **ジャーニー**. 次の指標があります。

### Web - 総エンゲージメント数 {#web-engagement-total}

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement"
>title="Web - 総エンゲージメント数"
>abstract="Web - 総エンゲージメント数 KPI には、インプレッション数やインタラクション数などの指標を含め、訪問者の web ページに対するエンゲージメントに関する包括的な情報が表示されます。"

![](assets/channel_web_engagement.png)

The **[!UICONTROL Web 合計エンゲージメント数]** KPI は、インプレッション数やインタラクション数などの主要指標を含む、訪問者の Web ページとのエンゲージメントに関する包括的なインサイトを提供します。

+++ Web 合計エンゲージメント指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション数]**：Web ページに対するエンゲージメントの合計数。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

### Web - 総エンゲージメント数の推移 {#web-engagement-total-overtime}

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement_overtime"
>title="Web - 総エンゲージメント数の推移"
>abstract="Web - 総エンゲージメント数の推移グラフには、web ページのインプレッション数やインタラクション数を追跡し、時間単位、日単位、週単位および月単位の分類が表示されます。"

![](assets/channel_web_engagement_overtime.png)

The **[!UICONTROL Web エンゲージメントの残存期間]** グラフは **Impressions** および **インタラクション** を参照し、時間単位、日単位、週単位、月単位の詳細な分類を提供します。

+++ Web エンゲージメントの時間外指標の詳細を説明します

* **[!UICONTROL インプレッション数]**：すべてのユーザーに配信された web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション数]**：Web ページに対するエンゲージメントの合計数。これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

+++

## チャネルレポート（ビデオ） {#channel-report-video}

このビデオでチャネルレベルのレポートにアクセス、ナビゲートおよび書き出し方法を学ぶ

>[!VIDEO](https://video.tv.adobe.com/v/3424537?quality=12)
