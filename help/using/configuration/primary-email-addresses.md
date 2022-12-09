---
solution: Journey Optimizer
product: journey optimizer
title: 一次電子メールアドレスの変更
description: プロファイルサービスのどの電子メールアドレスを使用するかを決定する方法について説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 0f69a47dccad20f3e978613b349a29f9daab94bd
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# 第1の住所を変更します。 {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="使用するアドレスの指定"
>abstract="データベースに複数の電子メールアドレスまたは電話番号が含まれている場合は、送信の優先順位を指定することができます。"

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address_header"
>title="使用するアドレスの指定"
>abstract="プロファイルの電子メールアドレスと電話番号を決定するために使用するフィールドを編集して、送信の優先度を指定します。"

プロファイルのターゲットを指定すると、いくつかの電子メールアドレスまたは電話番号がデータベースに含まれている可能性があります (プロフェッショナルな電子メールアドレス、個人電話番号など)。

で [!DNL Journey Optimizer] は、プロファイルサービスによって使用される電子メールアドレスと電話番号を決定し、複数のアドレスがある場合に優先順位を付けられるようにすることができます。 これを行うには、次の手順を実行します。

1. > **[!UICONTROL General]** > **[!UICONTROL Executions fields]** メニューに **[!UICONTROL Channels]** アクセスします。

   ![](assets/primary-address-execution-fields.png)

1. この画面に表示されるプロファイルの電子メールアドレスと電話番号は、初期設定で現在使用されているフィールドによって決まります。 クリック **[!UICONTROL Edit]** して変更します。

   ![](assets/primary-address.png)

1. 選択範囲の現在のフィールドまたは編集アイコンをクリックして、新しいフィールドを選択します。

   ![](assets/primary-address-edit.png)

1. 使用可能な email タイプリストが表示されます。 使用するフィールドを選択します。

   ![](assets/primary-address-select-field.png)

1. 選択内容を確認するには、をクリック **[!UICONTROL Save]** します。

実行フィールドが更新され、主住所として使用されるようになりました。

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
