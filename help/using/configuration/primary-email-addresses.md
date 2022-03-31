---
title: 'プライマリメールアドレスの変更 '
description: 使用するメールアドレスをプロファイルサービスから決定する方法を説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 5071de634c9dbb13908d3190fe1157831c372c7d
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 42%

---

# プライマリメールアドレスの変更 {#change-primary-email}

プロファイルをターゲットにする場合、使用できるメールアドレスがデータベース内に複数ある（個人用、仕事用のメールアドレスなど）場合があります。

を使用 [!DNL Journey Optimizer]を使用すると、プロファイルサービスから、使用する電子メールアドレスを決定し、複数のアドレスが使用可能な場合に優先付けをおこなうことができます。 それには、次の手順に従います。

1. 次にアクセス：  **[!UICONTROL チャネル]** > **[!UICONTROL 一般]** > **[!UICONTROL 実行フィールド]** メニュー

   ![](assets/primary-address-execution-fields.png)

1. プロファイルの E メールアドレスを決定するためにデフォルトで使用されているフィールドがこの画面に表示されます。 「**[!UICONTROL 編集]**」をクリックして変更します。

   ![](assets/primary-address.png)

1. 現在のフィールドまたは編集アイコンをクリックして、新しいフィールドを選択します。

   ![](assets/primary-address-edit.png)

1. 使用可能なメールタイプの XDM フィールドのリストが表示されます。 使用するフィールドを選択します。

   ![](assets/primary-address-field.png)

1. クリック **[!UICONTROL 保存]** をクリックして選択を確定します。

   ![](assets/primary-address-save.png)

   実行フィールドが更新され、プライマリアドレスとして使用されるようになります。

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
