---
solution: Journey Optimizer
product: journey optimizer
title: サンドボックスの管理
description: サンドボックスの管理方法について
feature: Sandboxes
topic: Administration
role: Admin
level: Intermediate
exl-id: 14f80d5d-0840-4b79-9922-6d557a7e1247
source-git-commit: d17e64e03d093a8a459caef2fb0197a5710dfb7d
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# サンドボックスの管理 {#sandboxes}

## サンドボックスの使用 {#using-sandbox}

[!DNL Journey Optimizer] では、サンドボックスと呼ばれる個別の仮想環境にインスタンスを分割することができます。サンドボックスは、管理コンソールの製品プロファイルに割り当てられます。 [サンド ](permissions.md#create-product-profile) ボックスの割り当て方法について説明します。

[!DNL Journey Optimizer] では、所定の組織に対して作成された Adobe エクスペリエンスプラットフォームサンドボックスが反映されています。Adobe エクスペリエンスプラットフォームのサンドボックスは、Adobe エクスペリエンスプラットフォームインスタンスから作成またはリセットすることができます。 [サンドボックスユーザーガイド ](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html) について詳しくは、target = &quot;_blank&quot;} を参照してください。

サンドボックス切り替えコントロールは、画面の右上にある、組織名の隣に表示されます。 サンドボックス間で切り替えを行うには、スイッチャーで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。

![](assets/sandbox_5.png)

➡️ [ このビデオのサンドボックスについて詳しくは、ここを参照してください。](#video)

## サンドボックスの割り当て {#assign-sandboxes}

>[!IMPORTANT]
>
> サンドボックスの管理は、 **[!UICONTROL Product]** または **[!UICONTROL System]** 管理者のみが実行できます。 詳細については、Admin console の [ マニュアル ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/admin-roles.ug.html) を参照してください。 {target = &quot;_blank 「}」を参照してください。

様々なサンドボックスをそのまま使用するか、またはカスタム **[!UICONTROL Product profiles]** に割り当てるかを選択できます。

サンドボックスを割り当てるには:

1. [!DNL Admin Console]で、タブから **[!UICONTROL Products]** 製品を選択 **[!UICONTROL Adobe Experience Platform Apps]** します。

1. **[!UICONTROL Product profile]**「」を選択します。

   ![](assets/sandbox_1.png)

1. **[!UICONTROL Permissions]**&#x200B;タブを選択します。

1. **[!UICONTROL Sandboxes]**&#x200B;機能を選択します。

   ![](assets/sandbox_2.png)

1. **[!UICONTROL Available Permissions Items]**&#x200B;で、「+」アイコンをクリックして、プロファイルにサンドボックスを割り当てます。[サンド ](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) ボックスについて詳しくは、{target = &quot;_blank 「}」を参照してください。

   ![](assets/sandbox_3.png)

1. 必要に応じて **[!UICONTROL Product profile]** 、で「サンドボックス **[!UICONTROL Included Permission Items]** のアクセス権を削除」の横にある X アイコンをクリックします。

   ![](assets/sandbox_4.png)

1. をクリック **[!UICONTROL Save]** します。

## コンテンツへのアクセス {#content-access}

コンテンツのアクセシビリティを設定するには、コンテンツの共有フォルダーを各サンドボックスに割り当てます。 「管理者向け」タブ [!DNL Admin Console] で **[!UICONTROL Storage]** は、共有フォルダーを作成して設定することができます。がシステム管理者としてアクセス [!DNL Admin Console] できるようになっている場合は、共有フォルダーを作成したり、共有フォルダーに別のアクセスレベルの代理人を追加することができます。

![](assets/do-not-localize/content_access.png)

適切なサンドボックスを使用してコンテンツを同期するには、サンドボックスの構文に従う必要があります。サンドボックスが開発と呼ばれる場合は、共有フォルダーの名前が同じである必要があります。

[共有フォルダー ](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-adobe-storage.ug.html) の管理方法については、{target = &quot;_blank&quot;} を参照してください。

## 操作方法のビデオ{#video}

サンドボックスの概要と、開発とプロダクションのサンドボックスの違いについて説明しています。 サンドボックスを作成、リセット、および削除する方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334355?quality=12)
