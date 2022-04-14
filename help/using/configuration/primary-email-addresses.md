---
title: 'プライマリメールアドレスの変更 '
description: 使用するメールアドレスをプロファイルサービスから決定する方法を説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: f1ac47a0cb405eaadc5428e7e5479eaf776d7abe
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 84%

---

# プライマリメールアドレスの変更 {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="使用するアドレスを定義"
>abstract="複数のアドレスがデータベースで使用可能な場合（個人、職場など）に、送信を優先する電子メールアドレスを選択できます。"

プロファイルをターゲットにする場合、使用できるメールアドレスがデータベース内に複数ある（個人用、仕事用のメールアドレスなど）場合があります。

[!DNL Journey Optimizer] では、プロファイルサービスから使用するメールアドレスを決定し、複数のアドレスが使用可能な場合に優先順位を付けることができます。それには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL 一般]**／**[!UICONTROL 実行フィールド]**&#x200B;メニューにアクセスします。

   ![](assets/primary-address-execution-fields.png)

1. プロファイルのメールアドレスを判断するために現在デフォルトで使用されているフィールドが、この画面に表示されます。「**[!UICONTROL 編集]**」をクリックして変更します。

   ![](assets/primary-address.png)

1. 現在のフィールドをクリックするか、編集アイコンをクリックして新しいフィールドを選択します。

   ![](assets/primary-address-edit.png)

1. 使用可能なメールタイプの XDM フィールドのリストが表示されます。 使用するフィールドを選択します。

   ![](assets/primary-address-field.png)

1. 「**[!UICONTROL 保存]**」をクリックして選択内容を確定します。

   ![](assets/primary-address-save.png)

   実行フィールドが更新され、プライマリアドレスとして使用されるようになります。

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
