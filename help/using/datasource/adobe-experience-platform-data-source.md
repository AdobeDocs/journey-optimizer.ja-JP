---
solution: Journey Optimizer
product: journey optimizer
title: Adobe Experience Platform のデータソース
description: Adobe Experience Platform のデータソースの設定方法を学ぶ
feature: Journeys, Data Sources
topic: Administration
role: Data Engineer, Data Architect, Admin
level: Intermediate, Experienced
keywords: 組み込み, ソース, データ, Platform, 統合
exl-id: 9083e355-15e3-4d1f-91ae-03095e08ad16
source-git-commit: e45ec5f0e1bbcc73892f9cde5923627886f44ef6
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 100%

---

# Adobe Experience Platform のデータソース {#adobe-experience-platform-data-source}

>[!CONTEXTUALHELP]
>id="ajo_journey_data_source_built_in"
>title="Adobe Experience Platform のデータソース"
>abstract="Adobe Experience Platform のデータソースは、Adobe リアルタイム顧客プロファイルサービスへの接続を定義します。このデータソースは組み込みで事前に設定されているので、削除できません。これは、リアルタイム顧客プロファイルサービスからデータを取得して使用するように設計されています（例えば、ジャーニーにエントリしたユーザーが女性かどうかを確認します）。プロファイルデータとエクスペリエンスイベントデータを使用できます。"

Adobe Experience Platform のデータソースは、Adobe リアルタイム顧客プロファイルサービスへの接続を定義します。このデータソースは組み込みで事前に設定されているので、削除できません。このデータソースは、リアルタイム顧客プロファイルサービスからデータを取得して使用するように設計されています（例えば、ジャーニーにエントリした人物が女性かどうかを確認します）。プロファイルデータとエクスペリエンスイベントデータを使用できます。Adobe リアルタイム顧客プロファイルサービスについて詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja){target="_blank"}を参照してください。

リアルタイム顧客プロファイルサービスへの接続を可能にするには、人物を特定するキーと、キーを説明する名前空間前を使用する必要があります。その結果、このデータソースは、ジャーニーが、キーと名前空間を含むイベントで開始する場合にのみ使用できます。[詳細情報](../building-journeys/journey.md)。

「ProfileFieldGroup」という名前の事前設定済みフィールドグループを編集し、新しいグループを追加して、ドラフトまたはライブジャーニーで使用されていないフィールドグループを削除できます。[詳細情報](../datasource/configure-data-sources.md#define-field-groups)。

>[!NOTE]
>
>1 年以内に作成された際の 1,000 件のエクスペリエンスイベントを取得できます。

ビルトインデータソースにフィールドグループを追加する主な手順は次のとおりです。

1. データソースのリストから、ビルトインの Adobe Experience Platform データソースを選択します。

   画面の右側にデータソース設定ペインが開きます。


   ![](assets/journey23.png)

1. 「**[!UICONTROL 新しいフィールドグループを追加]**」をクリックして、新しく取得する一連のフィールドを定義します。[詳細情報](../datasource/configure-data-sources.md#define-field-groups)。

   ![](assets/journey24.png)

1. **[!UICONTROL スキーマ]**&#x200B;ドロップダウンからスキーマを選択します。このフィールドリストのプロファイルとエクスペリエンスのイベントスキーマは、Adobe Experience Platform で入手できます。[!DNL Journey Optimizer] ではスキーマの作成は実行されません。Adobe Experience Platformでおこなわれます
1. 使用するフィールドを選択します。
1. 「**[!UICONTROL 保存]**」をクリックします。

フィールドグループの名前にカーソルを置くと、右側に 2 つのアイコンが表示されます。これらのアイコンを使用すると、フィールドグループを削除および複製できます。**[!UICONTROL 削除]**&#x200B;アイコンは、フィールドグループがライブジャーニーまたはドラフトジャーニー（「**[!UICONTROL 使用されている場所]**」フィールドに表示される情報）で使用されていない場合にのみ使用できます。
