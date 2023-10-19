---
solution: Journey Optimizer
product: journey optimizer
title: IP ウォームアッププランを作成
description: Journey Optimizer で IP ウォームアッププランを作成する方法を学ぶ
feature: IP Warmup Plans
topic: Administration
role: Admin
level: Experienced
keywords: IP、グループ、サブドメイン、配信品質
hide: true
hidefromtoc: true
exl-id: c2434086-2ed4-4cd0-aecd-2eea8f0a55f6
source-git-commit: 07b1f9b885574bb6418310a71c3060fa67f6cac3
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 97%

---

# IP ウォームアッププランを作成 {#ip-warmup}

>[!BEGINSHADEBOX]

このドキュメントガイドの内容は次のとおりです。

* [IP ウォームアップの概要](ip-warmup-gs.md)
* [IP ウォームアップキャンペーンを作成](ip-warmup-campaign.md)
* **[IP ウォームアッププランを作成](ip-warmup-plan.md)**
* [IP ウォームアッププランを実行](ip-warmup-execution.md)

>[!ENDSHADEBOX]

専用のサーフェスと対応するオプションを有効にして、1 つ以上の [IP ウォームアップキャンペーン](ip-warmup-campaign.md)を作成したら、IP ウォームアッププランの作成を開始できます。

## IP ウォームアッププランファイルを準備 {#prepare-file}

IP ウォームアップは、正当な送信者としての評判を確立するために、IP およびドメインから主要なインターネットサービスプロバイダー（ISP）に送信されるメールの量を徐々に増やすことで構成されるアクティビティです。

このアクティビティは、通常、配信品質の専門家の支援を受けて、業界ドメイン、ユースケース、地域、ISP、その他の様々な要因に基づいて綿密に検討されたプランを準備するのに役立ちます。

[!DNL Journey Optimizer] IP ウォームアップ機能を使用する場合、このプランでは、事前定義済みの列を多数含む Excel ファイルの形式を使用する必要があります。IP ウォームアッププランを [!DNL Journey Optimizer] インターフェイスで作成する前に、プランにフィードするすべてのデータをこのテンプレートに入力する必要があります。

>[!CAUTION]
>
>配信品質コンサルタントと協力して、IP ウォームアッププランファイルが正しく設定されていることを確認します。

以下は、IP ウォームアッププランを含むファイルの例です。

![](assets/ip-warmup-sample-file.png)

### 「IP ウォームアッププラン」タブ

* この例では、100 万を超えるプロファイルのターゲットボリュームを達成するために、17 日間にわたるプラン（「**実行**」と呼ばれる）が準備されています。

* この計画は 6 つの&#x200B;**フェーズ**&#x200B;を通じて実行され、各フェーズには少なくとも 1 回の実行が含まれます。

* 配信先のドメインに必要な数の列を含めることができます。この例では、プランは 6 つの列に分割されています。そのうち 5 つは&#x200B;**メインドメイングループ**（Gmail、Microsoft、Yahoo、Orange、Apple）に対応しており、6 列目の&#x200B;**その他**&#x200B;には、他のドメインの残りのアドレスがすべて含まれています。
* 「**エンゲージメント日数**」列は、過去 30 日間にブランドと関与したプロファイルのみがターゲットになっていることを示します。

このアイデアでは、各フェーズの実行数を減らしながら、各実行でターゲットアドレスの数を徐々に増やしていきます。

プランに追加できる標準のメインドメイングループを以下に示します。

* Gmail
* Adobe
* WP
* Comcast
* Yahoo
* Bigpond
* Orange
* Softbank
* Docomo
* United Internet
* Microsoft
* KDDI
* Italia Online
* La Poste
* Apple

### 「カスタムドメイングループ」タブ

また、カスタムドメイングループを含めることで、プランに列を追加することもできます。

「**[!UICONTROL カスタムドメイングループ]**」タブをクリックして、新しいドメイングループを定義します。各ドメインに対して、対象となるすべてのサブドメインを追加できます。<!--TBC-->

