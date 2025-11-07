---
solution: Journey Optimizer
product: journey optimizer
title: システムアラートへのアクセスと購読
description: システムアラートへのアクセスと購読方法を学ぶ
feature: Journeys, Alerts
topic: Administration
role: User
level: Intermediate
exl-id: 0855ca5b-c7af-41c4-ad51-bed820ae5ecf
source-git-commit: 1349da209bc90dd8ebad0bd309f89039aa6ea3f2
workflow-type: tm+mt
source-wordcount: '2153'
ht-degree: 76%

---

# システムアラートへのアクセスと購読 {#alerts}

ジャーニーとキャンペーンを作成する場合は、「**アラート**」ボタンを使用してエラーを確認および解決してから、実行または公開します。

* ジャーニーをトラブルシューティングする方法について詳しくは、[このページ](../building-journeys/troubleshooting.md)を参照してください

* キャンペーンのレビューとアクティブ化の方法について学ぶ：[&#x200B; アクションキャンペーン &#x200B;](../campaigns/review-activate-campaign.md) | [API トリガーキャンペーン &#x200B;](../campaigns/review-activate-api-triggered-campaign.md) | [&#x200B; 調整されたキャンペーン &#x200B;](../orchestrated/start-monitor-campaigns.md)


これらに加えて、特定の条件セットに達した場合、その条件を登録している組織内のユーザーにアラートメッセージを送信できます。これらのアラートは、専用の&#x200B;**[!UICONTROL アラート]**&#x200B;メニューから使用できます。 Adobe Experience Platform には、組織に対して有効にできる定義済みのアラートルールがいくつか用意されています。さらに、このページの説明に従って、[!DNL Adobe Journey Optimizer] 固有のシステムアラートを登録することもできます。

>[!NOTE]
>
>Adobe Experience Platform のアラートについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=ja){target="_blank"}を参照してください。

左側のメニューの&#x200B;**[!UICONTROL 管理]**&#x200B;で、「**[!UICONTROL アラート]**」をクリックします。Journey Optimizer には、事前設定済みのアラートがいくつか「**参照**」タブに用意されています。

![](assets/updated-alerts-list.png){width=50%}

