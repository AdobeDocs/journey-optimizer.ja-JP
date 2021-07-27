---
title: 許可リスト
description: 許可リスト
feature: 配信品質
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 2d03285400b86b2c296997537852bb89ae0f6d0a
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 1%

---

# 許可リスト {#allow-list}

[サンドボックス](administration/sandboxes.md)レベルで特定の送信セーフリストを定義して、テスト目的で安全な環境を構築できるようになりました。 実稼動以外のインスタンスでエラーが発生する可能性がある場合は、許可リストによって、不要なメッセージが顧客に送信されるリスクがなくなります。

「 」許可リストを使用すると、個々の電子メールアドレスまたはドメインを指定できます。このドメインは、特定のサンドボックスから送信される電子メールを受信する権限を持つ唯一の受信者またはドメインです。 これにより、テスト環境で実際の顧客アドレスに誤ってEメールを送信するのを防ぐことができます。


>[!CAUTION]
>
>この機能は、実稼動用サンドボックスでは&#x200B;**使用できません**。 これはEメールチャネルにのみ適用されます。


## 許可リスト {#enable-allow-list}

実稼動以外の許可リストでサンドボックスを有効にするには、空にならないように許可リストを更新します。 この機能を無効にするには、リストをクリアして、再び空にします。

<!--
you need to make an Adobe API call.

* Using this API, you can also disable the feature at any time.

* You can update the allowed list before or after enabling the feature.

* The allowed list logic applies when the feature is enabled and if the allowed list is not empty. Learn more in [this section](#logic).

-->
>[!NOTE]
>
>有効にすると、ジャーニーの実行時に許可リスト機能が有効になりますが、[配達確認](preview.md#send-proofs)を使用してメッセージをテストし、[テストモード](building-journeys/testing-the-journey.md)を使用してジャーニーをテストする場合にも機能します。

## エンティティの許可リスト {#add-entities}

新しい電子メールアドレスまたはドメインを特定のサンドボックスの許可リストに追加するには、`listType`属性の`ALLOWED`値でSuppression APIを呼び出す必要があります。 次に例を示します。

![](assets/allow-list-api.png)

**Add**、**Delete**&#x200B;および&#x200B;**Get**&#x200B;操作を実行できます。

>[!NOTE]
>
>許可リストには、最大1,000個のエントリを含めることができます。

<!--
Learn more on making Adobe API calls in the [Experience Platform documentation](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en).
-->


## 許可リスト論理 {#logic}

<!-- When the allowed list is [enabled](#enable-allow-list) at the sandbox level using the API call above, the following applies.-->

許可リストが&#x200B;**empty**&#x200B;の場合、許可リストロジックは適用されません。 つまり、[抑制リスト](suppression-list.md)に登録されていない場合は、任意のプロファイルにEメールを送信できます。

許可リストが&#x200B;**空でない**&#x200B;場合、許可リストロジックが適用されます。

* エンティティが許可リスト&#x200B;**になく、抑制リストにもない場合、対応する受信者はEメールを受け取りません（理由は**[!UICONTROL &#x200B;許可されていません&#x200B;]**）。**

* 許可リスト&#x200B;**のエンティティが**&#x200B;で、抑制リストにない場合は、対応する受信者にEメールを送信できます。 ただし、エンティティが[抑制リスト](suppression-list.md)にも登録されている場合、対応する受信者はEメールを受信しません。理由は「**[!UICONTROL 抑制]**」です。




