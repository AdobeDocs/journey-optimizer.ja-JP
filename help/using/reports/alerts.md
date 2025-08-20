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
source-git-commit: 3aa3203ae7763d81288cb70a2984d017b0006bb3
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 43%

---

# システムアラートへのアクセスと購読 {#alerts}

ジャーニーとキャンペーンを作成する場合は、実行または公開する前に「**アラート**」ボタンを使用してエラーを確認し解決します。

* ジャーニーのトラブルシューティング方法については、[ このページ ](../building-journeys/troubleshooting.md) を参照してください。
* キャンペーンをレビューする方法について詳しくは、[このページ](../campaigns/review-activate-campaign.md)を参照してください。

専用の **[!UICONTROL アラート]** メニューから、このページで説明しているよ [!DNL Adobe Journey Optimizer] に、システムアラートの配信を登録することもできます。

## アクセスアラート {#access-alerts}

エラーが発生した場合は、Journey Optimizer通知センターでシステムアラート（アプリ内アラート）を取得したり、メールを受信したりできます。 これらのアラートにアクセスするには、次の手順に従います。

<!--These messages can repeat over a pre-defined time interval until the alert has been resolved.-->

>[!NOTE]
>
>Adobe Experience Platform のアラートについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/overview.html?lang=ja){target="_blank"}を参照してください。

左側のメニューの&#x200B;**[!UICONTROL 管理]**&#x200B;で、「**[!UICONTROL アラート]**」をクリックします。Journey Optimizerの事前設定済みのアラートがいくつか用意されています。

これらのアラートは次のようにリストされ、各アラートの詳細は次のとおりです。

