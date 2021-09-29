---
product: experience platform
solution: Experience Platform
title: Offer Decisioning へのアクセス付与
description: Adobe Admin Console 経由で Offer Decisioning サービスに対するユーザーの権限を管理する方法について説明します。
feature: Collections
role: User
level: Intermediate
exl-id: 2a2fece9-1ad5-498e-b0ee-5bb0b73a2cd5
source-git-commit: 43fb98a08555e6b889ad537e79dba78286dafeb9
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 58%

---

# 意思決定管理へのアクセス権の付与 {#granting-acess-to-decision-management}

offer decisioning機能にアクセスして使用する権限は、[Adobe Admin Console](https://helpx.adobe.com/jp/enterprise/managing/user-guide.html){target=&quot;_blank&quot;}を使用して管理されます。

Decision Management機能へのアクセス権を付与するには、**[!UICONTROL 製品プロファイル]**&#x200B;を作成し、対応する権限をユーザーに割り当てる必要があります。 [!DNL Journey Optimizer]ユーザーと権限の管理について詳しくは、[この節](../../administration/permissions.md)を参照してください。

判定管理に関する権限の一覧は、[この節](../../administration/high-low-permissions.md#manage-decisioning)に記載されています。

<!--If you are a [!DNL Journey Optimizer] user leveraging the **Decision Management** functionality, you need to have the [Decision management permissions](../../administration/high-low-permissions.md#decisions-permissions) enabled to acces all related capabilities. Learn more on managing [!DNL Journey Optimizer] users and permissions in [this section](../../administration/permissions.md).

If you are an [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target="_blank"} user leveraging the **Offer Decisioning** application service, follow the steps [below](#granting-acess-to-offer-decisioning) to grant access to [!DNL Offer Decisioning].

Grant access to Offer Decisioning

The steps below only apply to **Experience Platform users** leveraging the [!DNL Offer Decisioning] service.-->

1. [Admin Console](https://helpx.adobe.com/enterprise/managing/user-guide.html)を開き、**[!UICONTROL Adobe Experience Platform]**&#x200B;を選択します。

   <!--![](../../assets/offers_admin_console.png)-->

1. サービスの製品プロファイルが表示されます。新しい製品プロファイルを作成するには、「**[!UICONTROL 新規プロファイル]**」ボタンをクリックします。

   ![](../../assets/offers_rights_productprofile.png)

   >[!NOTE]
   >
   >組織に対して設定する様々な役割に対応した、必要な数のプロファイルを持つことができます。

1. 製品プロファイルの名前と説明を指定し、「**[!UICONTROL 次へ]**」をクリックします。

   ![](../../assets/create-product-profile.png)

   <!--To access the product profile’s permissions, select the **[!UICONTROL Permissions]** line.-->

1. 製品プロファイルに対して有効にするサービスを選択します。デフォルトでは、すべてのサービスが選択されています。すべての Experience Platform 機能が使用可能であることを確認しておくことをお勧めします。

   ![](../../assets/enable-services.png)

1. **[!UICONTROL 「Decision Management]**」セクションで、「**+**」ボタンをクリックして製品プロファイルに権限を割り当て、「**[!UICONTROL 保存]**」をクリックします。

   ![](../../assets/configure-profile.png)

   使用可能な権限は次のとおりです。

   **[!UICONTROL Decisioning アクティビティの管理]**:

   * オファーの読み取り、書き込み、削除
   * 決定（旧称：オファーアクティビティ）の読み取り、書き込み、削除
   * プレースメントの読み取り、書き込み、削除

   **[!UICONTROL Decisioning アクティビティの実行]**:

   * オファーの読み取り
   * 決定の読み取り
   * プレースメントの読み取り

   **[!UICONTROL Decisioning オプションの管理]**:

   * オファーの読み取り、書き込み、削除
   * 決定の読み取り
   * プレースメントの読み取り、書き込み、削除



1. 製品プロファイルの権限の概要が表示されます。ユーザーが製品プロファイルにアクセスできるように、ユーザーを割り当てることができます。

   ![](../../assets/product-profile-created.png)

>[!NOTE]
>
>Admin Consoleの権限の管理方法の詳細については、ユーザーのドキュメント[{target=&quot;_blank&quot;}を参照してください。](https://helpx.adobe.com/enterprise/managing/user-guide.html)