例えば、カスタムドメイン Luma を追加する場合、サブドメイン（luma.com、luma.co.uk、luma.it、luma.fr、luma.de など）を含めます。

![](assets/ip-warmup-sample-file-custom.png)

## IP ウォームアッププランへのアクセスと管理 {#manage-ip-warmup-plans}

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスします。これまでに作成した IP ウォームアッププランがすべて表示されます。

   ![](assets/ip-warmup-filter-list.png)

1. ステータスに基づいてフィルタリングできます。 様々なステータスを以下に示します。

   * **未開始**：実行はまだアクティブ化されていません。 [詳細情報](ip-warmup-execution.md#define-runs)
   * **ライブ**：最初のフェーズの最初の実行が正常にアクティブ化されると、プランは直ちにこのステータスに変わります。[詳細情報](ip-warmup-execution.md#define-runs)
   * **完了**：プランは完了とマークされています。 このオプションは、プラン内のすべての実行が **[!UICONTROL 完了]** または **[!UICONTROL ドラフト]** ステータス（実行不可） **[!UICONTROL ライブ]**) をクリックします。 [詳細情報](ip-warmup-execution.md#mark-as-completed)
     <!--* **Paused**: to check (user action)-->

1. IP ウォームアッププランを削除するには、プラン名の横にある「**[!UICONTROL 削除]**」アイコンを選択し、削除を確定します。

   ![](assets/ip-warmup-delete-plan.png)

   >[!CAUTION]
   >
   >選択した IP ウォームアッププランは完全に削除されます。

## IP ウォームアッププランを作成 {#create-ip-warmup-plan}

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_upload"
>title="IP ウォームアッププランを指定"
>abstract="CSV テンプレートをダウンロードして、IP ウォームアップフェーズとプロファイルのターゲット数のデータを入力します。"

>[!CONTEXTUALHELP]
>id="ajo_admin_ip_warmup_surface"
>title="マーケティングサーフェスを選択"
>abstract="IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="チャネルサーフェスの設定"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/channel-surfaces.html?lang=ja" text="IP ウォームアップキャンペーンを作成"

「**[!UICONTROL IP ウォームアッププランのクティベーション]**」オプションが有効になっている 1 つ以上のライブキャンペーンがアクティブ化されている場合、IP ウォームアッププランに関連付けることができます。

>[!CAUTION]
>
>IP ウォームアッププランを作成、編集、削除するには、**[!UICONTROL 配信品質コンサルタント]**&#x200B;権限が必要です。<!--Learn more on managing [!DNL Journey Optimizer] users' access rights in [this section](../administration/permissions-overview.md).-->

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL IP ウォームアッププラン]**&#x200B;メニューにアクセスし、「**[!UICONTROL IP ウォームアッププランを作成]**」をクリックします。

   ![](assets/ip-warmup-create-plan.png)

1. IP ウォームアッププランの詳細（名前と説明）を入力します。

   ![](assets/ip-warmup-plan-details.png)

1. 「[サーフェス](channel-surfaces.md)」を選択します。  選択できるのはマーケティングサーフェスのみです。[メールのタイプの詳細情報](../email/email-settings.md#email-type)

   >[!CAUTION]
   >
   >IP ウォームアッププランに関連付けるキャンペーンで選択したサーフェスと同じサーフェスを選択する必要があります。[IP ウォームアップキャンペーンの作成方法を学ぶ](ip-warmup-campaign.md)

1. IP ウォームアッププランを含む Excel ファイルをアップロードします。[詳細情報](#prepare-file)

   <!--
    You can also download the Excel template from the [!DNL Journey Optimizer] user interface and upload it after filling it with the IP warmup details.-->

   ![](assets/ip-warmup-upload-success.png)

1. 「**[!UICONTROL 作成]**」をクリックします。アップロードしたファイルに定義されているすべてのフェーズ、実行、列、およびそれらのコンテンツは、[!DNL Journey Optimizer] インターフェイスに自動的に表示されます。[詳細情報](ip-warmup-execution.md)

   ![](assets/ip-warmup-plan-uploaded.png)
