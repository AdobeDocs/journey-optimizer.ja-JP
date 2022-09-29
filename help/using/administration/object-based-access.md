---
title: オブジェクトレベルのアクセス制御
description: オブジェクトレベルのアクセス制御の詳細
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
source-git-commit: 61293a2ad45d30d24e1b38d8a5df81534dc19b40
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 13%

---

# オブジェクトレベルのアクセス制御 {#object-level-access}

>[!CONTEXTUALHELP]
>id="ajo_olac_manage_access"
>title="オブジェクトレベルのアクセス制御"
>abstract="アクセス権のないラベルを適用すると、このオブジェクトへのアクセス権が失効します。"

>[!IMPORTANT]
>
>オブジェクトレベルのアクセス制御の使用は、現在、選択した顧客に制限されており、将来のリリースですべての環境にデプロイされます。

オブジェクトレベルのアクセス制御 (OLAC) を使用すると、以下のような様々なオブジェクトへのデータアクセスを管理する権限を定義できます。

* ジャーニー
* キャンペーン
* Landing page
* オファー
* オファーコレクション
* Offer decisioning

その目的は、機密性の高いデジタルアセットを権限のないユーザーから保護し、個人データの保護を向上させることです。

Adobe Journey Optimizerでは、OLAC を使用して、データを保護し、特定のオブジェクトに対して特定のアクセス権を付与できます。

## ラベルの作成 {#create-assign-labels}

>[!IMPORTANT]
>
>ラベルを作成するには、が **[!UICONTROL 使用状況ラベルの管理]** 権限。

**[!UICONTROL ラベル]** を使用すると、データに適用される使用ポリシーに従ってデータセットとフィールドを分類できます。 **[!UICONTROL ラベルはいつでも適用でき、データの管理方法を柔軟に選択できます。]**

ラベルは [!DNL Permissions] 製品。 詳しくは、[このページ](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/labels.html)を参照してください。

**[!UICONTROL ラベル]** また、Journey Optimizerで直接作成することもできます。

1. Adobe Journey Optimizerオブジェクトから、新しく作成された **[!UICONTROL Campaign]**、 **[!UICONTROL アクセスを管理]** 」ボタンをクリックします。

   ![](assets/olac_1.png)

1. 次の **[!UICONTROL アクセスを管理]** ウィンドウ、クリック **[!UICONTROL ラベルを作成]**.

   ![](assets/olac_2.png)

1. ラベルを設定するには、次を指定する必要があります。
   * **[!UICONTROL 名前]**
   * **[!UICONTROL わかりやすい名前]**
   * **[!UICONTROL 説明]**

   ![](assets/olac_3.png)

1. クリック **[!UICONTROL 作成]** を **[!UICONTROL ラベル]**.

新しく作成された **[!UICONTROL ラベル]** がリストで使用できるようになりました。 必要に応じて、 [!DNL Permissions] 製品。

## ラベルの割り当て {#assign-labels}

>[!IMPORTANT]
>
>ラベルを割り当てるには、管理権限を持つ役割 ( ) に属している必要があります。 [!DNL Manage journeys], [!DNL Manage Campaigns] または [!DNL Manage decisions]. この許可がなければ、 **[!UICONTROL アクセスを管理]** ボタンがグレー表示されます。

カスタムまたはコアのデータ使用ラベルをJourney Optimizerオブジェクトに割り当てるには：

1. Adobe Journey Optimizerオブジェクトから、新しく作成された **[!UICONTROL Campaign]**、 **[!UICONTROL アクセスを管理]** 」ボタンをクリックします。

   ![](assets/olac_1.png)

1. 次の **[!UICONTROL アクセスを管理]** ウィンドウで、このオブジェクトへのアクセスを管理するカスタムまたはコアのデータ使用ラベルを選択します。

   コアデータ使用ラベルについて詳しくは、 [このページ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=ja).

   ![](assets/olac_4.png)

1. クリック **[!UICONTROL 保存]** をクリックして、このラベルの制限を適用します。

このオブジェクトにアクセスするには、ユーザーが **[!UICONTROL ラベル]** に含まれる **[!UICONTROL 役割]**.
例えば、C1 ラベルを持つユーザは、C1 ラベル付きオブジェクトまたはラベル付けされていないオブジェクトにのみアクセスできます。

の割り当て方法の詳細については、 **[!UICONTROL ラベル]** から **[!UICONTROL 役割]**（を参照） [このページ](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/permissions.html?lang=en#manage-labels-for-a-role).



