---
solution: Journey Optimizer
product: journey optimizer
title: サンドボックスの使用と割り当て
description: サンドボックスの管理方法の詳細情報
feature: Sandboxes
topic: Administration
role: Admin, Developer
level: Experienced
keywords: サンドボックス, 仮想, 環境, 組織, プラットフォーム
exl-id: 14f80d5d-0840-4b79-9922-6d557a7e1247
TQID: https://experienceleague.adobe.com/8vcaHkqHeyoP-TZltCkjpBhvZIifuiPbKy-Whoj74Z8
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f9b8e1590f14cdcd00432295c653769f753b9b40
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 79%

---

# サンドボックスの使用と割り当て {#sandboxes}

**サンドボックス**&#x200B;は、Adobe Journey Optimizer インスタンスを個別の独立したワークスペース（開発、テスト、実稼動用）に分割する仮想環境です。 サンドボックス管理は、**管理** > **チャネル** > **システムと環境を接続** （またはインターフェイスの右上にあるサンドボックススイッチャーを使用）の下にあります。 サンドボックスを利用すれば、安全にテストを実施し、役割ごとに異なるアクセス権を割り当て、コンテンツを整理しておくことができます。 このページでは、サンドボックスの使用と割り当て、コンテンツアクセスの設定、および[&#x200B; オブジェクトを別のサンドボックスに書き出し](../configuration/copy-objects-to-sandbox.md)の記事で、サンドボックス間でジャーニーとテンプレートをコピーする方法について説明します。

## サンドボックスの使用 {#using-sandbox}

[!DNL Journey Optimizer] では、インスタンスをサンドボックスと呼ばれる個別の仮想環境に分割できます。 サンドボックスは、「権限」の役割を通じて割り当てられます。 [サンドボックスの割り当ての詳細情報](permissions.md#create-product-profile)

[!DNL Journey Optimizer] は、特定の組織用に作成された Adobe Experience Platform サンドボックスを反映します。 Adobe Experience Platform サンドボックスは、Adobe Experience Platform インスタンスから作成またはリセットできます。 [詳しくは、サンドボックスユーザーガイドを参照してください](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/user-guide.html?lang=ja){target="_blank"}。

画面の右上の組織名の横に、サンドボックス切り替えボタンコントロールがあります。 サンドボックスを切り替えるには、切り替えボタンで現在アクティブなサンドボックスをクリックし、ドロップダウンリストから別のサンドボックスを選択します。

![](assets/sandbox_5.png)

➡️ [このビデオのサンドボックスの詳細情報](#video)

## サンドボックスの割り当て {#assign-sandboxes}

>[!IMPORTANT]
>
> サンドボックスの管理は、**[!UICONTROL 製品]**&#x200B;または&#x200B;**[!UICONTROL システム]**&#x200B;の管理者のみが実行できます。

標準またはカスタムの&#x200B;**[!UICONTROL 役割]**&#x200B;に、異なるサンドボックスを割り当てることもできます。

サンドボックスを割り当てるには、以下の手順に従います。

1. [!DNL Permissions] で、「**[!UICONTROL 役割]**」タブから「**[!UICONTROL 役割]**」を選択します。

   ![](assets/sandbox_1.png)

1. 「**[!UICONTROL 編集]**」をクリックします。

1. **[!UICONTROL サンドボックス]**&#x200B;リソースのドロップダウンで、役割に割り当てるサンドボックスを選択します。

   ![](assets/sandbox_3.png)

1. 必要に応じて、横にある「X」アイコンをクリックして、**[!UICONTROL 役割]**&#x200B;からサンドボックスへのアクセス権を削除します。

   ![](assets/sandbox_4.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## コンテンツへのアクセス {#content-access}

コンテンツのアクセシビリティを設定するには、コンテンツの共有フォルダーを各サンドボックスに割り当てます。 管理者向けの [!DNL Admin Console] に表示される「**[!UICONTROL ストレージ]**」タブで、共有フォルダーを作成し、設定できます。 システム管理者として [!DNL Admin Console] にアクセスできる場合は、共有フォルダーを作成し、異なるアクセスレベルの委任を共有フォルダーに追加できます。

![](assets/do-not-localize/content_access.png)

コンテンツを正しいサンドボックスと同期させるには、サンドボックスと同じ構文に従う必要があります。 例えば、サンドボックスの名前が「開発」の場合、共有フォルダーも同じ名前にする必要があります。

[共有フォルダーの管理方法を学ぶ](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html){target="_blank"}。

## チュートリアルビデオ{#video}

サンドボックスの概要と、開発用サンドボックスと本番稼働用サンドボックスを区別する方法について説明します。 サンドボックスの作成、リセット、削除方法について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/334355?quality=12)