---
solution: Journey Optimizer
product: journey optimizer
title: チャネルレベルのレポート
description: チャネルレポートのデータの使用方法を説明します
feature: Reporting
topic: Content Management
role: User
level: Intermediate
exl-id: ead9359b-cdab-43ed-a469-d98b0ca19a17
source-git-commit: 6bceccc561daac594f5c84d3d3250d887a349b7b
workflow-type: tm+mt
source-wordcount: '2664'
ht-degree: 14%

---

# チャネルレポート {#channel-report}

>[!CONTEXTUALHELP]
>id="ajo_channel_level_report"
>title="チャネルレベルのレポート"
>abstract="チャネルレポートでは、すべてのチャネルにわたるトラフィックとエンゲージメント指標の包括的な概要を提供します。 レポートは、キャンペーンとジャーニーの成功とエラーを示す様々なウィジェットに分かれています。 各レポートダッシュボードは、ウィジェットのサイズ変更や削除を行うことで変更できます。"

>[!IMPORTANT]
>
> **レポート**&#x200B;メニューにアクセスするには、**[!UICONTROL チャネルレポートを表示]**&#x200B;する権限が必要です。[詳細情報](channel-report-gs.md#before-starting-manage-reports-prereq)

チャネルレポートでは、チャネルレベルで、トラフィックとエンゲージメント指標の包括的な概要を提供します。 指標は集計されて、様々なキャンペーンやジャーニーにわたる、選択したチャネルからのアクションの統合値を示します。

チャネルレポートにアクセスするには、 **レポート** メニュー内 **ジャーニー管理** 」セクションに入力します。 完全にカスタマイズ可能で、レポートの日付やアクションに応じてデータをフィルタリングできます。 [詳細情報](channel-report-gs.md)

次のタブを含むレポートページが表示されます。

