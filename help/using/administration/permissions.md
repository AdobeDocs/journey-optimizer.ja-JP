---
solution: Journey Optimizer
product: journey optimizer
title: ユーザーおよび製品プロファイルの管理
description: 権限を管理する方法について説明します。
exl-id: 85fd386a-45fa-4f9a-89d1-cecc0749b90d
feature: Access Management
topic: Administration
role: Admin
level: Intermediate
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# ユーザーおよび製品プロファイルの管理 {#manage-permissions}

>[!IMPORTANT]
>
> 以下に示す手順は、 **[!UICONTROL Product]** または **[!UICONTROL System]** 管理者のみが実行できます。 詳しくは、管理コンソールの [ マニュアル ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html) を参照してください。

**[!UICONTROL Product profiles]** は、組織内で同じ権限とサンドボックスを共有するユーザーのセットです。

[!DNL Journey Optimizer]この製品を使用すると、ユーザーに割り当てられるアクセス許可レベルの異なる、ボックス **[!UICONTROL Product profiles]** の中から選択することができます。使用可能な **[!UICONTROL Product profiles]** について詳しくは、この [ ページ ](ootb-product-profiles.md) を参照してください。

に **[!UICONTROL Product profiles]** 属している各ユーザーには、製品に含まれる Adobe アプリとサービスが与えられています。

また、インターフェイスの特定の機能またはオブジェクトに対するユーザーのアクセスを微調整する場合は、独自 **[!UICONTROL Product profiles]** のファイルを作成することもできます。

## 製品プロファイルの割り当て {#assigning-product-profile}

ユーザーには、そのまま使用することも、カスタム **[!UICONTROL Product profile]** に割り当てることもできます。

