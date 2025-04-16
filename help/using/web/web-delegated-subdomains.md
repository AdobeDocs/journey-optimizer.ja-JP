---
solution: Journey Optimizer
product: journey optimizer
title: Web サブドメインの設定
description: Journey Optimizerで web サブドメインを設定する方法を学ぶ
role: Admin
feature: Web Channel, Subdomains
level: Experienced
keywords: Web、サブドメイン、設定
exl-id: 6e00466d-4ce5-4d80-89ff-c7331a5ab158
source-git-commit: ce8818e0216d4f633770fecadd4e74c2651a62f3
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 75%

---

# Web サブドメインの設定 {#web-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_header"
>title="Web サブドメインのデリゲート"
>abstract="Web チャネルで使用するサブドメインを設定します。既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web"
>title="Web サブドメインのデリゲート"
>abstract="Adobe Experience Manager Assets のコンテンツを web エクスペリエンスに追加する場合は、このコンテンツの公開に使用するサブドメインを設定する必要があります。既にアドビにデリゲートされているサブドメインの中から選択するか、新しいサブドメインを設定します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_subdomain_web_default"
>title="Web サブドメインの設定"
>abstract="アドビにデリゲートされているサブドメインのリストからサブドメインを選択します。この web サブドメインをデフォルトのサブドメインとして設定できますが、一度に使用できるデフォルトのサブドメインは 1 つだけです。"

Web エクスペリエンスの作成時に [Adobe Experience Manager Assets](../integrations/assets.md) ライブラリのコンテンツを追加する場合は、このコンテンツの公開に使用するサブドメインを設定する必要があります。

既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。サブドメインのAdobeへのデリゲートについて詳しくは、[ この節 ](../configuration/delegate-subdomain.md) を参照してください。

Web サブドメインの設定は **すべての環境に共通** です。 したがって、

* Web サブドメインにアクセスして編集するには、実稼動サンドボックスで **[!UICONTROL Web サブドメインの管理]**&#x200B;権限が必要です。

* Web サブドメインへの変更は、実稼動サンドボックスにも影響します。

複数の web サブドメインを作成できますが、使用されるのは&#x200B;**デフォルト**&#x200B;のサブドメインのみです。デフォルトの web サブドメインは変更できますが、一度に使用できるのは 1 つのみです。

## Web サブドメインへのアクセスと管理 {#access-web-subdomains}

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューに移動して、**[!UICONTROL web 設定]**／**[!UICONTROL web サブドメイン]**&#x200B;を選択します。現在のサンドボックスで設定されているすべてのサブドメインが表示されます。

   ![](assets/web-access-subdomains.png)

1. 各サブドメインをデリゲートしたユーザーまたはデリゲーションステータス（**[!UICONTROL ドラフト]**、**[!UICONTROL 処理中]**、**[!UICONTROL 成功]**&#x200B;または&#x200B;**[!UICONTROL 失敗]**）に関してフィルタリングできます。

   ![](assets/web-filter-subdomains.png)

1. **[!UICONTROL デフォルト]**&#x200B;のバッジは、現在デフォルトとして使用されているサブドメインの横に表示されます。デフォルトのサブドメインを変更するには、該当するサブドメインの横にある&#x200B;**[!UICONTROL その他のアクション]**&#x200B;ボタンで「**[!UICONTROL デフォルトとして設定]**」を選択します。

   ![](assets/web-subdomain-default.png)

   デフォルトの web サブドメインは変更できますが、一度に使用できるのは 1 つのみです。

## 既存のサブドメインを使用 {#web-use-existing-subdomain}

既にアドビにデリゲートされているサブドメインを使用するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスして、**[!UICONTROL web 設定]**／**[!UICONTROL web サブドメイン]**&#x200B;を選択します。

1. 「**[!UICONTROL サブドメインを設定]**」をクリックします。

1. 「**[!UICONTROL 設定タイプ]**」セクションで「**[!UICONTROL デリゲートされたサブドメインを使用]**」オプションを選択し、デリゲートされたサブドメインをリストから選択します。

   ![](assets/web-subdomain-details.png)

   >[!NOTE]
   >
   >既に web サブドメインとして使用されているサブドメインは選択できません。

1. Web URL に表示されるプレフィックスは自動的に追加されます。変更することはできません。

1. このサブドメインをデフォルトとして設定するには、対応するオプションを選択します。

   ![](assets/web-subdomain-details-default.png)

   使用されるのは、**デフォルト**&#x200B;のサブドメインのみです。

1. 「**[!UICONTROL 送信]**」をクリックします。サブドメインは&#x200B;**[!UICONTROL 成功]**&#x200B;ステータスを取得します。これで、web エクスペリエンスで使用する準備が整いました。

   まれに、サブドメインの設定が失敗する場合があります。この場合、「**[!UICONTROL その他のアクション]**」アイコンの「**[!UICONTROL 削除]**」ボタンを使用して、**[!UICONTROL 失敗]**&#x200B;したサブドメインを削除してリストをクリーンアップできます。