* ジャーニーに固有のアラート：

   * [オーディエンスを読み取りトリガーに失敗しました](#alert-read-audiences)アラート
   * [Custom Action Error Rate Exceeded](#alert-custom-action-error-rate) アラート（前のジャーニーの Custom Action Failure アラートに代わる）
   * [プロファイルの破棄率を超えました](#alert-discard-rate)アラート
   * [プロファイルのエラー率を超えました](#alert-profile-error-rate)アラート
   * [ジャーニーが公開されました &#x200B;](#alert-journey-published) アラート
   * [ジャーニー完了 &#x200B;](#alert-journey-finished) アラート
   * [&#x200B; カスタムアクションキャッピングトリガー &#x200B;](#alert-custom-action-capping) アラート

* チャネル設定に固有のアラート：

   * [AJO ドメイン DNS レコードがありません](#alert-dns-record-missing)アラート
   * [AJO チャネル設定エラー](#alert-channel-config-failure)アラート
     <!--* the [AJO domain certificates renewal unsuccessful](#alert-certificates-renewal) alert-->

## アラートの配信を登録 {#subscribe-alerts}

予期しない動作が発生した場合や、操作の特定の条件（システムがしきい値に達した場合に問題が発生する可能性があるなど）に達した場合、その条件を登録している組織内のユーザーにアラート通知が配信されます。

各アラートは、ユーザーインターフェイスから個別に登録することも、**[!UICONTROL アラート]**&#x200B;メニューからグローバルに登録することも（[グローバル登録](#global-subscription)を参照）、特定のジャーニーに対して単一で登録することもできます（[単一登録](#unitary-subscription)を参照）。

登録者の環境設定に基づいて、アラートはメールで送信されるか、ユーザーインターフェイスの右上隅にある Journey Optimizer 通知センター内（アプリ内通知）で直接送信されます。[!DNL Adobe Experience Cloud] **[!UICONTROL 環境設定]**&#x200B;で、これらのアラートを受信する方法を選択します。[詳細情報](../start/user-interface.md#in-product-alerts)

アラートが解決されると、サブスクライバーは「解決済み」通知を受け取ります。 アラートは、値の切り替えを防ぐために、1 時間後に解決されます。


### グローバル登録 {#global-subscription}

すべてのジャーニーとキャンペーンのアラートを登録／登録解除するには、次の手順に従います。

1. 左側のメニューから&#x200B;**[!UICONTROL アラート]**&#x200B;ダッシュボードに移動し、登録するアラートの「**[!UICONTROL 登録]**」オプションを選択します。

   ![アラートの登録](assets/alert-subscribe.png){width=80%}

   >[!NOTE]
   >
   >登録は、特定のサンドボックスにのみ適用されます。各サンドボックスのアラートを個別に登録する必要があります。

1. **[!UICONTROL 登録解除]**&#x200B;する場合も同じ方法を使用します。

また、[I/O イベント通知](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html?lang=ja){target="_blank"}を通じて登録することもできます。アラートルールは、様々な登録パッケージに整理されます。特定の Journey Optimizer アラートに対応するイベント登録については、[以下](#journey-alerts)で詳しく説明します。

### 単一登録 {#unitary-subscription}

特定のジャーニーのアラートを登録／登録解除するには、次の手順に従います。

1. ジャーニーインベントリを参照し、特定のジャーニーの「**[!UICONTROL アラートの配信を登録]**」オプションを選択します。

   ![特定のジャーニーのアラートの登録](assets/subscribe-journey-alert.png){width=75%}

1. アラートを選択します。次のアラートを使用できます：[&#x200B; プロファイル破棄率を超えています &#x200B;](#alert-discard-rate)、[&#x200B; カスタムアクションエラー率を超えています &#x200B;](#alert-custom-action-error-rate)、[&#x200B; プロファイルエラー率を超えています &#x200B;](#alert-profile-error-rate)、6&rbrace;ジャーニーが公開されました [、](#alert-journey-published)ジャーニーが完了しました [、および &#x200B;](#alert-journey-finished) カスタムアクションキャッピングトリガー [。](#alert-custom-action-capping)

1. アラートを登録解除するには、同じ画面からアラートを選択解除します。

1. 「**[!UICONTROL 保存]**」をクリックして確認します。

<!--To enable email alerting, refer to [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html?lang=ja#enable-email-alerts){target="_blank"}.-->

## ジャーニーアラート {#journey-alerts}


ユーザーインターフェイスで使用できるすべてのジャーニー通知は次のとおりです。

>[!CAUTION]
>
>Adobe Journey Optimizer に特定のアラートは、**ライブ**&#x200B;ジャーニーにのみ適用されます。 テストモードのジャーニーでは、アラートはトリガーされません。

### オーディエンストリガーの読み取りが失敗しました {#alert-read-audiences}

このアラートは、スケジュールされた実行時間から 10 分経過しても、「**オーディエンスを読み取り**」アクティビティでプロファイルを処理されなかった場合に警告します。このエラーは、技術的な問題やオーディエンスが空であることが原因で発生する可能性があります。このエラーが技術的な問題によって発生した場合、問題のタイプに応じて、再試行が引き続き行われる可能性があります（例：エクスポートジョブの作成に失敗した場合、最大 1 時間、10 分ごとに再試行されます）。

「**オーディエンスを読み取り**」アクティビティに関するアラートは、繰り返しジャーニーにのみ適用されます。**1 回**&#x200B;または&#x200B;**できるだけ早く**&#x200B;実行するスケジュールが設定されているライブジャーニーの「**オーディエンスを読み取り**」アクティビティは無視されます。

**オーディエンスを読み取り** に関するアラートは、プロファイルが **オーディエンスを読み取り** ノードに入ったか、1 時間後に解決されます。

**オーディエンスを読み取りのトリガー失敗**&#x200B;アラートに対応する I/O イベント購読名は、**ジャーニーのオーディエンスを読み取りの遅延、失敗およびエラー**&#x200B;です。

**オーディエンスの読み取り**&#x200B;アラートのトラブルシューティングをするには、Experience Platform インターフェイスでオーディエンス数を確認します。

### プロファイルの破棄率を超えました {#alert-discard-rate}

このアラートは、過去 5 分間にエントリ済みのプロファイルに対するプロファイル破棄率がしきい値を超えた場合に警告します。デフォルトのしきい値は 20% に設定されていますが、[&#x200B; カスタムのしきい値を定義 &#x200B;](#custom-threshold) できます。

アラートの名前をクリックすると、アラートの詳細と設定を確認できます。

![](assets/profile-discard-alert.png)

プロファイルが破棄される理由はいくつかあり、それによってトラブルシューティングの方法がわかります。一般的な理由をいくつか以下に示します。

* プロファイルは、その単一ジャーニーで既にライブになっているので、エントリ時に破棄されます。これを解決するには、プロファイルに対する次のイベントが到達する前に、プロファイルがジャーニーを終了するのに十分な時間があることを確認します。
* プロファイルに ID が設定されていないか、オーディエンスを読み取りジャーニーで使用される名前空間がそのプロファイルで使用されていません。これを解決するには、ジャーニーの名前空間がプロファイルで使用される ID 名前空間と一致していることを確認します。
* イベントのスループット率を超えています。これを解決するには、システムに到達するイベントがこれらの制限を超えていないことを確認します。


### カスタムアクションのエラー率を超えました {#alert-custom-action-error-rate}

このアラートは、過去 5 分間に成功した HTTP 呼び出し数に対するカスタムアクションエラー率がしきい値を超えた場合に警告します。デフォルトのしきい値は 20% に設定されていますが、[&#x200B; カスタムのしきい値を定義 &#x200B;](#custom-threshold) できます。

>[!NOTE]
>
>このアラートは、前の **ジャーニーのカスタム動作の失敗** アラートに代わるものです。

アラートの名前をクリックすると、アラートの詳細と設定を確認できます。

カスタムアクションエラーは、様々な理由で発生する場合があります。これらのエラーのトラブルシューティングを行うには、次の操作を実行します。

* 別のジャーニーで[テストモード](../building-journeys/testing-the-journey.md)を使用してカスタムアクションを確認します。
* [ジャーニーレポート](../reports/journey-live-report.md)を調べて、アクションに関するエラー理由を確認します。
* ジャーニーの stepEvents で「failureReason」の詳細を確認します。
* カスタムアクションが正しく設定されていることを確認し、認証が引き続き有効であることを検証します。 例えば、Postman で手動で確認を実行します。
* エンドポイントが到達可能で、カスタムアクションがカスタムアクション接続チェッカーを使用してエンドポイントに到達できることを確認します。
* 認証資格照明を確認し、インターネット接続などを調べます

### プロファイルのエラー率を超えました {#alert-profile-error-rate}

このアラートは、過去 5 分間に入力されたプロファイルに対するエラー内のプロファイルの割合が、しきい値を超えた場合に警告します。 デフォルトのしきい値は 20% に設定されていますが、[&#x200B; カスタムのしきい値を定義 &#x200B;](#custom-threshold) できます。

アラートの名前をクリックすると、アラートの詳細と設定を確認できます。

プロファイルエラーのトラブルシューティングを行うには、ステップイベントのデータのクエリを実行して、プロファイルがジャーニーで失敗した場所と理由を理解します。

### 公開されたジャーニー {#alert-journey-published}

このアラートは、ジャーニーキャンバスで実務担当者がジャーニーを公開したときに通知します。

これは、組織のジャーニーライフサイクルイベントを追跡するのに役立つ情報アラートです。 これは 1 回限りの通知なので、解決条件はありません。

### ジャーニーが完了しました {#alert-journey-finished}

このアラートは、ジャーニーが完了すると通知します。 「完了」の定義は、ジャーニーのタイプによって異なります。

| ジャーニータイプ | 繰り返し？ | 終了日はありますか？ | 「finished」の定義 |
|--------------|------------|---------------|--------------------------|
| オーディエンスを読み取り | × | 該当なし | 実行開始 91 日後 |
| オーディエンスを読み取り | ○ | × | 実行開始 91 日後 |
| オーディエンスを読み取り | ○ | ○ | 終了日に達した場合 |
| イベントトリガージャーニー | 該当なし | ○ | 終了日に達した場合 |
| イベントトリガージャーニー | 該当なし | × | UI または API 経由で閉じた場合 |

これは、ジャーニーの完了を追跡するのに役立つ情報アラートです。 これは 1 回限りの通知なので、解決条件はありません。

### カスタムアクションキャッピングのトリガー {#alert-custom-action-capping}

このアラートは、カスタムアクションでキャッピングがトリガーされたときに警告します。 キャッピングは、外部エンドポイントに送信される呼び出しの数を制限して、エンドポイントの圧倒を防ぐために使用されます。

アラートの名前をクリックすると、アラートの詳細と設定を確認できます。

キャッピングがトリガーされると、定義された期間内に API 呼び出しの最大数に達し、それ以降の呼び出しはスロットルまたはキューに入れられています。 カスタムアクションのキャッピングについて詳しくは、[&#x200B; このページ &#x200B;](../action/about-custom-action-configuration.md#custom-action-enhancements-best-practices) を参照してください。

このアラートは、キャッピングがアクティブでなくなったとき、または評価期間中にプロファイルがカスタムアクションに到達しなかったときに解決されます。

キャッピングの問題をトラブルシューティングするには：

* カスタムアクションのキャッピング設定を確認し、使用例に適した制限になっていることを確認します。
* API 呼び出しの量が予想よりも多いかどうかを確認し、ジャーニーのデザインやキャッピングの設定の調整を検討します。
* 外部エンドポイントを監視して、想定される負荷に対応できることを確認します。

## アラートの設定 {#configuration-alerts}

ユーザーインターフェイスで使用できるチャネル設定監視アラートは次のとおりです。

### AJO ドメイン DNS レコードがありません {#alert-dns-record-missing}

このアラートは、適切な配信品質設定に必要な、重要な DNS レコード（NS または CNAME）が欠落しているか、誤って設定されている場合に通知します。これらのレコードがないと、メールの配信品質が損なわれる場合があります。

>[!NOTE]
>
>* NS レコードは、アドビへの完全なサブドメインデリゲーションに不可欠です。[詳細情報](../configuration/about-subdomain-delegation.md#full-subdomain-delegation)
>
>* CNAME レコードは、CNAME サブドメインの設定をサポートしています。[詳細情報](../configuration/about-subdomain-delegation.md#cname-subdomain-setup)

**AJO ドメイン DNS レコードがありません**&#x200B;アラートは、システムが必要な NS または CNAME レコードが存在しないか、設定標準と一致していないことを検出するとトリガーされます。

1. アラートをクリックして、[!DNL Journey Optimizer] インターフェイスで影響を受ける[サブドメイン](../configuration/delegate-subdomain.md)に移動します。

   <!--For guidance on editing delegated subdomains, see [this section](../configuration/delegate-subdomain.md).-->

1. レコードを正しく設定して DNS 設定を修正し、[サブドメインデリゲーションを再度送信](../configuration/delegate-subdomain.md#submit-subdomain)します。

   >[!NOTE]
   >
   >次に進む前に、ドメインをホストするソリューションですべてのレコードが適切に作成されていることを確認します。

1. 正しい値が不明な場合は、影響を受けるサブドメインと同じ名前で [!DNL Journey Optimizer] に新しいサブドメインを作成できます。[新しいサブドメインの設定方法の詳細情報](../configuration/delegate-subdomain.md#set-up-subdomain)

変更しても問題が解決しない場合は、翌日に同じアラートが再度トリガーされます。

<!--The I/O event subscription name corresponding to this alert is xx. > Do we need to mention this?-->

### AJO チャネル設定エラー {#alert-channel-config-failure}

>[!IMPORTANT]
>
>このアラートは、[カスタムサブドメイン](../configuration/delegate-custom-subdomain.md)デリゲーションタイプを使用する&#x200B;**メール**&#x200B;チャネル設定にのみ適用されます。<!--Other channel types (such as SMS, push, or in-app) are not covered by this alert.-->

このアラートは、システム監査によりメールチャネルの設定に関する問題が検出された場合にトリガーされます。これらの問題には、チャネル設定ミス、無効な DNS 設定、抑制リストの問題、IP の不一致、メールの配信に影響を与えることがあるその他のエラーが含まれる場合があります。

このようなアラートを受信した場合の解決手順を以下に示します。

1. アラートをクリックして、[!DNL Journey Optimizer] インターフェイスで影響を受ける[メールチャネル設定](../email/get-started-email-config.md)に移動します。

   チャネル設定の編集に関するガイダンスについて詳しくは、[この節](../configuration/channel-surfaces.md#edit-channel-surface)を参照してください。

1. 設定の詳細と表示されるエラーメッセージを確認します。一般的なエラーの理由を以下に示します。

   * SPF 検証に失敗しました
   * DKIM の検証に失敗しました
   * MX レコードの検証に失敗しました
   * DNS レコードが無効です

   >[!NOTE]
   >
   >考えられる設定エラーの理由について詳しくは、[この節](../configuration/channel-surfaces.md)を参照してください。

1. 次のように問題を解決します。

   * 必要に応じて、チャネル設定を更新します。
   * アラートに記載されている特定の DNS に関する問題を修正する必要がある場合があります。

   >[!NOTE]
   >
   >単一のドメインを複数のチャネル設定に関連付けることができるので、1 つのチャネル設定の DNS に関する問題を解決すると、複数の設定をまたいで関連する問題が自動的に修正される場合があります。

変更しても問題が解決しない場合は、翌日に同じアラートが再度トリガーされます。

メール設定に関する問題を解決する際は、以下に示すベストプラクティスに注意してください。

* 迅速に対応 - 設定エラーが検出されたらすぐに対処し、メール配信の中断を回避します。
* すべての設定を確認 - アラートに影響を受けるメール設定が複数示されている場合は、それぞれを確認して修正します。

<!--### AJO domain certificates renewal unsuccessful {#alert-certificates-renewal}

This alert warns you if a domain certificate (CDN, tracking URL) renewal failed for a specific Journey Optimizer subdomain.-->

## アラートの管理 {#manage-alerts}

### アラートの編集

アラートの行をクリックすると、そのアラートの詳細を確認できます。名前、ステータス、通知チャネルが左側のパネルに表示されます。
ジャーニーアラートの場合は、「**[!UICONTROL その他のアクション]**」ボタンを使用して編集します。その後、これらのアラートの [&#x200B; カスタムしきい値 &#x200B;](#custom-threshold) を定義できます。

![](assets/alert-more-actions.png){width=60%}

### カスタムしきい値の定義 {#custom-threshold}

[ジャーニーアラート](#journey-alerts)のしきい値を設定できます。上記のしきい値アラートのデフォルトは 20％です。

しきい値を変更するには：

1. **アラート**&#x200B;画面を参照します
1. 更新するアラートの「**[!UICONTROL その他のアクション]**」ボタンをクリックします
1. 新しいしきい値を入力して確定します。新しいしきい値は&#x200B;**すべて**&#x200B;のジャーニーに適用されます


![](assets/alert-threshold.png){width=60%}

>[!CAUTION]
>
>しきい値レベルは、すべてのジャーニーをまたいでグローバルで、ジャーニーごとに個別に変更できません。

### アラートの無効化

デフォルトでは、すべてのアラートが有効になっています。アラートを無効にするには、「**[!UICONTROL アラートを無効にする]**」オプションを選択します。このアラートのすべてのサブスクライバーは、関連する通知を受信しなくなります。


### アラートステータス

考えられるアラートステータスを以下に示します。

* **[!UICONTROL 有効]** - アラートは有効で、現在、トリガー条件を監視しています。
* **[!UICONTROL 無効]** - アラートは無効で、現在、トリガー条件を監視していません。このアラートに関する通知は受信されません。
* **[!UICONTROL トリガー]** - アラートのトリガー条件は、現在、満たされています。


### サブスクライバーの表示と更新 {#manage-subscribers}

アラートを登録しているユーザーのリストを表示するには、「**[!UICONTROL アラートサブスクライバーを管理]**」を選択します。

![](assets/alert-subscribers.png){width=80%}

サブスクライバーを追加するには、メールをコンマで区切って入力し、「**[!UICONTROL 更新]**」を選択します。

サブスクライバーを削除するには、現在のサブスクライバーからメールアドレスを削除し、「**[!UICONTROL 更新]**」を選択します。

## その他のリソース {#additional-resources-alerts}

* ジャーニーをトラブルシューティングする方法について詳しくは、[このページ](../building-journeys/troubleshooting.md)を参照してください。
* キャンペーンをレビューする方法について詳しくは、[このページ](../campaigns/review-activate-campaign.md)を参照してください。