* ジャーニーに固有のアラート：

   * [ジャーニーカスタムアクションエラー ](#alert-custom-actions) アラート
   * [ オーディエンスの読み取りトリガーに失敗 ](#alert-read-audiences) アラート

* チャネル設定に固有のアラート：

   * [AJO ドメイン DNS レコードがありません ](#alert-dns-record-missing) アラート
  <!--* the [AJO channel configuration failure](#alert-channel-config-failure) alert
   * the [AJO domain certificates renewal unsuccessful](#alert-certificates-renewal) alert-->

## アラートの配信を登録 {#subscribe-alerts}

1. 「**[!UICONTROL 登録]**」オプションを選択すると、ユーザーインターフェイスから各アラートを個別に登録できます。

   ![](assets/alert-subscribe.png){width=80%}

   >[!NOTE]
   >
   >購読は、特定のサンドボックスにのみ適用されます。 各サンドボックスのアラートを個別に購読する必要があります。

1. 同じメソッドを使用して **[!UICONTROL 登録解除]** します。

1. また、[I/O イベント通知](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/subscribe.html?lang=ja){target="_blank"}を通じてアラートを購読することもできます。アラートルールは、様々な購読パッケージに整理されます。特定のJourney Optimizer アラートに対応するイベント購読について詳しくは [ 以下 ](#journey-alerts) を参照してください。

1. 予期しない動作が発生した場合や、操作の特定の条件（システムがしきい値に達した場合に問題が発生する可能性があるなど）に達した場合、アラート通知は、そのアラートを購読している組織内のユーザーに配信されます。

購読者の好みに応じて、アラートがメールで送信されるか、Journey Optimizer通知センター内で直接ユーザーインターフェイスの右上隅に通知されます（アプリ内通知）。 これらのアラートを受け取る方法を [!DNL Adobe Experience Cloud] **[!UICONTROL 環境設定]** で選択します。 [詳細情報](../start/user-interface.md#in-product-alerts)

>[!NOTE]
>
>デフォルトでは、アプリ内アラートのみが有効になっています。

<!--To enable email alerting, refer to [Adobe Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/observability/alerts/ui.html#enable-email-alerts){target="_blank"}.-->

アラートが解決されると、購読者に「解決済み」通知が届きます。

## アラートの管理 {#manage-alerts}

アラートを管理するには、項目を選択し、「その他のアクション **[!UICONTROL ボタンを使用]** ます。

![](assets/alert-more-actions.png){width=80%}

デフォルトでは、すべてのアラートが有効になっています。 アラートを無効にするには、**[!UICONTROL その他のアクション]** メニューから **[!UICONTROL アラートを無効にする]** オプションを選択します。 このアラートのすべてのサブスクライバーは、関連する通知を受信しなくなります。

**[!UICONTROL アラート購読者を管理]** を選択して、アラートを購読しているユーザーのリストを表示します。 その他の購読者を追加するには、空白フィールドを使用します。

![](assets/alert-subscribers.png){width=80%}

考えられるアラートステータスを以下に示します。

* **[!UICONTROL 有効]** - アラートは有効で、現在、トリガー状態をモニタリングしています。
* **[!UICONTROL 無効]** - アラートは無効で、現在、トリガーの状態を監視していません。 このアラートの通知は受け取りません。
* **[!UICONTROL トリガー]** - アラートのトリガー条件が現在、満たされています。

## ジャーニーアラート {#journey-alerts}

>[!CAUTION]
>
>Adobe Journey Optimizer に特定のアラートは、**ライブ**&#x200B;ジャーニーにのみ適用されます。 テストモードのジャーニーでは、アラートはトリガーされません。

### ジャーニーカスタムアクションエラー {#alert-custom-actions}

このアラートは、カスタムアクションが失敗した場合に警告を表示します。過去 5 分間に特定のカスタムアクションで 1％以上のエラーが発生した場合、エラーが発生したとみなします。これは 30 秒ごとに評価されます。

![](assets/alerts-custom-action.png)

カスタムアクションに関するアラートは、過去 5 分間ににわたり次の場合に解決されます。

* そのカスタムアクションに関するエラー（または 1％のしきい値を下回るエラー）が発生していない。

* または、そのカスタムアクションに到達したプロファイルがない。

カスタムアクションアラートに対応する I/O イベント登録名は、**ジャーニーカスタムアクションエラー**&#x200B;です。

**カスタムアクション**&#x200B;アラートのトラブルシューティングをするには:

* 別のジャーニーでテストモードを使用してカスタムアクションを確認：

  ![](assets/alert-troubleshooting-2.png)

* ジャーニーレポートを調べて、アクションに関するエラー理由を確認します。

  ![](assets/alert-troubleshooting-3.png)

* ジャーニーの stepEvents で「failureReason」の詳細を確認します。

* カスタムアクション設定を確認し、認証が正常であることを検証します。例えば、Postman で手動チェックを実行します。

### オーディエンストリガーの読み取りが失敗しました {#alert-read-audiences}

このアラートは、スケジュールされた実行時間から 10 分経過しても、「**オーディエンスを読み取り**」アクティビティでプロファイルを処理されなかった場合に警告します。このエラーは、技術的な問題やオーディエンスが空であることが原因で発生する可能性があります。このエラーが技術的な問題によって発生した場合、問題のタイプに応じて、再試行が引き続き行われる可能性があります（例：書き出しジョブの作成に失敗した場合、最大 1 時間、10 分ごとに再試行されます）。

![](assets/alerts1.png)

「**オーディエンスを読み取り**」アクティビティに関するアラートは、繰り返しジャーニーにのみ適用されます。**1 回**&#x200B;または&#x200B;**できるだけ早く**&#x200B;実行するスケジュールが設定されているライブジャーニーの「**オーディエンスを読み取り**」アクティビティは無視されます。

**オーディエンスを読み取り**&#x200B;に関するアラートは、プロファイルが&#x200B;**オーディエンスを読み取り**&#x200B;ノードにエントリすると解決されます。

**オーディエンスを読み取りのトリガー失敗**&#x200B;アラートに対応する I/O イベント購読名は、**ジャーニーのオーディエンスを読み取りの遅延、失敗およびエラー**&#x200B;です。

**オーディエンスの読み取り**&#x200B;アラートのトラブルシューティングをするには、Experience Platform インターフェイスでオーディエンス数を確認します。

![](assets/alert-troubleshooting-0.png)

![](assets/alert-troubleshooting-1.png)

## 設定アラート {#configuration-alerts}

### AJO ドメイン DNS レコードがありません {#alert-dns-record-missing}

このアラートは、適切な配信品質設定に必要な重要な DNS レコード（NS または CNAME）が見つからないか、間違って設定されている場合に通知します。 これらの記録がないと、メールの配信品質が損なわれる可能性があります。

>[!NOTE]
>
>* NS レコードは、Adobeへの完全なサブドメインデリゲーションに不可欠です。 [詳細情報](../configuration/about-subdomain-delegation.md#full-subdomain-delegation)
>
>* CNAME レコードは、CNAME サブドメインの設定をサポートしています。 [詳細情報](../configuration/about-subdomain-delegation.md#cname-subdomain-setup)

**AJO ドメイン DNS レコードが見つかりません** アラートは、必要な NS または CNAME レコードがないか、構成標準に一致しないことをシステムが検出した場合にトリガーされます。

1. アラートをクリックして、[ インターフェイス内の影響を受ける ](../configuration/delegate-subdomain.md) サブドメイン [!DNL Journey Optimizer] にリダイレクトします。

   <!--For guidance on editing delegated subdomains, see [this section](../configuration/delegate-subdomain.md).-->

1. レコードを正しく設定して DNS 設定を修正し、再度 [ サブドメインを送信 ](../configuration/delegate-subdomain.md#submit-subdomain) デリゲーションを行います。

   >[!NOTE]
   >
   >続行する前に、ドメインホスティングソリューションですべてのレコードが正しく作成されていることを確認してください。

1. 正しい値が不明な場合は、影響を受けるサブドメインと同じ名前の新しいサブドメインを [!DNL Journey Optimizer] に作成できます。 [ 新しいサブドメインの設定方法を学ぶ ](../configuration/delegate-subdomain.md#set-up-subdomain)

変更しても問題が解決しない場合は、同じアラートが翌日に再度トリガーされます。

<!--The I/O event subscription name corresponding to this alert is xx. > Do we need to mention this?

### AJO channel configuration failure {#alert-channel-config-failure}

>[!IMPORTANT]
>
>This alert applies only to **email** channel configurations using the [custom subdomain](../configuration/delegate-custom-subdomain.md) delegation type. ///Other channel types (such as SMS, push, or in-app) are not covered by this alert.///

This alert is triggered in case the system audit detects email channel configuration issues. These issues may include misconfigured channel settings, invalid DNS configuration, suppression list issue, IP inconsistency, or any other errors that can impact email delivery.

If you receive such an alert, the resolution steps are listed below:

1. Click the alert to be directed to the impacted [email channel configuration](../email/get-started-email-config.md) in the [!DNL Journey Optimizer] interface.

   For guidance on editing channel configurations, see [this section](../configuration/channel-surfaces.md#edit-channel-surface).

1. Review the configuration details and error messages provided. Common failure reasons include:

   * SPF validation failed
   * DKIM validation failed
   * MX record validation failed
   * Invalid DNS records

   >[!NOTE]
   >
   >The possible configuration failure reasons are listed in [this section](../configuration/channel-surfaces.md).

1. Resolve the issue:

   * Update the channel configuration as needed.
   * You may need to fix specific DNS issues mentioned in the alert.

   >[!NOTE]
   >
   >As a single domain can be associated with multiple channel configurations, resolving DNS issues for one channel configuration may automatically fix related issues across several configurations.

If the change does not resolve the issue, the same alert will be triggered again the next day.

When resolving email configuration issues, keep in mind the best practices listed below:

* Act promptly - Address configuration failures as soon as they are detected to avoid disruptions in email delivery.
* Check all configurations - If the alert indicates multiple impacted email configurations, review and fix each of them.

### AJO domain certificates renewal unsuccessful {#alert-certificates-renewal}

This alert warns you if a domain certificate (CDN, tracking URL) renewal failed for a specific Journey Optimizer subdomain.-->