アクセス許可が割り当てられているすべての製品プロファイルの一覧は、「製品プロファイル ](ootb-product-profiles.md) 」セクションに [ あります。

を割り当てるには、次の **[!UICONTROL Product profile]** ようにします。

1. [!DNL Admin Console]で、タブから **[!UICONTROL Products]** 製品を選択 **[!UICONTROL Experience Cloud - Platform powered applications]** します。

1. **[!UICONTROL Product profile]**「」を選択します。

   ![](assets/do-not-localize/access_control_2.png)

1. **[!UICONTROL Users]**&#x200B;タブでをクリック **[!UICONTROL Add user]** します。

   ![](assets/do-not-localize/access_control_3.png)

1. ユーザーの名前または電子メールアドレスを入力して、ユーザーを選択します。

   ユーザーがで [!DNL Admin Console] 以前に作成されていない場合は、ユーザーマニュアル ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html#add-users) の追加を [ 参照してください。

   ![](assets/do-not-localize/access_control_4.png)

1. 他のユーザー **[!UICONTROL Product profile]** をに追加するには、上記の手順を実行します。 次に、をクリック **[!UICONTROL Save]** します。

これにより、ユーザーは、インスタンスにリダイレクトする電子メールを受信することになります。

ユーザーの管理について詳しくは、Admin Console の [ マニュアル ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-users-individually.ug.html) を参照してください。

インスタンスにアクセスすると、に **[!UICONTROL Product profile]** 割り当てられた権限によって、ユーザーに特定のビューが表示されます。 ユーザーが機能に対して適切なアクセス権を持っていない場合は、次のメッセージが表示されます。

`You don't have permission to access this feature. Permission needed: XX.`

## 既存の製品プロファイルの編集 {#edit-product-profile}

ユーザー **[!UICONTROL Product profiles]** にとっては、アクセス許可をいつでも追加または削除することができます。

この例では、旅ビューア **[!UICONTROL Product profile]** に割り当てられているユーザーの機能に関連する機能を **[!UICONTROL Journeys]** 追加 **[!UICONTROL Permissions]** します。これにより、ユーザーは journeys を公開することができます。

ただし、標準またはカスタム **[!UICONTROL Product profile]** に変更した場合は、それに **[!UICONTROL Product profile]** 割り当てられているすべてのユーザーに影響します。

1. [!DNL Admin Console]で、タブから **[!UICONTROL Products]** 製品を選択 **[!UICONTROL Experience Cloud - Platform powered applications]** します。

1. 「旅ビューア **[!UICONTROL Product profile]** 」を選択します。

1. **[!UICONTROL Permissions]**&#x200B;タブを選択します。

   このタブに **[!UICONTROL Permissions]** は、製品に **[!UICONTROL Experience Cloud - Platform powered applications]** 適用される機能のリストが表示されます。

   ![](assets/do-not-localize/access_control_5.png)

1. **[!UICONTROL Journeys]**&#x200B;機能を選択します。

   ![](assets/do-not-localize/access_control_6.png)

1. **[!UICONTROL Available Permission Items]**&#x200B;リストから、プラス (+) 記号アイコンをクリックして、に割り当て **[!UICONTROL Product profile]** られるアクセス権を選択します。

   ここでは、アクセス許可を追加 **[!UICONTROL Publish Journeys]** します。

1. 必要に応じ **[!UICONTROL Included Permission Items]** て、で「製品プロファイルに対する権限を削除」の横にある X アイコンをクリックします。

1. 終了したら、をクリック **[!UICONTROL Save]** します。

必要に応じて、特定の権限を使用して新しい製品プロファイルを作成することもできます。 詳細については、「製品プロファイル ](#create-product-profile) の作成」を [ 参照してください。

## 製品プロファイルの作成 {#create-product-profile}

[!DNL Journey Optimizer] では、独自 **[!UICONTROL Product profiles]** のセットを作成して、一連の権限とサンドボックスをユーザーに割り当てることができます。 で **[!UICONTROL Product profiles]** は、インターフェイスの特定の機能またはオブジェクトへのアクセスを許可または拒否することができます。

サンドボックスの作成と管理の方法について詳しくは、『 Adobe エクスペリエンス Platform ニュアル ](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html) {target = &quot;_blank&quot;} を [ 参照してください。

この例では、Journeys **という名前** の製品プロファイルを作成します。この場合は、旅機能に読み取り専用の権限を付与します。ユーザーは、journeys にアクセスして表示することはできますが、のよう **[!DNL  Decision management]** [!DNL Journey Optimizer] な他の機能にアクセスすることはできません。

Journeys を作成するには、 **次の** **[!UICONTROL product profiles]** 操作を行います。

1. に [!DNL Admin Console] アクセスします。

1. **[!UICONTROL Products]**&#x200B;タブから製品を選択 **[!UICONTROL Experience Cloud - Platform powered applications]** します。

1. をクリック **[!UICONTROL New Profile]** します。

   ![](assets/do-not-localize/access_control_9.png)

1. 新しい **[!UICONTROL product profiles]** を追加するには **[!UICONTROL Description]** **[!UICONTROL Product Profile Name]** **[!UICONTROL Display Name]** 、を追加します。

   ![](assets/do-not-localize/access_control_10.png)

1. **[!UICONTROL Notifications]**&#x200B;カテゴリで、このプロファイルに対してユーザーが追加または削除されたときに、ユーザーに電子メールで通知するかどうかを選択します。

1. 終了したら、をクリック **[!UICONTROL Save]** し、新しく作成 **[!UICONTROL product profiles]** したを選択します。

1. 様々な機能にアクセスするための権限をユーザーに追加するには、「タブ」を選択 **[!UICONTROL Permissions]** します。

1. 左側のメニューに一覧表示されて **[!DNL Journeys]** いるように、 **[!DNL Segments]** の各機能を選択することも **[!DNL Decision management]** でき [!DNL Journey Optimizer] ます。

   ここでは、 **[!UICONTROL Journeys]** 機能を選択します。

   ![](assets/do-not-localize/access_control_11.png)

1. **[!UICONTROL Available Permission Items]**&#x200B;リストから、プラス (+) 記号アイコンをクリックして、に割り当て **[!UICONTROL Product profile]** られるアクセス権を選択します。

   ここでは、および **[!DNL View journeys event, data sources, actions]** を選択 **[!DNL View journeys]** します。

   ![](assets/do-not-localize/access_control_12.png)

1. **[!UICONTROL Sandbox access]**&#x200B;に **[!UICONTROL Product profile]** 割り当てられるサンドボックスを選択する機能を選択します。

   ![](assets/do-not-localize/access_control_13.png)

1. **[!UICONTROL Available Permissions Items]**&#x200B;で、「+」アイコンをクリックして、プロファイルにサンドボックスを割り当てます。[サンド ](sandboxes.md) ボックスについて説明します。

1. 終了したら、をクリック **[!UICONTROL Save]** します。

は、 **[!UICONTROL Product profile]** 現在作成され、設定されています。 これで、ユーザーに割り当てる必要があります。

製品プロファイルの作成と管理について詳しくは、Admin Console の [ マニュアル ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-product-profiles.ug.html) を参照してください。
