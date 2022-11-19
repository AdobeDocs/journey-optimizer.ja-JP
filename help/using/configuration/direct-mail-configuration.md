---
title: ダイレクトメールの設定
description: Journey Optimizer でダイレクトメールチャネルを設定する方法を学ぶ
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ae5cc885-ade1-4683-b97e-eda1f2142041
source-git-commit: dbb668b219b8d2ccea4d340c019918d6a6e387bb
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 94%

---

# ダイレクトメールの設定 {#direct-mail-configuration}

[!DNL Journey Optimizer] では、ダイレクトメールプロバイダーが顧客にメールを送信するために必要なファイルをパーソナライズおよび生成できます。

[ダイレクトメールメッセージの作成](../messages/create-direct-mail.md)の場合は、選択した連絡先情報（住所など）を含む、ターゲットオーディエンスデータを定義します。このデータを含むファイルが自動的に生成され、サーバーに書き出されます。ダイレクトメールプロバイダーは、このファイルを取得して、実際の送信処理を行うことができます。

このファイルを生成する前に、以下を作成する必要があります。

1. [ファイルのルーティング設定](#file-routing-configuration)：ファイルの書き出し先となるサーバーを指定します。

1. [ダイレクトメールサーフェス](#direct-mail-surface)：ファイルのルーティング設定を参照します。

>[!CAUTION]
>
>ファイルのルーティングオプションを設定していない場合は、ダイレクトメールサーフェスを作成できません。

## ファイルのルーティングの設定 {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="ファイルのルーティング設定の定義"
>abstract="ダイレクトメールメッセージを作成すると、ターゲットオーディエンスデータを含むファイルが生成され、サーバーに書き出されます。ダイレクトメールプロバイダーがそのファイルにアクセスして、ダイレクトメールの配信に使用できるように、サーバーの詳細を指定する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/create-direct-mail.html?lang=ja" text="ダイレクトメールメッセージの作成"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details_header"
>title="ファイルのルーティング設定の定義"
>abstract="ダイレクトメールプロバイダーが使用するファイルの書き出し先を定義する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_dm_select_file_routing"
>title="ファイルのルーティング設定"
>abstract="任意のファイルのルーティング設定を選択します。この設定は、ダイレクトメールプロバイダーが使用するファイルの書き出し先を定義します。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_type"
>title="ファイルのサーバータイプの選択"
>abstract="ダイレクトメールファイルの書き出しに使用するサーバーのタイプを選択します。現在、Amazon S3 と SFTP のみが Journey Optimizer でサポートされています。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_aws_region"
>title="AWS リージョンの選択"
>abstract="ダイレクトメールファイルの書き出し先となる AWS サーバーの地域を選択します。一般的には、ダイレクトメールプロバイダーの場所に最も近い地域を選択することをお勧めします。"

ダイレクトメールメッセージを配信するために、[!DNL Journey Optimizer] はターゲットオーディエンスデータを含むファイルを生成し、サーバーに書き出します。

ダイレクトメールプロバイダーがそのファイルにアクセスして、メールの配信に使用できるように、そのサーバーの詳細を指定する必要があります。

ファイルのルーティングを設定するには、次の手順に従います。

1. **[!UICONTROL 管理]**／**[!UICONTROL チャネル]**／**[!UICONTROL ファイルのルーティング設定]**／**[!UICONTROL ファイルのルーティング]**&#x200B;メニューにアクセスし、「**[!UICONTROL ルーティング設定を作成]**」をクリックします。

   ![](assets/file-routing-config-button.png)

1. 設定の名前を設定します。

1. ダイレクトメールファイルの書き出しに使用する&#x200B;**[!UICONTROL サーバータイプ]**&#x200B;を選択します。

   ![](assets/file-routing-config-type.png)

   >[!NOTE]
   >
   >現在、[!DNL Journey Optimizer] では Amazon S3 と SFTP のみがサポートされています。

1. サーバーアドレス、アクセスキーなど、サーバーの詳細と資格情報を入力します。

   ![](assets/file-routing-config-sftp-details.png)

1. 「**[!UICONTROL Amazon S3]**」を選択した場合は、サーバーインフラストラクチャが配置される「**[!UICONTROL AWS リージョン]**」を選択します。

   ![](assets/file-routing-config-aws-region.png)

   >[!NOTE]
   >
   >AWS リージョンは、AWS がクラウドインフラストラクチャをホストするために使用する地理的エリアです。一般的には、ダイレクトメールプロバイダーの場所に最も近いリージョンを選択することをお勧めします。

1. 「**[!UICONTROL 送信]**」を選択します。ファイルのルーティング設定は、**[!UICONTROL アクティブ]**&#x200B;ステータスで作成されます。これで、[ダイレクトメールサーフェス](#direct-mail-surface)で使用する準備が整いました。

   >[!NOTE]
   >
   >「**[!UICONTROL ドラフトとして保存]**」を選択してファイルのルーティング設定を作成することもできますが、**[!UICONTROL アクティブ]**&#x200B;になるまでサーフェスで選択することはできません。

## ダイレクトメールサーフェスの作成 {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="ダイレクトメール設定を定義します。"
>abstract="ダイレクトメールサーフェスには、ターゲットオーディエンスデータを含み、メールプロバイダーによって使用されるファイルの書式設定の設定が含まれています。また、ファイルのルーティング設定を選択して、ファイルの書き出し先を定義する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configuration-message/direct-mail-configuration.html?lang=ja#file-routing-configuration" text="ファイルのルーティングの設定"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="ファイル分割しきい値の定義"
>abstract="オーディエンスデータを含む各ファイルの最大レコード数を設定する必要があります。1 ～ 200,000 件のレコードを選択できます。指定したしきい値に達すると、残りのレコードに別のファイルが作成されます。"

[!DNL Journey Optimizer] でダイレクトメールを配信できるようにするには、チャネルサーフェスを作成して、メールプロバイダーが使用するファイルの書式設定の設定を定義する必要があります。

ダイレクトメールサーフェスには、ダイレクトメールファイルの書き出し先となるサーバーを定義するファイルのルーティング設定も含める必要があります。

1. チャネルサーフェスを作成します。 [詳細情報](channel-surfaces.md)

1. 「**[!UICONTROL ダイレクトメール]**」チャネルを選択します。

   ![](assets/surface-direct-mail-channel.png)

1. チャネルサーフェス設定の専用セクションでダイレクトメール設定を定義します。

   ![](assets/surface-direct-mail-settings.png)

   <!--![](assets/surface-direct-mail-settings-with-insertion.png)-->

1. ファイル形式として **[!UICONTROL CSV]** または&#x200B;**[!UICONTROL テキスト区切り]**&#x200B;を選択します。

1. を選択します。 **[!UICONTROL ファイルルーティング設定]** 作成したものの中に含まれています。 これにより、ダイレクトメールプロバイダーが使用するファイルの書き出し先が定義されます。

   >[!CAUTION]
   >
   >ファイルのルーティングオプションを設定していない場合は、ダイレクトメールサーフェスを作成できません。[詳細情報](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png)

   <!--![](assets/surface-direct-mail-file-routing-with-insertion.png)-->

1. ダイレクトメールサーフェスを送信します。

キャンペーン内で[ダイレクトメールメッセージの作成](../messages/create-direct-mail.md)を行うことができるようになりました。キャンペーンが開始されると、ターゲットオーディエンスデータを含んだファイルが、定義したサーバーに自動的に書き出されます。その後、ダイレクトメールプロバイダーは、そのファイルを取得して、ダイレクトメール配信を続行できます。

>[!NOTE]
>
>重複した行は自動的に削除されます。
>
>プロファイルデータを含む各ファイルの最大レコード数（行数）が多すぎる場合、残りのレコードに対して別のファイルが自動的に作成されます。

<!--
    In the **[!UICONTROL Insertion]** section, you can choose to automatically remove duplicate rows.

    Define the maximum number of records (i.e. rows) for each file containing profile data. After the specified threshold is reached, another file will be created for the remaining records.

    ![](assets/surface-direct-mail-split.png)

    For example, if there are 100,000 records in the file and the threshold limit is set to 60,000, the records will be split into two files. The first file will contain 60,000 rows, and the second file will contain the remaining 40,000 rows.

    >[!NOTE]
    >
    >NOTE You can set any number between 1 and 200,000 records, meaning each file must contain at least 1 row and no more than 200,000 rows.

-->