## 新しいサブドメインを設定 {#web-configure-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo_admin_web_subdomain_dns"
>title="一致する DNS レコードを生成"
>abstract="新しい web サブドメインを設定するには、Journey Optimizer インターフェイスに表示されるアドビのネームサーバー情報をコピーし、お使いのドメインホスティングソリューションにペーストして、一致する DNS レコードを生成する必要があります。チェックが正常に完了すると、サブドメインを使用して、Adobe Experience Manager Assets ライブラリからのコンテンツを公開できるようになります。"


デフォルトでは、[!DNL Journey Optimizer] を使用すると、合計 **最大 10 個のサブドメイン** をデリゲートできます（メールと web チャネルの両方をカバー）。 ただし、ライセンス契約によっては、最大 100 個のサブドメインをデリゲートできる場合があります。自身が使用資格を持つサブドメインの数について詳しくは、アドビの連絡先にお問い合わせください。

新しいサブドメインを設定するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスして、**[!UICONTROL web 設定]**／**[!UICONTROL web サブドメイン]**&#x200B;を選択します。

1. 「**[!UICONTROL サブドメインを設定]**」をクリックします。

1. 「 **[!UICONTROL 設定タイプ]** 」セクションから「**[!UICONTROL 独自のドメインを追加]**」を選択します。

1. デリゲートするサブドメインを指定します。

   >[!CAUTION]
   >
   >* 既存の web サブドメインは使用できません。
   >
   >* サブドメインでは大文字は使用できません。

   ![](assets/web-add-your-own-domain.png)

   無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（marketing.yourcompany.com など）を入力してください。

   （同じ親ドメインの）複数レベルのサブドメインがサポートされます。例えば、「web.marketing.yourcompany.com」を使用できます。

1. このサブドメインをデフォルトとして設定するには、対応するオプションを選択します。

   >[!NOTE]
   >
   >使用されるのは、**デフォルト**&#x200B;のサブドメインのみです。

1. DNS サーバーに配置するレコードが表示されます。このレコードをコピーするか、CSV ファイルをダウンロードしてから、ドメインをホストするソリューションに移動し、一致する DNS レコードを生成します。

1. DNS レコードがドメインホスティングソリューションに生成されていることを確認します。すべてが正しく設定されている場合は、「確認しました」チェックボックスをオンにし、「**[!UICONTROL 送信]**」をクリックします。

   ![](assets/web-add-your-own-domain-confirm.png)

   新しい web サブドメインを設定すると、常に CNAME レコードを指すようになります。

1. サブドメインのデリゲーションが送信されると、そのサブドメインは「**[!UICONTROL 処理中]**」ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](../configuration/about-subdomain-delegation.md#access-delegated-subdomains)を参照してください。<!--Same statuses?-->

   そのサブドメインを使用して web メッセージを送信できるようになるには、必要なチェックがAdobeで実行されるまで待つ必要があります（最大で 4 時間 **。これには時間かかるこ** があります。

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。Web チャネル設定を作成する準備が整いました。

   ホスティングソリューションで検証レコードを作成できなかった場合、サブドメインは「**[!UICONTROL 失敗]**」とマークされます。

<!--
Only a subdomain with the **[!UICONTROL Success]** status can be set as default.
You cannot delete a subdomain with the **[!UICONTROL Processing]** status.
-->

## サブドメインのデリゲート解除 {#undelegate-subdomain}

Web サブドメインのデリゲートを解除する場合は、Adobe担当者にお問い合わせください。

ただし、Adobeにアクセスする前に、ユーザーインターフェイスでいくつかの手順を実行する必要があります。

>[!NOTE]
>
>**[!UICONTROL 成功]** ステータスのサブドメインのみをデリゲート解除できます。 **[!UICONTROL ドラフト]** および **[!UICONTROL 失敗]** ステータスのサブドメインは、ユーザーインターフェイスから削除できます。

まず、[!DNL Journey Optimizer] で次の手順を実行します。

1. サブドメインに関連付けられているすべてのチャネル設定をディアクティベートします。 [方法について詳しくは、こちらを参照してください](../configuration/channel-surfaces.md#deactivate-a-surface)

<!--
1. If the web subdomain is using an email subdomain that was [already delegated](#lp-use-existing-subdomain) to Adobe, undelegate the email subdomain. [Learn how](../configuration/delegate-subdomain.md#undelegate-subdomain)-->

1. サブドメインに関連付けられているアクティブなキャンペーンを停止します。 [方法について詳しくは、こちらを参照してください](../campaigns/modify-stop-campaign.md#stop)

1. サブドメインに関連付けられたアクティブなジャーニーを停止します。 [方法について詳しくは、こちらを参照してください](../building-journeys/end-journey.md#stop-journey)

1. Web サブドメインが [ 新しいデリゲートサブドメイン ](#web-configure-new-subdomain) だった場合は、そのサブドメインに関連付けられている DNS エントリを削除します。

完了したら、デリゲート解除するサブドメインをAdobe担当者に連絡します。

リクエストがAdobeによって処理されると、デリゲートされていないドメインはサブドメインインベントリページに表示されなくなります。

>[!CAUTION]
>
>サブドメインがデリゲート解除された後：
>
>   * そのサブドメインを使用していたチャネル設定を再アクティブ化することはできません。
>
>   * ユーザーインターフェイスを使用して正確なサブドメインを再度デリゲートすることはできません。 その場合は、Adobeの担当者にお問い合わせください。