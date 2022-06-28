---
title: ランディングページのサブドメインの設定
description: Journey Optimizer でランディングページのサブドメインを設定する方法を説明します
role: Admin
level: Intermediate
exl-id: dd1af8dc-3920-46cb-ae4d-a8f4d4c26e89
source-git-commit: 8fe960e490722878dfd6dce52a88c3a9ccb037c2
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 91%

---

# ランディングページのサブドメインの設定 {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain"
>title="ランディングページプリセットの作成"
>abstract="ランディングページプリセットを作成できるようにするには、少なくとも 1 つのランディングページサブドメインを、サブドメイン名リストから選択するように事前に設定しておく必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/lp-configuration.html?lang=ja#lp-create-preset" text="ランディングページプリセットを作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_lp"
>title="ランディングページのサブドメインをデリゲート"
>abstract="ランディングページプリセットを作成するにはこのサブドメインが必要なので、ランディングページで使用するサブドメインを設定する必要があります。既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/lp-configuration.html#lp-create-preset" text="ランディングページプリセットを作成"

[ランディングページプリセットの作成](lp-presets.md)を可能にするには、ランディングページに使用するサブドメインをセットアップする必要があります。

既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。サブドメインのアドビへのデリゲートについて詳しくは、[この節](delegate-subdomain.md)で説明します。

## 既存のサブドメインを使用 {#lp-use-existing-subdomain}

既にアドビにデリゲートされているサブドメインを使用するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスして、**[!UICONTROL メール設定]**／**[!UICONTROL ランディングページのサブドメイン]**&#x200B;を選択します。

   ![](assets/lp_access-subdomains.png)

1. 「**[!UICONTROL サブドメインを設定]**」をクリックします。

   ![](assets/lp_set-up-subdomain.png)

1. 「**[!UICONTROL 設定タイプ]** 」セクションから「**[!UICONTROL デリゲートドメインを使用]**」を選択します。

   ![](assets/lp_use-delegated-subdomain.png)

1. ランディングページの URL に表示するプレフィックスを入力します。

   >[!NOTE]
   >
   >英数字とハイフンのみが使用できます。

1. リストからデリゲートされたサブドメインを選択します。

   >[!NOTE]
   >
   >既にランディングページのサブドメインとして使用されているサブドメインは選択できません。

   ![](assets/lp_prefix-and-subdomain.png)

   同じ親ドメインの複数のデリゲートサブドメインを使用することはできません。 例えば、marketing1.yourcompany.com が既にランディングページのAdobeに委任されている場合、marketing2.yourcompany.com を使用することはできません。 ただし、ランディングページでは複数レベルのサブドメインがサポートされているので、「email.marketing1.yourcompany.com」を使用できます。

   <!--For landing pages, multi-level subdomains are supported. For example, you can use 'email.marketing.yourcompany.com'.-->

   >[!CAUTION]
   >
   >[CNAME メソッド](delegate-subdomain.md#cname-subdomain-delegation)を使用してアドビにデリゲートされたドメインを選択する場合、ホスティングプラットフォーム上に DNS レコードを作成する必要があります。DNS レコードを生成する手順は、新しいランディングページサブドメインを設定する際の手順と同じです。[この節](#lp-configure-new-subdomain)でその方法を説明します。

1. 「**[!UICONTROL 送信]**」をクリックします。

1. 送信されると、サブドメインは&#x200B;**[!UICONTROL 処理中]**&#x200B;ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。<!--Same statuses?-->

   ![](assets/lp_subdomain-processing.png)

   >[!NOTE]
   >
   >そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（最大で 4 時間かかることがあります）。<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。ランディングページプリセットの作成に使用する準備が整いました。

## 新しいサブドメインを設定 {#lp-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_lp_subdomain_dns"
>title="一致する DNS レコードを生成"
>abstract="新しいランディングページのサブドメインを設定するには、Journey Optimizer インターフェイスに表示されるアドビのネームサーバー情報をコピーし、ドメインホストソリューションに貼り付けて、一致する DNS レコードを生成する必要があります。チェックが正常に完了すると、ランディングページプリセットの作成にサブドメインを使用する準備が整います。"

新しいサブドメインを設定するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスして、**[!UICONTROL メール設定]**／**[!UICONTROL ランディングページのサブドメイン]**&#x200B;を選択します。

1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。

1. 「 **[!UICONTROL 設定タイプ]** 」セクションから「**[!UICONTROL 独自のドメインを追加]**」を選択します。

   ![](assets/lp_add-your-own-subdomain.png)

1. デリゲートするサブドメインを指定します。

   >[!CAUTION]
   >
   >既存のランディングページのサブドメインは使用できません。

   無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。

   >[!NOTE]
   >
   >ランディングページでは、複数レベルのサブドメインがサポートされます。 例えば、「email.marketing.yourcompany.com」を使用できます。

   <!--Journey Optimizer currently does not support multiple subdomains of the same parent domain for landing page configuration-->

1. DNS サーバーに配置するレコードが表示されます。このレコードをコピーするか、CSV ファイルをダウンロードしてから、ドメインをホストするソリューションに移動し、一致する DNS レコードを生成します。

1. DNS レコードがドメインホスティングソリューションに生成されていることを確認します。すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](assets/lp_add-your-own-subdomain-confirm.png)

   >[!NOTE]
   >
   >新しいランディングページのサブドメインを設定すると、常に CNAME レコードを指すようになります。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。<!--Same statuses?-->

   >[!NOTE]
   >
   >そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（最大で 4 時間かかることがあります）。<!--Learn more in [this section](#subdomain-validation).-->

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。ランディングページプリセットの作成に使用する準備が整いました。

   ホスティングソリューションで検証レコードを作成できなかった場合、サブドメインは「**[!UICONTROL 失敗]**」とマークされます。
