---
solution: Journey Optimizer
product: journey optimizer
title: 許可リスト
description: 許可リストの使用方法について
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
exl-id: 70ab8f57-c132-4de1-847b-11f0ab14f422
source-git-commit: 020c4fb18cbd0c10a6eb92865f7f0457e5db8bc0
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 0%

---

# 許可リスト {#allow-list}

サンドボックス ](../administration/sandboxes.md) レベルで [ 特定の送信セーフリストを定義することができます。

このリストでは、個々の電子メールアドレスまたはドメインを指定して、特定のサンドボックスから送信する電子メールの受信を承認された受信者またはドメインを指定することができます。

>[!NOTE]
>
>この機能は、プロダクションサンドボックスと非プロダクションサンドボックスで使用できます。

例えば、不正なインスタンスが生成され、その失敗が発生する可能性がある場合は、許可リストを使用して、不要なメッセージを実際の顧客の住所に送信することはできません。したがって、テスト目的には安全な環境が提供されます。

また、許可リストがアクティブである場合は、メールは送信されません。 そのため、何らかの大きな問題が発生した場合は、この機能を使用して、問題を解決するまで、発信されていない通信 [!DNL Journey Optimizer] をすべて停止することができます。 許可されたリストのロジック ](#logic) について詳しくは、 [ こちらを参照してください。

>[!CAUTION]
>
>この機能は、電子メールチャンネルにのみ適用されます。

## 許可リストへのアクセス {#access-allowed-list}

許可されている電子メールアドレスとドメインの詳細リストにアクセスするには、> **[!UICONTROL Channels]** > **[!UICONTROL Email configuration]** に **[!UICONTROL Administration]** 移動し、「」を選択 **[!UICONTROL Allowed list]** します。

![](assets/allow-list-access.png)

>[!CAUTION]
>
>許可リストの表示、エクスポートおよび管理の権限は、旅 ](../administration/ootb-product-profiles.md#journey-administrator) に [ 制限されます。この節 ](../administration/permissions-overview.md) では、 [ ユーザーによるアクセス権の管理 [!DNL Journey Optimizer] について詳しく説明しています。

許可リストを CSV ファイルとして書き出すには **[!UICONTROL Download CSV]** 、「ボタン」を選択します。

ボタンを使用して **[!UICONTROL Delete]** 、エントリを永久的に削除します。

電子メールアドレスまたはドメインを検索して、に **[!UICONTROL Address type]** フィルターを適用することができます。 選択すると、リストの上部に表示されているフィルターをオフにすることができます。

![](assets/allowed-list-filtering-example.png)

## 許可リストの有効化 {#enable-allow-list}

許可リストを有効にするには、次の手順に従います。

1. > **[!UICONTROL Email configuration]** > **[!UICONTROL Allow list]** メニューに **[!UICONTROL Channels]** アクセスします。

1. 切り替えボタンを選択します。

   ![](assets/allow-list-edit.png)

1. を選択 **[!UICONTROL Activate allowed list]** します。 許可リストが有効になりました。

   ![](assets/allow-list-enable.png)

   >[!NOTE]
   >
   >許可リストをアクティブ化した後は、5分間のレイテンシーが journeys とキャンペーンに反映されます。

許可されたリストのロジックは、機能がアクティブになったときに適用されます。 詳しくは、ここを [ ](#logic) 参照してください。

>[!NOTE]
>
>この機能が有効になっていると、journeys を実行するときに許可リストの機能が受け入れられます。また、テストモード ](../building-journeys/testing-the-journey.md) を使用して [ 、プレビューおよびテスト journeys で [ ](../email/preview.md#send-proofs) メッセージをテストする場合にも使用できます。

## 許可リストの無効化 {#deactivate-allow-list}

許可リストを非アクティブ化するには、次の手順に従います。

1. > **[!UICONTROL Email configuration]** > **[!UICONTROL Allow list]** メニューに **[!UICONTROL Channels]** アクセスします。

1. 切り替えボタンを選択します。

   ![](assets/allow-list-edit-active.png)

1. を選択 **[!UICONTROL Deactivate allowed list]** します。 許可リストはアクティブではありません。

   ![](assets/allow-list-deactivate.png)

   >[!NOTE]
   >
   >許可されたリストを非アクティブ化した後は、5分間の遅延が発生し、journeys とキャンペーンに反映されます。

許可されたリストのロジックは、機能が非アクティブになったときには適用されません。 詳しくは、ここを [ ](#logic) 参照してください。

## 許可された一覧へのエンティティの追加 {#add-entities}

特定のサンドボックスについて、新しい電子メールアドレスまたはドメインを許可リストに追加するには、 [ リスト ](#manually-populate-list) を手動で設定するか、API 呼び出し ](#api-call-allowed-list) を使用 [ します。

>[!NOTE]
>
>許可リストには最大1000エントリを含めることができます。

### 許可リストに手動で値を設定します。 {#manually-populate-list}

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_add_header"
>title="許可リストへのアドレスまたはドメインの追加"
>abstract="新しい電子メールアドレスまたはドメインを、許可リストに手動で追加するには、それらを1つ選択します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_add"
>title="許可リストへのアドレスまたはドメインの追加"
>abstract="新しい電子メールアドレスまたはドメインを、許可リストに手動で追加するには、それらを1つ選択します。"

ユーザーインターフェイスを使用して電子メールアドレスまたはドメインを追加することで、許可リストに [!DNL Journey Optimizer] 手動で値を設定することができます。

>[!NOTE]
>
>一度に追加できる電子メールアドレスまたはドメインは1つだけです。

これを行うには、次の手順を実行します。

1. **[!UICONTROL Add email or domain]**&#x200B;ボタンを選択します。

   ![](assets/allowed-list-add-email.png)

1. アドレスタイプ **[!UICONTROL Email address]** **[!UICONTROL Domain address]** を選択します。

1. 電子メールの送信先の電子メールアドレスまたはドメインを入力します。

   >[!NOTE]
   >
   >有効な電子メールアドレス (abc@company.com など) またはドメイン (abc.company.com など) を入力していることを確認してください。

1. 必要に応じて、理由を指定します。

   ![](assets/allowed-list-add-email-address.png)

   >[!NOTE]
   >
   >32と126の間で構成されている ASCII 文字はすべて、 **[!UICONTROL Reason]** フィールドに使用できます。 完全なリストについては、次のページ ](https://en.wikipedia.org/wiki/Wikipedia:ASCII#ASCII_printable_characters) を参照 [ してください。 {target = &quot;_blank&quot;} などが挙げられます。

1. をクリック **[!UICONTROL Submit]** します。

### API 呼び出しを使用したエンティティの追加 {#api-call-allowed-list}

許可リストに追加するには、その `listType` 属性の値を使用して `ALLOWED` 抑制 API を呼び出すこともできます。例えば：

![](assets/allow-list-api.png)

「追加 **」、「削除** 」および **「取得** 」 **の** 操作を実行できます。

Adobe エクスペリエンスプラットフォーム Api ](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html) での API 呼び出しの作成について詳しくは、 [ {target = &quot;_blank&quot;} リファレンスマニュアルを参照してください。

## 許可されたリストのロジック {#logic}

>[!CONTEXTUALHELP]
>id="ajo_admin_allowed_list_logic"
>title="許可リストの管理"
>abstract="許可リストがアクティブになっているときは、許可リストに含まれる受信者のみがこのサンドボックスから電子メールメッセージを受け取ることができます。 非アクティブにすると、すべての受信者が電子メールを受信するようになります。"

許可リストが [ アクティブな ](#enable-allow-list) 場合は、次のロジックが適用されます。

* 許可リストが **空** の場合、電子メールは送信されません。

* エンティティが許可 **リストに含まれていて、抑制リストでは** ない場合は、該当する受信者に電子メールが送信されます。ただし、エンティティが抑制リスト ](../reports/suppression-list.md) に [ も含まれている場合は、対応する受信者が電子メール、つまり、その理由 **[!UICONTROL Suppressed]** を受信することはできません。

* エンティティが **許可リスト** に含まれていなくて、抑制リストに含まれていない場合は、対応する受信者が電子メール、つまりその理由 **[!UICONTROL Not allowed]** を受信することはできません。

>[!NOTE]
>
>ステータスが表示されているプロファイル **[!UICONTROL Not allowed]** は、メッセージ送信処理中に除外されます。 そのため、これらのプロファイルは、旅中 **** に移動されるように ( [ セグメント ](../building-journeys/read-segment.md) の読み取りと [ メッセージアクティビティー ](../building-journeys/journeys-message.md) に) **** 、その後、電子メールを送信する前にフィルターが適用されているので、そのレポートではメトリックに **[!UICONTROL Sent]** は表示されません。
>
>ライブレポート ](../reports/live-report.md) と [ グローバルレポート ](../reports/global-report.md) について [ 詳しく説明します。

許可リストが [ 非アクティブ ](#deactivate-allow-list) 化されている場合は、現在のサンドボックスから送信しているすべての電子メールが、実際の顧客住所を含めて、すべての受信者に送信されます。

## 除外レポート {#reporting}

許可リストがアクティブな場合は、許可リストに含まれていないので、送信から除外された電子メールアドレスまたはドメインを取得することができます。 そのためには、Adobe エクスペリエンス Platform のクエリサービス ](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html) {target = &quot;_blank&quot;} を使用 [ して以下の API 呼び出しを行います。

受信者が許可リストに含まれていないために送信されなかった電子メール **の数を取得** するには、次のクエリーを使用します。

```sql
SELECT count(distinct _id) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID = '<MESSAGE_EXECUTION_ID>' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

受信者が許可されていない電子メールアドレス **のリストを取得** するには、次のクエリーを使用します。

```sql
SELECT distinct(_experience.customerJourneyManagement.emailChannelContext.address) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID IS NOT NULL AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```
