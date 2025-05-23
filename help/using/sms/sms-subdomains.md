---
solution: Journey Optimizer
product: journey optimizer
title: テキストメッセージ（SMS／MMS）のサブドメイン設定
description: Journey Optimizer で SMS サブドメインを設定する方法を学ぶ
role: Admin
feature: SMS, Channel Configuration
level: Intermediate
keywords: SMS, サブドメイン, 設定
exl-id: 08a546d1-060c-43e8-9eac-4c38945cc3e1
source-git-commit: 19f127c2abc81239abda8ebd38bdcacee796a1b0
workflow-type: ht
source-wordcount: '928'
ht-degree: 100%

---

# SMS サブドメインの設定 {#sms-mms-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms_header"
>title="SMS／MMS サブドメインのデリゲート"
>abstract="テキストメッセージ（SMS／MMS）のサブドメインを設定します。既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_sms"
>title="SMS／MMS サブドメインのデリゲート"
>abstract="SMS 設定を作成するにはこのサブドメインが必要なので、テキストメッセージで使用するサブドメインを設定する必要があります。既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを設定できます。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="SMS 設定の作成"

>[!CONTEXTUALHELP]
>id="ajo_admin_config_sms_subdomain"
>title="SMS／MMS サブドメインの選択"
>abstract="SMS 設定を作成できるようにするには、少なくとも 1 つの SMS サブドメインを、サブドメイン名リストから選択するように事前に設定しておく必要があります。"
>additional-url="https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/sms/configure-sms/sms-configuration-surface" text="SMS 設定の作成"

## SMS サブドメインの基本を学ぶ {#gs-sms-mms-subdomains}

