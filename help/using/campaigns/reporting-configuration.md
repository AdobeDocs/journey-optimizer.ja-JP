---
title: 実験用のJourney Optimizerレポートの設定
description: レポートデータソースの設定方法を説明します
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
exl-id: 327a0c45-0805-4f64-9bab-02d67276eff8
source-git-commit: 16c156d715a6b39652191909ca88f90e7f971706
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 4%

---

# 実験用のレポートの設定 {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="レポート用のデータセットの設定"
>abstract="レポートの設定では、キャンペーンレポートの「目標」タブで使用される追加の指標を取得できます。 技術ユーザーが実行する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="データセットの選択"
>abstract="イベントタイプのデータセットのみ選択できます。このデータセットには、サポートされている次のフィールドグループのうち少なくとも 1 つを含める必要があります。アプリケーションの詳細、コマースの詳細、Web の詳細。"

<!--The reporting data source configuration allows you to define a connection to a system in order to retrieve additional information that will be used in your reports.-->

レポートのデータソース設定を使用すると、 **[!UICONTROL 目標]** 」タブをクリックします。 [詳細情報](content-experiment.md#objectives-global)

>[!NOTE]
>
>レポートの設定は、技術ユーザーが実行する必要があります。 <!--Rights?-->

この設定の場合は、レポートに使用する追加の要素を含む 1 つ以上のデータセットを追加する必要があります。 これをおこなうには、次の手順に従います。 [下](#add-datasets).

<!--
➡️ [Discover this feature in video](#video)
-->

## 前提条件


データセットをレポート設定に追加する前に、そのデータセットを作成する必要があります。 詳しくは、 [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#create){target=&quot;_blank&quot;}。

* イベントタイプのデータセットのみを追加できます。

* これらのデータセットには、次のうち少なくとも 1 つを含める必要があります [フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **アプリの詳細**, **コマースの詳細**, **Web の詳細**.

   >[!NOTE]
   >
   >現在、これらのフィールドグループのみがサポートされています。

   例えば、購入や注文などのコマースデータに対する電子メールキャンペーンの影響を把握するには、 **コマースの詳細** フィールドグループを使用します。

   同様に、モバイルインタラクションに関するレポートを作成する場合は、 **アプリの詳細** フィールドグループを使用します。

   各フィールドグループに対応する指標が表示されます [ここ](#objective-list).

* これらのフィールドグループは、1 つまたは複数のデータセットで使用する 1 つまたは複数のスキーマに追加できます。

>[!NOTE]
>
>XDM スキーマとフィールドグループについて詳しくは、 [XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}。

## 各フィールドグループに対応する目標 {#objective-list}

次の表に、 **[!UICONTROL 目標]** 」タブに表示されます。

| フィールドグループ | 目標 |
|--- |--- |
| コマースの詳細 | 価格合計<br>支払い金額<br>（個別）チェックアウト<br>（個別）製品リストの追加数<br>（個別）製品リストの開封数<br>（個別）製品リストの削除<br>（個別）製品リスト表示<br>（個別）製品表示<br>（個別）購入<br>（一意）後で使用するために保存<br>製品価格合計<br>製品数 |
| アプリの詳細 | （個別）アプリの起動回数<br>アプリの初回起動<br>（個別）アプリインストール数<br>（個別）アプリのアップグレード |
| Web の詳細 | （個別）ページビュー数 |

## データセットを追加 {#add-datasets}

1. 次の **[!UICONTROL 管理]** メニュー、選択 **[!UICONTROL 設定]**. 内  **[!UICONTROL レポート]** セクションで、 **[!UICONTROL 管理]**.

   ![](assets/reporting-config-menu.png)

   既に追加されたデータセットのリストが表示されます。

1. 次の **[!UICONTROL データセット]** タブ、クリック **[!UICONTROL データセットを追加]**.

   ![](assets/reporting-config-add.png)

   >[!NOTE]
   >
   >次を選択した場合、 **[!UICONTROL システムデータセット]** 「 」タブには、システムで作成されたデータセットのみが表示されます。 他のデータセットを追加することはできません。

1. 次の **[!UICONTROL データセット]** ドロップダウンリストから、レポートに使用するデータセットを選択します。

   >[!CAUTION]
   >
   >選択できるのはイベントタイプのデータセットのみです。このデータセットには、サポートされている [フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **アプリの詳細**, **コマースの詳細**, **Web の詳細**. これらの条件に一致しないデータセットを選択した場合、変更を保存できません。

   ![](assets/reporting-config-datasets.png)

   のデータセットの詳細を説明します [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;}。

1. 次の **[!UICONTROL プロファイル ID]** ドロップダウンリストから、レポート内の各プロファイルを識別するために使用する dataset field 属性を選択します。

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >レポートに使用できる ID のみが表示されます。

1. この **[!UICONTROL プライマリID 名前空間を使用]** オプションはデフォルトで有効になっています。 選択した **[!UICONTROL プロファイル ID]** が **[!UICONTROL ID マップ]**&#x200B;を使用すると、このオプションを無効にして、表示されるドロップダウンリストから別の名前空間を選択できます。

   ![](assets/reporting-config-namespace.png)

   名前空間の詳細については、 [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja){target=&quot;_blank&quot;}。

1. 変更を保存し、選択したデータセットをレポート設定リストに追加します。

   >[!CAUTION]
   >
   >イベントタイプでないデータセットを選択した場合は、続行できません。

キャンペーンレポートを作成する際に、追加したデータセットで使用されるフィールドグループに対応する指標を表示できるようになりました。 次に移動： **[!UICONTROL 目標]** 」タブをクリックし、選択した指標を選択して、レポートを微調整します。 [詳細情報](content-experiment.md#objectives-global)

![](assets/reporting-config-objectives.png)

>[!NOTE]
>
>複数のデータセットを追加する場合、すべてのデータセットのすべてのデータをレポートに使用できます。

<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
