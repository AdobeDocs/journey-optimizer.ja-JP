---
solution: Journey Optimizer
product: journey optimizer
title: ブランドの管理
description: ブランドガイドラインの作成および管理方法について説明します
badge: label="ベータ版" type="Informative"
topic: Content Management
role: User
level: Beginner, Intermediate
source-git-commit: 6c99d733b973efd790f8727bf867fbf0a952f6d9
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 24%

---

# ブランドの作成と管理 {#brands}

>[!AVAILABILITY]
>
>この機能は、プライベートベータ版としてリリースされます。 今後のリリースで、すべてのお客様が段階的に利用できるようになります。

ブランドガイドラインは、ブランドの視覚的および言語的なアイデンティティを確立する詳細な一連のルールおよび基準です。 マーケティングプラットフォームとコミュニケーションプラットフォーム全体で一貫したブランド表現を維持するための参照として機能します。

<!--Upload feature currently behind feature flag--

In [!DNL Journey Optimizer], you now have the option to manually input and organize your brand details or upload brand guideline documents for automatic information extraction.-->

## ブランドへのアクセス {#generative-access}

[!DNL Adobe Journey Optimizer] で **[!UICONTROL ブランド]** メニューにアクセスするには、ユーザーに **[!UICONTROL Managed Brand kit]** または **[!UICONTROL AI アシスタントを有効にする]** 権限を付与する必要があります。 [詳細情報](../administration/permissions.md)

+++  ブランド関連の権限の割り当て方法を学ぶ

1. **権限**&#x200B;付きの製品で、「**役割**」タブに移動し、目的の「**役割**」を選択します。

1. 「**編集**」をクリックして、権限を変更します。

1. **AI アシスタント** リソースを追加し、ドロップダウンメニューから **Managed Brand kit** または **[!UICONTROL AI アシスタントを有効にする]** を選択します。

   **[!UICONTROL Ai アシスタントを有効にする]** 権限では、**[!UICONTROL ブランド]** メニューへの読み取り専用アクセスのみが提供されることに注意してください。

   ![](assets/brands-permission.png){zoomable="yes"}

1. 「**保存**」をクリックして、変更を適用します。

   この役割に既に割り当てられているユーザーの権限は、自動的に更新されます。

1. この役割を新しいユーザーに割り当てるには、**役割**&#x200B;ダッシュボード内の「**ユーザー**」タブに移動し、「**ユーザーを追加**」をクリックします。

1. ユーザーの名前、メールアドレスを入力するか、リストから選択して、「**保存**」をクリックします。

1. まだユーザーを作成していない場合は、[このドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/abac/permissions-ui/users)を参照してください。

+++

## ブランドを作成 {#create-brand-kit}

ブランドガイドラインを作成および管理するには、次の手順に従います。

<!--Upload feature currently behind feature flag--

To create and manage your Brand guideline, you can either enter the details yourself, or upload your brand guidelines document to have the information extracted automatically:-->

1. **[!UICONTROL ブランド]** メニューで、「**[!UICONTROL ブランドを作成]**」をクリックします。

   ![](assets/brands-1.png)

1. ブランドの **[!UICONTROL 名前]** を入力します <!--and a **[!UICONTROL Description]** to your brand guideline-->。

   ![](assets/brands-2-temp.png)

<!--Upload feature currently behind feature flag so hidden from doc - should be available again by EOM (Feb)--

1. Drag and drop or select your file to upload your brand guidelines and extract automatically relevant brand information. Click **[!UICONTROL Create brand]**.

    The information extraction process now begins. Note that it may take several minutes to complete.

    ![](assets/brands-2.png)

1. Your Content and visual creation standards are now automatically populated. Browse through the different tabs to adapt the information as needed.

-->

1. 「**[!UICONTROL ライティングスタイル]**」タブで「![](assets/do-not-localize/Smock_Add_18_N.svg)」をクリックし、例を含むガイドラインや除外を追加します。

   ![](assets/brands-3.png)

1. **[!UICONTROL ビジュアルコンテンツ]** タブで、![](assets/do-not-localize/Smock_Add_18_N.svg) をクリックして、別のガイドラインまたは除外を追加します。

1. 正しい使用方法を示す画像を追加するには、「例 **[!UICONTROL を選択し]** 「**[!UICONTROL 画像を選択]**」をクリックします。 また、除外の例として、誤った使用法を示す画像を追加することもできます。

   ![](assets/brands-4.png)

1. 設定が完了したら、**[!UICONTROL 保存]** をクリックしてから **[!UICONTROL 公開]** をクリックして、ブランドガイドラインを AI アシスタントで使用できるようにします。

1. 公開済みのブランドに変更を加えるには、「**[!UICONTROL ブランドを編集]**」をクリックします。

   >[!NOTE]
   >
   >これにより、編集モードで一時コピーが作成され、公開後にライブバージョンが置き換えられます。

   ![](assets/brands-8.png)

1. **[!UICONTROL ブランド]** ダッシュボードで、![](assets/do-not-localize/Smock_More_18_N.svg) のアイコンをクリックして詳細メニューを開きます。

   * ブランドを表示
   * 編集
   * 複製
   * 公開
   * 非公開
   * 削除

   ![](assets/brands-6.png)

ブランドガイドラインに AI アシスタントメニューの **[!UICONTROL ブランド]** ドロップダウンからアクセスできるようになり、仕様に合ったコンテンツとアセットを生成できるようになりました。 [ 詳しくは、AI アシスタントを参照してください ](gs-generative.md)

![](assets/brands-7.png)
