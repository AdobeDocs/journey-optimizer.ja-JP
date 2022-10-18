---
solution: Journey Optimizer
product: journey optimizer
title: プライマリメールアドレスの変更
description: 使用するメールアドレスをプロファイルサービスから決定する方法を説明します。
feature: Application Settings
topic: Administration
role: Admin
level: Intermediate
exl-id: fe2f6516-7790-4501-a3a1-3d7cb94d7874
source-git-commit: 021cf48ab4b5ea8975135a20d5cef8846faa5991
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# プライマリアドレスの変更 {#change-primary-email}

>[!CONTEXTUALHELP]
>id="ajo_admin_execution_address"
>title="使用するアドレスの定義"
>abstract="複数のアドレスがデータベースで使用可能な場合（個人用、仕事用など）、優先して送信するアドレスを選択できます。"

プロファイルをターゲットにする場合、データベースで複数のメールアドレスや電話番号（プロのメールアドレス、個人の電話番号など）を使用できる場合があります。

[!DNL Journey Optimizer] では、プロファイルサービスから使用するメールアドレスや電話番号を決定し、複数のアドレスが使用可能な場合に優先順位を付けることができます。それには、次の手順に従います。

1. **[!UICONTROL チャネル]**／**[!UICONTROL 一般]**／**[!UICONTROL 実行フィールド]**&#x200B;メニューにアクセスします。

   ![](assets/primary-address-execution-fields.png)

1. プロファイルのメールアドレスと電話番号を決定するためにデフォルトで使用されているフィールドが、この画面に表示されます。 「**[!UICONTROL 編集]**」をクリックして変更します。

   ![](assets/primary-address.png)

1. 選択した現在のフィールドまたは編集アイコンをクリックして、新しいフィールドを選択します。

   ![](assets/primary-address-edit.png)

1. 使用可能なメールタイプの XDM フィールドのリストが表示されます。使用するフィールドを選択します。

   ![](assets/primary-address-select-field.png)

1. 「**[!UICONTROL 保存]**」をクリックして選択内容を確定します。

実行フィールドが更新され、プライマリアドレスとして使用されるようになります。

<!--1. You can also select an additional field to use as secondary email address. This allows you to determine which field to use if the primary field is empty for a profile. -->
