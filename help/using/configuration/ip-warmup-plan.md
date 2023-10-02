---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランを作成する
description: Journey Optimizerで IP ウォームアッププランを作成する方法を説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Experienced
keywords: IP、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: 205f26d3f31b9f003fc1dbaf679021464429d144
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 5%

---

# IP ウォームアッププランを作成する {#ip-warmup}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* **[IP ウォームアッププランを作成する](ip-warmup-plan.md)**
* [IP ウォームアッププランを実行します。](ip-warmup-execution.md)

>[!ENDSHADEBOX]

1 つ以上の [IP ウォームアップキャンペーン](ip-warmup-campaign.md) 専用のサーフェスと対応するオプションを有効にした状態で、IP ウォームアッププランの作成を開始できます。

## IP ウォームアッププランファイルを準備する {#prepare-file}

IP ウォームアップは、正当な送信者としての評判を確立するために、IP およびドメインから主要なインターネットサービスプロバイダー (ISP) に送られる E メールの量を徐々に増やすことで構成されるアクティビティです。

このアクティビティは、配信品質の専門家の助けを借りて、業界ドメイン、使用例、地域、ISP、その他の様々な要因に基づいて適切に検討されたプランを準備するのに役立ちます。

を操作する場合、 [!DNL Journey Optimizer] IP ウォームアップ機能を使用すると、このプランでは、定義済みの列を多数含む Excel ファイルの形式を使用する必要があります。 IP ウォームアッププランを [!DNL Journey Optimizer] インターフェイスでは、プランに入力するすべてのデータをこのテンプレートに入力する必要があります。

>[!CAUTION]
>
>配信品質コンサルタントと協力して、IP ウォームアッププランファイルが正しく設定されていることを確認します。

以下は、IP ウォームアップ計画を含むファイルの例です。

![](assets/ip-warmup-sample-file.png)

### [IP ウォームアッププラン ] タブ

* この例では、17 日間にわたる計画 (「**実行**「)」をクリックして、100 万を超えるプロファイルのターゲットボリュームに到達します。

* この計画は 6 日までに実行されます **フェーズ**（それぞれに少なくとも 1 回の実行が含まれる）

* 配信先のドメインに対して、必要な数の列を設定できます。 この例では、計画は 6 つの列に分割されます。そのうち 5 つは **メインドメイングループ** を使用して、プラン (Gmail、Microsoft、Yahoo、Orange およびApple) と 6 列目を使用します。 **その他**&#x200B;には、他のドメインの残りのすべてのアドレスが含まれます。
* The **エンゲージメント日数** 「 」列には、過去 30 日間にブランドと関与したプロファイルのみがターゲットになっていることが示されます。

このアイデアでは、各フェーズの実行数を減らしながら、各実行でターゲットアドレスの数を徐々に増やします。

プランに追加できる標準のメインドメイングループを次に示します。

* Gmail
* Adobe
* WP
* Comcast
* Yahoo
* Bigpond
* オレンジ
* Softbank
* ドコモ
* United Internet
* Microsoft
* KDDI
* Italia Online
* ラポステ
* Apple

### 「カスタムドメイングループ」タブ

また、カスタムドメイングループを含めることで、プランに列を追加することもできます。

以下を使用します。 **[!UICONTROL カスタムドメイングループ]** タブをクリックして、新しいドメイングループを定義します。 各ドメインに対して、対象となるすべてのサブドメインを追加できます。<!--TBC-->

例えば、カスタムドメイン Luma を追加する場合、luma.com、luma.co.uk、luma.it、luma.fr、luma.de などのサブドメインを含めます。

![](assets/ip-warmup-sample-file-custom.png)

## IP ウォームアッププランへのアクセスと管理 {#manage-ip-warmup-plans}

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL IP 暖機プラン]** メニュー。 これまでに作成した IP ウォームアップ計画がすべて表示されます。

   ![](assets/ip-warmup-filter-list.png)

1. ステータスに基づいてフィルタリングできます。 様々なステータスを次に示します。

   * **未開始**：実行はまだアクティブ化されていません。 [詳細情報](ip-warmup-execution.md#define-runs)
   * **ライブ**：第 1 段階の最初の実行が正常にアクティブ化されると、プランは直ちにこのステータスに変わります。 [詳細情報](ip-warmup-execution.md#define-runs)
   * **完了**：プランは完了とマークされています。 このオプションは、プラン内のすべての実行が **[!UICONTROL 完了]** または **[!UICONTROL ドラフト]** ステータス（実行不可） **[!UICONTROL ライブ]**) をクリックします。 [詳細情報](ip-warmup-execution.md#mark-as-completed)
     <!--* **Paused**: to check (user action)-->

1. IP ウォームアッププランを削除するには、 **[!UICONTROL 削除]** プラン名の横にあるアイコンをクリックし、削除を確定します。

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >選択した IP ウォームアッププランは完全に削除されます。

## IP ウォームアッププランを作成する {#create-ip-warmup-plan}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_upload"
>title="IP ウォームアッププランを指定"
>abstract="CSV テンプレートをダウンロードし、IP ウォームアップフェーズのデータと、ターゲットプロファイル数を入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="マーケティングサーフェスを選択"
>abstract="IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="チャネルサーフェスの設定"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="IP ウォームアップキャンペーンを作成"

1 つ以上のライブキャンペーンで **[!UICONTROL IP ウォームアッププランの有効化]** オプションが有効になっている場合は、IP ウォームアッププランに関連付けることができます。

>[!CAUTION]
>
>IP ウォームアッププランを作成、編集、削除するには、 **[!UICONTROL 配信品質コンサルタント]** 権限。 <!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL IP 暖機プラン]** メニュー、次に「 **[!UICONTROL IP ウォームアッププランを作成]**.

   ![](assets/ip-warmup-create-plan.png)

1. IP ウォームアッププランの詳細を入力し、名前と説明を入力します。

   ![](assets/ip-warmup-plan-details.png)

1. を選択します。 [表面](channel-surfaces.md). 選択できるのはマーケティングサーフェスのみです。 [電子メールのタイプの詳細を説明します](../email/email-settings.md#email-type)

   >[!CAUTION]
   >
   >IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。 [IP ウォームアップキャンペーンの作成方法を説明します](ip-warmup-campaign.md)

1. IP ウォームアッププランを含む Excel ファイルをアップロードします。 [詳細情報](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

1. 「**[!UICONTROL 作成]**」をクリックします。アップロードしたファイルに定義されているすべてのフェーズ、実行、列、およびその内容は、自動的に [!DNL Journey Optimizer] インターフェイス。 [詳細情報](ip-warmup-execution.md)

   ![](assets/ip-warmup-plan-uploaded.png)