SMS／MMS メッセージに追加された URL を短縮できるようにするには、[SMS 設定を作成](sms-configuration.md#message-preset-sms)する際に選択するサブドメインを設定する必要があります。

既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。サブドメインのアドビへのデリゲートについて詳しくは、[この節](../configuration/delegate-subdomain.md)を参照してください。

SMS サブドメインの設定は、**すべての環境間で共有**&#x200B;されます。したがって、SMS サブドメインを変更すると、他の実稼動サンドボックスにも影響します。

SMS サブドメインにアクセスして編集するには、実稼動サンドボックスにおける **[!UICONTROL SMS サブドメインの管理]**&#x200B;権限が必要です。権限について詳しくは、[この節](../administration/high-low-permissions.md)を参照してください。

## 既存のサブドメインの使用 {#sms-use-existing-subdomain}

既にアドビにデリゲートされているサブドメインを使用するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューを参照して、**[!UICONTROL SMS 設定]**／**[!UICONTROL SMS サブドメイン]**&#x200B;を選択します。

1. 「**[!UICONTROL サブドメインを設定]**」をクリックします。

   ![](assets/sms_set-up-subdomain.png)

1. 「**[!UICONTROL 設定タイプ]**」セクションから「**[!UICONTROL デリゲートサブドメインを使用]**」を選択します。

   ![](assets/sms_use-delegated-subdomain.png)

1. SMS の URL に表示するプレフィックスを入力します。

   英数字とハイフンのみが使用できます。

1. リストからデリゲートされたサブドメインを選択します。

   既に SMS サブドメインとして使用されているサブドメインは選択できません。

   <!--Capital letters are not allowed in subdomains. TBC by PM-->

   ![](assets/sms_prefix-and-subdomain.png)

   <!--Note that you cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your SMS messages, you will not be able to use 'marketing2.yourcompany.com'. However, multi-level subdomains being supported for SMS, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.-->

   >[!CAUTION]
   >
   >[CNAME メソッド](../configuration/delegate-subdomain.md#cname-subdomain-delegation)を使用してアドビにデリゲートされたドメインを選択する場合、ホスティングプラットフォーム上に DNS レコードを作成する必要があります。DNS レコードを生成する手順は、新しい SMS サブドメインを設定する際の手順と同じです。[この節](#sms-configure-new-subdomain)でその方法を説明します。

1. 「**[!UICONTROL 送信]**」をクリックします。

1. 送信されると、サブドメインは&#x200B;**[!UICONTROL 処理中]**&#x200B;ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](../configuration/about-subdomain-delegation.md#access-delegated-subdomains)を参照してください。<!--Same statuses?-->

   そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（**最大で 4 時間**&#x200B;かかることがあります）。<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。SMS チャネル設定を作成する準備が整いました。

## 新しいサブドメインを設定 {#sms-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_sms_subdomain_dns"
>title="一致する DNS レコードを生成"
>abstract="新しい SMS サブドメインを設定するには、Journey Optimizer インターフェイスに表示されるアドビのネームサーバー情報をコピーし、ドメインホストソリューションに貼り付けて、一致する DNS レコードを生成する必要があります。チェックが正常に完了すると、SMS 設定の作成にサブドメインを使用する準備が整います。"

新しいサブドメインを設定するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューを参照して、**[!UICONTROL SMS 設定]**／**[!UICONTROL SMS サブドメイン]**&#x200B;を選択します。

1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。

   ![](assets/sms_set-up-subdomain.png)

1. 「 **[!UICONTROL 設定タイプ]** 」セクションから「**[!UICONTROL 独自のドメインを追加]**」を選択します。

   ![](assets/sms_add-your-own-subdomain.png)

1. デリゲートするサブドメインを指定します。

   >[!CAUTION]
   >
   >* 既存の SMS サブドメインは使用できません。
   >
   >* サブドメインでは大文字は使用できません。

   無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。

   （同じ親ドメインの）複数レベルのサブドメインがサポートされます。例えば、「sms.marketing.yourcompany.com」を使用できます。

1. DNS サーバーに配置するレコードが表示されます。このレコードをコピーするか、CSV ファイルをダウンロードしてから、ドメインをホストするソリューションに移動し、一致する DNS レコードを生成します。

1. DNS レコードがドメインホスティングソリューションに生成されていることを確認します。すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](assets/sms_add-your-own-subdomain-confirm.png)

   新しい SMS サブドメインを設定すると、常に CNAME レコードを指すようになります。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](../configuration/about-subdomain-delegation.md#access-delegated-subdomains)を参照してください。<!--Same statuses?-->

サブドメインを使用して SMS メッセージを送信するには、必要なチェックがアドビで実行されるまで待つ必要があります（最大で 4 時間かかることがあります）。<!--Learn more in [this section](#subdomain-validation).--> チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。SMS チャネル設定を作成する準備が整いました。

ホスティングソリューションで検証レコードを作成できなかった場合、サブドメインは「**[!UICONTROL 失敗]**」とマークされます。

## サブドメインのデリゲート解除 {#undelegate-subdomain}

SMS サブドメインをデリゲート解除する場合は、アドビ担当者にお問い合わせください。

ただし、アドビにお問い合わせいただく前に、ユーザーインターフェイスでいくつかの手順を実行する必要があります。

>[!NOTE]
>
>デリゲート解除できるのは、**[!UICONTROL 成功]**&#x200B;ステータスのサブドメインのみです。**[!UICONTROL ドラフト]**&#x200B;ステータスと&#x200B;**[!UICONTROL 失敗]**&#x200B;ステータスのサブドメインは、ユーザーインターフェイスから簡単に削除できます。

まず、[!DNL Journey Optimizer] で次の手順を実行します。

1. サブドメインに関連付けられているすべてのチャネル設定を非アクティブ化します。[方法についてはこちらを参照](../configuration/channel-surfaces.md#deactivate-a-surface)

<!--
1. If the SMS subdomain is using an email subdomain that was [already delegated](#lp-use-existing-subdomain) to Adobe, undelegate the email subdomain. [Learn how](../configuration/delegate-subdomain.md#undelegate-subdomain)-->

1. サブドメインに関連付けられているアクティブなキャンペーンを停止します。[方法についてはこちらを参照](../campaigns/modify-stop-campaign.md#stop)

1. サブドメインに関連付けられているアクティブなジャーニーを停止します。[方法についてはこちらを参照](../building-journeys/end-journey.md#stop-journey)

1. SMS サブドメインが[新しいデリゲートされたサブドメイン](#sms-configure-new-subdomain)であった場合は、そのサブドメインに関連付けられている DNS エントリを削除します。

完了したら、デリゲート解除するサブドメインについて、アドビ担当者にお問い合わせください。

アドビがリクエストを処理すると、デリゲート解除したドメインはサブドメイン在庫ページに表示されなくなります。

>[!CAUTION]
>
>サブドメインをデリゲート解除した後：
>
>   * そのサブドメインを使用していたチャネル設定を再アクティブ化することはできません。
>   * ユーザーインターフェイスを通じて正確なサブドメインを再度デリゲートすることはできません。ご希望の場合は、アドビ担当者にお問い合わせください。