* [メール](#email)
* [プッシュ 通知](#push)
* [SMS](#sms)
* [アプリ内](#inapp)
* [Web](#web)
* [ダイレクトメール](#direct-mail)

➡️ [この機能をビデオで確認](#channel-report-video)

## メール {#email}

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics"
>title="E メール — 合計送信統計"
>abstract="E メール — 合計送信統計 KPI は、ターゲットメッセージや配信済みメッセージなど、プッシュ通知に関する重要なデータを要約します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics"
>title="E メール — トラッキング統計の合計"
>abstract="E メール — 合計トラッキング統計 KPI は、E メールのプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_statistics_overtime"
>title="電子メール — 統計の送信（経時的）"
>abstract="E メール — 経時的な送信統計のグラフは、送信された E メールに関するデータを、時間単位、日単位、週単位、月単位で分類して表示します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_tracking_statistics_overtime"
>title="E メール — 経時的なトラッキング統計"
>abstract="E メール — 経時的な追跡統計グラフは、時間単位、日単位、週単位、月単位で分類された、E メールのプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_categories"
>title="バウンスのカテゴリ"
>abstract="バウンスカテゴリのグラフと表は、一時的なエラーと永続的なエラーの両方に関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons"
>title="バウンスの理由"
>abstract="バウンス理由グラフとテーブルには、バウンスメッセージに関連して使用できるデータが含まれています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_error_reasons"
>title="エラー理由"
>abstract="「エラー理由」のグラフと表を使用して、送信プロセス中に発生した特定のエラーを特定できます。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_excluded_reasons"
>title="除外された理由"
>abstract="除外された理由のグラフと表は、ターゲットオーディエンスから除外され、メッセージを受信しなかった、ユーザープロファイルにつながった様々な要因を示しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_sending_delivered_domains"
>title="ドメイン別に送信および配信"
>abstract="「送信済みおよび配信済み（ドメイン別） 」のグラフと表は、E メール送信の重要なデータすべてのドメインレベルの分類を表しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounces_errors_domains"
>title="ドメイン別バウンス数とエラー数"
>abstract="ドメイン別バウンス数とエラー数のグラフと表は、送信プロセス中に発生した特定のエラーのドメインレベルでの分類を表しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_open_clicks_domains"
>title="ドメイン別の開封数およびクリック数"
>abstract="ドメイン別の開封数およびクリック数のグラフおよび表は、訪問者の E メールに対するエンゲージメントのドメインレベルの分類を表します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_email_bounce_reasons_domains"
>title="ドメイン別のバウンス理由"
>abstract="ドメイン別のバウンス理由グラフと表は、一時的なエラーと永続的なエラーの両方でのデータのドメインレベルの分類を表しています。"

チャネルレポートの E メールメニューには、キャンペーンおよびジャーニーで送信された E メールに関する主な情報が表示されます。 以下に、指標について詳しく説明します。

![](assets/email_channel_1.png)

+++ 電子メールレポートで使用できる様々な指標およびウィジェットの詳細を説明します。

The **[!UICONTROL 電子メールの合計送信統計]** グラフには、電子メールの成功の詳細が記載されています。

* **[!UICONTROL ターゲット]**：処理された電子メールの合計数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：送信されたメッセージの合計数に関する、正常に送信された電子メールの数。

* **[!UICONTROL 配信率]**：正常に送信された電子メールの割合。

* **[!UICONTROL バウンス]**：送信されたメッセージの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL バウンス率]**：送信メールに対するバウンスメールの割合。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

* **[!UICONTROL エラー率]**：送信された E メールと比較して、エラーが発生して送信できなかった割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

* **[!UICONTROL 除外率]**:Adobe Journey Optimizerによって除外されたプロファイルの割合。

The **[!UICONTROL メール合計トラッキング統計]** ウィジェットには、メールのプロファイルアクティビティで使用できるデータが含まれています。

* **[!UICONTROL 開封数]**：メッセージが開封された回数。

* **[!UICONTROL 開封率]**：配信されたメール数に対して、開封されたメールの合計数。

* **[!UICONTROL クリック数]**：メッセージ内でコンテンツがクリックされた回数。

* **[!UICONTROL クリック率]**:E メールでやり取りしたユーザーの割合。

* **[!UICONTROL スパムのの苦情数]**：メッセージがスパムまたはジャンクとして宣言された回数。

* **[!UICONTROL スパムの苦情率]**：送信された E メールの数に対する、スパムまたは迷惑メールとして宣言されたメッセージの割合。

* **[!UICONTROL 配信停止]**：購読リンクのクリック数。

* **[!UICONTROL 配信停止率]**：送信済み E メールの数に対する、購読解除の割合。

The **[!UICONTROL 経時的な統計の送信]** グラフには、次のような送信済み E メールで使用できるデータが含まれます。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL 配信済み]**：送信された電子メールの合計数に関する、正常に送信された電子メールの数。

* **[!UICONTROL バウンス]**：送信された E メールの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

The **[!UICONTROL E メールトラッキング統計の残り時間]** グラフには、開封数およびクリック数に使用できるデータが含まれます。

**[!UICONTROL バウンスの理由]**&#x200B;ウィジェットおよび&#x200B;**[!UICONTROL バウンスのカテゴリ]**&#x200B;ウィジェットには、次のようなバウンスメッセージに関するデータが含まれています。

* **[!UICONTROL ハードバウンス]**：永続的なエラー（メールアドレスの間違いなど）の合計数。このエラーは、アドレスが無効であることを明示的に示すエラーメッセージ（例：「不明なユーザー」）を伴います。

* **[!UICONTROL ソフトバウンス数]**：一時的なエラー（インボックスが満杯など）の合計数。

* **[!UICONTROL 無視]**：一時的なエラー（不在など）や技術的なエラー（送信者のタイプが postmaster の場合など）の合計数。

バウンスの詳細については、[抑制リスト](../reports/suppression-list.md)のページを参照してください。

The **[!UICONTROL エラーの理由]** グラフと表を使用して、発生したエラーを確認できます。

この&#x200B;**[!UICONTROL 除外された理由]**&#x200B;グラフおよびテーブルには、ターゲットプロファイルから除外されたユーザープロファイルがメッセージを受信できなかった様々な理由が表示されます。

The **[!UICONTROL ドメイン別のバウンス理由]**, **[!UICONTROL ドメイン別に送信および配信]**, **[!UICONTROL ドメイン別の開封数およびクリック数]**  および **[!UICONTROL ドメイン別のバウンスとエラー]** テーブルとグラフは、E メール配信とトラッキングデータの重要なすべてのドメインレベルの分類を表します。
+++

## プッシュ通知 {#push}

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics"
>title="プッシュ通知 — 合計送信統計"
>abstract="プッシュ通知 — 合計送信統計 KPI は、ターゲットや配信など、プッシュ通知に関する重要なデータを要約します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics"
>title="プッシュ通知 — トラッキング統計の合計"
>abstract="プッシュ通知 — 合計トラッキング統計は、プッシュ通知のプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_overtime"
>title="プッシュ通知 — 時間の経過に伴う統計の送信"
>abstract="プッシュ通知送信統計の経時的なグラフは、送信されたプッシュ通知に関するデータを、1 時間ごと、1 日ごと、1 週間ごと、または 1 ヶ月ごとに分類して表示します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_overtime"
>title="プッシュ通知 — 経時的なトラッキング統計"
>abstract="プッシュ通知 — 経時的な追跡統計グラフは、時間単位、日単位、週単位、月単位で分類された、プッシュ通知のプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_excluded_reasons"
>title="除外された理由"
>abstract="除外された理由のグラフと表は、ターゲットオーディエンスから除外され、メッセージを受信しなかった、ユーザープロファイルにつながった様々な要因を示しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_error_reasons"
>title="エラー理由"
>abstract="「エラー理由」のグラフと表を使用して、送信プロセス中に発生した特定のエラーを特定できます。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_tracking_statistics_platform"
>title="プラットフォーム別のトラッキング統計"
>abstract="プラットフォーム別のトラッキング統計のグラフと表は、プロファイルの運用システムに応じて、プッシュ通知のプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_push_sending_statistics_platform"
>title="プラットフォーム別の送信統計"
>abstract="「プラットフォーム別送信統計」グラフと表は、送信されたプッシュ通知に関するデータを示します。"

チャネルレポートのプッシュ通知メニューには、キャンペーンおよびジャーニーで送信されるプッシュ通知に関する主な情報の詳細が表示されます。 指標については、以下で詳しく説明します。

![](assets/push_channel_1.png)

+++  プッシュレポートで使用できる様々な指標およびウィジェットの詳細を説明します。

The **[!UICONTROL プッシュ通知 — 合計送信統計]** この表には、プッシュ通知に関する主な情報の詳細がグラフおよび KPI と共に表示されます。

* **[!UICONTROL ターゲット]**：処理されたプッシュ通知の合計数。

* **[!UICONTROL 送信済み]**：送信されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に関する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL 配信率]**：正常に送信されたプッシュ通知の割合。

* **[!UICONTROL バウンス]**：送信されたメッセージの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL バウンス率]**：送信済みのプッシュ通知に対する、バウンスしたプッシュ通知の割合。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知と比較して、送信を妨げていたエラーの割合。

* **[!UICONTROL 除外済み]**：Adobe Journey Optimizer によって除外されたプロファイルの数。

* **[!UICONTROL 除外率]**:Adobe Journey Optimizerによって除外されたプロファイルの割合。

The **[!UICONTROL プッシュ通知 — トラッキング統計の合計]** には、プッシュ通知用のプロファイルアクティビティに使用できるデータが含まれます。

* **[!UICONTROL 開封数]**：プッシュ通知が開かれた回数。

* **[!UICONTROL 開封率]**：開封されたプッシュ通知の割合。

* **[!UICONTROL アクション]**：配信されたプッシュ通知に対するアクション（ボタンのクリックや解除など）の合計数。

* **[!UICONTROL アクション率]**：送信されたプッシュ通知に対する、配信されたプッシュ通知に対するアクションの割合。

* **[!UICONTROL エンゲージメント率]**：このプッシュ通知の開封とアクションの割合（プロファイルによるプッシュの開封や、ボタンのクリックなど）。

The **[!UICONTROL プッシュ通知 — 時間の経過に伴う統計の送信]** グラフには、次のような送信済みのプッシュ通知で使用できるデータが含まれます。

* **[!UICONTROL 送信済み]**：送信されたプッシュ通知の合計数。

* **[!UICONTROL 配信済み]**：送信されたプッシュ通知の合計数に関する、正常に送信されたプッシュ通知の数。

* **[!UICONTROL バウンス]**：送信されたメッセージの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

この&#x200B;**[!UICONTROL 除外された理由]**&#x200B;グラフおよびテーブルには、ターゲットプロファイルから除外されたユーザープロファイルがメッセージを受信できなかった様々な理由が表示されます。

The **[!UICONTROL エラーの理由]** グラフと表を使用して、発生したエラーを確認できます。

The **[!UICONTROL プラットフォーム別のトラッキング]** および **[!UICONTROL プラットフォームごとの送信]** グラフと表は、プロファイルの運用システムに応じて、プッシュ通知の成功の詳細を示します。
+++

## SMS {#sms}

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics"
>title="SMS — 送信統計の合計"
>abstract="SMS — 合計送信統計 KPI は、ターゲットや配信などの SMS メッセージに関する重要なデータを要約します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics"
>title="SMS — トラッキング統計の合計"
>abstract="「SMS — 追跡統計の合計」は、SMS メッセージのプロファイルアクティビティに関するデータを提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_sending_statistics_overtime"
>title="SMS — 経時的に統計を送信"
>abstract="SMS — 経時的な送信統計グラフは、送信した SMS メッセージに関するデータを、1 時間ごと、1 日ごと、1 週間ごと、または 1 ヶ月ごとに分類して表示します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_tracking_statistics_overtime"
>title="SMS — 経時的なトラッキング統計"
>abstract="SMS — 経時的な追跡統計グラフは、SMS メッセージのプロファイルアクティビティに関するデータを、1 時間ごと、1 日ごと、1 週間ごと、または 1 月ごとに分類して提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_excluded_reasons"
>title="除外された理由"
>abstract="除外された理由のグラフと表は、ターゲットオーディエンスから除外され、メッセージを受信しなかった、ユーザープロファイルにつながった様々な要因を示しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_bounce_reasons"
>title="バウンスの理由"
>abstract="バウンス理由グラフとテーブルには、バウンスメッセージに関連して使用できるデータが含まれています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_sms_error_reasons"
>title="エラー理由"
>abstract="「エラー理由」のグラフと表を使用して、送信プロセス中に発生した特定のエラーを特定できます。"

チャネルレポートの SMS メニューには、キャンペーンおよびジャーニーで送信された SMS に関する主な情報の詳細が表示されます。 以下に、指標について詳しく説明します。

![](assets/sms_channel_1.png)

+++ SMS レポートで使用できる様々な指標およびウィジェットの詳細を説明します。

The **[!UICONTROL SMS — 送信統計の合計]** 表に、SMS の成功の詳細を示します。

* **[!UICONTROL ターゲット]**:SMS チャネルのターゲットプロファイルとして認定されるユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信された SMS メッセージの合計数。

* **[!UICONTROL 配信済み]**：送信された SMS メッセージの合計数に対する、正常に送信された SMS メッセージの数。

* **[!UICONTROL 配信率]**：正常に送信された SMS メッセージの割合。

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL バウンス率]**：送信された SMS メッセージに対する、バウンスした SMS メッセージの割合。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

* **[!UICONTROL エラー率]**：送信された SMS メッセージと比較して、エラーが発生して送信を妨げていた割合。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 除外率]**:Adobe Journey Optimizerによって除外されたプロファイルの割合。

The **[!UICONTROL SMS — トラッキング統計の合計]** widget は、訪問者の URL とのエンゲージメントに関する主な情報の詳細を示します。

* **[!UICONTROL クリック数]**:SMS メッセージでコンテンツがクリックされた回数。

* **[!UICONTROL クリック率]**:SMS メッセージで操作をしたユーザーの割合。

The **[!UICONTROL SMS — 経時的に統計を送信]** widget は、メッセージに関連する主な情報の詳細をグラフで示します。

* **[!UICONTROL 送信済み]**：送信された SMS メッセージの合計数。

* **[!UICONTROL 配信済み]**：送信された SMS メッセージの合計数に対する、正常に送信された SMS メッセージの数。

* **[!UICONTROL バウンス]**：送信された SMS メッセージの合計数に関する累積エラーと自動返信処理の合計。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

The **[!UICONTROL 理由を除外]**, **[!UICONTROL バウンス理由]** および **[!UICONTROL エラーの理由]** グラフと表を使用すると、発生したエラーと除外を確認できます。

+++

## ダイレクトメール {#direct-mail}

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_sending_statistics"
>title="ダイレクトメール — 合計送信統計"
>abstract="ダイレクトメール — 合計送信統計 KPI は、ターゲットや配信済みなどのダイレクトメールメッセージに関する重要なデータを要約します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_excluded_reasons"
>title="除外された理由"
>abstract="除外された理由のグラフと表は、ターゲットオーディエンスから除外され、メッセージを受信しなかった、ユーザープロファイルにつながった様々な要因を示しています。"

>[!CONTEXTUALHELP]
>id="ajo_channel_direct_error_reasons"
>title="エラー理由"
>abstract="「エラー理由」のグラフと表を使用して、送信プロセス中に発生した特定のエラーを特定できます。"

「チャネル」レポートのダイレクトメールメニューには、キャンペーンおよびジャーニーで送信されたダイレクトメールメッセージに関する主な情報が詳細に表示されます。 次に、指標について詳しく説明します。

![](assets/direct_mail_channel_1.png)

+++ ダイレクトメールレポートで使用できる様々な指標およびウィジェットの詳細を説明します。

The **[!UICONTROL ダイレクトメール — 合計送信統計]** 表に、メッセージの成功の詳細を示します。

* **[!UICONTROL ターゲット]**：ダイレクトメールメッセージのターゲットプロファイルとして認定されるユーザープロファイルの数。

* **[!UICONTROL 送信済み]**：送信の合計数。

* **[!UICONTROL エラー]**：エラーが発生してプロファイルに送信できなかった合計数。

* **[!UICONTROL エラー率]**：送信されたプッシュ通知と比較して、送信を妨げていたエラーの割合。

* **[!UICONTROL 除外済み]**：ターゲットプロファイルから除外されメッセージを受信しなかったユーザープロファイルの数。

* **[!UICONTROL 除外率]**:Adobe Journey Optimizerによって除外されたプロファイルの割合。

The **[!UICONTROL 理由を除外]** および **[!UICONTROL エラーの理由]** グラフと表を使用すると、発生したエラーと除外を確認できます。
+++

## アプリ内 {#in-app}

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement"
>title="アプリ内 — 合計エンゲージメント数"
>abstract="アプリ内 — 合計エンゲージメント KPI は、インプレッション数やインタラクション数などの指標を含め、訪問者のアプリ内メッセージに対するエンゲージメントに関する包括的な情報を提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_inapp_engagement_overtime"
>title="アプリ内 — エンゲージメントの推移"
>abstract="アプリ内 — エンゲージメントオーバータイムグラフは、アプリ内のインプレッションとインタラクションを追跡し、時間別、日別、週別、月別の分類を提供します。"

チャネルレポートのアプリ内メニューには、キャンペーンおよびジャーニーで送信されたアプリ内メッセージに関する主な情報が詳細に表示されます。 以下に、指標について詳しく説明します。

![](assets/inapp_channel_1.png)

+++  アプリ内レポートで使用できる様々な指標およびウィジェットについて詳しく説明します。

The **[!UICONTROL アプリ内の合計エンゲージメント数]** KPI では、次のような、訪問者のアプリ内メッセージに対するエンゲージメントに関する主な情報の詳細を説明します。

* **[!UICONTROL Impressions]**：すべてのユーザーに配信されたアプリ内メッセージの合計数。

* **[!UICONTROL インタラクション]**：アプリ内メッセージに対するエンゲージメントの合計数。 これには、クリック、破棄、その他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

* **[!UICONTROL 破棄]**：プロファイルが「閉じる」ボタンをクリックするか自動的に閉じることによって閉じたアプリ内メッセージの合計数。

* **[!UICONTROL 却下率]**：プロファイルが閉じたアプリ内メッセージの割合。

The **[!UICONTROL アプリ内エンゲージメントの時間外]** グラフは、任意のインプレッション、却下またはインタラクションを追跡することにより、該当する期間のアプリ内インプレッションおよびインタラクションの推移を表示します。

+++

## Web {#web}

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement"
>title="Web — 合計エンゲージメント数"
>abstract="Web — 合計エンゲージメント KPI は、インプレッション数やインタラクション数などの指標を含め、訪問者の Web ページに対するエンゲージメントに関する包括的な情報を提供します。"

>[!CONTEXTUALHELP]
>id="ajo_channel_web_engagement_overtime"
>title="Web — 合計エンゲージメント残高"
>abstract="Web — エンゲージメントオーバータイムグラフは、Web ページのインプレッション数とインタラクション数を追跡し、時間別、日別、週別、月別の分類を提供します。"

チャネルレポートの Web メニューには、キャンペーンおよびジャーニーに含まれる Web ページに関する主な情報の詳細が表示されます。 以下に、指標について詳しく説明します。

![](assets/web_channel_1.png)

+++ Web レポートで使用できる様々な指標およびウィジェットの詳細を説明します。

The **[!UICONTROL Web 合計エンゲージメント数]** KPI では、次のような、訪問者の Web エクスペリエンスとのエンゲージメントに関する主な情報の詳細を説明します。

* **[!UICONTROL Impressions]**：すべてのユーザーに配信された Web エクスペリエンスの合計数。

* **[!UICONTROL インタラクション]**:Web ページに対するアクションの合計数。 これには、クリックやその他のインタラクションなど、ユーザーが実行したすべてのアクションが含まれます。

* **[!UICONTROL 破棄]**：プロファイルが閉じた Web ページの合計数。

* **[!UICONTROL 却下率]**：プロファイルが閉じた Web ページの割合。

The **[!UICONTROL Web エンゲージメントの残存期間]** のグラフは、訪問者の web ページに対するエンゲージメントに関する主な情報の詳細を示します。

+++

## チャネルレポート（ビデオ） {#channel-report-video}

チャネルレベルでレポートにアクセス、ナビゲート、および書き出しする方法については、このビデオを参照してください。

>[!VIDEO](https://video.tv.adobe.com/v/3424537?quality=12)
