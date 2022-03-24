---
title: ランディングページの設定
description: Journey Optimizer でランディングページを作成し、使用するために環境を設定する方法を説明
role: Admin
level: Intermediate
exl-id: 7cf1f083-bef0-40b5-8ddd-920a9d108eca
source-git-commit: e9878246c2af5c7ee0f961aaaad64e186431d96e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 96%

---

# ランディングページの設定 {#lp-configuration}

## ランディングページのサブドメインを設定 {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo_admin_config_lp_subdomain"
>title="ランディングページプリセットの作成"
>abstract="ランディングページプリセットを作成できるようにするには、少なくとも 1 つのランディングページサブドメインを「サブドメイン名」リストから選択するように事前に設定しておく必要があります。"

[ランディングページプリセットを作成](#lp-create-preset)できるようにするためには、ランディングページに使用するサブドメインを設定する必要があります。

既にアドビにデリゲートされているサブドメインを使用するか、別のサブドメインを設定できます。サブドメインのアドビへのデリゲートについて詳しくは、[この節](delegate-subdomain.md)で説明します。

### 既存のサブドメインを使用 {#lp-use-existing-subdomain}

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

   >[!CAUTION]
   >
   >[CNAME メソッド](delegate-subdomain.md#cname-subdomain-delegation)を使用してアドビにデリゲートされたドメインを選択する場合、ホスティングプラットフォーム上に DNS レコードを作成する必要があります。DNS レコードを生成する手順は、新しいランディングページサブドメインを設定する際の手順と同じです。 [この節](#lp-configure-new-subdomain)でその方法を説明します。

1. 「**[!UICONTROL 送信]**」をクリックします。

1. 送信されると、サブドメインは&#x200B;**[!UICONTROL 処理中]**&#x200B;ステータスでリストに表示されます。サブドメインのステータスについて詳しくは、[この節](access-subdomains.md)を参照してください。<!--Same statuses?-->

   ![](assets/lp_subdomain-processing.png)

   >[!NOTE]
   >
   >そのサブドメインを使用してメッセージを送信できるようになるには、必要なチェックがアドビで実行されるまで待つ必要があります（最大で 4 時間かかることがあります）。<!--Learn more in [this section](delegate-subdomain.md#subdomain-validation).-->

1. チェックが正常に完了すると、サブドメインのステータスが「**[!UICONTROL 成功]**」になります。ランディングページプリセットの作成に使用する準備が整いました。

### 新しいサブドメインを設定 {#lp-configure-new-subdomain}

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

   「email.marketing.yourcompany.com」などマルチレベルのサブドメインは、現在サポートされていません。

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

## ランディングページプリセットを定義 {#lp-define-preset}

[ランディングページの作成](../landing-pages/create-lp.md#create-a-lp)を行う場合は、ランディングページを作成し、**[!DNL Journey Optimizer]** を介して活用できるように、ランディングページプリセットを選択する必要があります。

### ランディングページプリセットへのアクセス {#lp-presets}

ランディングページプリセットにアクセスするには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスします。

1. **[!UICONTROL ブランディング]**／**[!UICONTROL ランディングページプリセット]**&#x200B;を選択します。

   ![](assets/lp_presets-access.png)

1. 任意のプリセットラベルをクリックして、ランディングページプリセットの詳細にアクセスします。

   ![](assets/lp_preset-details.png)

### ランディングページプリセットの作成 {#lp-create-preset}

ランディングページプリセットを作成するには、次の手順に従います。

>[!NOTE]
>
>プリセットを作成するには、少なくとも 1 つのランディングページサブドメインを既に設定してあることを確認してください。[方法についてはこちらを参照](#lp-subdomains)

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**&#x200B;メニューにアクセスし、**[!UICONTROL ブランディング]**／**[!UICONTROL ランディングページプリセット]**&#x200B;を選択します。

1. 「**[!UICONTROL ランディングページプリセットを作成]**」を選択します。

   ![](assets/lp_create-preset-temp.png)

1. プリセットの名前と説明を入力します。

   >[!NOTE]
   >
   > 名前は、文字（A ～ Z）で始める必要があります。使用できるのは英数字のみです。 アンダースコア（`_`）、ドット（`.`）、ハイフン（`-`）も使用できます。

1. ドロップダウンリストからランディングページのサブドメインを選択します。

   ![](assets/lp_preset-subdomain.png)

   >[!NOTE]
   >
   >サブドメインを選択するには、少なくとも 1 つのランディングページサブドメインを事前に設定していることを確認してください。[方法](#lp-subdomains)

   選択したサブドメインに対応する設定が表示されます。

1. ランディングページサブドメインをトラッキング URL として選択する場合は、「**[!UICONTROL ランディングページサブドメインと同じ]**」オプションをオンにします。[トラッキングの詳細情報](../messages/message-tracking.md)

   ![](assets/lp_preset-subdomain-settings-same.png)

   例えば、ランディングページの URL が「pages.mail.luma.com」で、トラッキング URL が「data.mail.luma.com」の場合、トラッキングサブドメインとして「pages.mail.luma.com」を使用するように選択できます。

1. 「**[!UICONTROL 送信]**」をクリックして、ランディングページプリセットの作成を確認します。なお、プリセットをドラフトとして保存し、後で設定を再開することもできます。

   ![](assets/lp_preset-subdomain-settings-submit.png)

1. ランディングページプリセットが作成されると、リストに「**[!UICONTROL アクティブ]**」のステータスで表示されます。これで、ランディングページで使用する準備が整いました。

   ![](assets/lp-preset-active-temp.png)

これで、[!DNL Journey Optimizer] で[ランディングページの作成](../landing-pages/create-lp.md)を行う準備が整いました。

>[!NOTE]
>
>[この節](message-presets.md)では、プッシュ通知とメールのメッセージプリセットを作成する方法について説明します。

**関連トピック**:

* [ランディングページの基本を学ぶ](../landing-pages/get-started-lp.md)
* [ランディングページの作成](../landing-pages/create-lp.md#create-a-lp)
