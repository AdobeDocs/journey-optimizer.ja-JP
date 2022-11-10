---
title: ダイレクトメールの設定
description: Journey Optimizerでダイレクトメールチャネルを設定する方法を説明します
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
ht-degree: 1%

---

# ダイレクトメールの設定 {#direct-mail-configuration}

[!DNL Journey Optimizer] では、ダイレクトメールプロバイダーが顧客にメールを送信するために必要なファイルをパーソナライズおよび生成できます。

条件 [ダイレクトメールメッセージの作成](../messages/create-direct-mail.md)」をクリックすると、選択した連絡先情報（例えば、郵送先住所）を含む、ターゲットオーディエンスデータを定義できます。 このデータが含まれるファイルが自動的に生成され、サーバーにエクスポートされます。ダイレクトメールプロバイダーは、このファイルを取得して、実際の送信処理をおこなうことができます。

このファイルを生成する前に、以下を作成する必要があります。

1. A [ファイルルーティング設定](#file-routing-configuration) ：ファイルを書き出すサーバーを指定します。

1. A [ダイレクトメール面](#direct-mail-surface) ファイルルーティング設定を参照する

>[!CAUTION]
>
>ファイルルーティングオプションを設定していない場合、ダイレクトメールサーフェスを作成できません。

## ファイルルーティングの設定 {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="ファイルルーティング設定を定義"
>abstract="ダイレクトメールメッセージを作成すると、ターゲットオーディエンスデータを含むファイルが生成され、サーバーに書き出されます。 ダイレクトメールプロバイダーがそのファイルにアクセスして、ダイレクトメールの配信に使用できるように、サーバーの詳細を指定する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/create-direct-mail.html" text="ダイレクトメールメッセージの作成"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details_header"
>title="ファイルルーティング設定を定義"
>abstract="ダイレクトメールプロバイダーが使用するファイルのエクスポート先を定義する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_dm_select_file_routing"
>title="ファイルルーティング設定"
>abstract="任意のファイルルーティング設定を選択します。この設定は、ダイレクトメールプロバイダーが使用するファイルの書き出し先を定義します。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_type"
>title="ファイルのサーバータイプを選択"
>abstract="ダイレクトメールファイルのエクスポートに使用するサーバーの種類を選択します。 現在、Journey OptimizerではAmazon S3 と SFTP のみがサポートされています。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_aws_region"
>title="AWS地域の選択"
>abstract="ダイレクトメールファイルをエクスポートするAWSサーバーの地域を選択します。 一般的には、ダイレクトメールプロバイダーの場所に最も近い地域を選択することをお勧めします。"

ダイレクトメールメッセージを配信するには、 [!DNL Journey Optimizer] は、ターゲットオーディエンスデータを含むファイルを生成し、サーバーに書き出します。

ダイレクトメールプロバイダーがそのファイルにアクセスしてメールの配信に使用できるように、サーバーの詳細を指定する必要があります。

ファイルのルーティングを設定するには、次の手順に従います。

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL ファイルルーティング設定]** > **[!UICONTROL ファイルルーティング]** メニュー、次に「 **[!UICONTROL ルーティング設定を作成]**.

   ![](assets/file-routing-config-button.png)

1. 設定の名前を設定します。

1. を選択します。 **[!UICONTROL サーバータイプ]** をクリックします。

   ![](assets/file-routing-config-type.png)

   >[!NOTE]
   >
   >現在、では、Amazon S3 と SFTP のみがサポートされています。 [!DNL Journey Optimizer].

1. サーバーの詳細と資格情報（サーバーアドレス、アクセスキーなど）を入力します。

   ![](assets/file-routing-config-sftp-details.png)

1. 選択した場合 **[!UICONTROL Amazon S3]**、 **[!UICONTROL AWS]** サーバインフラストラクチャが配置される場所。

   ![](assets/file-routing-config-aws-region.png)

   >[!NOTE]
   >
   >AWSの地域は、AWSがクラウドインフラストラクチャをホストするために使用する地理的地域です。 一般的には、ダイレクトメールプロバイダーの場所に最も近い地域を選択することをお勧めします。

1. **[!UICONTROL 送信]**&#x200B;を選択します。ファイルルーティング設定は、 **[!UICONTROL アクティブ]** ステータス。 これで、 [ダイレクトメール面](#direct-mail-surface).

   >[!NOTE]
   >
   >また、 **[!UICONTROL ドラフトとして保存]** ファイルルーティング設定を作成する場合は、その設定が作成されるまでサーフェスで選択できません。 **[!UICONTROL アクティブ]**.

## ダイレクトメールサーフェスを作成する {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="ダイレクトメール設定の定義"
>abstract="ダイレクトメールの表面には、対象のオーディエンスデータを含み、メールプロバイダが使用するファイルの形式設定に関する設定が含まれています。 また、ファイルルーティング設定を選択して、ファイルの書き出し先を定義する必要があります。"
>additional-url="https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configuration-message/direct-mail-configuration.html#file-routing-configuration" text="ファイルルーティングの設定"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="ファイル分割しきい値を定義"
>abstract="オーディエンスデータを含む各ファイルの最大レコード数を設定する必要があります。 1 ～ 200,000 個のレコードを選択できます。 指定したしきい値に達すると、残りのレコードに別のファイルが作成されます。"

ダイレクトメールを [!DNL Journey Optimizer]の場合は、チャネルサーフェスを作成して、メールプロバイダが使用するファイルの形式設定の設定を定義する必要があります。

ダイレクトメールサーフェスには、ダイレクトメールファイルをエクスポートするサーバーを定義するファイルルーティング設定も含める必要があります。

1. チャネルサーフェスの作成. [詳細情報](channel-surfaces.md)

1. を選択します。 **[!UICONTROL ダイレクトメール]** チャネル。

   ![](assets/surface-direct-mail-channel.png)

1. チャネルサーフェス設定の専用セクションでダイレクトメール設定を定義します。

   ![](assets/surface-direct-mail-settings.png)

   <!--![](assets/surface-direct-mail-settings-with-insertion.png)-->

1. ファイル形式を選択します。 **[!UICONTROL CSV]** または **[!UICONTROL 区切り文字]**.

1. を選択します。 **[!UICONTROL ファイルルーティング設定]** 作成したものの中に含まれています。 これは、ダイレクトメールプロバイダーが使用できるようにファイルを書き出す場所を定義します。

   >[!CAUTION]
   >
   >ファイルルーティングオプションを設定していない場合、ダイレクトメールサーフェスを作成できません。 [詳細情報](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png)

   <!--![](assets/surface-direct-mail-file-routing-with-insertion.png)-->

1. ダイレクトメールサーフェスを送信します。

次の操作を実行できます。 [ダイレクトメールメッセージの作成](../messages/create-direct-mail.md) キャンペーン内で キャンペーンが開始されると、ターゲットオーディエンスデータを含むファイルが、定義したサーバーに自動的にエクスポートされます。 その後、ダイレクトメールプロバイダーは、そのファイルを取得して、ダイレクトメール配信を続行できます。

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