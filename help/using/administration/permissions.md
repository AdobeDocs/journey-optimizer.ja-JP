---
solution: Journey Optimizer
product: journey optimizer
title: ユーザーとグループの管理
description: ユーザーと役割を管理する方法を説明します
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
keywords: 製品, プロファイル, サンドボックス
source-git-commit: 417eea2a52d4fb38ae96cf74f90658f87694be5a
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 26%

---

# ユーザーとグループの管理 {#manage-permissions}

>[!IMPORTANT]
>
> 次に説明する各手順は、**[!UICONTROL 製品]**&#x200B;または&#x200B;**[!UICONTROL システム]**&#x200B;の管理者のみが実行できます。詳しくは、[Admin Console ドキュメント](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html)を参照してください。

**[!UICONTROL 役割]** 同じ権限とサンドボックスを共有するユーザーのコレクションを参照します。 これらの役割を使用すると、組織内の様々なユーザーグループのアクセスおよび権限を簡単に管理できます。

を使用 [!DNL Journey Optimizer] 製品を使用すると、既存の様々な製品から選択できます **[!UICONTROL 役割]**（それぞれ様々なレベルの権限を持ち、ユーザーに割り当てる） 利用可能な **[!UICONTROL 役割]**（これを参照） [ページ](ootb-product-profiles.md).

ユーザーが **[!UICONTROL 役割]**&#x200B;の場合、製品に含まれるAdobeアプリやサービスへのアクセス権が付与されます。

既存の役割が組織の特定のニーズを満たさない場合は、カスタムの役割を作成することもできます **[!UICONTROL 役割]** を使用して、インターフェイス内の特定の機能やオブジェクトへのアクセスを微調整できます。 これにより、各ユーザーが、タスクを効率的に実行するために必要なリソースおよびツールにのみアクセスできるようにすることができます。

## ロールを割り当て {#assigning-role}

標準またはカスタムの割り当てを選択できます **[!UICONTROL 役割]** をユーザーに送信します。

権限が割り当てられているすべての標準の役割のリストは、 [組み込みの役割](ootb-product-profiles.md) 」セクションに入力します。

を割り当てるには **[!UICONTROL 役割]**:

1. でユーザーにロールを割り当てるには [!DNL Permissions] 製品の場合は、 **[!UICONTROL 役割]** 」タブをクリックし、目的の役割を選択します。

   ![](assets/do-not-localize/access_control_2.png)

1. 「**[!UICONTROL ユーザー]**」タブで「**[!UICONTROL ユーザーを追加]**」をクリックします。

   ![](assets/do-not-localize/access_control_3.png)

1. ユーザー名または電子メールアドレスを入力するか、リストからユーザーを選択して、 **[!UICONTROL 保存]**.

   [!DNL Admin Console] でまだユーザーを作成していない場合は、[ユーザーの追加についてのドキュメント](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users)を参照してください。

   ![](assets/do-not-localize/access_control_4.png)

これにより、ユーザーをインスタンスへリダイレクトするメールが、ユーザーに送られます。

ユーザー管理の詳細については、[Admin Console ドキュメント](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html)を参照してください。

