---
title: 許可リスト
description: 許可リストの使用方法を説明します。
feature: 配信品質
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: e2743c8fa624a7a95b12c3adb5dc17a1b632c25d
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 86%

---

# 許可リスト {#allow-list}

特定の送信セーフリストを[サンドボックス](administration/sandboxes.md)レベルで定義して、テスト目的の安全な環境を構築できるようになりました。ミスが発生する可能性のある非実稼働インスタンスでは、許可リストにより、不要なメッセージが顧客に送信されるリスクがなくなります。

許可リストを使用すると、特定のサンドボックスから送信するメールを受信する権限のある唯一の受信者またはドメインとなる個々のメールアドレスまたはドメインを指定できます。これにより、テスト環境で実際の顧客アドレスに誤ってメールを送信するのを防ぐことができます。

>[!CAUTION]
>
>この機能は、実稼動用サンドボックスでは使用&#x200B;**できません**。 Eメールチャネルにのみ適用されます。

## 許可リストの有効化 {#enable-allow-list}

実稼動以外のサンドボックスでこの機能を有効にするには、空にならないように許可リストを更新します。 無効にするには、許可リストをクリアして、再度空にします。

許可リストロジックの詳細については、[この節](#logic)を参照してください。

<!--
To enable the allowed list on a non-production sandbox, you need to make an Adobe API call.

* Using this API, you can also disable the feature at any time.

* You can update the allowed list before or after enabling the feature.

* The allowed list logic applies when the feature is enabled and if the allowed list is not empty. Learn more in this section (logic).
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

<!--Learn more on making Adobe API calls in the [Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en).-->

## 許可リストロジック {#logic}

<!-- When the allowed list is enabled (enable-allow-list) at the sandbox level using the API call above, the following applies.-->

許可リストが&#x200B;**空**&#x200B;の場合、許可リストロジックは適用されません。 つまり、プロファイルが[抑制リスト](suppression-list.md)に含まれていない限り、任意のプロファイルにメールを送信できるということです。

許可リストが&#x200B;**空でない**&#x200B;場合、許可リストロジックが適用されます。

* エンティティが&#x200B;**許可リストになく**、抑制リストにもない場合、対応する受信者はメールを受信しません（**[!UICONTROL 許可されていない]**&#x200B;ことが理由）。

* エンティティが&#x200B;**許可リストにあり**、抑制リストにない場合は、対応する受信者にメールを送信できます。ただし、エンティティが[抑制リスト](suppression-list.md)にも登録されている場合、対応する受信者はメールを受信しません（**[!UICONTROL 抑制されている]**&#x200B;ことが理由）。




