---
title: 'プライマリメールアドレスの変更 '
description: 使用するメールアドレスをプロファイルサービスから決定する方法を説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 4e52be8fb4a6b996d20cc831247b7e4f6d333840
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 100%

---

# プライマリメールアドレスの変更 {#change-primary-email}

プロファイルをターゲットにする場合、使用できるメールアドレスがデータベース内に複数ある（個人用、仕事用のメールアドレスなど）場合があります。

Journey Optimizer では、プロファイルサービスから使用するメールアドレスを決定し、複数のアドレスが使用可能な場合に優先順位を付けることができます。 それをおこなうには、次の手順に従います。

1. **[!UICONTROL チャネル]** `>` **[!UICONTROL 一般]**&#x200B;メニューにアクセスします。
1. プロファイルのメールアドレスを判断するために、現在デフォルトで使用されているフィールドがこの画面に表示されます。 「**[!UICONTROL 編集]**」をクリックして変更します。

   ![](../assets/primary-address.png)

1. 「変更」ボタンをクリックし、プライマリメールアドレスとして使用する新しいフィールドを選択します。

   ![](../assets/primary-address-edit.png)

1. 使用可能なメールタイプの XDM フィールドのリストが表示されます。 使用するフィールドを選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![](../assets/primary-address-field.png)

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. >> will be done later on-->