インスタンスにアクセスすると、割り当てられた権限に応じて、特定のビューがユーザーに表示されます ( **[!UICONTROL 役割]**. ユーザーが機能にアクセスする権限を持っていない場合は、次のメッセージが表示されます。

`You don't have permission to access this feature. Permission needed: XX.`

## 既存の役割の編集 {#edit-product-profile}

標準またはカスタムの場合 **[!UICONTROL 役割]**&#x200B;を使用すると、いつでも権限を追加または削除できます。

この例では、 **[!UICONTROL 権限]** 関連する **[!UICONTROL ジャーニー]** リソースビューアに割り当てられたジャーニーのリソース **[!UICONTROL 役割]**. その後、ユーザーはジャーニーを公開できます。

標準またはカスタムを変更した場合は、 **[!UICONTROL 役割]**&#x200B;の場合は、割り当てられたすべてのユーザーに影響します **[!UICONTROL 役割]**.

1. でユーザーにロールを割り当てるには [!DNL Permissions] 製品の場合は、 **[!UICONTROL 役割]** 「 」タブをクリックし、目的の役割を選択します。ここでは、ジャーニー・ビューア **[!UICONTROL 役割]**.
   ![](assets/do-not-localize/access_control_5.png)

1. お使いの **[!UICONTROL 役割]** ダッシュボードで、 **[!UICONTROL 編集]**.

   ![](assets/do-not-localize/access_control_6.png)

1. この **[!UICONTROL リソース]** メニューには、 **[!UICONTROL Experience Cloud- Platform を利用したアプリケーション]** 製品。 リソースをドラッグ&amp;ドロップして権限を割り当てます。

   次の **[!UICONTROL ジャーニー]** リソースドロップダウンで、「パブリッシュジャーニー」を選択します。 **[!UICONTROL 権限]**.

   ![](assets/do-not-localize/access_control_14.png)

1. 必要に応じて、 **[!UICONTROL 含まれる権限項目]**&#x200B;の横にある X アイコンをクリックして、役割に対する権限やリソースを削除します。

1. 終了したら、「**[!UICONTROL 保存]**」をクリックします。

必要に応じて、特定の権限を持つ新しい役割を作成することもできます。 詳しくは、 [新しいロールを作成](#create-product-profile).

## 新しい役割の作成 {#create-product-profile}

[!DNL Journey Optimizer] 独自の **[!UICONTROL 役割]** ユーザーに一連の権限とサンドボックスを割り当てます。 を使用 **[!UICONTROL 役割]**&#x200B;を使用すると、インターフェイス内の特定の機能やオブジェクトへのアクセスを許可または拒否できます。

サンドボックスの作成および管理方法について詳しくは、[Adobe Experience Platform ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ja){target="_blank"}を参照してください。

この例では、という名前の役割を作成します。 **ジャーニー読み取り専用** ジャーニー機能に読み取り専用権限を付与する ユーザーはジャーニーにアクセスして表示できますが、[!DNL Journey Optimizer] の **[!DNL  Decision management]** など、他の機能にはアクセスできません。

次の手順で **ジャーニー読み取り専用** **[!UICONTROL 役割]**:

1. でユーザーにロールを割り当てるには [!DNL Permissions] 製品の場合は、 **[!UICONTROL 役割]** タブをクリックし、 **[!UICONTROL ロールを作成]**.

   ![](assets/do-not-localize/access_control_9.png)

1. を追加します。 **[!UICONTROL 名前]** および **[!UICONTROL 説明]** 新しい **[!UICONTROL 役割]**. 次に、「 **[!UICONTROL 確認]**.

   ![](assets/do-not-localize/access_control_10.png)

1. 次の **[!UICONTROL サンドボックス]** リソースドロップダウン：割り当てるサンドボックスを選択します。 **[!UICONTROL 役割]**. [サンドボックスの詳細情報](sandboxes.md)。

   ![](assets/do-not-localize/access_control_13.png)

1. 次のような様々なリソースを選択します。 **[!DNL Journeys]**, **[!DNL Segments]** または **[!DNL Decision management]** 次の場所で使用可能： [!DNL Journey Optimizer] リストが左側のメニューに表示されます。

   ここで、 **[!UICONTROL ジャーニー]** リソース。

   ![](assets/do-not-localize/access_control_11.png)

1. 次の **[!UICONTROL ジャーニー]** ドロップダウンで、 **[!UICONTROL 役割]**.

   ここでは、 **[!DNL View journeys]**, **[!DNL View journeys report]**  および **[!DNL View journeys event, data sources, actions]**.

   ![](assets/do-not-localize/access_control_12.png)

1. 終了したら、「**[!UICONTROL 保存]**」をクリックします。

お使いの **[!UICONTROL 役割]** が作成され、設定されました。 次に、ユーザーに割り当てる必要があります。

ロールの作成と管理について詳しくは、 [Admin Console文書](https://experienceleague.adobe.com/docs/experience-platform/access-control/abac/permissions-ui/roles.html?lang=ja).