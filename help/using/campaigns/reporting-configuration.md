---
title: 実験用の Journey Optimizer レポートを設定
description: レポートデータソースの設定方法を学ぶ
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
ht-degree: 96%

---

# 実験用のレポートを設定 {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="レポート用のデータセットを設定"
>abstract="レポート設定では、キャンペーンレポートの「目的」タブで使用する追加指標を取得できます。技術ユーザーが実行する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="データセットの選択"
>abstract="イベントタイプのデータセットのみ選択できます。このデータセットには、サポートされている次のフィールドグループのうち少なくとも 1 つを含める必要があります。アプリケーションの詳細、コマースの詳細、Web の詳細。"

<!--The reporting data source configuration allows you to define a connection to a system in order to retrieve additional information that will be used in your reports.-->

レポートデータソースの設定により、キャンペーンレポートの「**[!UICONTROL 目的]**」タブで使用する追加指標を取得できます。[詳細情報](content-experiment.md#objectives-global)

>[!NOTE]
>
>レポートの設定は、技術ユーザーが実行する必要があります。<!--Rights?-->

この設定の場合は、レポートに使用する追加の要素を含む 1 つ以上のデータセットを追加する必要があります。 これをおこなうには、[以下](#add-datasets)の手順に従います。

<!--
➡️ [Discover this feature in video](#video)
-->

## 前提条件


レポート設定にデータセットを追加する前に、そのデータセットを作成する必要があります。方法については、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja#create){target=&quot;_blank&quot;}を参照してください。

* イベントタイプのデータセットのみを追加できます。

* これらのデータセットには、次の[フィールド グループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja#field-group){target=&quot;_blank&quot;}のうち少なくとも 1 つが含まれている必要があります：**アプリケーションの詳細**、**コマースの詳細**、 **web の詳細**。

   >[!NOTE]
   >
   >現在、これらのフィールドグループのみがサポートされています。

   例えば、メールキャンペーンが購入や注文などのコマースデータに与える影響を知りたい場合は、**コマースの詳細**&#x200B;フィールドグループを使用してエクスペリエンスイベントデータセットを作成する必要があります。

   同様に、モバイルインタラクションに関してレポートする場合は、**アプリケーションの詳細**&#x200B;フィールドグループを使用してエクスペリエンスイベントデータセットを作成する必要があります。

   各フィールドグループに対応する指標は[こちら](#objective-list)に表示されます。

* これらのフィールドグループは、1 つまたは複数のデータセットで使用する、1 つまたは複数のスキーマに追加できます。

>[!NOTE]
>
>XDM スキーマとフィールドグループについて詳しくは、[XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

## 各フィールドグループに対応する目標 {#objective-list}

以下の表は、各フィールドグループのキャンペーンレポートの「**[!UICONTROL 目標]**」タブに追加される指標を示しています。

| フィールドグループ | 目標 |
|--- |--- |
| コマースの詳細 | 価格合計<br>支払い金額<br>（一意の）チェックアウト<br>（一意の）製品リストの追加数<br>（一意の）製品リストの開封数<br>（一意の）製品リストの削除<br>（一意の）製品リスト表示<br>（一意の）製品表示<br>（一意の）購入<br>（一意の）後で使用するために保存<br>製品価格合計<br>製品数 |
| アプリケーションの詳細 | （一意の）アプリの起動回数<br>アプリの初回起動数<br>（一意の）アプリインストール数<br>（一意の）アプリのアップグレード数 |
| Web の詳細 | （一意の）ページビュー数 |

## データセットを追加 {#add-datasets}

1. **[!UICONTROL 管理]**&#x200B;メニューで、「**[!UICONTROL 設定]**」を選択します。「**[!UICONTROL レポート]**」セクションで、「**[!UICONTROL 管理]**」をクリックします。

   ![](assets/reporting-config-menu.png)

   既に追加されたデータセットのリストが表示されます。

1. 「**[!UICONTROL データセット]**」タブで、「**[!UICONTROL データセットを追加]**」をクリックします。

   ![](assets/reporting-config-add.png)

   >[!NOTE]
   >
   >「**[!UICONTROL システムデータセット]**」タブを選択した場合、システムで作成されたデータセットのみが表示されます。他のデータセットを追加することはできません。

1. **[!UICONTROL データセット]**&#x200B;ロップダウンリストで、レポートに使用するデータセットを選択します。

   >[!CAUTION]
   >
   >選択できるのは、次のサポートされている[フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}のうち少なくとも 1 つを含むイベントタイプのデータセットのみです：**アプリケーションの詳細**、**コマースの詳細**、**web の詳細**。これらの条件に一致しないデータセットを選択した場合、変更を保存できません。

   ![](assets/reporting-config-datasets.png)

   データセットについて詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

1. **[!UICONTROL プロファイル ID]**&#x200B;ドロップダウンリストで、レポート内の各プロファイルを識別するために使用するデータセットフィールド属性を選択します。

   ![](assets/reporting-config-profile-id.png)

   >[!NOTE]
   >
   >レポートに使用できる ID のみが表示されます。

1. 「**[!UICONTROL プライマリ ID 名前空間を使用]**」オプションはデフォルトで有効になっています。選択した&#x200B;**[!UICONTROL プロファイル ID]** が **[!UICONTROL ID マップ]**&#x200B;の場合、このオプションを無効にして、表示されるドロップダウンリストから別の名前空間を選択できます。

   ![](assets/reporting-config-namespace.png)

   名前空間について詳しくは、[Adobe Experience Platform のドキュメント](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ja){target=&quot;_blank&quot;}を参照してください。

1. 変更を保存し、選択したデータセットをレポート設定リストに追加します。

   >[!CAUTION]
   >
   >イベントタイプでないデータセットを選択した場合は、続行できません。

キャンペーンレポートを作成する際に、追加したデータセットで使用されるフィールドグループに対応する指標を表示できるようになりました。「**[!UICONTROL 目標]**」タブに移動し、目的の指標を選択して、レポートを微調整します。[詳細情報](content-experiment.md#objectives-global)

![](assets/reporting-config-objectives.png)

>[!NOTE]
>
>複数のデータセットを追加した場合、すべてのデータセットのすべてのデータをレポートできるようになります。

<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
