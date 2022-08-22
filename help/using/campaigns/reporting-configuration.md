---
title: レポート設定
description: レポートデータソースの設定方法を説明します
feature: Data Sources
topic: Administration
role: Admin
level: Intermediate
hide: true
hidefromtoc: true
source-git-commit: 11f7ce37dc1a99de4ed29fa7793f126e259f518d
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 5%

---

# レポート設定 {#reporting-configuration}

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_config"
>title="レポート用のデータセットの設定"
>abstract="レポート設定を使用すると、システムへの接続を定義して、レポートで使用する追加のカスタム情報を取得できます。 技術ユーザーが実行する必要があります。"

>[!CONTEXTUALHELP]
>id="ajo_admin_reporting_dataset"
>title="データセットの選択"
>abstract="選択できるのは、サポートされているフィールドグループの 1 つ以上を含む必要があるイベントタイプデータセットのみです。experienceevent-web、experienceevent-application、experienceevent-commerce。"

レポートデータソースの設定を使用すると、システムへの接続を定義して、レポートで使用される追加情報を取得できます。

>[!NOTE]
>
>データソースの設定は、技術ユーザーが実行する必要があります。 <!--Rights?-->

この設定の場合は、レポートに使用する属性を含む 1 つ以上のデータセットを追加する必要があります。 それには、次の手順に従います。

>[!CAUTION]
>
>データセットをレポート設定に追加する前に、データセットを作成する必要があります。 詳しくは、 [Adobe Experience Platformドキュメント](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=en#create){target=&quot;_blank&quot;}。
>
>イベントタイプのデータセットのみを追加できます。追加できるデータセットには、サポートされている [フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **experienceevent-web**, **experienceevent-application**, **experienceevent-commerce**.

<!--
➡️ [Discover this feature in video](#video)
-->

例えば、購入や注文などのコマースデータに対する電子メールキャンペーンの影響を把握するには、 **experienceevent-commerce** フィールドグループを使用します。 同様に、モバイルインタラクションに関するレポートを作成する場合は、 **experienceevent-application** フィールドグループを使用します。 <!--If you want to report on web interactions then you need to include the web field group.--> これらのフィールドグループを、1 つのデータセットまたは異なるデータセットで使用する 1 つまたは複数のスキーマに追加できます。

>[!NOTE]
>
>XDM スキーマとフィールドグループについて詳しくは、 [XDM システムの概要ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja){target=&quot;_blank&quot;}。

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
   >選択できるのはイベントタイプのデータセットのみです。このデータセットには、サポートされている [フィールドグループ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#field-group){target=&quot;_blank&quot;}: **experienceevent-web**, **experienceevent-application**, **experienceevent-commerce**. これらの条件に一致しないデータセットを選択した場合、変更を保存できません。

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

配信のレポートを作成する際に、このデータセットのデータを使用して、追加のカスタム情報を取得し、レポートをより微調整できるようになりました。 [詳細情報](campaign-global-report.md#objectives-global)

>[!NOTE]
>
>複数のデータセットを追加する場合、すべてのデータセットのすべてのデータをレポートに使用できます。


<!--
## How-to video {#video}

Understand how to configure Experience Platform reporting data sources.

>[!VIDEO]()
-->
