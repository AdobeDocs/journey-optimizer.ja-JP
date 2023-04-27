---
solution: Journey Optimizer
product: journey optimizer
title: Web サブドメインの設定
description: Journey Optimizerで Web サブドメインを設定する方法を説明します
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
keywords: web，サブドメイン，設定
source-git-commit: 803c9f9f05669fad0a9fdeeceef58652b6dccf70
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 6%

---

# Web サブドメインの設定 {#web-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_header"
>title="Web サブドメインをデリゲート"
>abstract="Web チャネル用にサブドメインを設定します。 既に Delegated にデリゲートされているサブドメインからAdobeします。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web"
>title="Web サブドメインをデリゲート"
>abstract="Adobe Experience Manager Assets Essentialsからのコンテンツを Web エクスペリエンスに追加する場合は、このコンテンツの公開に使用するサブドメインを設定する必要があります。 既にAdobeにデリゲートされたサブドメインの中から選択します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_default"
>title="デフォルトのサブドメインを設定"
>abstract="複数の Web サブドメインを作成できますが、デフォルトのサブドメインのみが使用されます。 デフォルトの Web サブドメインは変更できますが、一度に 1 つのみ使用できます。"

Web エクスペリエンスの作成時に、 [Adobe Experience Manager Assets Essentials](../email/assets-essentials.md) ライブラリの場合、このコンテンツの公開に使用するサブドメインを設定する必要があります。

そのためには、既に Delegated にデリゲートされているサブドメインのリストからAdobeする必要があります。 サブドメインのアドビへのデリゲートについて詳しくは、[この節](../configuration/delegate-subdomain.md)で説明します。

>[!CAUTION]
>
>Web サブドメインの設定は、すべての環境で共通です。 したがって、
>
>* Web サブドメインにアクセスして編集するには、 **[!UICONTROL Web サブドメインの管理]** 実稼動サンドボックスに対する権限。
>
> * Web サブドメインを変更すると、実稼働用サンドボックスにも影響します。


複数の Web サブドメインを作成できますが、 **デフォルト** サブドメインが使用されます。 デフォルトの Web サブドメインは変更できますが、一度に 1 つのみ使用できます。

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** メニューから、 **[!UICONTROL Web 設定]** > **[!UICONTROL Web サブドメイン]**.

   ![](assets/web-access-subdomains.png)

1. 「**[!UICONTROL サブドメインを設定]**」をクリックします。

1. リストからデリゲートされたサブドメインを選択します。

   ![](assets/web-subdomain-details.png)

   >[!NOTE]
   >
   >既に Web サブドメインとして使用されているサブドメインは選択できません。

1. このサブドメインをデフォルトとして設定するには、対応するオプションを選択します。

   ![](assets/web-subdomain-details-default.png)

   >[!NOTE]
   >
   >次の項目のみ **デフォルト** サブドメインが使用されます。 デフォルトの Web サブドメインは変更できますが、一度に 1 つのみ使用できます。

1. 「**[!UICONTROL 送信]**」をクリックします。サブドメインは **[!UICONTROL 成功]** ステータス。 これで、Web エクスペリエンスで使用する準備が整いました。

1. この **[!UICONTROL デフォルト]** バッジは、現在デフォルトとして使用されているサブドメインの横に表示されます。 デフォルトのサブドメインを変更するには、 **[!UICONTROL デフォルトとして設定]** から **[!UICONTROL その他のアクション]** ボタンをクリックします。

   ![](assets/web-subdomain-default.png)

   <!--Only a subdomain with the **[!UICONTROL Success]** status can be set as default.-->

1. 削除できるのは **[!UICONTROL 失敗]** サブドメインを使用してリストをクリーンアップします。 それには、「 **[!UICONTROL 削除]** から **[!UICONTROL その他のアクション]** ボタンをクリックします。

<!--You cannot delete a subdomain with the **[!UICONTROL Processing]** status.-->

