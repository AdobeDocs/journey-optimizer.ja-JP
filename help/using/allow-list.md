---
title: 許可リスト
description: 許可リストの使用方法を説明します。
feature: Deliverability
topic: Content Management
role: User
level: Intermediate
source-git-commit: 9408a93deecfb12f28a0a87c19fa0074c66844a9
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 56%

---

# 許可リスト {#allow-list}

特定の送信セーフリストを[サンドボックス](administration/sandboxes.md)レベルで定義して、テスト目的の安全な環境を構築できるようになりました。ミスが発生する可能性のある非実稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。

許可リストを使用すると、特定のサンドボックスから送信するメールを受信する権限のある唯一の受信者またはドメインとなる個々のメールアドレスまたはドメインを指定できます。これにより、テスト環境で実際の顧客アドレスに誤ってメールを送信するのを防ぐことができます。

>[!CAUTION]
>
>この機能は、実稼動用サンドボックスでは使用&#x200B;**できません**。 Eメールチャネルにのみ適用されます。

## 許可リストの有効化 {#enable-allow-list}

実稼動以外のサンドボックスで許可リストを有効にするには、メッセージプリセットサービスの対応するAPIエンドポイントを使用して、一般設定を更新する必要があります。

* このAPIを使用して、いつでもこの機能を無効にすることもできます。

* この機能を有効にする前または後に許可リストを更新することができます。

* 許可リストロジックは、許可リストが空でない場合に&#x200B;**および**&#x200B;が有効になっている場合に適用されます。 ****&#x200B;詳しくは、[この節](#logic)を参照してください。

<!--To enable this feature on a non-production sandbox, update the allowed list so that it is no longer empty. To disable it, clear up the allowed list so that it is again empty.

Learn more on the allowed list logic in this section.
-->

>[!NOTE]
>
>有効にすると、ジャーニーの実行時に許可リスト機能がアクティブになりますが、[配達確認](preview.md#send-proofs)を使用してメッセージをテストし、[テストモード](building-journeys/testing-the-journey.md)を使用してジャーニーをテストする場合にも機能します。

## 許可リストへのエンティティの追加 {#add-entities}

特定のサンドボックスの許可リストに新しいメールアドレスまたはドメインを追加するには、`listType` 属性に `ALLOWED` の値を指定して抑制 API を呼び出す必要があります。例えば：

![](assets/allow-list-api.png)

「**追加**」、「**削除**」および「**取得**」の操作を実行できます。

>[!NOTE]
>
>許可リストには、最大 1,000 個のエントリを含めることができます。

<!--
Learn more on making these API calls in the API reference documentation.
Found this link in Experience Platform documentation, but may not be the final one: (https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en).-->

## 許可リストロジック {#logic}

<!-- When the allowed list is enabled (enable-allow-list) at the sandbox level using the API call above, the following applies.-->

許可リストが&#x200B;**空**&#x200B;の場合、許可リストロジックは適用されません。 つまり、プロファイルが[抑制リスト](suppression-list.md)に含まれていない限り、任意のプロファイルにメールを送信できるということです。

許可リストが&#x200B;**空でない**&#x200B;場合、許可リストロジックが適用されます。

* エンティティが&#x200B;**許可リストになく**、抑制リストにもない場合、対応する受信者はメールを受信しません（**[!UICONTROL 許可されていない]**&#x200B;ことが理由）。

* エンティティが&#x200B;**許可リストにあり**、抑制リストにない場合は、対応する受信者にメールを送信できます。ただし、エンティティが[抑制リスト](suppression-list.md)にも登録されている場合、対応する受信者はメールを受信しません（**[!UICONTROL 抑制されている]**&#x200B;ことが理由）。

>[!NOTE]
>
>「**[!UICONTROL 許可されていません]**」ステータスのプロファイルは、メッセージ送信プロセス中に除外されます。 したがって、**ジャーニーレポート**&#x200B;は、ジャーニー（[セグメントの読み取り](building-journeys/read-segment.md)および[メッセージ](building-journeys/journeys-message.md)）を通過したとプロファイルを表示しますが、電子メールが除外される前は、**送信された**&#x200B;指標には含まれません送信中&#x200B;****
>
>[ライブレポート](reports/live-report.md)と[グローバルレポート](reports/global-report.md)の詳細をご覧ください。

## 除外レポート {#reporting}

この機能が実稼動以外の許可リストで有効になっている場合、サンドボックス上にないので、送信から除外された電子メールアドレスまたはドメインを取得できます。 これをおこなうには、[Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/api/getting-started.html){target=&quot;_blank&quot;}を使用して、以下のAPI呼び出しをおこないます。

受信者が許可リストにいなかったために送信されなかった&#x200B;**電子メール**&#x200B;の数を取得するには、次のクエリを使用します。

```
SELECT count(distinct _id) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID = '<MESSAGE_EXECUTION_ID>' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

受信者が許可リストにいなかったために送信されなかった電子メールアドレス&#x200B;**の**&#x200B;リストを取得するには、次のクエリを使用します。

```
SELECT distinct(_experience.customerJourneyManagement.emailChannelContext.address) from cjm_message_feedback_event_dataset WHERE
_experience.customerJourneyManagement.messageExecution.messageExecutionID IS NOT NULL AND
_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus = 'exclude' AND
_experience.customerJourneyManagement.messageDeliveryfeedback.messageExclusion.reason = 'EmailNotAllowed'
```

