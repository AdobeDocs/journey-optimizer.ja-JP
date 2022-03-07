---
title: 保存済み式の使用
description: 保存した式を [!DNL Journey Optimizer] ライブラリ。
feature: Personalization
topic: Personalization
role: Data Engineer
level: Intermediate
exl-id: 74b1be18-4829-4c67-ae45-cf13278cda65
source-git-commit: 60081eedd02d3f9e5654f8a91f6d486b75953daf
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# 保存済み式の使用 {#expression-library}

>[!CONTEXTUALHELP]
>id="ajo_perso_library"
>title="式ライブラリについて"
>abstract="[!DNL Journey Optimizer] は、管理者ユーザーが設定した、保存済みのパーソナライゼーション式にアクセスできるライブラリを提供します。 "

[!DNL Journey Optimizer] は、管理者ユーザーが追加した、以前に保存したパーソナライゼーション式にアクセスできるライブラリを提供します。

1. 保存された式にアクセスするには、 **[!UICONTROL ライブラリ]** ボタンをクリックします。 リストには、管理者ユーザーが保存したすべての式が表示されます ( [ライブラリへの式の保存](#save-expressions)) をクリックします。

   >[!NOTE]
   >
   >情報ボタンを使用して、保存した式の内容に関する詳細情報を取得できます。 ライブラリ項目を管理する権限を持っている場合は、情報ボタンが楕円メニューに表示されます。

   ![](assets/library-list.png)

1. 「 + 」をクリックして、式をエディターに挿入します。 その後、通常どおりにパーソナライゼーションコンテンツをカスタマイズして検証できます。 [詳細情報](../personalization/personalization-build-expressions.md)

   ![](assets/library-add.png)

## ライブラリへの式の保存 {#save-expressions}

[!DNL Journey Optimizer] 管理者ユーザーは、パーソナライゼーション式をライブラリに保存できます。 これらの式は、パーソナライゼーションコンテンツを構築するために、すべてのユーザーが使用できます。

ライブラリに式を保存するには、次の手順に従います。

1. エディターインターフェイスで、式を作成し、「 **[!UICONTROL ライブラリに追加]**.

   >[!NOTE]
   >
   >ボタンが表示されない場合は、必要な権限があることをAdmin Consoleで確認します ( [権限レベル](../administration/high-low-permissions.md)) をクリックします。

   ![](assets/library-save.png)

1. 右側のウィンドウで、式のタイトルと説明を入力し、式を見つけやすくします。その後、「 **[!UICONTROL 追加]**.

   ![](assets/add-expression.png)

1. 式がライブラリに追加されます。 これで、ユーザーはこの機能を使用してパーソナライゼーションコンテンツを構築できるようになります。


>[!NOTE]
>
>* ライブラリには、最大 40 個の式を保存できます。
>
>* 式は 200 KB を超えることはできません。
>
>* 保存済みの式は作成日別に並べ替えられます。最近追加された式がリストの最初に表示されます。



既存の式を編集するには、式をエディターに追加し、必要に応じて変更します。 クリック **[!UICONTROL ライブラリに追加]** 構文を検証し、式を保存する場合。

式を削除するには、楕円形ボタンをクリックし、 **[!UICONTROL 削除]**.
