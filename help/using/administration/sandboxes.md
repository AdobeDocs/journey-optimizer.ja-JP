---
solution: Journey Optimizer
product: journey optimizer
title: サンドボックスの使用と割り当て
description: サンドボックスの管理方法の詳細情報
feature: Sandboxes
topic: Administration
role: Admin, Architect, Developer
level: Experienced
keywords: サンドボックス, 仮想, 環境, 組織, プラットフォーム
exl-id: 14f80d5d-0840-4b79-9922-6d557a7e1247
source-git-commit: 8093af8c3e7484f9ebed8dbc50065bcff0459581
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 52%

---

# サンドボックスの使用と割り当て {#sandboxes}

## サンドボックスの使用 {#using-sandbox}

[!DNL Journey Optimizer] を使用すると、インスタンスをサンドボックスと呼ばれる個別の仮想環境に分割できます。 サンドボックスは、権限の役割を通じて割り当てられます。[サンドボックスの割り当ての詳細情報](permissions.md#create-product-profile)

[!DNL Journey Optimizer] は、特定の組織用に作成されたAdobe Experience Platform サンドボックスを反映します。 Adobe Experience Platform サンドボックスは、Adobe Experience Platform インスタンスから作成またはリセットできます。[詳しくは、サンドボックスユーザーガイドを参照してください](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ja){target="_blank"}。

画面の右上、組織名の横に、サンドボックス切り替えコントロールがあります。 サンドボックスを切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。

![](assets/sandbox_5.png)

➡️ [ サンドボックスの詳細については、このビデオを参照してください ](#video)

## サンドボックスの割り当て {#assign-sandboxes}

>[!IMPORTANT]
>
> サンドボックスの管理は、**[!UICONTROL 製品]** または **[!UICONTROL システム]** 管理者のみが実行できます。

標準またはカスタムの&#x200B;**[!UICONTROL 役割]**&#x200B;に、異なるサンドボックスを割り当てることもできます。

サンドボックスを割り当てるには、以下の手順に従います。

1. [!DNL Permissions] で、「**[!UICONTROL 役割]**」タブから「**[!UICONTROL 役割]**」を選択します。

   ![](assets/sandbox_1.png)

1. 「**[!UICONTROL 編集]**」をクリックします。

1. **[!UICONTROL サンドボックス]**&#x200B;リソースのドロップダウンで、役割に割り当てるサンドボックスを選択します。

   ![](assets/sandbox_3.png)

1. 必要に応じて、横にある「X」アイコンをクリックして、**[!UICONTROL 役割]**&#x200B;へのサンドボックスのアクセス権を削除します。

   ![](assets/sandbox_4.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## コンテンツへのアクセス {#content-access}

コンテンツのアクセシビリティを設定するには、コンテンツの共有フォルダーを各サンドボックスに割り当てます。 管理者向けの [!DNL Admin Console] に表示される「**[!UICONTROL ストレージ]**」タブで、共有フォルダーを作成し、設定できます。 システム管理者として [!DNL Admin Console] にアクセスできる場合は、共有フォルダーを作成し、異なるアクセスレベルの委任を共有フォルダーに追加できます。

![](assets/do-not-localize/content_access.png)

コンテンツを正しいサンドボックスと同期させるには、サンドボックスと同じ構文に従う必要があります。 例えば、サンドボックスの名前が「開発」の場合、共有フォルダーも同じ名前にする必要があります。

[共有フォルダーの管理方法を学ぶ](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html){target="_blank"}。

## チュートリアルビデオ{#video}

サンドボックスの概要と、開発用サンドボックスと実稼動用サンドボックスを区別する方法について説明します。サンドボックスの作成、リセット、削除方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334355?quality=12)