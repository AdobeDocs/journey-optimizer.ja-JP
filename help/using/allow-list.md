---
title: 許可リスト
description: 許可リスト
feature: 配信品質
topic: コンテンツ管理
role: User
level: Intermediate
source-git-commit: 288c27d4fc64a6d0a6f07b634ed044a6e858d0c1
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 2%

---

# 許可リスト {#allow-list}

[サンドボックス](administration/sandboxes.md)レベルで特定の送信セーフリストを定義して、テスト目的で安全な環境を構築できるようになりました。 実稼動以外のインスタンスでエラーが発生する可能性がある場合は、許可リストによって、不要なメッセージが顧客に送信されるリスクがなくなります。

>[!CAUTION]
>
>この機能は、実稼動用サンドボックスでは使用できません。

「 」許可リストを使用すると、個々の電子メールアドレスまたはドメインを指定できます。このドメインは、特定のサンドボックスから送信される電子メールを受信する権限を持つ唯一の受信者またはドメインです。 これにより、テスト環境で実際の顧客アドレスに誤ってEメールを送信するのを防ぐことができます。

>[!NOTE]
>
>この機能は、Eメールチャネルにのみ適用されます。

## 許可リスト {#enable-allow-list}

実稼動以外のサンドボックスで許可リストを有効にするには、AdobeAPI呼び出しをおこなう必要があります。

* このAPIを使用して、いつでもこの機能を無効にすることもできます。

* この機能を有効にする前または後に許可リストを更新することができます。

* 許可リストロジックは、この機能が有効で、許可リストが空でない場合に適用されます。 詳しくは、[この節](#logic)を参照してください。

>[!NOTE]
>
>有効にすると、ジャーニーの実行時に許可リスト機能が有効になりますが、[配達確認](preview.md#send-proofs)を使用してメッセージをテストし、[テストモード](building-journeys/testing-the-journey.md)を使用してジャーニーをテストする場合にも機能します。

## エンティティの許可リスト {#add-entities}

>[!CAUTION]
>
>この機能は、実稼動用サンドボックスでは&#x200B;**使用できません**。 これはEメールチャネルにのみ適用されます。

新しい電子メールアドレスまたはドメインを特定のサンドボックスの許可リストに追加するには、`listType`属性の`ALLOWED`値でSuppression APIを呼び出す必要があります。 次に例を示します。

![](assets/allow-list-api.png)

**Add**、**Delete**&#x200B;および&#x200B;**Get**&#x200B;操作を実行できます。

>[!NOTE]
>
>許可リストには、最大1,000個のエントリを含めることができます。

AdobeAPI呼び出しの実行に関する詳細は、[Experience Platformのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-guide.html?lang=en)を参照してください。

## 許可リスト論理 {#logic}

<!-- When the allowed list is \[enabled\]\(\add link here\) at the sandbox level using the API call above, the following applies.-->

1. 許可リストが&#x200B;**empty**&#x200B;の場合、許可リストロジックは適用されません。 つまり、[抑制リスト](suppression-list.md)に登録されていない場合は、任意のプロファイルにEメールを送信できます。

1. 許可リストが&#x200B;**空でない**&#x200B;場合、許可リストロジックが適用されます。

   * エンティティが許可リスト&#x200B;**になく、抑制リストにもない場合、対応する受信者はEメールを受け取りません（理由は**[!UICONTROL &#x200B;許可されていません&#x200B;]**）。**

   * 許可リスト&#x200B;**のエンティティが**&#x200B;で、抑制リストにない場合は、対応する受信者にEメールを送信できます。 ただし、エンティティが[抑制リスト](suppression-list.md)にも登録されている場合、対応する受信者はEメールを受信しません。理由は「**[!UICONTROL 抑制]**」です。




