---
solution: Journey Optimizer
product: journey optimizer
title: サブドメインに Google TXT レコードを追加します。
description: サブドメインに Google TXT レコードを追加する方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: 311eb2d1-e445-43e6-bc2c-c6288b637f47
source-git-commit: c6498633fdfdc9442203a3bf980f1b12bd1c6a6b
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# サブドメインに Google TXT レコードを追加します。 {#google-txt-record}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_google"
>title="Google TXT レコード"
>abstract="電子メールが Gmail アドレスへ確実に配信されるようにするには、特別な Google site verify TXT レコードをサブドメインに追加し、検証が行われるようにすることができます。"

TXT レコードは、ドメインについてのテキスト情報を提供するために使用される DNS レコードの一種であり、外部ソースによって読み取ることができます。

最適な deliverability を使用して、Gmail アドレスへの電子メール配信が成功するようにするために、ドメインに対して特別な Google site verify TXT レコードを追加することで、 [!DNL Journey Optimizer] それらが検証されるようにすることができます。

>[!CAUTION]
>
> この操作は、 **[!UICONTROL Success]** サブドメインに状態がある場合にのみ実行できます。 サブドメインの状態について詳しくは、この節 ](about-subdomain-delegation.md#access-delegated-subdomains) を [ 参照してください。

サブドメインに Google TXT レコードを追加するには、次の手順を実行します。

1. / **[!UICONTROL Subdomains]** メニューから **[!UICONTROL Channels]** サブドメインを開きます。

1. **[!UICONTROL Google txt record]**&#x200B;セクションで、Google Workspace ](https://support.google.com/a/answer/183895) から [ 生成された検証コードを入力し、target = &quot;_blank&quot;} <!--G Suite Admin tools--> をクリック **[!UICONTROL Save]** します。

   ![](assets/subdomain-google-txt.png)

1. TXT レコードが追加されたら、Google はそのレコードを確認する必要があります。 これを行うには、Google Workspace ](https://support.google.com/a/answer/183895) に [ 移動します {target = &quot;_blank&quot;} <!--G Suite Admin tools--> 、検証手順を起動します。
