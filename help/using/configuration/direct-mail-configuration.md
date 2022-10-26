---
title: ダイレクトメールの設定
description: Journey Optimizerでダイレクトメールチャネルを設定する方法を説明します
feature: Overview
topic: Content Management
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 1f6b29d781abc17e238e4a3e051dc61d250b37a0
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 3%

---

# ダイレクトメールの設定 {#direct-mail-configuration}

[!DNL Journey Optimizer] では、ダイレクトメールプロバイダーが顧客にメールを送信するために必要なファイルをパーソナライズおよび生成できます。

ダイレクトメール配信を準備する際、 [!DNL Journey Optimizer] は、すべてのターゲットプロファイルと選択した連絡先情報（例：郵送先住所）を含むファイルを生成します。 その後、このファイルを実際の発送処理をおこなうダイレクトメールプロバイダーに送信できます。

ダイレクトメールメッセージを送信するには、ファイルを作成し、サーバーにアップロードする必要があります。 その前に、 [ファイルルーティング設定](#file-routing-configuration) および [ダイレクトメール面](#direct-mail-surface) ファイルルーティング設定を参照する

## ファイルルーティングの設定 {#file-routing-configuration}

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details"
>title="ファイルルーティング設定の設定を定義する"
>abstract="ダイレクトメールメッセージを作成する際に、必要なプロファイル情報をすべて含んだファイルが生成されます。 このファイルは、ダイレクトメールプロバイダーがそのファイルにアクセスしてダイレクトメール配信に使用できるように、サーバーにエクスポートしてアップロードする必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_details_header"
>title="ファイルルーティング設定の設定を定義する"
>abstract="ダイレクトメールプロバイダーが使用するファイルの書き出し場所とアップロード先を定義する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_dm_select_file_routing"
>title="ファイルルーティング設定"
>abstract="任意のファイルルーティング設定を選択します。この設定は、ダイレクトメールプロバイダーが使用するファイルのエクスポートおよびアップロード先を定義します。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_type"
>title="ファイルルーティングのサーバータイプを選択"
>abstract="ダイレクトメールファイルのアップロードと保存に使用するサーバーを選択します。 現在、Amazon S3 と SFTP のみがサポートされています。"

>[!CONTEXTUALHELP]
>id="ajo_dm_file_routing_aws_region"
>title="AWS地域の選択"
>abstract="ダイレクトメールファイルの書き出しおよびアップロードを行う地域を選択します。 最適な使用方法を得るには、クラウドインフラストラクチャをホストする最も近い地域を選択することをお勧めします。"

1. 次にアクセス： **[!UICONTROL 管理]** > **[!UICONTROL チャネル]** > **[!UICONTROL ファイルルーティング設定]** > **[!UICONTROL ファイルルーティング]** メニュー、次に「 **[!UICONTROL ルーティング設定を作成]**.

   ![](assets/file-routing-config-button.png)

1. 設定の名前を設定します。

1. 設定を選択 **[!UICONTROL サーバータイプ]**（ダイレクトメールファイルのアップロードと保存に使用するサーバー）。

   ![](assets/file-routing-config-type.png)

   >[!NOTE]
   >
   >現在、Amazon S3 と SFTP のみを使用できます。

   ダイレクトメールメッセージを作成する際に、必要なプロファイル情報をすべて含んだファイルが生成されます。 このファイルは、ダイレクトメールプロバイダーがそのファイルにアクセスしてダイレクトメール配信に使用できるように、サーバーにエクスポートしてアップロードする必要があります。

1. サーバーアドレス、アクセスキーなど、選択した設定タイプに固有の詳細と資格情報を入力します。

   ![](assets/file-routing-config-sftp-details.png)

1. 選択した場合 **[!UICONTROL Amazon S3]**「 」で、ダイレクトメールファイルの書き出しおよびアップロードを行うAWS地域を選択します。

   ![](assets/file-routing-config-aws-region.png)

   >[!NOTE]
   >
   >AWSの地域は、AWSがインフラストラクチャを収容するために使用する、世界中に分散した別々の地域です。 最適な使用方法を得るには、クラウドインフラストラクチャをホストする最も近い地域を選択することをお勧めします。

1. **[!UICONTROL 送信]**&#x200B;を選択します。ファイルルーティング設定は、 **[!UICONTROL アクティブ]** ステータス。 これで、ダイレクトメールをダイレクトメール表面で使用して、からダイレクトメールを配信する準備が整いました。 [!DNL Journey Optimizer].

   >[!NOTE]
   >
   >また、 **[!UICONTROL ドラフトとして保存]** ファイルルーティング設定を作成する場合は、その設定が作成されるまでサーフェスで選択できません。 **[!UICONTROL アクティブ]**.

## ダイレクトメールサーフェスを作成する {#direct-mail-surface}

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_settings"
>title="ダイレクトメール設定の定義"
>abstract="ダイレクトメールサーフェスには、ダイレクトメール用のプロファイルデータを含むファイルの形式設定に関する設定が含まれています。 また、ファイルルーティング設定を選択して、ファイルの書き出し先を定義する必要があります。"

<!--
>[!CONTEXTUALHELP]
>id="ajo_dm_surface_sort"
>title="Define the sort order"
>abstract="If you select this option, the sort will be by profile ID, ascending or descending. If you unselect it, the sorting configuration defined when creating the direct mail message within a journey or a campaign."-->

>[!CONTEXTUALHELP]
>id="ajo_dm_surface_split"
>title="ファイル分割しきい値を定義"
>abstract="プロファイルデータを含む各ファイルの最大レコード数を設定する必要があります。 指定したしきい値に達すると、残りのレコードに別のファイルが作成されます。"

ファイルルーティングを設定したら、ダイレクトメールを配信できるように、チャネルサーフェスを作成する必要があります。 [!DNL Journey Optimizer]. 各サーフェスで、ファイルのルーティング設定を選択する必要があります。

1. チャネルサーフェスの作成. [詳細情報](channel-surfaces.md)

1. を選択します。 **[!UICONTROL ダイレクトメール]** チャネル。

   ![](assets/surface-direct-mail-channel.png)

1. チャネルサーフェス設定の専用セクションでダイレクトメール設定を定義します。

   ![](assets/surface-direct-mail-settings.png)

1. ファイル形式を選択します。 **[!UICONTROL CSV]** または **[!UICONTROL 区切り文字]**.

1. 内 **[!UICONTROL 挿入]** 「 」セクションで、重複行を自動的に削除するよう選択できます。

1. プロファイルデータを含む各ファイルの最大レコード数（行数）を定義します。 指定したしきい値に達すると、残りのレコードに別のファイルが作成されます。

   ![](assets/surface-direct-mail-split.png)

   例えば、ファイルに 100,000 個のレコードがあり、しきい値の制限が 60,000 に設定されている場合、レコードは 2 つのファイルに分割されます。 最初のファイルには 60,000 行、2 番目のファイルには残りの 40,000 行が含まれます。

   >[!NOTE]
   >
   >1 ～ 200,000 個のレコードの任意の数値を設定できます。つまり、各ファイルには少なくとも 1 つの行と 200,000 行以下の行を含める必要があります。

1. 最後に、 **[!UICONTROL ファイルルーティング設定]** 作成したものの中に含まれています。 これは、ダイレクトメールプロバイダーが使用できるように、ファイルの書き出しとアップロードを行う場所を定義します。

   >[!CAUTION]
   >
   >ファイルルーティングオプションを設定していない場合、ダイレクトメールサーフェスを作成できません。 [詳細情報](#file-routing-configuration)

   ![](assets/surface-direct-mail-file-routing.png)