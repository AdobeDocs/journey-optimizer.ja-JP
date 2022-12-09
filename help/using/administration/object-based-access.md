---
solution: Journey Optimizer
product: journey optimizer
title: オブジェクトレベルのアクセス制御
description: オブジェクトレベルのアクセス制御について
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
exl-id: 02ccdd95-426c-4b61-9834-7f2dcd5abdbb
source-git-commit: 8d56e3060e78422b028ced17f415497789908ff9
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 0%

---

# オブジェクトレベルのアクセス制御 {#object-level-access}

>[!CONTEXTUALHELP]
>id="ajo_olac_manage_access"
>title="オブジェクトレベルのアクセス制御"
>abstract="にアクセスできない場合は、このオブジェクトへのアクセスが取り消されます。"

>[!IMPORTANT]
>
>オブジェクトレベルのアクセス制御の使用は、現在選択されている顧客に制限されているため、将来のリリースではすべての環境にデプロイされます。

オブジェクトレベルのアクセス制御 (OLAC) を使用すると、選択したオブジェクトに対するデータアクセスを管理するための認証を定義できます。

* 旅
* キャンペーン
* ランディングページ
* 一元化
* オファーコレクション
* Offer decisioning

この機能は、許可されていないユーザーから機密情報を保護し、さらに個人データを保護することを目的としています。

Adobe 旅のオプティマイザーでは、データを保護し、特定のオブジェクトに対して特定のアクセスを許可することができます。

## ラベルの作成 {#create-assign-labels}

>[!IMPORTANT]
>
>ラベルを作成できるようにするには、アクセス許可を持つ役割に属して **[!UICONTROL Manage usage labels]** いる必要があります。

**[!UICONTROL Labels]** データに適用される使用ポリシーに従って、データセットとフィールドを分類できます。 **[!UICONTROL Labels]** いつでも適用することができ、データの管理方法を柔軟に選択できます。

製品に [!DNL Permissions] ラベルを作成することができます。 詳しくは、このページ ](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/labels.html) を [ 参照してください。

**[!UICONTROL Labels]** さらに、次のように、旅オプティマイザーで直接作成することもできます。

1. Adobe の旅の Optimizer オブジェクトから、新しく作成され **[!UICONTROL Campaign]** たのボタンをクリック **[!UICONTROL Manage access]** します。

   ![](assets/olac_1.png)

1. **[!UICONTROL Manage access]**&#x200B;ウィンドウでをクリック **[!UICONTROL Create label]** します。

   ![](assets/olac_2.png)

1. ラベルを設定するには、次の内容を指定する必要があります。
   * **[!UICONTROL Name]**
   * **[!UICONTROL Friendly name]**
   * **[!UICONTROL Description]**

   ![](assets/olac_3.png)

1. をクリック **[!UICONTROL Create]** して、 **[!UICONTROL Label]** を保存します。

新しく作成した **[!UICONTROL Label]** がリストに表示されるようになりました。 必要に応じて、製品に [!DNL Permissions] 変更を行うことができます。

## ラベルの割り当て {#assign-labels}

>[!IMPORTANT]
>
>ラベルを割り当てるには、「管理」のアクセス許可を持つ役割に属している必要があります。 [!DNL Manage journeys] [!DNL Manage Campaigns] つまり、または [!DNL Manage decisions] . この権限がない場合、 **[!UICONTROL Manage access]** ボタンはグレー表示されます。

カスタムまたはコアデータ使用状況のラベルを、次のような旅のオプティマイザーオブジェクトに割り当てることが可能です。

1. Adobe の旅の Optimizer オブジェクトから、新しく作成され **[!UICONTROL Campaign]** たのボタンをクリック **[!UICONTROL Manage access]** します。

   ![](assets/olac_1.png)

1. **[!UICONTROL Manage access]**&#x200B;ウィンドウで、このオブジェクトへのアクセスを管理するために、カスタムまたは中核データ使用状況ラベルを選択します。

   コアデータ使用状況のラベルについて詳しくは、このページ ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html) を [ 参照してください。

   ![](assets/olac_4.png)

1. クリック **[!UICONTROL Save]** すると、このラベル制限が適用されます。

このオブジェクトにアクセスするには、ユーザーに対し **[!UICONTROL Roles]** て、このオブジェクトに固有 **[!UICONTROL Label]** のファイルが含まれている必要があります。例えば、C1 ラベルを使用しているユーザーには、ラベルの付いたオブジェクトまたはラベルが付いていないオブジェクトにのみアクセスできます。

A に割り当てる **[!UICONTROL Label]** 方法について詳しくは、このページ ](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/permissions.html?lang=en#manage-labels-for-a-role) を [ 参照して **[!UICONTROL Role]** ください。
