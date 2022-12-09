---
solution: Journey Optimizer
product: journey optimizer
title: 実験用の旅オプティマイザーのレポートの設定
description: レポートデータソースの設定方法について説明します。
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 327a0c45-0805-4f64-9bab-02d67276eff8
source-git-commit: 021cf48ab4b5ea8975135a20d5cef8846faa5991
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 0%

---

# 実験用のレポートの設定 {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="レポート用のデータセットの設定"
>abstract="レポート設定を使用すると、キャンペーンレポートの目的タブに表示されるその他のメトリックスを取得することができます。 これは、テクニカルユーザーによって実行される必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="データセットを選択します。"
>abstract="選択できるイベントタイプのデータセットは、サポートされているフィールドグループのうち少なくとも1つを含む必要があります。これには、Application Details、商業詳細、Web 詳細が含まれています。"

<!--The reporting data source configuration allows you to define a connection to a system in order to retrieve additional information that will be used in your reports.-->

レポートデータソース設定を使用すると、キャンペーンレポートのタブに **[!UICONTROL Objectives]** 表示される追加のメトリックスを取得することができます。 [詳細情報](content-experiment.md#objectives-global)

>[!NOTE]
>
>レポート設定は、テクニカルユーザーが実行する必要があります。 <!--Rights?-->

この設定では、レポートに使用する追加エレメントを含む1つまたは複数のデータセットを追加する必要があります。 これを行うには、次の手順 [ ](#add-datasets) を実行します。

<!--
➡️ [Discover this feature in video](#video)
-->

## 知識


データセットをレポート構成に追加するには、事前にそのデータセットを作成しておく必要があります。 Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#create) {target = &quot;_blank&quot;} についての説明を参照して [ ください。

* イベントタイプのデータセットを追加することはできません。

* このようなデータセットには、次 [ のフィールドグループ ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group) のうち少なくとも1つを含める必要があります {target = &quot;_blank&quot;}: **Application Details** 、 **商業 Details** 、 **Web Details**

   >[!NOTE]
   >
   >これらのフィールドグループのみが現在サポートされています。

   例えば、購買や注文などの commerce データに対する電子メールキャンペーンの影響について理解する必要がある場合は、「commerce Details **」フィールドグループを使用** して、経験イベントデータセットを作成する必要があります。

   同様に、モバイルインタラクションについてのレポートを作成する場合は、Application Details **フィールドグループを使用して** 、経験イベントデータセットを作成する必要があります。

   各フィールドグループに対応するメトリックがここに ](#objective-list) 一覧表示 [ されます。

* これらのフィールドグループは、1つまたは複数のデータセットで使用される1つまたは複数のスキーマに追加できます。

>[!NOTE]
>
>Xdm について詳しくは、 [ xdm の「システム概要 ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en) について」を参照してください。 {target = &quot;_blank&quot;}。

## 各フィールドグループに対応する目的 {#objective-list}

以下の表は、各フィールドグループのキャンペーンレポートのタブに追加されるメトリックを **[!UICONTROL Objectives]** 示しています。

| フィールドグループ | 学習 |
|--- |--- |
| 商取引の詳細 | 価格合計 <br> 支払額 <br> (一意 <br> ) 製品リストの追加 <br> (一意) 製品リストの表示 <br> (独自) 製品リストの削除 <br> (一意) 製品リストビュー (一意) 製品一覧ビュー <br> (一意) 製品ビュー <br> <br> (一意) Laters <br> 製品価格合計 <br> 製品の数量 |
| アプリケーションの詳細 | Uniqueアプリが最初 <br> に起動 <br> (一意) アプリケーションのインストール <br> (独自) アプリアップグレード |
| Web の詳細 | Uniqueページビュー |

## データセットの追加 {#add-datasets}

1. **[!UICONTROL ADMINISTRATION]**&#x200B;メニューから、を選択 **[!UICONTROL Configurations]** します。**[!UICONTROL Reporting]**&#x200B;セクションのをクリック **[!UICONTROL Manage]** します。

   ![](assets/reporting-config-menu.png)

   既に追加されたデータセットのリストが表示されます。

1. **[!UICONTROL Dataset]**&#x200B;タブでをクリック **[!UICONTROL Add dataset]** します。

   ![](assets/reporting-config-add.png)

   >[!NOTE]
   >
   >タブを選択 **[!UICONTROL System dataset]** した場合は、システムによって作成されたデータセットのみが表示されます。 他のデータセットを追加することはできません。

1. **[!UICONTROL Dataset]**&#x200B;ドロップダウンリストから、レポートに使用するデータセットを選択します。

   >[!CAUTION]
   >
   >選択できるイベントタイプのデータセットは、サポートされて [ いるフィールドグループ ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group) のうち、少なくとも1つは {target = &quot;_blank&quot;}: **Application Details** 、 **商業 Details** 、 **Web details** 、のいずれかを含む必要があります。 この条件に一致しないデータセットを選択した場合は、変更を保存することはできません。

   ![](assets/reporting-config-datasets.png)

   Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html) のデータセットについて詳しくは、 [ {target = &quot;_blank&quot;} を参照してください。

1. **[!UICONTROL Profile ID]**&#x200B;ドロップダウンリストから、レポート内の各プロファイルを識別するために使用されるデータセットのフィールド属性を選択します。

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >レポートに使用できる Id のみが表示されます。

1. **[!UICONTROL Use Primary ID namespace]**&#x200B;このオプションは初期設定では有効になっています。が **[!UICONTROL Identity Map]** 選択 **[!UICONTROL Profile ID]** されている場合は、このオプションを無効にして、表示されるドロップダウンリストから別の名前空間を選択することもできます。

   ![](assets/reporting-config-namespace.png)

   Adobe エクスペリエンスプラットフォームマニュアル ](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) の名前空間について詳しくは、 [ {target = &quot;_blank&quot;} を参照してください。

1. 変更を保存して、選択したデータセットをレポート設定リストに追加します。

   >[!CAUTION]
   >
   >イベントタイプではないデータセットを選択した場合、処理を続行することはできません。

キャンペーンレポートの作成時に、追加したデータセットで使用されているフィールドグループに対応するメトリックが表示されるようになりました。 タブに **[!UICONTROL Objectives]** 移動して、選択したメトリックを選択して、レポートをより細かく調整します。 [詳細情報](content-experiment.md#objectives-global)

![](assets/reporting-config-objectives.png)

>[!NOTE]
>
>複数のデータセットを追加した場合は、すべてのデータセットのすべてのデータをレポートに使用できます。

<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
