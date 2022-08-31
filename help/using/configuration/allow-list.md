---
title: 許可リスト
description: 許可リストの使用方法を説明します。
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
source-git-commit: 28380dbadf485ba05f7ef6788a50253876718441
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 96%

---

# 許可リスト {#allow-list}

特定の送信セーフリストを[サンドボックス](../administration/sandboxes.md)レベルで定義して、セキュリティで保護されたテスト用の環境を用意することができます。

ミスが発生する可能性のある非実稼動インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。

>[!NOTE]
>
>この機能は、実稼動サンドボックスと実稼動以外のサンドボックスで使用できます。

許可リストを使用すると、特定のサンドボックスから送信するメールを受信する権限のある唯一の受信者またはドメインとなる個々のメールアドレスまたはドメインを指定できます。これにより、テスト環境で実際の顧客アドレスに誤ってメールを送信するのを防ぐことができます。

>[!CAUTION]
>
>これはメールチャネルにのみ適用されます。

## 許可リストへのアクセス {#access-allowed-list}

許可されたメールアドレスとドメインの詳細なリストにアクセスするには、**[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**&#x200B;に移動し、「**[!UICONTROL 許可リスト]**」を選択します。

>[!CAUTION]
>
>許可リストの表示、エクスポートおよび管理を行う権限は、[ジャーニー管理者](../administration/ootb-product-profiles.md#journey-administrator)にのみ付与されます。[!DNL Journey Optimizer] ユーザーのアクセス権の管理について詳しくは、[この節](../administration/permissions-overview.md)を参照してください。

## 許可リストの有効化 {#enable-allow-list}

許可リストを有効にするには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL メール設定]**／**[!UICONTROL 許可リスト]**&#x200B;メニューにアクセスします。

1. 「**[!UICONTROL 編集]**」をクリックします。

1. 「**[!UICONTROL 許可リストを有効化]**」を選択します。

1. 「**[!UICONTROL 保存]**」をクリックします。この許可リストは有効です。

許可リストのロジックは、この機能が有効な場合に適用されます。 詳しくは、[この節](#logic)を参照してください。

>[!NOTE]
>
>有効にすると、ジャーニーの実行時に許可リスト機能がアクティブになりますが、[配達確認](../design/preview.md#send-proofs)を使用してメッセージをテストし、[テストモード](../building-journeys/testing-the-journey.md)を使用してジャーニーをテストする場合にも機能します。

## 許可リストへのエンティティの追加 {#add-entities}

特定のサンドボックス用に新しい電子メールアドレスまたは許可リストをドメインに追加するには、 [API 呼び出し](#api-call-allowed-list).

>[!NOTE]
>
>許可リストには、最大 1,000 個のエントリを含めることができます。

### API 呼び出しを使用したエンティティの追加 {#api-call-allowed-list}

許可リストに入力するには、`listType` 属性に `ALLOWED` 値を指定して抑制 API を呼び出すこともできます。例えば：

![](assets/allow-list-api.png)

「**追加**」、「**削除**」および「**取得**」の操作を実行できます。

API 呼び出しについて詳しくは、 [Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=ja){target=&quot;_blank&quot;} リファレンスドキュメントを参照してください。

## 許可リストのロジック {#logic}

許可リストが[有効](#enable-allow-list)の場合、次のロジックが適用されます。

* 許可リストが&#x200B;**空**&#x200B;の場合、メールは送信されません。

* エンティティが&#x200B;**許可リストに登録されており**、抑制リストに登録されていない場合は、対応する受信者にメールを送信できます。ただし、エンティティが[抑制リスト](../reports/suppression-list.md)にも登録されている場合、対応する受信者にはメールは届きません（**[!UICONTROL 抑制されている]**&#x200B;ことが理由）。

* エンティティが&#x200B;**許可リストに登録されていない**（かつ抑制リストにも登録されていない）場合、対応する受信者にはメールは届きません（**[!UICONTROL 許可されていない]**&#x200B;ことが理由）。

>[!NOTE]
>
>「**[!UICONTROL 許可されていない]**」のステータスを持つプロファイルは、メッセージ送信プロセス中に除外されます。したがって、**ジャーニーレポート**&#x200B;では、これらのプロファイルがジャーニー（[セグメントを読み取り](../building-journeys/read-segment.md)アクティビティと[メッセージアクティビティ](../building-journeys/journeys-message.md)）内を移動したものとして表示されますが、これらはメール送信前に除外されるので、**メールレポート**&#x200B;では、**[!UICONTROL 送信済み]**&#x200B;指標に含まれません。
>
>詳しくは、[ライブレポート](../reports/live-report.md)と[グローバルレポート](../reports/global-report.md)を参照してください。

## 除外レポート {#reporting}

実稼働以外のサンドボックスでこの機能を有効にすると、許可リストに登録されていなかったので送信から除外されたメールアドレスやドメインを取得できます。それには、[Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html?lang=ja){target=&quot;_blank&quot;} を使用して、以下の API 呼び出しを行います。

受信者が許可リストに登録されていなかったので送信されなかった&#x200B;**メールの数**&#x200B;を取得するには、次のクエリを使用します。

```sql
SELECT count(distinct _id) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID = '<MESSAGE_EXECUTION_ID>' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

受信者が許可リストに登録されていなかったので送信されなかった&#x200B;**メールアドレスのリスト**&#x200B;を取得するには、次のクエリを使用します。

```sql
SELECT distinct(_experience.customerJourneyManagement.emailChannelContext.address) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID IS NOT NULL AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```
